---
author: Raquel Tobes
comments: false
date: 2011-06-08 16:00:37
layout: post
slug: are-there-plasmids-in-the-e-coli-ty-2482-genome
title: Are there plasmids in the E. coli TY-2482 genome?
wordpress_id: 442
categories:
- ngs
tag:
- annotation
- EHEC
- Escherichia coli
---

After taken a first look at the annotation of  the second BGI assembly of the E. coli `TY-2482` genome there are lot's of questions arising. The quality of the sequence and assembly of this second version of `TY-2482` genome is much higher allowing more detailed analysis.

The presence of plasmids is clearly an interesting one.

In the automatic annotation we published yesterday (see post [here ](http://blog.ohnosequences.com/2011/06/automatic-annotation-of-the-second-bgi-assembly-of-e-coli-ty-2482-genome/http://blog.ohnosequences.com/2011/06/automatic-annotation-of-the-second-bgi-assembly-of-e-coli-ty-2482-genome/)and wiki page [here](https://github.com/ehec-outbreak-crowdsourced/BGI-data-analysis/wiki/Era7-annotation-of-bgi-v2-assembly-of-e.-coli-ty-2482)) we've detected 4 contigs that may probably be part of plasmids

* Contig 63 with 48 predicted genes
* Contig 74 with 7 predicted genes; all of these involved in Mercury resistance
* Contig 98 with 12 predicted genes. This contig contain SOS inhibition proteins, nucleases, single-stranded DNA binding protein  and other uncharacterized proteins
* Contig 503 with 37 predicted proteins. Among these proteins we find a beta-lactamase and some interesting proteins (in terms of mobility and gene transfer) like several transposons and proteins involved in conjugation and plasmid maintenance.

We can't conclude yet how many different plasmids `TY-2482` may have.

We'll keep on analysing this genome and posting updates here and in the [EHEC GitHub wiki](https://github.com/ehec-outbreak-crowdsourced/BGI-data-analysis/wiki)

**Update88 (10-Jun-2011):

Kat Holt has noticed that the protein annotated as beta-lactamase CTX-M-3 in the contig 503 is actually beta-lactamase CTX-M-15. Read the whole story in the comments of this Kat's post [http://bacpathgenomics.wordpress.com/2011/06/07/new-german-stecehec-data-from-bgi/](http://bacpathgenomics.wordpress.com/2011/06/07/new-german-stecehec-data-from-bgi/)
