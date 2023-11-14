---
layout: post
title:  "Feedback Loops in Software Engineering"
date:   Tue Nov 14 19:34:31 IST 2023
---

For a long time in my career, I have disliked Agile methodology (at least the way "Agile" was taught to me).
My first introduction to Agile was a 2-day training we have been put through at my organization.
One thing which I took positively from that training is that we should deliver value to the customers faster
(it was explained by taking an example of a pipeline - kind of like a factory pipeline).
I also remember being a bit disinterested in the training since the trainers didn't seem to be working software
professionals, they were training on Agile but they were not writing any software, thus, I had a doubt whether
things they are teaching makes sense in my team's context. The only material thing which changed after training
in my team was that we started creating our jira tickets with the prefix "As a user, I would ...".
This grew my disinterest in Agile further as nothing improved in the team after the training.
In hindsight, the reason things didn't improve was because team didn't really change their working style and
never adopted the Agile mindset. I was of the opinion that Agile way works for teams which are doing "known"
things which can be accurately estimated, and who doesn’t like to believe that the problem they are working
on is novel and no one has solved it before  . So, discussions in our team always used to discredit Agile that
it won't work in our team since there are so many unknowns in the problems we are working on.

Fast forward few years, I was told that team should spend time in going through jira backlog of 2 years back
to clean it since “Agile” way of working requires to have a healthy backlog
(don't get me wrong, I do agree that teams should have a maintainable jira backlog,
but I was not convinced that it is right investment to go through 2 years old issues and clean them up).
In my opinion, all of us have been accustomed to create a jira ticket to put an end to a conversation and
often we have no intent to pick those jiras, and that's why jira backlog keeps growing - which is another
thing I want to solve in my future teams.

Here is a dictionary definition of agile for reference and a question for reader: 
**are you able to move quickly and easily in your project execution by following various “Agile” ceremonies? **

