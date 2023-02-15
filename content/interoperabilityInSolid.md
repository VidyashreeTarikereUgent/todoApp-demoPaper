## Interoperability in Solid

Interoperibilty in Solid is the ability of multiple heterogenous Solid Pods and applications to work together to communicate with each other, to exchange data and to process data among themselves.

Solid protocol uses linked data and RDF to help with interoperability.  Ontologies are important as they give semantics to the data. Vocabularies give a structure to the data. Applications who follow a same vocabulary will have a same structure and enables interoperability. Building applications using same vocabularies will make the applications interoperable. [Link-traversal](cite:cites hartig2013overview) can be used for retrieving data from the Solid Pods and query them with comunica query engine. 

We explain how our todo applications are interoperable and carry-out the basic read and write operations. In Solid, each application uses user's WebId to authenticate against the user's pod. [Web Access Control(WAC)](cite:cites WAC) is used to regulate which application is eligible to read, write or modify resources in the Pod. Once an application is authorised with WebID and WAC to access a certain Solid Pod, the application can choose to start to traverse from a [seed URI](cite:cites hartig2011zero) for the link traversal. 

For reading data from a Solid Pod in our todo application, the application chooses to traverse starting with the seed URI, the WebID, looks up at LDP containers stored at one of the storage spaces, pim:storage, and traverses through the pod completely. The mentioned read operation can be carried out using comunica. A new comunica query engine should be created which is used to execute all the SPARQL queries. SPARQL SELECT queries can be used to read data from the Pod. 

```const bindingsStream = await myEngine.queryBindings(`
        SELECT ?id ?todo WHERE {
         ?id <http://example.org/example/todo> ?todo .
        }`, context
    )```

Listing 1.1:  SPARQL SELECT query which is executed by Comunica query engine, myEngine, and query context holding the WebID of the user. 

If the application is eligible to read the WebID profile of the user and has read access to the LDP containers, it traverses through the pod data and if it finds a matching predicate as mentioned in the in Listing 1.1, the stream of bindings for 'id' and 'todo' is saved at bindingStream. This way the application developer need not have to know where in the Pod to read the data. 

For writing data to the Solid Pod in our todo application, the application has a fixed location where the todo application's data will be stored. If there isn't already a resource for the todo in the pod, it will be created using SPARQL INSERT at the location set out by the todo application. If a todo needs to be modified, i.e., if a specific todo wants to be marked as done or update todo details, patching of resources is carried out using SPARQL DELETE and SPARQL INSERT. 

