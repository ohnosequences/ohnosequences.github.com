---
comments: false
author: Pablo Pareja
date: 2011-03-25 17:29:11
layout: post
slug: using-bio4j-go-tools-to-get-the-go-annotations-of-a-set-of-uniprot-proteins-2
title: Using Bio4j Go Tools to get the GO annotations of a set of Uniprot proteins
wordpress_id: 198
categories:
- bio4j
tag:
- go
---

We have recently launched a first version of Bio4j Go Tools: an [AIR application ](https://github.com/bio4j/Bio4jGoTools/blob/master/releases/Bio4jGoTools.air)that allows the user to perform different kinds of GO Analysis using [Bio4j ](bio4j.com)as back-end.
More info about the tool in [this post](http://blog.bio4j.com/?p=9) of [Bio4j blog](http://blog.bio4j.com/)

{% img /images/Bio4jJPG.jpg %}

So far you can do the following:

1. Get the GO annotations of a set of proteins. All the GO annotations belonging to the three different GO ontologies (Molecular function, Biological process y Cellular component) are provided separately
2. "Perform" a GO Slim analysis

Using this tool for 1) is pretty easy. You just have to enter in the text field the Uniprot IDs (protein accessions) of the set of proteins of interest and select which kind of separator you are using (enter, tab, whitespace...). Then click on "Get results", select the location where the result file will be downloaded and wait until the "File downloaded!" message appears.

New charts utilities are coming soon. By now, you can import the XML result file into an Excel file and create the charts there. The following ones are an example of the charts you can make. They represent the GO annotations of all the _Helicobacter pylori_ proteins (11,934 proteins), only those GO terms that appear 20 times or more in the set of proteins are depicted.

{% img /images/HPylori_BP2.jpg %}

{% img /images/HPylori_CC.jpg %}

{% img /images/HPylori_MF.jpg) %}

How to use this tool to perform GOSlim analysis in upcoming posts...
