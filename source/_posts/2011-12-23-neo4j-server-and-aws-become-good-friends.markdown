---
author: Pablo Pareja
comments: false
date: 2011-12-23 14:14:50
layout: post
slug: neo4j-server-and-aws-become-good-friends
title: Neo4j Server and AWS become good friends!
wordpress_id: 629
categories:
- cloud computing
- ec2
- neo4j
tag:
- aws
- cloudformation
- ebs
- ec2
- neo4j
- neo4j-server
---

Hi everyone!

Christmas Eve is almost here and there's still time for a last-minute present. 
Thanks to **[CloudFormation](http://aws.amazon.com/cloudformation/)** and this template I'm about to show you, **[Neo4j Server](http://docs.neo4j.org/chunked/snapshot/server.html)** is now friends with **[AWS](http://aws.amazon.com)** _(Amazon Web Services)_ and together they bring you the opportunity of getting your own fresh Neo4j Server machine running in just a few clicks!

I created the github repository **[Neo4jAWS](https://github.com/pablopareja/Neo4jAWS)** where you can find all the files needed for this, _(which are actually not many but probably I'll be adding more tools for Neo4j and AWS integration soon)_.

Ok, so what does this CloudFormation template actually do?

1. It **launches an instance** in the availability zone you decide and with a type of your choice -_ you should also provide your key-pair_
2. **Attaches the volume including your Neo4j DB** to the new instance _(you must provide your volume ID)_
3. **Downloads** the **latest Neo4j stable release** (1.5) and **overwrites the server properties file with your own file**_(you have to provide a public URL where it should be available)_
4. It finally **starts the Neo4j Server** previously copying your DB folder under the data server folder (you have to provide the name of that folder as a parameter for the template)

And, what do you have to do?

1. Go to the **CloudFormation section**[ of the AWS console](https://console.aws.amazon.com/cloudformation/)
2. Click on 'Create New Stack' button
3. Download the [**template file**](https://github.com/pablopareja/Neo4jAWS/raw/master/Neo4jServerCloudFormationTemplate.txt) from the github repository and then select the option 'Upload a Template File' 
4. You should be seeing now the parameters window where you should enter the values: **KeyPairName**, **Neo4jDBFolder**, **AvailabilityZone**, **EBSVolumeID**, **ServerPropertiesFile **(this should be a public URL), and **InstanceType**
5. Once you've reviewed that everything's OK, just click next and wait for the stack to change to the **state CREATE_COMPLETE**

**UPDATE** --> Here you have the set of screenshots you should see in the process:

[![](http://blog.ohnosequences.com/wp-content/uploads/2011/12/CloudFormationCreateStackScreenShot.jpg)](http://blog.ohnosequences.com/2011/12/neo4j-server-and-aws-become-good-friends/cloudformationcreatestackscreenshot/)

CloudFormation tab: click on Create new stack button.

[![](http://blog.ohnosequences.com/wp-content/uploads/2011/12/Neo4jTemplateScreenshot2.jpg)](http://blog.ohnosequences.com/2011/12/neo4j-server-and-aws-become-good-friends/neo4jtemplatescreenshot2/)

Give a name to your stack and choose the option for uploading a file, browsing to the template file you previously downloaded from Neo4jAWS repository. Click 'Continue' then.

[![](http://blog.ohnosequences.com/wp-content/uploads/2011/12/Neo4jTemplateScreenshot3.jpg)](http://blog.ohnosequences.com/2011/12/neo4j-server-and-aws-become-good-friends/neo4jtemplatescreenshot3/)

You should be seeing something like this by now. It's time to provide all the parameters!
When you're done, click con 'Continue' after reviewing the values and just wait for it to change to state 'CREATE_COMPLETE' ;)

If nothing weird happens, you should be able to see the WebAdmin in your browser typing as URL the public IP given as output of the stack plus the port you specified in your neo4j-server.properties file.

> Beware that the template opens by default the port 7474 for communicating with the Server, if you want to use another port number for any reason, you should change the SecurityGroup manually

As always, please don't hesitate to give any kind of feedback or suggestion you may have, as well as pointing to possible issues/bugs _(you can use github issues in the repository for that)_.

Happy Holidays!

[**@pablopareja**](http://www.twitter.com/pablopareja)
