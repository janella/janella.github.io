---
layout: post
title:  "Building domain knowledge"
date:   2020-08-16 12:00:00 +1200
categories: posts
---
I started a new engineering role two weeks ago, after ten years at my previous company.

It's also been years since I've been a hands-on developer. I was pretty worried about being out of practice: all the forgotten keybindings, the new best practices, how slow I'd be writing code.

I picked up a ticket on my second day. "I'll write some tests first, so I'm sure I won't break anything," I told myself, nervous about my rusty code craft.

![No contributions on Aug 4, 2020](/img/2020-08-16_1_nocontribs.png)

I spent the rest of the day going down rabbit holes and making zero commits. I finally gave up at 7pm, well past my usual time, frustrated about how long it was taking to work out what was going on.

My first ticket looked a little like this:

> Create a workflow available only when a supplier is unclaimed.

I had _so many questions_.

* What's a workflow? What's a supplier?
* What's the difference between "unclaimed" and "claimed"?
* How is the test data set up? Where even _is_ the test data?

![So many questions...](/img/2020-08-16_2_wtf.png)

My entire second day was me slowly finding answers, writing no code, and pestering people hoping they would point me in the right direction.

This was a far cry from my last job. Ten years at a company has its perks - over time, I had built up an extensive mental map of keywords and resources. I was able to quickly make connections between concepts, point people to information, and make educated guesses.

In the new environment, company, team, and code, those reference points weren't there.

## Connecting the dots
Building domain knowledge is a slow process, even in a startup where the codebase is less than a year old. Human brains are great at pattern matching, but I had nothing that matched these new patterns.

These are some things that helped me rebuild those connections. 

### Understand the gap
A good first step is identifying your growth areas and prioritising your learning time.

There are a few factors that impact your ability to contribute to code, whatever stage you are in your career. These include but aren't limited to:
1. Learning the language and tools.
1. Learning how to write code.
1. Learning the problem and the "why" of the change.
1. Learning the domain, keywords, conventions, and assumptions of the codebase.

At the end of the second day, I took some time to think about each of those areas and tried to identify what was holding me back.
1. I was using a familiar language, familiar dev environment, and a familiar cloud provider. It took some time to refresh my memory, but I had used the tools before.
1. I regularly reviewed code at my old role, so I still knew what "good" coding looked like.
1. Someone walked me through the design flows, and I was involved in some user testing the previous day, so I had a rough idea of the "why".
1. And… most of my questions were related to the domain space.

I was slowing down on things that related to #4, meaning the best use of my time was improving my understanding of the domain and codebase.

### Identify the building blocks
The next step is understanding key concepts and how they interact.

In a new codebase, these building blocks come in two flavours: 
* Domain concepts. In my ticket, they were "suppliers" and "workflow".
* Code structure. This is how the application is constructed, what classes are responsible for what function.

I spent some time following keywords in the code, drawing rough diagrams and writing down conclusions. These diagrams didn't have to be perfect UML - they just had to help me keep track of the concepts and relationships.

![Diagram of concepts and questions](/img/2020-08-16_3_blocks.png)

I prioritised the questions I needed to answer now, to keep things from feeling too overwhelming. I could dig into the other areas once I had a little more context.

Finally, I focused on making educated guesses instead of looking for a perfect solution. As someone prone to worrywarting, this was important. It gave me permission to be wrong and to concentrate on learning.

Something that helped me was checking conclusions with others on Slack. This was a good way to try and work through the problem, and gave an opportunity for others to nudge me in the right direction.

![Confirming my conclusions on Slack](/img/2020-08-16_4_check.png)

### Consider intent
When making decisions in code, I like knowing:
* The original intent - why is the code written the way it is?
* The future intent - what's the ideal state of this application? (we can't predict the future, but we know roughly where we want to end up)
* Your current intent - what do I actually want to do?

I like to believe engineers don't write code trying to do a bad job - sometimes it was the right tradeoff at the time.

Engineers can fall into the trap of thinking old or legacy code is automatically bad code. Our industry changes so fast which makes this problem worse - something new and shiny always comes along touting itself as the next big thing.

Before making the knee-jerk response of rewriting everything, take time to think about the questions above to understand why things are the way they are, and what constraints might still be relevant today.

### Optimise for finding, not memorising
It's impossible to keep everything you're learning in your head. The mental map at my last job was not some photographic memory of all the detail I ever needed - it was a mental map of _where_ to find the information I needed.

Spend time optimising for finding information, not memorising information.

Key areas to think about improving are:
* Information that was hard to find.
* Information that was vague or hard to understand.
* Gotchas or annoying pitfalls.
* Routine, common tasks, or questions.

I'm only the fifth engineer at this company, and we hope to get some great interns for the summer. Making the search for information faster helps both current and future engineers - including you, looking at code you wrote five years ago!

### Patience
The last thing that helped while building up domain knowledge was giving myself a break.

I'm lucky to have supportive and patient teammates who I've worked with before - people who were probably more patient with me than I was with myself.

There was no way I was going to be able to make the same intuitive leaps I was capable of in my old job. I'd literally been in the new company for _two days_.

Be kind to yourself. 🙂

## Being a beginner
Starting fresh at a company with a decent culture feels like a rare opportunity for me. I get to be a true newbie - no one would judge me too harshly for not knowing how everything works.

When building domain knowledge, it's  important for me to:
* Understand how and what I needed to learn.
* Be systematic about my learning.
* Help build a safe environment for myself and others.

Despite thinking I was okay at being a beginner again, I really struggled in that first week. It was a lesson in patience, and a reminder about how much I needed to learn - I'm looking forward to the next few months!
