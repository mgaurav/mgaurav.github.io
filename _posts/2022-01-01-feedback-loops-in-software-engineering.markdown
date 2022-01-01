---
layout: post
title:  "Feedback Loops in Software Engineering"
date:   Sat Jan  1 14:13:39 IST 2022
---

Feedback loops are a useful design pattern in control systems.
Feedback loops take the system output into consideration, which enables the system to adjust its performance to meet a desired output response.[^1]

In Software engineering as well, there are a number of feedback loops which we can utilize.

### 1. Testing
Unit testing is the first feedback loop we have on the design and complexity of our production code.
A test is the first client-side usage of the code we are writing.
If it is harder to write test, then it will be harder to use the code by clients.
That's a first feedback to us that we can improve the interface.

If we haven't paid attention to separation of concerns in the production code,
then test itself will be complex which is a sign to improve the production code as the test code should be dead simple
as John Jagger said
> Cyclomatic Complexity of tests should be one.

### 2. Modularization
Our discipline has evolved to bundle up functionalities in smaller modules
and have dependencies between modules for re-use.
There are build systems like Bazel which allow to define modules and their inter-dependencies.
Modules provide a feedback on coupling and cohesion in how we organize our codebase.

If we include 2 distinct concepts (which evolve independently) in a single module,
then we are messing up your dependency graph.
If any one of those changes, all usages of either will get re-compiled and re-deployed.
That's an unnecessary increase in our build times and deployment times.

We had a feedback about those as soon as we modified the module definition or added
module dependencies. Listen to such feedback to improve the organization of the codebase.

### 3. Code Reviews
Code reviews are the first feedback on readability of our code. This is the feedback
which would be most useful to address to make lives of future developers (which includes author as well)
easier.


We need to listen to our feedback loops as we develop software.
They are telling us where to improve, but only if we listen.
We should utilize the fastest feedback loop as much as possible.

[^1]: https://en.wikibooks.org/wiki/Control_Systems/Feedback_Loops
