---
comments: false
date: 2011-03-29 15:27:17
layout: post
author: Pablo Pareja
slug: playing-with-gephi-bio4j-and-go
title: Playing with Gephi, Bio4j and Go
wordpress_id: 221
categories:
- bio4j
tag:
- bio4j
- gephi
- go
- graph
- ontology
- seadragon
- visualization
---

It had already been some time without having some fun with [**Gephi**](http://www.gephi.org) so today I told myself: why not trying visualizing the whole Gene Ontology and seeing what happens?

First of all I had to generate the corresponding file in [gexf format](http://gexf.net/format/) containing all the terms and relationships belonging to the ontology.
For that I did a small program ([**GenerateGexfGo.java**](https://github.com/bio4j/Bio4jTools/blob/master/src/com/era7/bioinfo/bio4j/tools/GenerateGexfGo.java)) which uses [**Bio4j**](http://www.bio4j.com) for terms/relationships info retrieval and a couple of XML Gexf wrapper classes from the github project [BioinfoXML](https://github.com/pablopareja/BioinfoXML).

Once I had my gexf file I tried opening it (~17 MB) with gephi in my laptop with no success, (_gephi froze forever when trying to import the file_). 
Then, after a quick search on google I figured out that the amount of memory used by Gephi was really easy to change, (_just open the file 'etc/gephi07beta.conf' and change the -Xmx value_).

With my file already imported, first I applied the algorithm [**OpenOrd**](http://gephi.org/2010/openord-new-layout-plugin-the-fastest-algorithm-so-far/) (which is the best one for large graphs) and then once it had an acceptable distribution I finally applied some iterations of the algorithm Fruchterman Reingold for a better visualization.
And this is what I got:

{% img /images/wholeGo.svg %}

Colors correspondance:	

* **Green**: Cellular component
* **Blue**: Molecular function
* **Orange**: Biological process

**UPDATE:** zoomable independent ontology visualizations using gephi [SeaDragon plugin](http://gephi.org/plugins/seadragon/).

**Molecular function**

{% img /images/molecularFunctionScreenShot-300x281.jpg %}

**Cellular component**

{% img /images/cellularComponentScreenShot-300x280.jpg %}

**Biological process**

{% img /images/biologicalProcessScreenShot-300x275.jpg %}


[Here](https://s3-eu-west-1.amazonaws.com/pablo-tests/wholeGo.gexf) you can download the gexf file in case you want to experiment a bit with it.




