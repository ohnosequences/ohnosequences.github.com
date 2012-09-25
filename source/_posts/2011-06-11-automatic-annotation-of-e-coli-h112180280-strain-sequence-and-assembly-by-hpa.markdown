---
author: Raquel Tobes
comments: false
date: 2011-06-11 14:47:48
layout: post
slug: automatic-annotation-of-e-coli-h112180280-strain-sequence-and-assembly-by-hpa
title: Automatic annotation of E. coli H112180280 strain (sequence and assembly by
  HPA)
wordpress_id: 529
categories:
- ngs
tag:
- annotation
- E. coli
- EHEC
- genome
---

And right now we've finished the automatic annotation of the assembly of new strain that HPA ([Health Protection Agency UK](http://www.hpa.org.uk/))  made available yesterday (get the assembly file here [http://www.hpa-bioinformatics.org.uk/lgp/resource/454Scaffolds.fna](http://www.hpa-bioinformatics.org.uk/lgp/resource/454Scaffolds.fna))

Once more we've used [BG7](http://bg7.ohnosequences.com) and the same set of reference proteins (137,063 proteins in total):

- The representative Uniprot proteins corresponding to all Uniref90 clusters for all Escherichia coli proteins
- All Uniprot proteins from organisms including in their name the terms “EHEC” or “EAEC”
- All Uniprot proteins from bacteria that have in any Uniprot field the term “toxin”
- All Uniprot proteins from bacteria that have in any Uniprot field  “hemolysin”
- All the proteins from Salmonella typhi, Yersinia pestis and Shigella dysenteriae

#### Results

We've detected 5,916 genes

- 5,792 protein encoding genes
- 124 RNA genes

4,912 out of the 5,792 (84.80%) protein encoding genes have canonical start and stop codon and haven´t either frame-shifts or intragenic stop codons.

615 out of the 5,792 (10.61%) protein encoding genes have some frameshifts or intragenic stop codon in their sequences, probably caused by inherent technology errors.

You can get the results of the annotation here [https://github.com/ehec-outbreak-crowdsourced/BGI-data-analysis/tree/master/strains/H112180280/seqProject/HealthProtectionAgencyUK/annotations/era7bioinformatics/era7_HPA_H112180280_annotations](https://github.com/ehec-outbreak-crowdsourced/BGI-data-analysis/tree/master/strains/H112180280/seqProject/HealthProtectionAgencyUK/annotations/era7bioinformatics/era7_HPA_H112180280_annotations))
