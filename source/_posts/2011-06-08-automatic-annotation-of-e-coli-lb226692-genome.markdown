---
author: Raquel Tobes
comments: false
date: 2011-06-08 10:35:22
layout: post
slug: automatic-annotation-of-e-coli-lb226692-genome
title: Automatic annotation of E. coli LB226692 genome
wordpress_id: 430
categories:
- ngs
tag:
- annotation
- EHEC
- Escherichia coli
---

And this morning we've finished the automatic annotation of the other isolate from the outbreak whose sequence is also available. The isolate `LB226692`.

Life Tech and University of Muenster have sequenced the genome and done a hybrid mapping assembly getting finally 364 contigs. More details on the assembly method [here](https://github.com/ehec-outbreak-crowdsourced/BGI-data-analysis/wiki/Assemblies)

We used[BG7 system](http://www.slideshare.net/marina_manrique/bg7-a-new-system-for-bacterial-genome-annotation-designed-for-ngs-data) to annotate the genome.

In this case we've selected as reference protein the same protein set we used to annotate the other E. coli isolate (the `TY-2482`). This protein set has 137,063 proteins and includes:

* The representative Uniprot proteins corresponding to all Uniref90 clusters for all Escherichia coli proteins
* All Uniprot proteins from organisms including in their name the terms “EHEC” or “EAEC”
* All Uniprot proteins from bacteria that have in any Uniprot field the term “toxin”
* All Uniprot proteins from bacteria that have in any Uniprot field  “hemolysin”
* All the proteins from Salmonella typhi, Yersinia pestis and Shigella dysenteriae

#### Results

We've detected **6,302** genes

* 6,132 protein encoding genes
* 170 RNA genes

4,504 out of the 6,132 (73.45%) protein encoding genes have canonical start and stop codon and haven´t either frame-shifts or intragenic stop codons.

1,125 out of the 6,132 (18.34%) protein encoding genes have some frameshifts or intragenic stop codon in their sequences, probably caused by inherent technology errors.

You can get the results of the annotation here [https://github.com/ehec-outbreak-crowdsourced/BGI-data-analysis/tree/master/strains/LB226692/annotations/era7bioinformatics](https://github.com/ehec-outbreak-crowdsourced/BGI-data-analysis/tree/master/strains/LB226692/annotations/era7bioinformatics)
