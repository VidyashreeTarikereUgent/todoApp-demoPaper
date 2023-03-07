## Introduction
{:#introduction}

An increasing number of decentralized Solid Web applications are being built according to the [Solid Protocol](cite:cites sambra2016solid). 
In Solid, the applications and data are decoupled 
which give users great freedom to be in control of data and who has access to it and how it is used. 
Solid Pods can be considered _personal [Knowledge Graphs](cite:cites hogan2021knowledge)_,
as they consist of [Linked Data documents](cite:cites linkeddata) containing [Resource Description Framework(RDF) triples](cite:cites spec:rdf). 
These resources are interconnected through RDF triples forming a Knowledge Graph in Solid Pods. 
Thus, the SPARQL query language can be used to query over Solid Pods as it is the standard for querying Knowledge Graphs.

Solid pods can store any kind of data, RDF or non-RDF resources, inside [LDP](cite:cites spec:ldp) containers,
similar to directories in document-oriented design models. 
Since the data is spread across the Pod, [link traversal](cite:cites taelman2023evaluation) is used to evalute SPARQL queries.
The resources inside LDP containers can be read with HTTP GET requests to their URIs. 
Resources can be created or modified using HTTP POST, PUT, and PATCH requests.
Every Solid user can be identified using a URI called [WebID](cite:cites sambra2014webid). 
Users can authenticate themselves with [Solid OIDC](cite:cites debackere2022policy),
and [Web Access Control(WAC)](cite:cites spec:wac) enables authorization for interacting with resources.
The WebID document can contain the user's basic information and links to the root LDP container. 

In this demonstration we are showcasing two todo apps which are developed with two different frameworks, a [React-based todo app](https://solidlabresearch.github.io/solid-todo-app-react/){:.mandatory} and [Vue-based todo app](https://solidlabresearch.github.io/solid-todo-app-vue/){:.mandatory}, which are interoperable in the Solid ecosystem. The two apps access the authenticated user's pod by authorizing with the user's WebID. These applications can create new tasks, mark them as ntpleted or pending, modify the tasks and delete the tasks in the user's pod.
