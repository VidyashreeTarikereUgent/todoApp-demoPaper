## Interoperability in Solid

Interoperibilty in Solid is the ability of multiple heterogenous Solid Pods and applications to work together to communicate with each other, to exchange data and to process data among themselves.

At present, the applications have hardcoded locations in the Pod for storing the app data while it should be the users choice to organise their Pods. 
By adopting to declarative queries and link traversal query processing in applications, the users can organise data according to their needs and application developers do not need to know where the data is stored in the Pod.   
Thus, any changes to the query engine will have no effect on the application's declartive query. 
Discovery of data within the Pod is achieved using [link traversal](cite:cites taelman2023evaluation) initialised with a [seed URI](cite:cites hartig2011zero), WebID document. All resources within the Pod are discovered by following ldp:contains links in the root document 
which is found by the pim:storage predicate related to the WebID document.


Ontologies give semantics to the data. 
One way to achieve interoperability for Solid applications is to follow a same ontology which will give same structure to the application data and enables interoperability. 
Therefore, both our todo apps use the same ontology. 

The todo apps authenticate users using their WebID 
and uses [Web Access Control(WAC)](cite:cites spec:wac) to regulate access control in the Pod. 
The todo apps navigate to the root document with the WebID and traverse through the LDP containers and the resources. 
The link traversal based query engine will not assume the location of the app data and traverses the entire Pod after matching the query. 

For all operations in the Solid Pod query engine, [comunica](cite:cites taelman2018comunica), is used. 
Comunica is a modular meta query engine which can do federated query processing over Solid Pods. 
A new comunica query engine should be created which is used to execute all the SPARQL queries. 
SPARQL SELECT queries can be used to read data from the Pod. 

<figure id="select-query" class="listing">
    SELECT &nbsp; ?id &nbsp; ?todo &nbsp; WHERE &nbsp; { <br>
    &emsp; &emsp; &emsp; ?id <http://example.org/example/todoLabel> &nbsp; ?todo &nbsp; . <br>
        } 
)

<figcaption markdown="block">
SPARQL SELECT query
</figcaption>
</figure>

For our todo applications, writing data to the Solid Pod has a fixed location where the apps data will be stored. 
This is a limitation of our applications as they store data in the Pod in a fixed location rather than chosen by the user. 
If there isn't already a resource for the todo apps data in the pod, 
it will be created using SPARQL INSERT at the location set out by the todo application. 
If a task needs to be modified, i.e., if a specific todo wants to be marked as done or update todo details, patching of resources is carried out using SPARQL DELETE and SPARQL INSERT. 

