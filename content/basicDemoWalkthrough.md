## Basic Demo Walkthrough

Notes: (TODO: remove these in the final version1)

Goal of this section: Describe the capabilities of our app, ie. what we will be demonstrating live .

list of acronyms?
- CSS
- RDF
- POD: personal online data store/space
- CRUD

----

![vue_demo_screenshot](../assets/screenshots/vue_demo_screenshot.png)

Our demo shows how a _[non-technical?]_ user can use either of our two separate application to manage a task-list[^4] in his or her POD. Both applications interoperate and allow basic CRUD operations -- tasks can be displayed, added, deleted, toggled and edited. These operations reflect on the underlying data and mirror in the other app _[ideally we could show both apps side by side and have them automatically update when the underlying data changes.]_. That means adding, editing or deleting a task in app A will also be shown in app B, and vice-versa, as they use the same ontology and operate on the same data.

The source code and hosted versions of the app are available online[^1][^2] _[Note: Do we need to anonymize this?]_. Using the app requires a _[working]_ WebID and a POD. It is therefore recommended to test the apps with a local version of the CSS[^3] instead _[I don't like to write this -- the server is annoying to set up. Also, should we say something about the CSS/NSS/ESS logins? And should we give a test repo for people to set it up themselves?]_.

[^1]: [Vue-Application](https://github.com/SolidLabResearch/solid-todo-app-vue)
[^2]: [React-Apllication](https://github.com/SolidLabResearch/solid-todo-app-react)
[^3]: [Community Solid Server](https://github.com/CommunitySolidServer/CommunitySolidServer)
[^4]: colloquially called 'todolist'; this term however lead to a lot of confusion during development, as 'todo' is also commonly used to denote issues in the source code

