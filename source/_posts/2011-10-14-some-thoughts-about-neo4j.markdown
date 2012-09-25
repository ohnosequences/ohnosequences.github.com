---
author: Pablo Pareja
comments: false
date: 2011-10-14 18:33:15
layout: post
slug: some-thoughts-about-neo4j
title: Some thoughts about Neo4j
wordpress_id: 535
categories:
- neo4j
tag:
- database
- graph-databases
---

Today I found an [interesting discussion](http://neo4j.org/forums/#nabble-td730422) in Neo4j user list and found myself in the mood of writing a couple of related thoughts I have had in mind the last months.

Here they are: (the titles are taken from the [guidelines for building your domain model](http://wiki.neo4j.org/content/Guidelines_for_Building_a_Neo4j_Application))

### Use reference and subreference nodes to organize entry points

In principle I don't agree with this. Well, I do in theory _(it actually is how I implemented things in the beginning)_. However in one of my projects, where I'm dealing with huge amounts of relationships, reference and subreference nodes become supernodes which in turn are a very problematic bottleneck in most traversals; (this is due to the lack of a natively implemented system for discerning between relationships with different types, I opened this issue about this [here](https://github.com/neo4j/community/issues/19)). While this is solved, I'm always tempted/forced to start using indexes instead of relationships, but then I wonder how different things are in the end compared to other not graph-based DB systems !??

### Use relationships types appropiately

I'm gonna be frank with this, I never understood why there're mandatory relationships types but not mandatory nodes types!? 
It just doesn't make any sense for me. I can understand that this could bring some trouble depending on implementation decisions taken at core level but then, why doing this only half way? It'd have been better having no restriction for either nodes or relationships than how things are now. 

With all this having been said, I still find Neo4j a very promising DB in the near future and I'm really happy to use it in a lot of different projects/use-cases; however I think the way for it to get better each day is not keeping saying how cool it is but actually pointing at the weak spots it may have.

Pablo Pareja