![image](https://github.com/mgaurav/mgaurav.github.io/assets/1040514/ecaf806a-1661-44c5-bd18-d0822e8ae0e7)

At that time, I finally decided to read [Agile Manifesto](https://agilemanifesto.org/) to know whether it
really says anything about Jira backlogs and/or estimations, various ceremonies we follow.
The Agile Manifesto is surprisingly very short, it's based on just 12 principles.
There is hardly anything in the 12 principles which I can disagree with as an engineer.

Surprising, All the "Agile" ceremonies we follow (Story point estimates, Sprint Planning, Stand ups) are
missing from the Agile manifesto - which is not to say that they are not important, but it signifies that
just having these ceremonies doesn't qualify any team to say they practice Agile.
And, how many times we have individuals and teams saying that they follow Agile when most of them have
never read Agile Manifesto (I didn't read for the 3-4 years while we were doing "Agile" so to say).   

# Agile Principles

I will try to list down Agile principles and my commentary on them based on my understanding with some examples.
I am still learning about them, so I am sure I might have misunderstood some of them.

## 1. Our highest priority is to satisfy the customer through early and continuous delivery of valuable software.

Satisfying the customer and continuous delivery are key terms for me. 

If each engineer thinks about what is the customer need they are solving at any point of time,
it will give them a good sense of purpose in their work.
Customer could mean different for different teams - for a feature team, it means company customers,
for a Platform team, it means other engineers in the company. 

Continuous delivery means software is delivered continuously to the customers to satisfy their needs.
This in my opinion requires a mindset shift in most of the teams.
We often think of delivering customer needs in a time span of 3-6 months.
We should strive to deliver value every week/sprint and doing that requires how we approach execution of
any project such that uses can get their hands on the deliverable faster.
I understand that doing so in a platform team is easier than a feature team since platform team customers
are more amenable. However, for a feature team as well, often it might be possible to treat PM, SE as
good proxy to customers to deliver incremental value.

## 2. Welcome changing requirements, even late in development. Agile processes harness change for the customer's competitive advantage.

Change is the only constant as a saying goes. It is seen from time to time in any feature development that
requirements do change over time for various reasons - more domain knowledge, better understanding of problem space,
better understanding of solution space, feedback from various stakeholders, competitive products etc.
Trying to resist changing requirements is futile, as a delivered software which is not being used is of no value.
Thus, welcoming changing requirements is the only possible reaction. However, this often seems opposing to
predictability. Often in the name of predictability, teams are required to commit to a release date for a feature
3-6 months in advance. That requires team to attempt to finalize requirements very upfront and thus, they are
hesitant to change them or if they are forced to change them then it leads to issues like burnout.

## 3. Deliver working software frequently, from a couple of weeks to a couple of months, with a preference to the shorter timescale.

This is related to Continuous Delivery point. We should strive to break down feature development in units such that
smaller units can be delivered incrementally.

## 4. Business people and developers must work together daily throughout the project.

One of the mistakes I did early in my career was to treat PRD as a holy document.
I never questioned or challenged PRD in my early days.

## 5. Build projects around motivated individuals. Give them the environment and support they need, and trust them to get the job done.

This one is probably the only trait which I was good at from early days.
For as long as I can remember, seeing people's growth gave me joy.
Giving people freedom and trust is something which I truly believe in, and have been practicing for a long time.

## 6. The most efficient and effective method of conveying information to and within a development team is face-to-face conversation.

This one is likely the only principle which I don't fully agree to. I do agree face to face conversations
are easier to convey information, but if people have right accountability mindset, other forms of communication
can also be effective I think.

## 7. Working software is the primary measure of progress.

This one is a bit nuanced in my opinion. When do you call a software working - is it when it works on your machine,
is it when you can have automated tests for it, is it when an end user can use the software. For a long time,
my measure of progress has been that I have committed the change in master with appropriate unit tests.
However, if viewed from a left shift mindset, I realize that this definition is not sufficient. 
To make the software working, you need to integrate it with other components (e.g. UI, APIs etc.) -
this again shows the limited world view we often have. This changed the way I used to think about project execution,
suddenly the checkpoints which deliver a partial value seemed much better to me than to have full value delivered at
the end of project completion. This introduced an element of art in project execution - how do you plan the work
such that you are able to deliver incremental value to the customers at frequent and small intervals.

## 8. Agile processes promote sustainable development. The sponsors, developers, and users should be able to maintain a constant pace indefinitely.

Sustainable development is what I have constantly strived to achieve for myself and my team members.
I consider myself fortunate to have read [Opportunistic Refactoring](https://martinfowler.com/bliki/OpportunisticRefactoring.html) article by Martin Fowler very early in my career,
and have continuously followed it since then. This allowed me to not succumb to ever growing tech debts.
However, I can't say that me or my teams have been able to maintain constant pace indefinitely.
This is something which I probably don't understand well yet, so continuously trying to improve on it.

## 9. Continuous attention to technical excellence and good design enhances agility.

It will be impossible for anyone to disagree with this statement. If we get our key design decisions right,
then it will save us time to revisit those later. This is not to say that we will never make bad design decisions,
but being more knowledgeable helps avoid costly mistakes (see [Tech Debt Quadrant](https://martinfowler.com/bliki/TechnicalDebtQuadrant.html)).
Some of the ways I have tried to achieve this is to
[read books, follow external software engineers, follow mailing groups/blogs](https://mgaurav.github.io/2021/12/30/people-resources-i-follow.html)
related to anything which I am working with. This is also one of the principles which is totally in an individual's control,
you truly own your destiny w.r.t this principle.

## 10. Simplicity--the art of maximizing the amount of work not done--is essential.

I also consider myself fortunate to have listened to "[Simple made Easy](https://www.youtube.com/watch?v=SxdOUGdseq4)" talk from Alan Kay,
and talks from Martin Thompson early in my career.
They exposed me to the virtue of simplicity in software systems.
Building complex systems take time, maintaining then take even more time, evolving them takes even much more time.
Thus, having an eye for simplicity proves useful over a period of time.
One of the ways I have tried to practice it is while working on a problem, I would try to reduce it to simpler problems.
Often I have found that generalizing a problem makes it simpler since we start decoupling the layers which reduces complexity.
One of the most common advice I give to engineers working with me is to solve any problem at the right layer -
a simplest example is if you are writing a string manipulation function, don't write in the same file as your business logic,
put in the common place where other string manipulation functions are present, often when you do so, either you find that
function already available or you create a more reusable function/better testable function due to decoupling from the business logic.

## 11. The best architectures, requirements, and designs emerge from self-organizing teams.

Self organizing team is a dream team for any engineer I think. It means that team within itself is able to make
right design decisions, trade-offs, prioritization calls based on the context.
Each member of the team is accountable for the team deliverables.
The team members have full trust on each other. This is easier said than done, it even becomes more difficult
when there is a continuous influx/outflux of team members as trust building takes time and energy

## 12. At regular intervals, the team reflects on how to become more effective, then tunes and adjusts its behavior accordingly.

This principle was probably founding stone for Sprint retrospective ceremony.
However, I have rarely seen sprint retrospectives to be catered towards making teams more effective,
it has mostly been about making individuals more accurate with their estimations.
To become a high performing team, one must constantly look out for efficient ways & promote them further,
and find inefficient ways & remove them.
This requires each member of the team to be absolutely transparent about what's slowing them down, and
team members to continuously adapt team processes and behaviors to improve on them. 

# Conclusion

In a nutshell, Agile way of software development is to make small incremental steps with a feedback loop
which allows you to course correct as you move forward.
A really interesting metaphor which Dave Farley uses for it is the problem of balancing a broom.
You may try to apply all laws of physics and try to calculate exact point at which you should hold the
broom with right pressure being applied, it may still lead to failure since there are environmental
factors like wind speed which can change the equations.
Or, you can try to balance the broom by just adjusting your grip based on the feedback you receive
and balance it within seconds. 

**Which way would you choose in real life for balancing the broom? **

**Which way do you choose for developing software?**

**Are you just following ceremonies without really being Agile?**
