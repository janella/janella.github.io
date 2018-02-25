---
layout: post
title:  "On-call training for developers"
date:   2018-02-25 07:47:00 +1200
categories: posts
---
We had a problem at my company a couple of years ago. We were writing code, only to throw it over the fence to our infrastructure team to support in production. As a result the disconnect between the developers writing the code and the actual shipped product was becoming more pronounced.

To help with these ownership issues we brought production support of applications within the teams themselves.

These days my team is happily supporting our myriad of microservices in production ourselves, 24/7. That's despite most of us only having backgrounds as developers - only one member of the team has a systems administration or operations background.

In this post I'm going to tell you how we made that happen.

## The problem

My team grew very suddenly, from four developers to eight.

We ran into a classic growth problem.

The original developers had lots of background knowledge and intuition which they gained while supporting our applications in production. The new members of the team lacked this knowledge.

It was hard to get new team members more experience because when something customer-facing broke, we struggled to take the time to guide them through fixing it.

This led to a situation where the old members of the team were the only ones who could be on-call.

We decided we had to find a way to train our new team members for the wide variety of issues they could encounter.

## An experiment: simulating incidents

The idea was to put the newer members of the team into situations where failure *can* and *will* occur, but *safely*. No live customers are affected, no data is lost, and the situation can be fixed quickly.

It's sort of like training new pilots how to land a plane with one engine in a simulator, rather than waiting for it to happen in real life and cleaning up the mess afterwards.

This gives our "triage team" the chance to explore and refine their troubleshooting and triaging process in the same way that original members of the team had to.

### How we did it
1. Senior dev breaks something on the staging environment
2. Alert the triage team in some way (monitors, metrics, logs, or plain ol' someone going into Slack to complain that something's broken).
3. Triage team pairs up, in order to:
    * Investigate the symptoms (monitors/metrics/logs)
    * Identify the issue
    * Resolve the issue
4. Run a post-mortem afterwards, with the senior dev and the triage team, discussing:
    * The process used to investigate, identify, and resolve the issue
    * What was missed
    * What could be done better next time

The senior devs should allow the triage team to direct the investigation, but be available to explain concepts like application architecture, directing them to appropriate dashboards, or answer simple knowledge-based questions to speed up the process (for example, "how do I check the DNS routes of this URI?"). Coaching questions should be used to get the triage team to consider what could be going wrong.

The post-mortems allow the triage team to discover any gaps in their knowledge. For example, it's quite hard to triage where a request is failing if the dev only has a vague understanding of general networking. It also serves as a useful way to identify when processes, dashboards, and logs are not sufficient or are unclear. This helps improve production alerting, tooling, and process.

### What we broke

Our team adds production incidents into an incident log. This gives us a running record of what's gone wrong with our services, detailed information on how it was triaged and what the fix was.

The incidents we ran were based off of issues that we had run into previously. They could be things that could feasibly happen, or even things that were highly unlikely but would force the triage team to go through the troubleshooting process.

They ranged from incorrect DNS records (to familiarise the triage team with how our team managed those), failing load balancer healthchecks, stopped services, or an event stream choking on an invalid event.

(We decided against doing incidents caused by code changes - it was too easy to tell if something changed due to the paper trail (Github commit history, Slack notifications, Octopus releases, and so on).)

## Did it work?
So, what was the result of all this simulated problem solving?

* It allowed the triage team to build confidence that, yes, they actually knew how to fix problems in our (sometimes very complex) services. At the very least, it equipped them with patterns to help identify an issue. This meant that when something bad happened, they were a bit more comfortable at least knowing where to start.

* Simulating actual incidents and alerts meant the scenarios were relevant and somewhat realistic. They had a chance to become more familiar with tools to investigate problems.

* It allowed them to observe metric, dashboard, and log patterns that might correlate to something broken. This addresses a personal pet peeve: metrics are nice, but if you're unaware of what is "normal" and what is "maybe broken", the graphs will mean nothing to you.

* As a bonus for the team, it let us exercise dashboarding and alerts for services, sometimes ones that we don't often look at. It let us identify and refine old or little-used dashboards, which we then changed to give us useful information. Sometimes we even added more metrics for greater visibility over the service.

* Finally, it was fun! It was a practical alternative to just reading runbooks. Our triage team found it engaging and a great way to exercise some ownership over our services.

## Some thoughts and further reading
Both the triage team and the team as a whole found this exercise very beneficial. I would recommend running an exercise like this to anyone with an on-call component to their job, or any type of service that requires support. Our team now has much more depth when it comes to triaging issues with our service in general, easing the burden on the developers that are usually tasked with resolving issues.

In terms of further reading, unsurprisingly, someone else did this first: Google's excellent Site Reliability Engineering handbook is available for free online and has [a great chapter](https://landing.google.com/sre/book/chapters/accelerating-sre-on-call.html) on a similar approach.

If you try something like this out in your team, I'd love to hear about it - flick me a message [on Twitter](http://twitter.com/{{site.twitter_username}})! Thanks for reading. :)

