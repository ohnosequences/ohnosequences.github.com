---
author: Raquel Tobes
comments: false
date: 2011-06-07 23:58:28
layout: post
slug: automatic-annotation-of-the-second-bgi-assembly-of-e-coli-ty-2482-genome
title: Automatic annotation of the second BGI assembly of E. coli TY-2482 genome
wordpress_id: 402
categories:
- ngs
tag:
- bacterial genome
- EHEC
- Escherichia coli
---

We've just finished the automatic annotation of the second BGI assembly of the E. coli `TY-2482` genome ([https://github.com/ehec-outbreak-crowdsourced/BGI-data-analysis/blob/master/strains/TY2482/assemblies/BGI/Escherichia_coli_TY-2482.contig.20110606.fa.gz](https://github.com/ehec-outbreak-crowdsourced/BGI-data-analysis/blob/master/strains/TY2482/assemblies/BGI/Escherichia_coli_TY-2482.contig.20110606.fa.gz)). In this case BGI combined `200x` of Illumina single-end reads and `12x` of Ion Torrent. They have done a de novo assembly with Newbler v. 2.0.00.22, Soapdenovo v. 1.06 and AMOS minimus2 v. 1.59 getting finally 513 contigs.

In this case we have used the same set of reference proteins as we used in the annotation of the Nick Loman's assembly of the same isolate, `TY-2482` (see annotation in [this post](http://blog.ohnosequences.com/2011/06/275/)).

This set has 137,063 proteins and includes:
	
* The representative Uniprot proteins corresponding to all Uniref90 clusters for all Escherichia coli proteins
* All Uniprot proteins from organisms including in their name the terms
“EHEC” or “EAEC”
* All Uniprot proteins from bacteria that have in any Uniprot field the term “toxin”	
* All Uniprot proteins from bacteria that have in any Uniprot field  “hemolysin”
* All the proteins from _Salmonella typhi, Yersinia pestis_ and _Shigella dysenteriae_

#### Results

We have predicted 5,982 genes
	
* 5,849 protein encoding genes	
* 133 RNA genes (rRNA and tRNA)

4,797 out of the 5,849 (82.01%) protein encoding genes have canonical start and stop codon and haven´t either frame-shifts or intragenic stop codons.

658 out of the 5,849 (11.24%) protein encoding genes have some frameshifts or intragenic stop codon in their sequences.

You can get the results here [https://github.com/ehec-outbreak-crowdsourced/BGI-data-analysis/tree/master/strains/TY2482/annotations/era7bioinformatics/BGI_V2](https://github.com/ehec-outbreak-crowdsourced/BGI-data-analysis/tree/master/strains/TY2482/annotations/era7bioinformatics/BGI_V2)

We have just had time to take a quick glance at these results but they look promising. We'll come back with more results on this genome, that's for sure :)
