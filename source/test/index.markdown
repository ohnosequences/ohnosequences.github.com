---
layout: page
title: "legal issues"
comments: false
sharing: true
footer: true
---

## contributions ##

We need to have a contribution policy which 

1. doesn't create any kind of _legal_ issues for us
2. does not get in the way of contributions/contributors

As our license of choice is [AGPLv3](http://www.gnu.org/licenses/agpl-3.0.html), and we don't believe in dual licensing, there's an easy path for us: a **DCO** plus `git -s` feature (`-s` for _signed-off-by_). 

### DCO with signed commits ###

This schema makes submitting pull requests (contributions) a completely unobtrusive process: from the contributor side, he just needs to add the `-s` to his commit/s. From our side, we don't need to manage signed CLAs (Contributor License Agreements) and whatnot: we just reproduce the standard DCO text on the readme, together with whatever contribution guidelines/instructions are needed. For completeness, the DCO text:

```
 Developer's Certificate of Origin 1.1

        By making a contribution to this project, I certify that:

        (a) The contribution was created in whole or in part by me and I
            have the right to submit it under the open source license
            indicated in the file; or

        (b) The contribution is based upon previous work that, to the best
            of my knowledge, is covered under an appropriate open source
            license and I have the right under that license to submit that
            work with modifications, whether created in whole or in part
            by me, under the same open source license (unless I am
            permitted to submit under a different license), as indicated
            in the file; or

        (c) The contribution was provided directly to me by some other
            person who certified (a), (b) or (c) and I have not modified
            it.

        (d) I understand and agree that this project and the contribution
            are public and that a record of the contribution (including all
            personal information I submit with it, including my sign-off) is
            maintained indefinitely and may be redistributed consistent with
            this project or the open source license(s) involved.

```

The only thing I would add here is that the license we use is AGPLv3 _or later_.

#### practical contribution management ####

We need to have something: which branch to use for submitting pull requests (`develop`, I guess), tests, etc. _But_, we need to first achieve this _for our own work_.

#### legal implications ####

Basically, as far as I can understand, this will be more than enough for keeping us safe from copyright/IP rights infringement suits and related stuff. 

Concerning **dual licensing**, this is about the strongest statement one can make about being **opposed** to it: it makes pretty hard to dual-license anything _including_ the contributions (you could obviously still do whatever you want with _your_ codebase); doing it would boil down to getting an agreement to do so from every contributor. Signing off commits makes this _possible_, by the way.

**refs:**

1. [Bradley Kuhn - Project Harmony Considered Harmful](http://ebb.org/bkuhn/blog/2011/07/07/harmony-harmful.html)
2. [Richard Fontana - Contribution Policies for Open Source Projects](http://ref.fedorapeople.org/fontana-linuxcon.html)

### sample math ###

Let's test if $f = g_1 \circ \beta$ inline math works. It does! Now

$$
U \colon \mathbf{Cat} / C \to \mathbf{Cat}
$$

_yeah!_ now, test AMSMath:

$$
\chi_a \colon \mathcal{C}^{\infty}_{\mathbb{R}} \to \mathbb{R}
$$

It's nice that math displays ok, I _love_ [MathJax](http://mathjax.org).


