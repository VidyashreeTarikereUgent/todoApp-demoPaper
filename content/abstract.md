## Abstract
<!-- Context      -->
The Solid ecosystem promises to give users the ability to fully control their data,
and the freedom to choose where and how that data is stored. 
The decoupling of data and applications in Solid enables multiple applications to act upon the same data,
offering users the freedom to choose any application they wish to use on top of their data.
However, application interoperability in Solid is not guaranteed at the moment,
as the choices of data storage location and vocabularies by one application can impact those of other ones.
<!-- Need         -->
Hence, we need a better understanding of how to achieve interoperable Solid apps.
<!-- Task         -->
To investigate the requirements and open challenges,
we designed two Solid applications that are built using different frameworks and can operate on the same data from a user.
Both applications manage personal to-do lists.
<!-- Object       -->
In this paper, we explain the details of these applications, and how they achieve interoperability through a query-driven implementation.
<!-- Findings     -->
<!-- Conclusion   -->
We show that such a query-driven implementation is able to cope with different user preferences of storage locations,
but that more research is needed to handle writing of data,
and to handle heterogeneous data models through schema alignment.
<!-- Perspectives -->
As such, our work provides a baseline use case for further interoperability research.
