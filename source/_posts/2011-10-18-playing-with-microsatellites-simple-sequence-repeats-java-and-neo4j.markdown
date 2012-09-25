---
author: Pablo Pareja
comments: false
date: 2011-10-18 19:28:04
layout: post
slug: playing-with-microsatellites-simple-sequence-repeats-java-and-neo4j
title: Playing with microsatellites (Simple Sequence Repeats), Java, and Neo4j
wordpress_id: 551
categories:
- neo4j
tag:
- database
- graph
- graph-databases
- java
- microsatellites
- neo4j
- nosql
- repeats
- sequence
- ssr
- visualization
---

Hi!

I just finished this afternoon a small project I had to do about identification of microsatellites in DNA sequences. As with every new project I start, I think of something that:

* I **didn't try before**
* is **worth learning**
* is **applicable** in order to meet the needs of the specific project

These last few days it was the chance to get to know and try the visualization tool included in the last version of [**Neo4j Webadmin dashboard**](http://blog.neo4j.org/2011/10/announcing-neo4j-15-boden-bord.html).
I had already heard of it a couple of times from different sources but had not had the chance to play a bit with it yet. So, after my first contact with it I have to say that although it's something [Neo4j](http://www.neo4j.org) introduced in the last versions, it already has a decent GUI and promising functionality. 

Apart from GUI considerations, I created the repository [**MicrosatellitesNeo4jModel**](https://github.com/pablopareja/MicrosatellitesNeo4jModel) with a bunch of nodes and relationships wrappers as an API for  performing traversals for all this data in an easy way.
Here is the domain model I chose:

[![Microsatellites Neo4j domain model](https://s3-eu-west-1.amazonaws.com/pablo-tests/MicrosatellitesDomainModel.jpg)](https://s3-eu-west-1.amazonaws.com/pablo-tests/MicrosatellitesDomainModel.svg)

On the programs side, I developed two different Java classes, one dealing with the identification of the microsatellites and their subsequent storage on the Neo4j DB ([CreateMicrosatellitesDB.java](https://github.com/pablopareja/Microsatellites/blob/develop/src/com/era7/bioinfo/microsats/programs/CreateMicrosatellitesDB.java)) and another ([ExtractDataToCSV.java](https://github.com/pablopareja/Microsatellites/blob/develop/src/com/era7/bioinfo/microsats/programs/ExtractDataToCSV.java))for extracting statistical information for a set of specific parameters like tuple length and things like that. 
Both classes are in the repository [**Microsatellites**](https://github.com/pablopareja/Microsatellites).

Once the DB was created, I played a bit with the display profiles in the WebAdmin data browser so that different node types had a different aspect and this is what I got:

[![Microsatellites DB data browser screenshot](https://s3-eu-west-1.amazonaws.com/pablo-tests/MicrosatellitesDataBrowserScreenshot.jpg)](https://s3-eu-west-1.amazonaws.com/pablo-tests/MicrosatellitesDataBrowserScreenshot.jpg)

Here you can find blue circles (**sequence IDs**), orange boxes (**tuples** repeated in the microsatellites found), and greenish squares (**tuple length** nodes). 

One of the features I was missing in the visualization was having style rules for relationships as well as for nodes. This was specially important in my case where I have relevant information stored as relationships attributes, _(I actually could not visualize the number of tuple repeats in the microsatellites found, just the name of the relationship 'MICROSATELLITE_FOUND' everywhere)_.
However I posted a question on neo4j user list about this and it seems they already are working on this, cool!

As always, everything here is open source and released under under [**AGPLv3**](http://www.gnu.org/licenses/agpl.html).

Cheers,

[@pablopareja](http://twitter.com/pablopareja)



