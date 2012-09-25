---
comments: false
date: 2011-03-23 13:29:56
layout: post
slug: bio4j-a-graph-based-db-containing-most-of-data-available-in-uniprot-uniref-and-gene-ontology
title: 'Bio4j: a graph based DB containing most of data available in Uniprot, Uniref
  and Gene Ontology'
wordpress_id: 161
categories:
- bio4j
tag:
- database
- nosql
- uniprot
---

We have recently launched Bio4j, a graph based database that includes most of the data available in Uniprot, Uniref clusters and Gene Ontology. Quoting from the Bio4j wiki:

 
> Bio4j provides a completely new and powerful framework for protein related information querying and management. Since it relies on a high-performance graph engine (Neo4j), data is stored in a way that semantically represents its own structure. On the contrary, traditional relational databases must flatten the data they represent into tables, creating “artificial” ids in order to connect the different tuples; which can in some cases eventually lead to domain models that have almost nothing to do with the actual structure of data.

Thanks to its graph structure queries that could be time consuming or even inpossible in relational DBs can be performed easily in Bio4j.

An example of this kind of queries would be the following:

Suppose you are working in the membrane proteins of a non model organism that unfortunately have very poor annotations. Searching for proteins of your interest in Uniprot by your organism name or taxonomy only results in a few unrewieved entries with few more than the sequence. Next step could probably be to use the Uniprot advance search tool to get the proteins similar to your proteins in a 50, 90 or 100% (the Uniref clusters) and then look protein by protein which of them have annotations that could indicate that they are membrane proteins and select those that 1) have good enough annotaions for your purpose and 2) are related enough to your protein to be able to infer the functions of the well-annotated proteins to your protein. This would be a manual and tedious process time consuming and error prone.

All this process of getting all the proteins of your organism, then getting the high similar ones and then getting only those which are in the membrane and have quality annotations could be perfomed programmatically in a fairly simple graph traversal. All you would have to specify would be:

* The level of needed similarity between the proteins of your organism and the well-characterized ones
* The criteria to consider a protein has good enough annotations: if the entry is reviewed, if it's got lots of cross references, of functional data (Interpro, GO...)
* The criteria to consider a protein is in the membrane, for example that it's got a GO ID indicating that is a membrane protein, that its subcellular location is the membrane... both...

More information about Bio4j in its [website](http://www.bio4j.com), the [blog](http://blog.bio4j.com/), the [wiki ](http://wiki.bio4j.com/) and the [twitter profile](http://twitter.com/#!/bio4j).
