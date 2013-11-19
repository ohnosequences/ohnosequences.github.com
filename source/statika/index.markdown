---
layout: page
title: "Statika"
comments: false
sharing: true
footer: true
---

> managing dependencies on the type-level

Statika is a set of Scala libraries, which allows you to declare dependencies between components of any modular system and track their correctness using Scala type system. 

This allows one to create configurations of modules, for example, for applying it to a set of Amazon EC2 computation instances, being _statically_ insured, that it won't fail because of dependencies resolution issues.


### Components of Statika

The key components of the project are

* [statika](https://github.com/ohnosequences/statika/) — the core library defining the most abstract concepts;
* [aws-statika](https://github.com/ohnosequences/aws-statika/) — an extension of the abstract library with the things related to [Amazon Web Services (AWS)](http://aws.amazon.com/);
* [sbt-statika](https://github.com/ohnosequences/sbt-statika/) — an sbt plugin, which standardizes the project settings for statika bundles and distributions within one Amazon account;

#### Convenience tools:

* [statika-bundle.g8](https://github.com/ohnosequences/statika-bundle.g8) — giter8 template of a project for a new statika bundle;
* [statika-cli](https://github.com/ohnosequences/statika-cli/) — a command line tool for using this template (because giter8 is not enough), and for _applying_ (i.e. deploying) existing bundles from the command line;

#### Examples:

* [statika github org](https://github.com/ohnosequences/statika/) contains all our public bundles (mostly bioinformatics tools);
* [statika-distributions](https://github.com/ohnosequences/statika-distributions/) — a repository with example distributions. There is one distribution which contains all existing public bundles.
* [amazon-linux-ami](https://github.com/ohnosequences/amazon-linux-ami/) — implementation of AMI (Amazon Machine Image) abstraction from aws-statika for the official Amazon Linux AMI.

#### Documentation

Each sub-project has documentation in its github repository, see the links above.
