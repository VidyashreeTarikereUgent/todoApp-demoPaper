## Conclusion

While Solid itself offers the foundations for separating data from applications, more work is still needed in making that reality in practice.
We have demonstrated the use of SPARQL queries to address the challenges in storage location interoperability between Solid applications,
at the expense of having to potentially scan the entire pod in search of relevant data.
Our approach still results in applications having to decide where to write their data,
prompting for some form of abstraction in that regard, as well, perhaps on a query engine library level or within the pod itself as it ingests data.
The challenges around ontology interoperability through schema alignment likewise remain to be addressed in future work,
perhaps also on a query engine library level, making any solutions reusable by multiple applications.
