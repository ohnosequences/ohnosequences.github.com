---
layout: page
title: "Bio4j: bigger, faster, leaner"
comments: false
sharing: true
footer: true
---

Slides of ["Bio4j: bigger, faster, leaner"](https://fosdem.org/2014/schedule/event/graphdevroom_bio4j_2/) talk by [Pablo Pareja](/ppareja) on the [FOSDEM 2014](https://fosdem.org/2014/) conference.


<iframe class="frame" width="640" height="500" allowfullscreen mozallowfullscreen webkitallowfullscreen src="../embedder.html#fosdem-2014/raw.bio4j-bigger-faster-leaner.html"></iframe>
  

Bio4j is a high-performance cloud-enabled graph-based bioinformatics data platform. It integrates most data available in UniProt KB (SwissProt + Trembl), Gene Ontology (GO), UniRef (50, 90, 100), RefSeq, NCBI taxonomy, and Expasy Enzyme DBs. Data is organized in a way semantically equivalent to what it represents in the graph structure, and thanks to this, queries which would even be impossible to perform with a standard Relational DB can just take a couple of seconds with Bio4j.

This year has seen important updates and new developments on Bio4j. It now includes 1.216.993.547 relationships and 190.625.351 nodes, almost triple the figures from one year ago. We have introduced a new level of abstraction for the domain model, by decoupling the inner database implementation from the relationships among entities themselves. Interfaces has been developed for each node and relationship present in the database, including methods to access both the properties of the entity it represents and utility methods that allow to easily navigate to the entities that will be linked to it.

Implementing that set of interfaces we have developed another layer for the domain model using Blueprints, the de-facto graph data model standard, making the domain model independent from the choice of database technology. Building on that, we now offer specifically tuned data binary distributions for TitanDB, yielding a dramatic increase in performance due to vertex-local edge-typed indexes.

Bio4j is open source, available under the AGPLv3 license.
