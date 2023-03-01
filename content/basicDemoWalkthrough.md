## Basic Demo Walkthrough

![vue_demo_screenshot](../assets/screenshots/vue_demo_screenshot.png)

{:.comment data-author="RT"}
Screenshot doesn't work for me.
{:.comment data-author="JST"}
I am using standard Markdown image notation, so it should work.. but looking it up in the ScholarMarkdown wiki it seems a different syntax is needed

<figure id="vue_demo_screenshot">
<img src="assets/screenshots/vue_demo_screenshot.png" alt="[Demo screenshot]">
<figcaption markdown="block">
The interoperable web interface to manage the task-list in one of the apps.
</figcaption>
</figure>

Our demo shows how a non-technical user can use either of our two separate application to manage a task-list[^4] in his or her POD ([](#vue_demo_screenshot)).

Both applications interoperate and allow basic CRUD operations -- tasks can be displayed, added, deleted, toggled and edited.
{:.comment data-author="JST"}
Should we add a list of acronyms? Or is CRUD, CSS, POD, RDF clear?

These operations reflect on the underlying data and mirror in the other app.
{:.comment data-author="JST"}
Ideally we could show both apps side by side and have them automatically update when the underlying data changes -> In the demo

That means adding, editing or deleting a task in app A will also be shown in app B, and vice-versa, as they use the same ontology and operate on the same data.




The source code and hosted versions of the app are available online[^1][^2] 
{:.comment data-author="JST"}
Do we need to anonymize this?

Using the app requires a working WebID and a POD.

It is therefore recommended to test the apps with a local version of the CSS[^3].
{:.comment data-author="JST"}
I don't like to write this -- the server is annoying to set up

{:.comment data-author="JST"}
Also, should we mention the different CSS/NSS/ESS logins? And should we give a test repo for people to set it up themselves?

[^1]: [Vue-Application](https://github.com/SolidLabResearch/solid-todo-app-vue)

[^2]: [React-Apllication](https://github.com/SolidLabResearch/solid-todo-app-react)

[^3]: [Community Solid Server](https://github.com/CommunitySolidServer/CommunitySolidServer)

[^4]: colloquially called 'todolist'; this term however lead to a lot of confusion during development, as 'todo' is also commonly used to denote issues in the source code

