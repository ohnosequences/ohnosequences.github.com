---
author: Raquel Tobes
comments: false
date: 2011-06-11 14:22:47
layout: post
slug: automatic-annotation-of-bgi-v3-assembly-of-e-coli-ty-2482-genome
title: Automatic annotation of BGI V3 assembly of E. coli TY-2482 genome
wordpress_id: 527
categories:
- ngs
tag:
- annotation
- E. coli
- EHEC
- genome
---

We've finished the automatic annotation of the third BGI assembly of the E. coli TY-2482 strain genome (get the assembly file here ftp://ftp.genomics.org.cn/pub/Ecoli_TY-2482/Escherichia_coli_TY-2482.scaffold.20110610.fa.gz)

As in the other annotations we've done so far we used[ BG7 system](http://www.slideshare.net/marina_manrique/bg7-a-new-system-for-bacterial-genome-annotation-designed-for-ngs-data) to annotate the genome. And we have used the same set of reference proteins (137,063 proteins in total):

- The representative Uniprot proteins corresponding to all Uniref90 clusters for all Escherichia coli proteins
- All Uniprot proteins from organisms including in their name the terms “EHEC” or “EAEC”
- All Uniprot proteins from bacteria that have in any Uniprot field the term “toxin”
- All Uniprot proteins from bacteria that have in any Uniprot field  “hemolysin”
- All the proteins from Salmonella typhi, Yersinia pestis and Shigella dysenteriae

#### Results

We've detected 5,936 genes

- 5,806 protein encoding genes
- 130 RNA genes

4,881 out of the 5,806 (84.06%) protein encoding genes have canonical start and stop codon and haven´t either frame-shifts or intragenic stop codons.

533 out of the 5,806 (9.18%) protein encoding genes have some frameshifts or intragenic stop codon in their sequences, probably caused by inherent technology errors.

You can get the results of the annotation here [https://github.com/ehec-outbreak-crowdsourced/BGI-data-analysis/tree/master/strains/TY2482/seqProject/BGI/annotations/era7bioinformatics/BGI_V3](https://github.com/ehec-outbreak-crowdsourced/BGI-data-analysis/tree/master/strains/TY2482/seqProject/BGI/annotations/era7bioinformatics/BGI_V3)
