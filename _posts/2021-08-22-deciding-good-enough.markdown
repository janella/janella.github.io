---
layout: post
title:  "Good enough"
date:   2021-08-22 12:00:00 +1200
categories: posts
---

I've fallen into a lot of gold-plated holes as a developer. I'd find edge-case after edge-case, digging into all of the possible ways I could extend code in the future. I'd blink and my afternoon would be gone.

They say perfect is the enemy of good, and eventually I needed a way to decide when my code was "good enough".

## Warning signs
These are some key signs telling me I need to take a step back from the details:
* A task taking significantly longer than I originally estimated or timeboxed
* Finding many edge cases or bugs
* My other work-in-progress increasing
* Being unable to help others with their tasks

If it's not a deliberate choice to only focus on one thing, I know I need to take a breath and make sure I'm using my time wisely.

## Factors
Once I realise I need to step back, I ask myself these questions to see if something is good enough:
* **Value** - Is this _actually_ important to get right?
* **Priorities** - Is this the most important thing I could be doing with my time?
* **Authority** - Am I the best person to make this decision?
* **Information** - Do I know enough to make this decision?

### Value
> Is this actually important to get right?

You can't predict the future. Bugs will creep into your code, and you won't know exactly how this code will be used five years from now.

In some cases, it might be worth architecting a future proof solution. The code might be a business-critical, or you need high precision, or there might be a major security risk. In these situations taking time to decide and nail the user and developer experience is important - up to a point (for example, the exponentially increasing cost of adding a "nine" of uptime).

At other times, though, the edge case is so unlikely it isn't worth the effort right now.

I once stumbled upon a bug caused by a specific combination of user input and state.

I pondered about it all afternoon and brought it up at stand up the next day. Our designer came back to me thirty minutes later, and walked me through how a user would cause this: a convoluted six-step process using obscure areas of the site, ignoring safety nets we'd built, in an act of active user sabotage (okay, I'm kidding, but sometimes it feels like that!).

You're trading time and money for correctness, or availability, or some other quality metric. 

Sometimes it's just not that important.

### Priority
> Is this the most important thing I could be doing with my time?

Your time and brainspace is limited. If you've decided what you're doing is valuable, then you're going to give something up in return.

Priorities come from a few different places:
* Your company's strategy
* Your team's responsibilities
* Your own experience of work that needs doing

It's important to understand the tradeoffs and the other possible things you could be doing. Work out what will give the most value (the 80:20 rule), what you can delegate to others, and decide what to do next.

### Authority
> Am I the best person to make this decision?

Sometimes you are the best person to decide. Maybe you're the only person familiar with this code, or it's an engineering decision where you need to advocate for non-functional requirements like maintainability or speed of deployment.

Sometimes, though, there is a better person to ask - maybe it's a design decision, or a question of business strategy. Maybe both tasks are equally important.

Find out who needs to make the decision, and clearly communicate the information they need to make the choice.

If you're prone to impostor syndrome, it's easy to think you're not the right person to make the decision. An easy way to ease yourself into it is:
1. Make a guess on what the best option is, based on the information you have.
1. Escalate to someone who can help you make the decision.
1. Ask them what their reasoning was, and compare with your own thoughts from earlier.

This is a great way to build up confidence in your decision-making skills - eventually you'll be pitching your option, instead of just asking for help, which building other people's perception of your authority as well.

### Information
> Do I know enough to make this decision?

Sometimes you just don't have enough information. You might be unsure about the technology, the problem, the customers needs, and so on. 

Try to make a decision that does some of the following:
* Helps find information about the next best step (eg, instrumenting to see user behaviour or preferences)
* Breaks down the problem into smaller, more solvable problems
* Keeps the door open to multiple options when we find more information
* Makes it easy to change if it ends up being the wrong

If I don't know, I generally prefer the "safe" option - the one that keeps options open. If we accept that we can't predict everything, the best step is often the one that doesn't overinvest in unproven assumptions. That gives us enough time to gather more information to make a better decision next time.

## Practice
It becomes easier to step back from overengineering, and to make these tradeoffs, the more you do it. Exposing yourself decisionmaking helps you practice - for example, when it's someone else's responsibility, try and predict what they might say beforehand and listen to their reasoning behind their thoughts.

Interestingly, I found it easier to make these "good enough" decisions in a startup - I think there's a bit of clarity in knowing there's lots to do and not many people to do it. It also helps that in a smaller group you often have the agency to make a decision and follow through with it. 

The equivalent in a larger organisation would be to have a strong understanding and alignment to the company strategy, but there's a risk you don't have the agency to drive the change you need. That's a different blog, though. 🙂

Technical rabbit holes can feel overwhelming, making it hard to take the next step. For me, it's important to have a framework to remind myself how to decide in these situations - hope this helps you too!