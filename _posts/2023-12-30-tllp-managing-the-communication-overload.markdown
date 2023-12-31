---
layout: post
title:  "Tech Lead Learning Path: Managing the Communication Overload"
date:   Sun Dec 30 18:21:40 IST 2023
---

As a Tech Lead, you are often involved in various kind of communications (below is not an exhaustive
list):

- Within team communication

  - Planning activities (OKR planning, Sprint planning, estimations etc.)

  - Unblocking team engineers on any blockers/questions/doubts they are facing

  - Roadmap shaping with product managers

  - Mentoring other engineers in your team

- Outside team communication

  - Helping other team engineers on things they need to integrate with your component

  - Handling feature asks from other teams

- Horizontal

  - Handling various customer calls, bugs

  - Status updates to higher management

Depending on the team composition, Tech Lead and Engineering Manager can split some of these
communications among them or can do these collaboratively. However, irrespective of team
composition, communication is a very important skill for a Tech Lead. A communication overload may
happen if you are constantly struggling to remain on top of all the communications you are part of.
Common symptoms for it would be being reminded of things falling past due dates, losing track of
Slack threads, delays in replying to folks waiting for your replies. It impacts your credibility as
a Tech Lead as people might perceive you as someone lacking accountability.

We can categorize communication into 2 broad categories:

1. Synchronous communication - Meetings.

2. Asynchronous communication - Slack/Jira/Emails.

This blog post will go into some of the practices which may help with managing the communication
overload. It won't cover all aspects related to communication skills needed for a Tech Lead.

## Planned and Proactive Communication

A lot of communication is actually predictive in our environment, e.g.

- If a quarter end is approaching and you have the responsibility to plan OKRs, then you are aware
  that communication need is approaching near you and so you can plan for it.

- If you had committed for some feature delivery and it is getting delayed, then you can do
  proactive communication to stakeholders to avoid surprises or need to fire fight later.

There is no way you would avoid these communications, so preparing yourself upfront would help you
to stay on top of them.

> [!NOTE]
> A general rule of thumb I follow is to plan for any communication coming in next 2 weeks
> and be proactive in communicating things as soon as I become aware of them.

## Scheduled Communication

As a Tech Lead, you often need to communicate with a bunch of stakeholders. It is often helpful to
have recurring 1:1 syncs with your stakeholders whom you interact frequently. You can utilize these
1:1 syncs as an opportunity such that it leads to reduced asynchronous communication. Some examples:

- Sync with manager: Discuss top of mind things for the manager, update on key initiatives for the
  team, any risks you foresee, any help you need from the manager.

- Sync with leadership (say, VP of your org): Similar to communication with manager (can be little
  light on granular details). You can utilize this time to find what matters for the org and how you
  can organize your team to contribute towards those goals.

- Sync with product manager: continuous refinement of product roadmap, proactive communication on
  any challenges you see with key customers, what would help with further adoption of the product.

- Sync with another team lead: continuous refinement of feature asks on other team or on your team,
  prioritization discussions, opportunities for 2 teams to integrate better (at code level, culture
  level).

- Sync with your team engineers: continuous feedback, bridging skill gaps (both technical &
  non-technical), clarifying priorities.

The good part with synchronous communication is it often doesn't lead to subsequent context switches
(which is the case with asynchronous communication). Note that I am not suggesting to avoid
asynchronous communication fully, I am only suggesting to accompany that with synchronous
communication and using synchronous communication to reduce need of asynchronous communication
wherever possible. With a bit of preparation before your 1:1 syncs, you can avoid a lot of
asynchronous communication (especially with higher management).

> [!NOTE]
> A general advice for 1:1s is to always keep a shared doc for your 1:1s where during the
> meeting, the doc is shared on the screen and you take notes during the meeting itself where both
> persons can see the notes. This simple tip would help significantly to be on top of whatever is
> being discussed and be a driver of those conversations.

## Managing Asynchronous Communication

It is important for a Tech lead to be on top of anything which needs their attention on
Slack/Jira/Emails. Above practices talks about using synchronous communication to reduce
asynchronous communication wherever possible, however, it won't (& shouldn't) remove asynchronous
communication fully. Different people follow different ways to be on top of all asynchronous
channels, I will list few I follow or have heard from other folks:

### Slack

Some good practices on how to manage Slack communication better:

- Get out of channels you don't need to follow;

- Prioritize your channels: code reviews, team channel, general communications;

- Check higher priority channels with more frequency;

- Set up a time window to be on Slack and a time window to get work done;

- Don't feel ashamed to mute/close Slack to work on something concrete.

Slack has features to save threads which will show in
[Later](https://slack.com/intl/en-in/help/articles/13453851074067-Save-it-for-Later) section. You
can set reminders on messages. Different people might have different mileage in using these, I
personally struggle to get to items I have marked as Later.

I try to commit an ETA on Slack threads and try to meet those (once I have given an ETA, it becomes
a planned/predictive communication). I would exercise caution on giving ETAs which I don't have
confidence of meeting. And, in case I miss the ETAs, I would be sincerely apologetic and try not to
miss the next ETA.

I maintain 0 unread Slack messages, Marking everything as read helps me to get to know incremental
incoming messages.

### Jira

Often the most important jiras which a Tech lead shouldn't miss would be customer issues, high
priority bugs etc. One way which works well for me for those is to have a
[Jira dashboard](https://support.atlassian.com/jira-work-management/docs/create-and-edit-a-dashboard/)
for the team which shows jiras which need attention. That way, even if I may have missed a Jira
notification, I can go to a dashboard and see what needs my attention quickly. Creating a Jira
dashboard is pretty simple and anyone can do, so you can use it based on your custom needs.

I also rely on Jira email notifications to know of all jiras which I care about, I watch any Jira
issue which I intend to follow and then follow email notifications for them.

To summarize, my approach is mostly to know what all I need to watch for and have discipline to go
through those various sources periodically so that I don't miss anything. Just acting on push
notifications doesn't work for me, so it is a mix of push notifications + on-demand pull that I do.
