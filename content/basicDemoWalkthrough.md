## Basic Demo Walkthrough

The two to-do applications are used to manage and store a user's to-dos in their Solid pod.
When opening the applications, they ask the user to authenticate themselves with their WebID via [Solid OIDC](cite:cites spec:oidc) protocol.
After logging in, if the name of the user is found via a SPARQL `SELECT` query, it will be shown,
otherwise the WebID of the user is displayed.

Both applications provide an input field for users to enter their to-do entries.
These to-do entries consist of text content, creation date and status.
New tasks are assigned the 'pending' status and are stored in the pod.
The stored to-dos can be modified, and an additional modification date is added when this happens.
The to-dos can be toggled as pending or completed.
Using SPARQL `SELECT` queries, the stored to-dos are read from the Pod and displayed in the applications. 
To-do's can be deleted via SPARQL `DELETE` queries, which removes all the associated information from the Pod.

<div class="sidebyside">

<figure id="figure-react" >
<img src="img/react_app.png" />
<figcaption markdown="block">
React application.
</figcaption>
</figure>

<figure id="figure-vue" >
<img src="img/vue_app.png" />
<figcaption markdown="block">
Vue application.
</figcaption>
</figure>

</div>

[](#figure-vue) and [](#figure-react) feature screenshots of the user interfaces of the two applications.
In these examples, the same user is logged in, showing the same to-do lists.
If new to-dos are added, modified, toggled, or deleted in one app, they will also be reflected in the other app.
