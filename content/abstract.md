## Abstract
<!-- Context      -->
A lot of museums publish data on their collections which then requires a mechanism to keep that data synchronized with any additions, updates or deletions of the collections.
With the current approach of International Image Interoperability Framework Change Discovery ( IIIF-CD) API with ActivityStreams 2.0, the changes in the museum records are indicated.
<!-- Need         -->
However, IIIF-CD API only alerts about the change in the museum records and doesn’t specify what exactly has changed.
The IIIF-CD doesn’t filter on specific items but rather publishes all the changes in the museum records.
<!-- Task         -->
Is there a way to filter specific items and showcase what are the changes that happened to the museum records?
<!-- Object       -->
In this paper, we show how Linked data event streams (LDES) compatible with AcitvityStreams 2.0 can be used in the place of IIIF-CD API for change discovery with member extraction algorithm.
LDES also synchronises specific subsets, i.e. for example only colonial heritage data in museum records.
One of the outstanding feature of LDES is it’s a tree-structure unlike a doubly-linked list in ActivityStreams 2.0.
<!-- Findings     -->

<!-- Conclusion   -->

<!-- Perspectives -->
As such, our work provides a baseline use case for further research in compatibility of LDES with other standards.
