## Interoperability in Solid

Interoperibilty in Solid is the ability of multiple heterogenous Solid Pods and applications to work together to communicate with each other, to exchange data and to process data among themselves.

The application developers need not have to know where the data relavent to the application is stored in the Pod as it is handled by declarative queries. Thus, any changes to the query engine will have no effect on the apllication's declartive query. Discovery of data within the Pod is achieved using [link traversal](cite:cites hartig2013overview) initialised with a seed URI, WebID document. All resources within the Pod are discovered by following ldp:contains links in the root document which is found by the pim:storage predicate related to the WebID document.

Ontologies give semantics to the data. Vocabularies give a structure to the data. Applications who follow a same vocabulary will have a same structure and enables interoperability. Building applications using same vocabularies will make the applications interoperable. Therefore, both our todo apps use the same vocabulary. 

The todo apps authenticate users using their WebID and uses [Web Access Control(WAC)](cite:cites spec:wac) to regulate access control in the Pod. The todo apps navigate to the root document with the WebID and traverse through the LDP containers and the resources. The link traversal will not assume the location of the app data and traverses the entire Pod after matching the query. 

For reading data from a Solid Pod in our todo application comunica is used. A new comunica query engine should be created which is used to execute all the SPARQL queries. SPARQL SELECT queries can be used to read data from the Pod. 

<figure id="select-query" class="listing">

const bindingsStream = await myEngine.queryBindings(`
        SELECT ?id ?todo WHERE {
         ?id <http://example.org/example/todo> ?todo .
        }`, context
)
<figcaption markdown="block">
SPARQL SELECT query which is executed by Comunica query engine, myEngine, and query context holding the WebID of the user. 
</figcaption>
</figure>

Listing 1.1:  SPARQL SELECT query which is executed by Comunica query engine, myEngine, and query context holding the WebID of the user. 

For writing data to the Solid Pod in our todo application, the application has a fixed location where the todo application's data will be stored. If there isn't already a resource for the todo apps data in the pod, it will be created using SPARQL INSERT at the location set out by the todo application. If a task needs to be modified, i.e., if a specific todo wants to be marked as done or update todo details, patching of resources is carried out using SPARQL DELETE and SPARQL INSERT. 

