---
layout: post
title:  "Why I love Code Reviews"
date:   Sun Oct  3 17:17:06 IST 2021 
categories: codereviews
---

Doing code reviews is one of my favourite activities at work.
This post goes into reasons why I love doing code reviews and how
I do them.

## Why?
1. **Learning Opportunity**

    I consider code reviews as a great tool to learn new things.
    At any point of time, I might be working on a handful of things.
    But, my team or my company would have a large number of things being worked on.
    E.g. someone might be working on solving a concurreny problem,
    someone might be working on solving a cache related problem,
    someone else might be working on designing a database schema and so on.
    By doing code reviews, I might get a peek into what problems others are solving
    and have opportunity to learn from it so that when I get to work on similar
    problems, I am already familiar with how to solve them.

2. **Getting familiar with codebase**

    I have built familiarity with codebases by just doing code reviews.
    There are always parts of the codebase you wouldn't work on otherwise
    because of team boundaries, but code reviews allows you to explore
    those in a piecemeal fashion.
    It might be daunting otherwise to explore a large codebase since
    you would be lost on where to start from.
    But, a code review gives enough context to start exploring a new codebase.
    And, needless to say, having more familiarity with the codebase is
    biggest productivity boost you can give to yourself.

3. **Enhance problem solving skills**

    I look at a code review as a solution presented to a real problem.
    The author of the review faced a problem (which they have described in the description),
    they came up with a solution for it and raised a review for it.
    You are getting a chance to know about the problem and solution learning from
    someone else's effort - *what more do you need!*
 
4. **Learn coding standards & best practices**

    Every organization and team has their own set of coding standards and best practices
    being followed.
    Some of those practices would be documented in ramp up docs, but not all of them.
    Code reviews present an opportunity to know the *latest* set of guidelines being
    followed as you would generally either see the author following them or see other
    reviewers pointing them out.
    If you don't do any code reviews and straight go to raising reviews for your work,
    you will likely get lot of comments about code style/guidelines in your first
    set of work.

5. **Learn about non-functional practices**

    Typically, reviewers would comment about error handling, scale/performance issues etc.
    These are very hard to pick from documentation because these are generally very
    contextual.
    By doing code reviews, you can learn from other reviewers about how they go about
    identifying parts of the code where non-functional requirements are important to be
    considered.

Having looked at why's, let's look into how I approach doing code reviews.

## How?
1. **Which reviews I pick?**

    Anything which sounds interesting to me, irrespective of which part of organization it belongs to.
    If I come across a review and find its subject interesting, then I will review it thoroughly.
    Obviously, within team, I would pick any review which needs my attention irrespective
    of whether the subject is interesting or not.

2. **How do I review a diff in an unfamiliar codebase?**

    I might start slowly in an unfamiliar codebase, i.e. say start with a function.
    Look at the function body and its callers, understand them.
    May be in next review, I would be more comfortable reviewing an entire file.
    Note that the intent is to build my knowledge base and I am not trying to
    find mistakes in the diff, but rather using it as a way to gain knowledge in the
    unfamiliar codebase.
    I do not hesitate to ask questions on the review, those might be *naive* questions,
    but that's fine because if I don't get those clarified, I would not make progress
    in understanding the codebase.

3. **What is my intent in reviewing a diff?**

    I do not try to look out for bugs in the diff. That's a side-effect, not the intent.
    The intent is to understand the problem and solution presented in the diff, thus,
    I focus on whether
    - I am convinced of the solution for the given problem.
      If there are any bugs, they might get detected during this exercise.
    - Can I think of any alternate simpler solution?
    - Did I have difficulty in the understanding the solution? That's a sign of complexity
      which will lead to maintainence issues over time.
    - Is the diff consistent with the code style/practices? If not, then it will hamper
      readability over time.
