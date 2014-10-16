---
layout: page
title: "about"
sharing: true
footer: true
---

_Oh no sequences!_ is the research and development group at [era7 bioinformatics](http://era7bioinformatics.com). 

We've been doing a lot of R&D at era7 bioinformatics since the start of the company, but _oh no sequences!_ as a group officially started at the spring of 2011. Since then, we'd 

- released [bio4j](http://bio4j.com), UniprotKB + GeneOntology + NCBI taxonomy + RefSeq + Expasy Enzyme, integrated in a graph DB with easy [AWS](http://aws.amazon.com) deployment.
- released [bg7](http://bg7.ohnosequences.com), our bacterial genome annotation system, designed from the ground up for NGS data.
- did a lot of work on the crowdsourced data analysis from the EHEC outbreak: annotated _all_ released genomes, set up and coordinated the [github repository](http://github.com/ehec-outbreak-crowdsourced/BGI-data-analysis) and [wiki](http://github.com/ehec-outbreak-crowdsourced/BGI-data-analysis/wiki), etc.

## interests

As our name suggests, we're interested in _sequences_; but in lots of other things too: cloud computing, graph DBs, functional programming and category theory... 

### bacterial genomics

- **horizontal gene transfer** In particular its relationship with antibiotic resistance, outbreaks, and related stuff.
- **repeated extragenic sequences** In particular, _REPs_: Repetitive extragenic _palindromic_ sequences.

### metagenomics

We have developed an AWS-based system for this, called _mg7_ (manuscript in preparation).

### cloud computing

We've been using AWS since 2005, and it plays a critical role in everything we do. You can take a look at two of our cloud-related libraries:

- [nispero](/nispero): an easy to use, scalable AWS-based library for declaring and executing stateless computations
- [statika](/statika): a completely immutable, type-safe Scala system for writing and deploying machine configurations.

### NoSQL databases

We're particularly interested in graph DBs: We've been heavy users of [neo4j](http://neo4j.com) since 2010, and [Titan](https://github.com/thinkaurelius/titan) from its inception; [Pablo Pareja](ppareja) is a well-known participant of the graph db community. We've built and use on a daily basis one of the biggest and more complex graph DBs for biological data out there, [bio4j](http://bio4j.com).

### category theory

Enriched category theory, in particular as applied to categorical/functional programming. The relationship between monoidal categories equipped with trace-like structures and concurrent and distributed systems. Applications of these ideas to the study of complex inherently distributed systems appearing in bacterial genomics, specifically horizontal gene transfer and highly interrelated microbial communities.









