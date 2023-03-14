## Introduction
{:#introduction}

An increasing number of decentralized Web applications are being built following the [Solid](cite:cites sambra2016solid) protocol.
Solid builds upon the [Resource Description Framework (RDF)](cite:cites spec:rdf) and [Linked Data](cite:cites linkeddata),
and introduces personal online datastores (pods) as a means of storing both RDF and non-RDF data inside [Linked Data Platform (LDP)](cite:cites spec:ldp) containers,
similar to directories in document-oriented design models.
Access control via [Web Access Control (WAC)](cite:cites spec:wac) allows the owner of a Solid pod to manage access to the data it contains.
Users are identified by their unique [WebID](cite:cites sambra2014webid),
and the WebID document may contain a link to a user's pod to locate their data.
Authentication takes place using [Solid OIDC](cite:cites debackere2022policy).

Notably, Solid promises to decouple applications and data, placing the user in possession and control of their data,
and in theory allowing the users to use any application with the data in their pod.
Thus, within the context of Solid, interoperability can be described as the ability of multiple heterogenous Solid pods and applications to work together,
by communicating with each other, by exchanging data, and by processing data among themselves.

Within this demonstration, we will present two interoperable to-do applications developed on top of Solid pods,
one using React[^reactapp] and the other one Vue[^vueapp].
Both applications have been made available as open-source.
These applications can create new tasks, mark them as completed or pending, modify the tasks and delete the tasks in the user's pod.

[^reactapp]: [https://github.com/SolidLabResearch/solid-todo-app-react](https://github.com/SolidLabResearch/solid-todo-app-react)
[^vueapp]: [https://github.com/SolidLabResearch/solid-todo-app-vue](https://github.com/SolidLabResearch/solid-todo-app-vue)

