## Basic Demo Walkthrough

{:.comment data-author="RT"}
In general, everything that needs to be in this section is here, but the section is lacking a good structure, as it's very hard for the reader to follow it at the moment.
I would suggest a more structured approach.
Here's one suggestion (but feel free to go for another structure):
- Data model: so that the reader understands what kind of data is managed
- A description of the capabilities of both apps, and their differences.
- A step-by-step guide of how a user can manage their todo's (e.g. hopping over the 2 apps)

{:.comment data-author="RT"}
The screenshot below doesn't show up in scholarmarkdown.

![vue_demo_screenshot](../assets/screenshots/vue_demo_screenshot.png)


Our demo shows how a user can use either of our two separate applications to manage todos in  the Pod. 

{:.comment data-author="RT"}
What is the Pod? I supposed you are referring to the pod of the user that is authenticated?

Both applications allow basic CRUD operations on todo's - tasks can be displayed, added, deleted, toggled and edited.

{:.comment data-author="RT"}
These operations deserve some more explanation.

{:.comment data-author="RT"}
Either use todo or task, but not interchangeable. This is confusing to the reader.

These operations apply to the underlying data inside the user's Pod, which are then automatically mirrored in the other app.
That means adding, editing or deleting a task in React app will also be shown in Vue app, and vice-versa, as they store data in the same pod, and use the same ontology.

Users with the valid Solid Pods have an associated WebId.
The two todo applications ask the user to use their WebIDs to authorize to interact with the app data in the Pods. 

{:.comment data-author="RT"}
The above is a bit out of place.
It might be better to have some kind of step-by-step guide in a listing to show the different steps a user may take when using these apps.

It is therefore recommended to test the apps with a local version of the CSS[^3] instead _[I don't like to write this -- the server is annoying to set up. Also, should we say something about the CSS/NSS/ESS logins? And should we give a test repo for people to set it up themselves?]_.
{:.comment data-author="Jonas"}

<figure id="figure-main">
<img src="img/react_app.png" >

<img src="img/vue_app.png" >

<figcaption markdown="block">
Screenshots of React App and Vue App
</figcaption>
</figure>

Both the apps have a Login button which use the [Solid OIDC](cite:cites spec:oidc) protocol for authenticating with their WebID .
As shown in [](#figure-main), the apps display the name of the user after logging in, if it is found in their root document else it will simply display the WebID of the user. 

{:.comment data-author="RT"}
What the "the root document"?

Once a user is logged in, the state persists even after a refresh. 

{:.comment data-author="RT"}
What is "the state"?

The apps provide a textbox for users to enter their todo entries.
These todo entries have an id, date of creation and the status as 'pending' assigned while storing them to the Pod. 
The stored todos can be modified, then an additional date of modification is added as well. 
The todos can be toggled as pending or completed, which will be updated in the Pod. 
Using Comunica with SPARQL SELECT queries, the stored todos are read from the Pod and displayed in the applications. 
Finally, the todos can be deleted which removes all the associated information from the Pod. This will be reflected in the apps as well.