## Interoperability in Solid

Interoperibilty in Solid is the ability of multiple heterogenous Solid Pods and applications to work together to communicate with each other, to exchange data and to process data among themselves.

The application developers need not have to know where the data relavent to the application is stored in the Pod as it is handled by declarative queries.

{:.comment data-author="RT"}
You're skipping some steps here.
First, say that current apps rely on hardcoded access to certain document paths in the pod.
However, since different users can organize their pods in different ways, we need a layer of abstraction.
Declarative queries and link traversal query processing offer a solution to this, as we have proven in https://arxiv.org/abs/2302.06933

 Thus, any changes to the query engine will have no effect on the application's declarative query. Discovery of data within the Pod is achieved using [link traversal](cite:cites hartig2013overview) initialised with a seed URI, WebID document. All resources within the Pod are discovered by following `ldp:contains` links in the root document which is found by the `pim:storage` predicate related to the WebID document.
 
{:.comment data-author="RT"}
The process above is explain in detail in https://arxiv.org/abs/2302.06933, so you can cite that paper for this.

Ontologies give semantics to the data. Vocabularies give a structure to the data.

{:.comment data-author="RT"}
Ontologies and vocabularies are usually used as synonyms for each other, so I suggest picking just one to avoid confusion.

Applications who follow a same vocabulary will have a same structure and enables interoperability. Building applications using same vocabularies will make the applications interoperable. Therefore, both our todo apps use the same vocabulary. 

{:.comment data-author="RT"}
Say that this is just one way of achieving interop.
Hint towards future work that always having the same vocab is not always possible, and schema alignment is needed to handle those cases.

The todo apps authenticate users using their WebID and uses [Web Access Control(WAC)](cite:cites spec:wac) to regulate access control in the Pod.

{:.comment data-author="RT"}
WAC should have come in the introduction.

The todo apps navigate to the root document with the WebID and traverse through the LDP containers and the resources.

{:.comment data-author="RT"}
This detail is not needed, as it's explain in detail in that other paper.

The link traversal will not assume the location of the app data and traverses the entire Pod after matching the query. 

{:.comment data-author="RT"}
The above is important indeed!
But don't say "the link traversal", say "the link traversal-based query engine".

For reading data from a Solid Pod in our todo application comunica is used. A new comunica query engine should be created which is used to execute all the SPARQL queries. SPARQL SELECT queries can be used to read data from the Pod. 

{:.comment data-author="RT"}
Citation for comunica is needed.
Also explain why you use it (because it implements traversal over Solid pods, with authentication)

<figure id="select-query" class="listing">
    SELECT &nbsp; ?id &nbsp; ?todo &nbsp; WHERE &nbsp; { <br>
    &emsp; &emsp; &emsp; <http://example.org/example/todo> &nbsp; ?todo &nbsp; . <br>
        } 
)

<figcaption markdown="block">
SPARQL SELECT query
</figcaption>
</figure>

{:.comment data-author="RT"}
The query above is invalid.
I guess you can just copy-paste a query that is used in your app?

For writing data to the Solid Pod in our todo application, the application has a fixed location where the todo application's data will be stored. If there isn't already a resource for the todo apps data in the pod, it will be created using SPARQL INSERT at the location set out by the todo application. If a task needs to be modified, i.e., if a specific todo wants to be marked as done or update todo details, patching of resources is carried out using SPARQL DELETE and SPARQL INSERT. 

{:.comment data-author="RT"}
This is a limitation of your work, so do be clear about that!
While reading is location-agnostic, writing is not (yet).

