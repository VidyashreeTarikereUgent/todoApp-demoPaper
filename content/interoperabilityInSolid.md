## Query-driven application code

Interoperability in Solid is the ability of multiple heterogenous Solid Pods and applications to work together,
by communicating with each other, by exchanging data, and by processing data among themselves.

At present, most Solid applications assume hardcoded locations in Pods for storing data,
which is incompatible with the idea of Solid that every user should have the choice to organise their Pod as they see fit. 
Furthermore, not all Solid applications may make use of the same hardcoded locations.
One way of making Solid applications independent of the precise location at which data is stored inside a Pod,
is by building applications on top of *declarative queries*, such as SPARQL queries.
These SPARQL queries can then be evaluated by query engines that are able to find data in Solid Pods,
for example by making use of [Link Traversal Query Processing techniques dedicated to Solid Pods](cite:cites taelman2023evaluation).
This gives users the freedom to choose where and how they store their data,
without application developers needing to be aware of this heterogeneity across Pods.

<del class="comment" data-author="RV">In RDF, ontologies are used to give semantics to the data. </del>
<span class="comment" data-author="RV">That is known already by the target audience.</span>
<del class="comment" data-author="RV">One way to achieve interoperability for Solid applications is to follow the same ontology, as this will give the same structure to the application data. 
Therefore, both our to-do apps use the same ontology.</del>
<span class="comment" data-author="RV">That's a bit too straightforward: of course two apps using the same ontology will have interoperable data models. We can perhaps make the more general point here: how strong does the prior agreement need to be? Do they need to use exactly the same data model and exactly the same locations? Well, we'll look into that second question by keeping the first constant.</span>
<span class="comment" data-author="RV">In that sense, the title and abstract of the paper might need to be adapted to location-independence.</span>

Both to-do apps are query-driven,
meaning that all read and write operations are expressed using declarative queries on the data level,
such that the application developer can be agnostic about the storage location.
An application-independent query engine then needs to derive the storage location automatically;
we make use of the [Comunica SPARQL query engine](cite:cites taelman2018comunica).
Comunica allows WebID-authenticated fetch operations, and is able to [traverse over Solid Pods](cite:cites taelman2023evaluation).
For example, [](#select-query) shows a SELECT query that returns all to-do triples from a Pod, independent of the precise storage location.

<figure id="select-query" class="listing">
<pre><code>PREFIX todo: <http://example.org/todolist/>

SELECT * WHERE {
    ?id a todo:Task ;
        todo:title ?title ;
        todo:status ?status ;
        todo:dateCreated ?dateCreated .
}</code></pre>

<figcaption markdown="block">
SPARQL SELECT query which selects <span class="rephrase" data-author="RV">all triples matching the predicates</span> in the Pod.
</figcaption>
</figure>

One of the current limitations of our apps, is that we write data to a fixed location in the pod, rather than being user-defined.
Like reading data from Pods, writing data to Pods is also abstracted using SPARQL queries.
More specifically, we make use of SPARQL INSERT and DELETE queries,
which can be resolved by Comunica,
which in its turn takes care of creating new resources if they don't exist yet,
or modifying them if they already exist.

