## Interoperability in Solid

Interoperability in Solid is the ability of multiple heterogenous Solid Pods and applications to work together,
by communicating with each other, by exchanging data, and by processing data among themselves.

{:.comment data-author="RT"}
Can we add some subsections in here for the different topics?
Like querying, ontologies, ...

At present, most Solid applications assume hardcoded locations in Pods for storing data,
which is incompatible with the idea of Solid that every user should have the choice to organise their Pod as they see fit. 
Furthermore, not all Solid applications may make use of the same hardcoded locations.
One way of making Solid applications independent of the precise location at which data is stored inside a Pod,
is by building applications on top of *declarative queries*, such as SPARQL queries.
These SPARQL queries can then be evaluated by query engines that are able to find data in Solid Pods,
for example by making use of [Link Traversal Query Processing techniques dedicated to Solid Pods](cite:cites taelman2023evaluation).
This gives users the freedom to choose where and how they store their data,
without application developers needing to be aware of this heterogeneity across Pods.

In RDF, ontologies are used to give semantics to the data. 
One way to achieve interoperability for Solid applications is to follow the same ontology, as this will give the same structure to the application data. 
Therefore, both our todo apps use the same ontology. 

Our todo apps follow the Solid protocol, which authenticates users using their WebID 
and uses [Web Access Control (WAC)](cite:cites spec:wac) to regulate access control in the Pod. 
The todo apps navigate to the root document with the WebID and traverse through the LDP containers and the resources. 
The link traversal based query engine will not assume the location of the app data and traverses the entire Pod after matching the query. 

{:.comment data-author="RT"}
I don't think we need the section above, as it's mainly a repetition from what has been said before.

Both todo apps are query-driven, which means that all reads and writes to and from the pod are done via a query engine.
This allows the application developer to be agnostic about the precise storage location,
as this can be derived automatically by the query engine.
Concretely, we make use of the [Comunica SPARQL query engine](cite:cites taelman2018comunica),
as it has been implemented in JavaScript, and can therefore run in a user-facing browser application.
Furthermore, Comunica allows users to log in with their WebID, and is able to [traverse over Solid Pods](cite:cites taelman2023evaluation).
For example, [](#select-query) shows a query that ... from a Pod, independent of the precise storage location.

<figure id="select-query" class="listing">
    SELECT &nbsp; ?id &nbsp; ?todo &nbsp; WHERE &nbsp; { <br>
    &emsp; &emsp; &emsp; ?id <http://example.org/example/todoLabel> &nbsp; ?todo &nbsp; . <br>
        } 
)

<figcaption markdown="block">
SPARQL SELECT query
</figcaption>
</figure>

{:.comment data-author="RT"}
The query above is invalid syntactically.
Also, can we have a more interesting query? (more than just one triple pattern.)
Also, in the caption, describe what the query does exactly.

One of the current limitation of our apps, is that we write data to a fixed location in the pod, rather than being user-defined.
Like reading data from Pods, writing data to Pods is also abstracted using SPARQL queries.
More specifically, we make use of SPARQL INSERT and DELETE queries,
which can be resolved by Comunica,
which in its turn takes care of creating new resources if they don't exist yet,
or modifying them if they already exist.

