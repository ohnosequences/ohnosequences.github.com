---
author: Raquel Tobes
comments: false
date: 2011-06-11 11:04:16
layout: post
slug: missed-region-in-ehec
title: 'Missed region in EHEC '
wordpress_id: 505
categories:
- ngs
tag:
- E. coli
- EAEC
- EHEC
- Escherichia coli
- European outbreak
- genome annotation
- HUS
- pathogenicity
- secretion system
- virulence
---

David Studholme detected a missed region in EHEC TY-2482-v1 ([http://www.genomic.org.uk/blog/?p=523](http://www.genomic.org.uk/blog/?p=523)) assembly that was also absent in TY-2482-v2.

This is the region with type VI secretion system surrounding the detected by Studholme missed region:

``` yaml
contig  Era7 geneID ini Era7 tags Protein name
106 108864  2776  secretion system VI Putative uncharacterized protein
106 83591 6193  secretion system VI Putative uncharacterized protein
106 85611 6792  secretion system VI Putative uncharacterized protein
106 107028  7091  secretion system VI Putative type VI secretion protein
106 79778 8549  secretion system VI Putative uncharacterized protein
106 58451 9104  secretion system VI Putative uncharacterized protein
106 108747  10185 secretion system VI Putative uncharacterized protein
106 60210 10494 secretion system VI Putative uncharacterized protein
106 106509  10965 secretion system VI Putative uncharacterized protein
106 75277 12958 secretion system VI Putative type VI secretion protein
106 99465 13930 secretion system VI Putative uncharacterized protein
106 92338 15696 secretion system VI Putative uncharacterized protein
106 94122 16111 secretion system VI Putative uncharacterized protein
106 81926 16627 secretion system VI Putative type VI secretion protein
106 95285 18115 secretion system VI Putative type VI secretion protein
106 102409  18594 secretion system VI Putative type VI secretion protein
106 11998 19032   Transposase
```




contig


Era7 geneID


ini


Era7 tags


Protein name






106


108864


2776


secretion system VI


Putative   uncharacterized protein






106


83591


6193


secretion system VI


Putative   uncharacterized protein






106


85611


6792


secretion system VI


Putative   uncharacterized protein






106


107028


7091


secretion system VI


Putative type VI   secretion protein






106


79778


8549


secretion system VI


Putative   uncharacterized protein






106


58451


9104


secretion system VI


Putative   uncharacterized protein






106


108747


10185


secretion system VI


Putative   uncharacterized protein






106


60210


10494


secretion system VI


Putative   uncharacterized protein






106


106509


10965


secretion system VI


Putative   uncharacterized protein






106


75277


12958


secretion system VI


Putative type VI   secretion protein






106


99465


13930


secretion system VI


Putative   uncharacterized protein






106


92338


15696


secretion system VI


Putative   uncharacterized protein






106


94122


16111


secretion system VI


Putative   uncharacterized protein






106


81926


16627


secretion system VI


Putative type VI   secretion protein






106


95285


18115


secretion system VI


Putative type VI   secretion protein






106


102409


18594


secretion system VI


Putative type VI   secretion protein






106


11998


19032




Transposase




.

These are the BLASTN results for that region of  BGI_assembly_v2 vs EC 55989:

```
query id  subject id  % identity  align len q. start  q. end  s. start  s. end  evalue
106 gi|218350208  99.88 18937 1 18937 3369005 3387941 0.0
106 gi|218350208  100.00  3964  18923 22886 3389265 3393228 0.0
106 gi|218350208  99.92 3832  22885 26716 3397877 3401707 0.0
106 gi|218350208  99.84 2455  26837 29291 3427391 3429843 0.0
```





query id


subject id


% identity


align len


q. start


q. end


s. start


s. end


evalue






106


gi|218350208


99.88


18937


1


18937


3369005


3387941


0.0






106


gi|218350208


100.00


3964


18923


22886


3389265


3393228


0.0






106


gi|218350208


99.92


3832


22885


26716


3397877


3401707


0.0






106


gi|218350208


99.84


2455


26837


29291


3427391


3429843


0.0




.

These are the EC 55989 genes missed in BGI assembly v2:

```
hypothetical protein EC55989_3318 3401747 3402160 EC55989_3318
hypothetical protein EC55989_3319 3402305 3402739 EC55989_3319
hypothetical protein EC55989_3320 3402739 3403275 EC55989_3320
hypothetical protein EC55989_3321 3403256 3404356 EC55989_3321
hypothetical protein EC55989_3322 3404311 3406074 EC55989_3322
hypothetical protein; putative membrane protein 3406082 3406879 EC55989_3323
hypothetical protein EC55989_3324 3406776 3408374 EC55989_3324
hypothetical protein EC55989_3325 3408374 3411763 EC55989_3325
hypothetical protein EC55989_3326 3411756 3412904 EC55989_3326
hypothetical protein EC55989_3327 3412908 3413174 EC55989_3327
Conserved hypothetical protein. Putative exported protein 3413206 3413883 EC55989_3328
conserved hypothetical protein; putative exported protein 3414027 3414704 EC55989_3329
hypothetical protein EC55989_3330 3414724 3416406 EC55989_3330
hypothetical protein EC55989_3331 3416403 3418928 EC55989_3331
hypothetical protein EC55989_3333 3419451 3420026 EC55989_3333
putative chaperone clpB 3420014 3422680 EC55989_3334
hypothetical protein EC55989_3335 3422840 3423331 EC55989_3335
hypothetical protein EC55989_3336 3423337 3425163 EC55989_3336
hypothetical protein EC55989_3337 3425070 3425789 EC55989_3337
hypothetical protein EC55989_3338 3425720 3427057 EC55989_3338
hypothetical protein EC55989_3339 3427073 3428617 EC55989_3339
```




hypothetical   protein EC55989_3318


3401747


3402160


EC55989_3318






hypothetical protein EC55989_3319


3402305


3402739


EC55989_3319






hypothetical protein EC55989_3320


3402739


3403275


EC55989_3320






hypothetical protein EC55989_3321


3403256


3404356


EC55989_3321






hypothetical protein EC55989_3322


3404311


3406074


EC55989_3322






hypothetical protein; putative membrane protein


3406082


3406879


EC55989_3323






hypothetical protein EC55989_3324


3406776


3408374


EC55989_3324






hypothetical protein EC55989_3325


3408374


3411763


EC55989_3325






hypothetical protein EC55989_3326


3411756


3412904


EC55989_3326






hypothetical protein EC55989_3327


3412908


3413174


EC55989_3327






Conserved hypothetical protein. Putative exported protein


3413206


3413883


EC55989_3328






conserved hypothetical protein; putative exported protein


3414027


3414704


EC55989_3329






hypothetical protein EC55989_3330


3414724


3416406


EC55989_3330






hypothetical protein EC55989_3331


3416403


3418928


EC55989_3331






hypothetical protein EC55989_3333


3419451


3420026


EC55989_3333






putative chaperone clpB


3420014


3422680


EC55989_3334






hypothetical protein EC55989_3335


3422840


3423331


EC55989_3335






hypothetical protein EC55989_3336


3423337


3425163


EC55989_3336






hypothetical protein EC55989_3337


3425070


3425789


EC55989_3337






hypothetical protein EC55989_3338


3425720


3427057


EC55989_3338






hypothetical protein EC55989_3339


3427073


3428617


EC55989_3339




.

We will review this region in the new annotations that we will do for the two new available genome sequences contributed by HPA and BGI.
