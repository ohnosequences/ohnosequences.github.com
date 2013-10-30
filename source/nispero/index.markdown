---
layout: page
title: ""
comments: false
sharing: true
footer: true
---

![nispero](nispero.png)

## what?

*Nispero* is distributive system that can solve a some amount of tasks using Amazon EC2 computation capacity.

## why?

Amazon EC2 offer you to use their computation capacity, to solve possible very complex computation tasks. *Nispero* allows you
construct computations networks without complex configuration.

## how?
To use *nispero* first of all you need Amazon AWS Account. *Nispero* will create for you infrastructure for executing your tasks. Take a look at these documents:

* [nispero overview](doc/overview.md)
* [nispero architecture](doc/architecture.md)

to get basic view of it.

To start work with *nispero* read [nispero usage](doc/usage.md) document.

### additional resources:

* [nispero configuration](doc/config.md)

* [script executor](doc/script-executor.md)

* [SQS visibility timeout](doc/visibality-timeout.md)

* [nispero console](doc/console.md)

## nispero design notes
Key property of *nispero* that is doesn't contains any stateful things,
input tasks, result, *workers* amount -- all these data stored in Amazon AWS  resources such as queues and S3.
It makes *nispero* very safe and fault tolerant, in case of fails of *worker* and even *manager* instances you don't lost
any data.
Another important feature of *nispero* that it use only auto scaling group for launching instances.

[nispero REST API](doc/devel/rest-api.md)



