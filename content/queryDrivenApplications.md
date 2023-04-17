## Query-Driven Applications

At present, numerous Solid applications make assumptions about data locations in pods,
which is incompatible with the idea of Solid that every user should have the power to organise their Pod as they see fit.
Furthermore, not all Solid applications may assume the same locations for data.
This present an interoperability challenge, which we have tackled through the use of *declarative queries* as a data access abstraction layer,
allowing application developers to make use of pods with varying data locations,
while maintaining the ability of users to freely organise their pods.

Solid Pods can be considered [_personal knowledge graphs_](cite:cites hogan2021knowledge),
consisting of a combination of interlinked LDP containers, Linked Data documents and non-RDF data.
The resources in LDP containers can be read with HTTP `GET` requests to their URIs.
This characteristic allows the use of [Link Traversal Query Processing (LTQP)](cite:cites hartig2011zero,taelman2023evaluation)
to execute declarative SPARQL queries over Solid pods,
which in turn helps abstract away the location of data within a pod for read operations.
Furthermore, as resources in LDP containers can be created or modified using HTTP `POST`, `PUT`, and `PATCH` requests,
queries can also be used to abstract modifications to data contained within a Solid pod.

We have taken advantage of this to achieve interoperability between two applications, by making both applications query-driven.
All read and write operations are expressed using declarative SPARQL queries with `INSERT` and `DELETE`.
We chose [Comunica](cite:cites taelman2018comunica), an application-independent query engine library to execute these queries,
as it has been previously used [within Solid](cite:cites taelman2023evaluation),
and is able to translate our queries into operations on the Solid pod, by creating or updating resources.
[](#select-query) illustrates an example SELECT query to obtain tasks within a to-do application, regardless of the exact location within a pod.
However, writing the data is done to a fixed location in a pod, rather than being user-defined.

<figure id="select-query" class="listing">
<pre><code>PREFIX todo: <http://example.org/todolist/>

SELECT ?id ?title ?status ?dateCreated WHERE {
    ?id a todo:Task;
        todo:title ?title;
        todo:status ?status;
        todo:dateCreated ?dateCreated.
}</code></pre>

<figcaption markdown="block">
Example query to select tasks with a title, status and creation date.
</figcaption>
</figure>

Beyond the data location, the ontologies used for the data should also be interoperable.
In practice, this could be realised through the use of the same ontology, or through the mapping of different ontologies into each other.
Within the scope of this demonstration, we have chosen to use the same ontology to make the two applications interoperable,
to help us focus on the challenge of data storage itself.
