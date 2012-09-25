---
author: Raquel Tobes
comments: false
date: 2011-06-10 21:06:54
layout: post
slug: hpa-announces-a-new-e-coli-genome-strain-h112180280-we-do-a-quick-visual-comparison-with-ty-2482
title: HPA announces a new E. coli genome. Strain H112180280. We do a quick & visual
  comparison with TY-2482
wordpress_id: 468
categories:
- ngs
tag:
- E. coli
- EHEC
- genome
---

HPA (Health Public Agency [http://www.hpa.org.uk/](http://www.hpa.org.uk/)) has just announced the sequence of a E. coli strain. the strain `H112180280`.

They have sequenced the strain with 454 and they've released

* sff files
* FASTA file with the scaffolds
* The annotation (done by Anthony Underwood) in GenBank format

Data available here [http://www.hpa-bioinformatics.org.uk/lgp/genomes](http://www.hpa-bioinformatics.org.uk/lgp/genomes)

They got

* 13 scaffolds
* 5405081 bp
* 88748 Ns (1.64%)

When we saw the data, the genome in only 13 scaffolds... we couldn't help aligning it with the other high-quality de novo assembly we have so far (the BGI version 2 of the TY-2482 strain)

How similar these two strains would be? 454 assembly could help scaffolding Illumina-IonTorrent contigs?

Here's what we got after aligning both genomes using Mauve ([http://gel.ahabs.wisc.edu/mauve/](http://gel.ahabs.wisc.edu/mauve/))

{% img /images/MAUVE_EHEC_UK454_vs_TY-2482.jpg %}

You can get the results of this Mauve analysis in the GitHub repository [https://github.com/ehec-outbreak-crowdsourced/BGI-data-analysis/tree/master/strains/comparativeAnalysis/era7bioinformatics/Mauve_H112180280_TY2482](https://github.com/ehec-outbreak-crowdsourced/BGI-data-analysis/tree/master/strains/comparativeAnalysis/era7bioinformatics/Mauve_H112180280_TY2482)

This quick analysis could give us some hints to reduce the number of contigs in both assemblies.

For example. Scaffolds 1, 2, 3 and 4 in the HPA assembly (the one above) could be merged in one contig (provided confirmation with PCR, Sanger sequence, etc).

And from the point of view of `TY-2482` assembly, even more contigs could be merged. See for instance the similarity region in green bottom left (red vertical lines indicate different contigs) . As well as the other similarity regions along the whole assembly (the pink, light green, turquoise and purple blocks)
