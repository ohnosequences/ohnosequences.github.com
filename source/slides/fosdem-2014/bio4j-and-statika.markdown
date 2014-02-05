---
layout: page
title: "Bio4j + Statika: Managing module dependencies on the type level"
comments: false
sharing: true
footer: true
---

Slides of ["Bio4j + Statika: Managing module dependencies on the type level"](https://fosdem.org/2014/schedule/event/graphdevroom_bio4j_1/) talk by [Alexey Alekhin](/aalekhin) on the [FOSDEM 2014](https://fosdem.org/2014/) conference.

<script async class="speakerdeck-embed" data-id="cb7e6b7070a60131f1195e173af38d18" data-ratio="1.29456384323641" src="//speakerdeck.com/assets/embed.js"></script>
  
Bio4j bioinformatics graph database is modular and customizable, allowing you to import just the data you are interested in. There exist, though, dependencies among these resources that must be taken into account and that's where Statika enters the picture; a set of Scala libraries which allows you to declare dependencies between components of any modular system and track their correctness using Scala type system. Thanks to this, it's possible now to deploy only selected components of the integrated data sets, with Amazon Web Services deployments on hardware specifically configured for them.
