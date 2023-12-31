---
layout: post
title:  "Tech Lead Learning Path: Prioritization As An Act Of Balance"
date:   Sun Dec 30 18:21:40 IST 2023
---

# The Competing Forces

Any software team often has multiple competing forces to balance - product roadmap, strategic
customer asks, horizontal initiatives, tech debt etc. Each of these buckets would typically have
many items and there would never be enough headcount to do it all. This leads to the need of
prioritizing among various possible things a team can do. Most of the items in above list come from
Leadership and Product Managers (e.g. product roadmap, strategic customer asks, horizontal
initiatives) whereas tech debt is often crowd-sourced from within the team.

On top of above categories, there is another category where Tech Lead needs to be forward looking
and identify & mitigate items which will put team at risk in future. This could include items like
scalability as the current system will reach scale limits in about one year, performance as the
current system will breach acceptable thresholds in some time, sustainability as current way of
operating will incur higher on-call bandwidth in future etc. The role of a Tech Lead in this
category is to identify such engineering initiatives and determine how much runway is available and
appropriately take incremental steps to solve the problem before it becomes a critical issue.

In this post, we will touch upon both aspects which can help Tech Leads manage the various competing
forces effectively:

1. Backlog prioritization

2. Identifying Engineering Initiatives

# Backlog Prioritization

Tech Leads and Engineering Managers play a crucial role in doing prioritization of various items
which team need to execute upon. There are different tools and frameworks different companies/teams
use to achieve this - Jira, Google Sheets, Project Management tools like AHA!

The key aspect of being able to prioritize well is to have a single source of truth so that you are
able to view all items to be prioritized at one place. Once you have all items at a single place,
you can choose to prioritize them via different mechanisms:

- Some teams use Px (P0, P1, P2, P3 …) priorities to be marked against each item. The priority value
  can be gauged based on each stakeholder input (PMs, TLs, EMs, Team Members).

- Some teams use frameworks like [RICE](https://www.productplan.com/glossary/rice-scoring-model/)
  (Reach, Impact, Confidence, Effort) or
  [BRICE](https://kaseykaplan.medium.com/how-to-use-brice-scoring-to-solve-relevant-product-problems-42610fafc931)
  (Business Importance + RICE) to assign score to each item which leads to overall prioritization.

I don't have any specific recommendations on which tools or prioritization frameworks to use - use
whatever works best in the context your team is in. However, I recommend to:

1. Have a single source of truth for all work items. This will help in a) not missing any item, b)
   create a transparent backlog with your stakeholders, c) allow you to prioritize. Maintaining this
   backlog is not a single person's job, this should be done by each member of the team whereby
   entire team is aware about adding an item in the backlog whenever something is deferred (it could
   be a Slack conversation where you promised a customer that this will be picked up later). Thus,
   defining the single source of truth will allow everyone to add items in the backlog.

2. Prioritize the list of work items in each planning cycle. Typical planning cycle at various
   companies is quarterly where each team decides their OKRs. In each planning cycle, go over the
   list of work items which are remaining and review notes added in previous cycles, add notes based
   on current context and prioritize. Note that an item being a P0 in last planning cycle doesn't
   necessarily make it a P0 in subsequent planning cycles as context might have changed since last
   planning cycle.

3. Involve the stakeholders in your prioritization decisions - take their inputs and inform them of
   final priority order.

The above steps creates a healthy feedback cycle:

1. **Collection**: All feature asks from stakeholders are transparently captured in a single source
   of truth which is visible to them.

2. **Prioritization**: Inputs from all stakeholders are captured during planning cycle. Something
   which was higher priority for your stakeholder last quarter may not be high priority now, or
   vice-versa.

3. **Inform**: Stakeholders are informed with decisions taken during planning cycle - leads to no
   surprises later.

In my experience, different teams operate at different maturity levels in Collection and Inform
phases of above cycle. This leads to creation of more adhoc work which could have been planned work
if we collected and informed stakeholders during planning cycles.

It is also important to understand that not all items in the backlog will have uniform treatment.
One specific aspect I want to call out is about putting estimates/efforts in the prioritization
backlog.

> Estimates/efforts are necessarily required to evaluate priority (e.g. E in RICE stands for
> Efforts). However, it should not be required to have expectation of accurate estimates on all work
> items as it could lead to unnecessary work being spent upfront. E.g. it would hardly be the case
> that all work items will be picked up in next quarter, and if we already know rough capacity for
> execution and relative prioritization, then there is no benefit of doing accurate effort
> estimation for items lower in the priority list which won't likely be picked in next quarter.

Estimations and role of Tech Lead in estimation process is worth a blog post by itself, so I will
defer that.

# Identifying Engineering Initiatives

Tech Leads play an important role in identifying Engineering Initiatives at both team-level and
organization-level. Engineering initiatives differ from product features. Product features often
have clear deliverable and release timelines attached to them due to external factors (competitors,
marketing events etc.) and thus, requires Tech Leads to answer mostly how (execution plan) and how
much (scoping) questions. On the other hand, Engineering initiatives need Tech Leads to identify
what (identifying problem), why (impact), how (execution plan), how much (scoping), and when
(timelines) questions:

- **What do we need to do?** - identify the problem to be solved. If what involves a specific
  solution, then consider that as a red flag for an engineering initiative as the initiative might
  be inspired from individual's interest to work on the specific solution. E.g. what should not be
  "move our stack to Kubernetes", it should rather be the problem we are trying to solve, e.g.
  "single VM deployments are not scalable". Writing down the problem statement clearly will make you
  think more about the problem you are trying to solve. If you are not able to write the problem
  statement clearly, that's likely a good signal that there isn't actually a problem to solve or you
  haven't spent enough time thinking about it.

- **Why we need to work on this problem?** - identify the impact this could have. The two important
  questions here is:

  - What if we maintain the status quo and doesn't change anything?

  - What will we gain by solving the problem? Discuss the possible impact with your peers and
    stakeholders.

- **By when do we need to solve this problem?** - identify the timelines. While answering this, it
  is important to be honest, often times, engineers will be pessimistic about runway available to
  them for solving the problem especially when they are the ones who identified the problem as
  working on your own idea is often the biggest motivator for an engineer. To be able to evaluate
  the available runway, rely on the data rather than intuition.

- **How are we going to solve the problem?** - if above questions have been answered and you have
  taken feedback with your peers and there is consensus on the impact of the problem, you can work
  on to define incremental steps to solve the problem.

Often, engineers skip answering What and Why questions and directly jump on how part. This is
natural for a budding Tech Lead as by that time, they have likely identified problems which they can
code themselves up quickly or can do piece-wise in their free time. However, same approach won't be
effective when you are defining an Engineering Initiative for your team or organization which will
be executed by other engineers. Not answering why and when questions may lead to:

- Not having full buy-in from the team on the initiative.

- Slow progress on the initiative or worse, initiative being dropped half-way after some progress
  has been made.

Note that it is possible that when you get peer feedback on the problem statement and impact it
could create, there is a chance that there is a conflict in which the impact is perceived
differently by different stakeholders. This is generally a good signal about your biases and
attachment to the problem/solution you have in mind. Be as objective as possible at this stage and
more data driven. Remember that it is still beneficial to drop an initiative at this stage when not
much effort has been spent rather than spending more bandwidth on it only to later realize that it
didn't create enough impact.

Answering above questions would lead you to judge true priority of the problem, and thus, help with
sourcing bandwidth for the problem at the right point of time.
