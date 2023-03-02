## Abstract

<!-- Context      -->
The Solid ecosystem is of great interest as it promises to give users the ability to fully control their data,
and to give them the freedom to choose where and how their data is stored. 
The decoupling of data and application in Solid enables multiple applications to act upon the same data,
giving the users freedom to choose which applications to use over their data.
However, interoperability does not come out of the box by default with Solid at the moment,
as their are difficulties pertaining to data storage location and the availability of different vocabularies.
<!-- Need         -->
Hence, we need a better understanding of how to achieve interoperable Solid apps.
<!-- Task         -->
To investigate the requirements and open challenges of this interoperability,
we designed two Solid applications that are built using different frameworks that can operate on the same data of a user.
Both applications manage personal todo lists.
<!-- Object       -->
In this paper, we explain the details of these applications, and how they achieve interoperability through a query-driven implementation.
<!-- Findings     -->
<!-- Conclusion   -->
We show that such a query-driven implementation is able to cope with different user preferences of storage locations in pods,
but that more research is needed to handle writing of data to pods,
and how to handle heterogeneous data models through schema alignment.
<!-- Perspectives -->
As such, our work provides a baseline use case onto which further interoperability research can be investigated.
