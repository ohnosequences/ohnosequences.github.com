---
layout: page
title: "credentials"
sharing: true
footer: true
---

after reading _lots_ of security whitepapers, blog posts, technical notes and such, I've arrived at the conclusion that

> there's no sane way of managing AWS credentials, as of now

We need to live with that; the lesser evil I'm proposing is a combination of CF templates, IAM and S3. In essence:

1. store credentials as **private** S3 objects, plain-text
2. retrieve them via CF authenticated resources, providing them to the instance/s at boot time
3. use IAM users with the only privilege of _launching_ those templates

Let's go into detail a bit.

## S3 storage ##

We will scope credentials by user, with a common file layout. Basically, something like

- `$authBucket/$user/cert.pem`
- `$authBucket/$user/pk.pem`
- `$authBucket/$user/credentials.pem`

This bucket will be kept **private**. Again, **private**. This is important.

In principle, we will do this manually. The important thing is that it is straightforward to automate if needed.

## CF retrieve ##

CF has a more or less recent feature which lets you download to a file/folder the contents of a _private_ S3 object, by providing an IAM user with the needed rights to do so. This eases a lot of the pain involved in providing instances with credentials at boot time, but it ties you to CF. Our approach will be to make as little use as possible of CF, wrapping this functionality into a minimal API. 

Due to the quirks of CF S3 support, we need to grant the IAM user access to _a whole bucket_. 

## boot time conf ##

There's a little bit of work to do with this at boot time, such as setting env-vars. For simplicity, we will do this through shell scripts. 

## features ##

This approach has a number of important benefits:

1. _easy key rotation procedure_ at least for newly launched instances; but that's not a problem for us.
2. _add/remove users_ this is straightforward, and it could even be kept at compile time.
3. _separate launch from key management_ those launching instances need not have access to the keys provided.
4. _extensible_ it is easy to use this very same mechanism to provide _other_ credentials (github, for example)


## references ##

- [Operational Checklists for AWS](http://d36cz9buwru1tt.cloudfront.net/AWS_Operational_Checklists.pdf)
- [AWS Security Best Practices](http://d36cz9buwru1tt.cloudfront.net/Whitepaper_Security_Best_Practices_2010.pdf)
- [Storing your AWS Credentials on an EBS Snapshot securely](http://shlomoswidler.com/2010/07/storing-aws-credentials-on-an-ebs-snapshot-securely.html)
- [How to keep your AWS Credentials on an EC2 instance securely](http://shlomoswidler.com/2009/08/how-to-keep-your-aws-credentials-on-ec2.html)

## sample scala code ##

this bit is extracted from **doBLAST**, a pretty cool project:

``` scala
object BLASTN {
  
  // implicit ev for OptionsOf#λ[L] implies L list of BLASTN option values
  type OptionsOf = Keys[Options]

  def Options[L <: HList : OptionsOf#λ](l: L) = l
}
```


