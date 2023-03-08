## Abstract

<!-- Context      -->
The Solid ecosystem promises to give users the ability to fully control their data,
and to give them the freedom to choose where and how their data is stored. 
The decoupling of data and application in Solid enables multiple applications to act upon the same data,
giving the users freedom to choose which applications use their data.
However, interoperability in Solid does not come out of the box at the moment,
as apps' choices of data storage location and vocabularies impact those of others.
<!-- Need         -->
Hence, we need a better understanding of how to achieve interoperable Solid apps.
<!-- Task         -->
To investigate the requirements and open challenges,
we designed two Solid applications that are built using different frameworks and can operate on the same data of a user.
Both applications manage personal to-do lists.
<!-- Object       -->
In this paper, we explain the details of these applications, and how they achieve interoperability through a query-driven implementation.
<!-- Findings     -->
<!-- Conclusion   -->
We show that such a query-driven implementation is able to cope with different user preferences of storage locations in pods,
but that more research is needed to handle writing of data to pods,
and to handle heterogeneous data models through schema alignment.
<!-- Perspectives -->
As such, our work provides a baseline use case to further interoperability research.
