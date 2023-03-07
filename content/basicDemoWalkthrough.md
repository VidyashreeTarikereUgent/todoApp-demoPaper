## Basic Demo Walkthrough

The React app and Vue app are todo applications which manage and store user's todos in their Solid Pods. 
The application asks user to authenticate access to their Pods with their WebIDs 
using the Login button which uses the [Solid OIDC](cite:cites spec:oidc) protocol.
After logging in, if the name of the user is found in their WebID profile it will be shown, else it will simply display the WebID of the user. 

Once a user is logged in, the login state persists even after a refresh. 

The apps provide a textbox for users to enter their todo entries.
These todo entries have an id, date of creation and the status as 'pending' assigned while storing them to the Pod. 
The stored todos can be modified, then an additional date of modification is added as well. 
The todos can be toggled as pending or completed, which will be updated in the Pod. 
Using Comunica with SPARQL SELECT queries, the stored todos are read from the Pod and displayed in the applications. 
Finally, the todos can be deleted which removes all the associated information from the Pod. This will be reflected in the apps as well.
<figure id="figure-vue" >
<img src="img/vue_app.png" style="height: 225px" />
<figcaption markdown="block">
Vue app
</figcaption>
</figure>
<figure id="figure-react" >
<img src="img/react_app.png" style="height: 425px"/>
<figcaption markdown="block">
React app
</figcaption>
</figure>


A user can login to a todo app, React or Vue framework based, and add a todo in the textbox available
and this can be viewed in the other app as seen in Figure 1 and Figure 2.
All the previously mentioned operations --adding, modifying, toggling and deleting a todo in one app--
will be reflected in the other app.   
