## Introduction
{:#introduction}

In recent times there are applications which are built on the basis of [Solid Protocol](cite:cites sambra2016solid). All these Web applications focus on keeping users data decentralized from the application themselves

{:.comment data-author="RT"}
Not exactly, the Solid protocol enables decentralization of data, Solid apps just build on top of this.

and give users a great liberty to be in control of their own data and who has access to it and how it is used. Solid Pods form personal [Knowledge Graphs](cite:cites hogan2021knowledge) that are constituted by [Linked Data documents](cite:cites linkeddata) containing [Resource Description Framework (RDF) triples](cite:cites spec:rdf).

Each of these RDF triples have subject, predicate and object, where subject and object are resources identified by Uniform Resource Identifiers(URIs) or blank nodes. Predicates represent a relationship between subject and object. These resources are interconnected through RDF triples forming a Knowledge Graph in Solid Pods. Thus, SPARQL query language can be used to query over Solid Pods as it is the standard for querying Knowledge Graphs.

{:.comment data-author="RT"}
No need to explain what RDF triples are, not needed for a poster paper at a semantic web conference.

Solid pods can store any kind of data, RDF or non-RDF resources, in LDP Containers,

{:.comment data-author="RT"}
Citation needed for LDP.

similar to directories in document-oriented design models. These resources in LDP Containers can be read with HTTP GET requests to their URIs. With HTTP POST and PATCH requests, resources are created or modified. 

Every Solid Pod user can be identified using a URI called [WebID](cite:cites sambra2014webid). The users can authenticate themselves via [Solid OIDC](cite:cites debackere2022policy) for reading and writing of resources.

{:.comment data-author="RT"}
The access control part is missing here (ACL/ACP).

The WebID document can contain basic information of the user, such as the name, phone number, etc., and links to the root LDP container.  


In this demonstration we are showcasing two todo apps which are developed with two different frameworks, a [React-based todo app](https://solidlabresearch.github.io/solid-todo-app-react/){:.mandatory} and [Vue-based todo app](https://solidlabresearch.github.io/solid-todo-app-vue/){:.mandatory}, which are interoperable in the Solid ecosystem. The two apps access the authenticated user's pod by authorizing with the user's WebID. These applications can create new tasks, mark them as completed or pending, modify the tasks and delete the tasks in the user's pod.