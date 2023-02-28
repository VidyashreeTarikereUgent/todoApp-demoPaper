## Abstract

The Solid ecosystem and Solid Pods are of great interest as they promise to give developers freedom of developing innovative applications and users the power of storing their data anywhere on the web.

{:.comment data-author="RT"}
I think innovative apps are not a main concern for Solid.
But giving users the freedom to choose where and how their data is stored certainly is.
So I would focus only on that second part.

Different applications built for performing the same tasks are not interoperable with app data stored in the Pod.

{:.comment data-author="RT"}
Why is that?

In this demo, we show how two todo applications which are built using different frameworks are interoperable with the data in the Pod. These two todo applications share a same vocabulary and use WebID to authenticate themselves for creating resources,

{:.comment data-author="RT"}
The apps don't authenticate themselves.
Instead, users authenticate themselves to the app.

modifying the data and also deleting them.
These applications make use of link traversal with declarative SPARQL queries which relieve the app developers from being aware of where the data is stored in the decentralized Pod environment.

{:.comment data-author="RT"}
No need to mention link traversal here in the abstract.
Just keep it at the level of query-driven applications, which are indeed important for the reason you give.

In this demonstration, we present two interoperable Web applications that store data in the user's Solid Pod and give them the freedom to choose how and where this data is stored.