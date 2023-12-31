---
layout: post
title:  "Tech Lead Learning Path: Taking An Outsider View"
date:   Sun Dec 30 18:21:40 IST 2023
---

# Context Is The Key

Tech Leads are responsible for making engineering decisions. A good engineering decision requires
context. The context may include:

- What are you trying to do? Are there constraints w.r.t time, bandwidth?

- Are there organizational directions you need to align with?

- Is it a [reversible or irreversible decision](https://fs.blog/reversible-irreversible-decisions/)?

- Will the decision slow us down in long run (e.g. introduce a
  [reckless/deliberate tech debt](https://martinfowler.com/bliki/TechnicalDebtQuadrant.html))?

If a Tech Lead only considers an insider view (i.e. be laser-focused on achieving their team's
goals), then they will tend to optimize for the team's interest. It might lead them to make a
decision which is best decision for their team - a local maxima. However, that might not be the best
decision for the organization as often decisions have consequences on other teams and the
organization.

Local maxima is definitely the fastest path to deliver the feature at current point of time,
however, it leads to slow down of the team/organization in the future and thus, may lead to overall
lesser velocity (note that engineering velocity is measured over the entire lifetime of the feature
rather than just its first release). Taking the broader view may have an impact on short-term
delivery due to Tech Lead optimizing for the long-term. This might also sometimes raise a conflict
with Engineering Manager of the team as Managers would often be more short term focused (ref.
[The Art of Leadership](https://www.amazon.in/Art-Leadership-Michael-Lopp/dp/1492045691) by Michael
Lopp). And thus, it should be Tech Leads responsibility to make Manager aware of trade off between
short-term and long-term view and why they prefer the long-term view and build a consensus on the
decision.

## Building the Organizational Context

By the nature of their role within their team, Tech Leads have a good understanding of their team's
strategy and roadmap. However, that is not sufficient to make good engineering decisions as that
doesn't include organizational context. Tech Leads **should invest their time** in understanding
long term engineering architecture, key initiatives which are in progress, roadmap of the
platform/infra teams or any of their dependent teams. Building the organizational context would
allow a Tech Lead to flow with the stream rather than inadvertently running against it. The *harsh
reality* of running against the stream is that impact of your decisions won't be visible
immediately, they will start surfacing after a year or two in the form of Tech Debt/need to
re-architect the product.

This brings us to the question of how to build the organizational context? There are few ways in
which this could be done effectively:

1. Utilize 1:1s with your manager, leadership in your org to become aware of key initiatives. Often
   your manager and/or leadership chain would have visibility into these and they can point you to
   relevant engineers to get more context.

2. Know roadmap of platform/infra teams, this might help you avoid building on top of technologies
   which are being replaced.

3. Know roadmap of your dependent teams, have regular connect with their Tech Leads/engineers.

4. Eng All Hands typically have segments where some of the projects related to organizational
   direction are presented. This could also be a good source to know the direction organization is
   headed towards.

## Taking An Outsider View

Having both their team's context and organizational context allows Tech Leads to take an outsider
view as well as an insider view while making engineering decisions. This would avoid the trap of
falling into local maxima which might hamper team/organizational velocity at a later point of time.

Taking the outsider view may also allow a Tech Lead to solve generic problems which leads to bigger
impact (e.g. implementing a feature at a team level v/s implementing it at a platform level and
thus, benefiting all teams).

Taking the outsider view will also allow a Tech Lead to build better network with other
engineers/Tech Leads as it would often require to discuss ideas with other engineers. If someone
sees you as making decisions considering both local context as well as organizational context, I am
sure your reputation as an engineer will increase in their eyes.

## References

- The Big Picture section from
  [The Staff Engineer's Path](https://www.amazon.in/Art-Leadership-Michael-Lopp/dp/1492045691) by
  Tanya Reilly
