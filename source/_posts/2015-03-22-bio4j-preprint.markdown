---
layout: post
author: Eduardo Pareja-Tobes
title: "Bio4j preprint"
date: 2015-03-22 19:35
comments: false
categories:
- ngs
- cloud computing
- bioinformatics
- news
tag:
- preprint
- graphs
- bio4j
- ngs
- big data
- cloud computing
---

It's been _years_ since we started working on [Bio4j][Bio4j], and during all this time we have prioritized working on Bio4j over writing about (and publishing) what we were doing. Thanks in part to this, Bio4j 1.0 is going to be an amazing resource for the Bioinformatics community, built by only a handful of people; which I personally found quite impressive, given the scale and scope of the project. 

However, not having a standard way of citing Bio4j was starting to cause some difficulties for Bio4j users; a link to a GitHub repository is (still) not a generally accepted practice. This was so even for ourselves: we have several papers in the works which build on Bio4j, which are basically blocked because of this.

Well, this is no longer an issue: yesterday a preprint in the [bioRxiv][bioRxiv] went online, describing what is Bio4j

- **[Bio4j: a high-performance cloud-enabled graph-based data platform][Bio4j preprint]**

We chose the bioRxiv because preprints there are easily citable (they get a [DOI][DOI] assigned), and several open-access journals are happy with publishing a manuscript based on a preprint submitted to it (something which we will certainly do in the next few months).

I'm including below the citing info and abstract; any sort of feedback is welcome!

----
<br/>

### Bio4j: a high-performance cloud-enabled graph-based data platform

_Pablo Pareja-Tobes, Raquel Tobes, Marina Manrique, Eduardo Pareja, Eduardo Pareja-Tobes_ <br/>
**bioRxiv** -- **doi**: [10.1101/016758](http://dx.doi.org/10.1101/016758)

<!-- ### Abstract -->

**Background.** Next Generation Sequencing and other high-throughput technologies have brought a revolution to the bioinformatics landscape, by offering sheer amounts of data about previously unaccessible domains in a cheap and scalable way. However, fast, reproducible, and cost-effective data analysis at such scale remains elusive. A key need for achieving it is being able to access and query the vast amount of publicly available data, specially so in the case of knowledge-intensive, semantically rich data: incredibly valuable information about proteins and their functions, genes, pathways, or all sort of biological knowledge encoded in ontologies remains scattered, semantically and physically fragmented.

**Methods and Results.** Guided by this, we have designed and developed Bio4j. It aims to offer a platform for the integration of semantically rich biological data using typed graph models. We have modeled and integrated most publicly available data linked with proteins into a set of interdependent graphs. Data querying is possible through a data model aware Domain Specific Language implemented in Java, letting the user write typed graph traversals over the integrated data. A ready to use cloud-based data distribution, based on the Titan graph database engine is provided; generic data import code can also be used for in-house deployment.

**Conclusion.** Bio4j represents a unique resource for the current Bioinformatician, providing at once a solution for several key problems: data integration; expressive, high performance data access; and a cost-effective scalable cloud deployment model.

[Bio4j]: http://bio4j.com
[Bio4j preprint]: http://biorxiv.org/content/early/2015/03/20/016758
[bioRxiv]: http://biorxiv.org/
[DOI]: https://en.wikipedia.org/wiki/Digital_object_identifier

