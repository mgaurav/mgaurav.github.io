---
layout: post
title:  "What is a good software product?"
date:   2018-10-15 22:45:35 +0530
categories: software-engineering
---
How do you classify a good software engineering product? How often do we see teams having dependency
on a single/few engineer/s for maintainence or enhancement of a software product? What happens to that
product when that engineer leaves? How often do we see new engineers struggle to maintain an
existing product? How should software deteriorate? Should it stop working suddenly one fine day?

Let's take an analogy with other engineering fields. Do we have the dependency on the original engineers
of the building to fix up any issues in the building in which we live? Do we not expect any other
engineer to quickly understand the issue and fix it? Are we okay with our buildings collapsing one fine day?
Do we not expect any issues to be isolated and leaving other parts/components working as expected?

In my opinion, a good software engineering product should have similar qualities as that of other
good engineering products. It should be
* easier to maintain
* easier to extend
* easier to reason about
* silent when it works correctly, noisy when it doesn't
* easier to diagnose when it doesn't work correctly
* a fault in one part should be locally isolated 
* shouldn't require regular maintainence, and if it does then that should be part of product documentation,
  and it should be noisy if maintainence is missed.
