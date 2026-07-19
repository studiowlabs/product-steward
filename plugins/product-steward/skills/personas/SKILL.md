---
name: personas
description: Build and maintain the small set of real people a product is for, so every product decision has a specific human behind it. Use when a product has no clear picture of who it serves, when a feature is being scoped without a named user, or when the existing personas have gone stale. Grounds in the product, asks sharp questions, and writes personas into the product's repo, each with their job to be done, what they need to trust and do, what would make them feel behind, and how you would know the product served them. Never invents a stock "Sarah Chen." Confirm the product read with steward-the-product first.
---

# Personas

A persona is the specific person a product decision is for. Without one, a backlog fills with features that serve nobody in particular, and "the user" becomes a stand-in for whatever the builder happened to want. The steward's job is to make the customer concrete, so every story, journey, and roadmap item has a real human behind it.

Personas are the product's, so build them *with* the evidence the product already has, and write them into the **product's own repo**. Do not import a persona from another product. The person `tide` serves is not the person `hoodlums-home` serves.

## The build loop

### 1. Ground in who is already here
Before inventing anyone, find out who the product already knows it serves:
- Read the repo for existing personas, audience notes, the README's stated audience, marketing copy, and the thesis or promise.
- Read the git history and `docs/` for the real person the work has been shaped around. webs's products often serve a specific, real person (in `tide`, the solo or fractional worker webs is building for, which is close to webs herself). Start from that real person, not a demographic.
- Look for evidence of real use: support notes, testimonials, survey results, interview notes. Evidence beats invention every time.

### 2. Facilitate the set, do not assume it
Ask a **small number of high-leverage questions**, never a blank "who is this for" and never a long dump:
- Who is the one person you are most building this for right now? Describe a real one.
- What are they trying to get done, in their words, on the day they reach for this?
- What do they already do instead, and what does that cost them?
- What would make them feel behind, talked down to, or like they are not the kind of person this is for?
- Who is this explicitly *not* for right now?

Keep the set small. Two or three personas that are sharp beat six that blur together. A product serving everyone serves no one in particular.

### 3. Write each persona as a decision tool
For each persona, capture what actually changes a product decision, using `persona-template.md`. The parts that earn their place:
- **A real name and a one-line who.** Use a real person the product serves, or a clearly-chosen placeholder webs picks. Never a stock AI name like Sarah Chen, John Smith, or Acme Corp.
- **The job to be done.** What they hire the product to do, in their language, tied to a real moment and a real trigger. Not a feature list; the outcome they want.
- **What they need to trust.** What has to be true for them to rely on the product with something that matters to them (their money, their time, their reputation, their classroom).
- **What they need to be able to do.** The plain capabilities, stated as outcomes, that the product owes them.
- **Where they are new.** What they may not know yet, and the jargon that would make them feel behind. This drives the teach-don't-gatekeep stance: name the plain idea before the term.
- **How you would know it worked.** The observable signal that this person was served, so the roadmap can aim at it.

### 4. Add the anti-persona
Name who the product is deliberately not for right now, and why. An anti-persona stops scope creep as clearly as a persona directs it, because it gives the team explicit permission to say no.

### 5. Keep them living
- Write personas into the product's `docs/` (a `personas.md`, or one file each for a larger set).
- Date them, and revisit when real evidence contradicts them. A persona invented once and never checked against reality becomes fiction.
- When a story, journey, or roadmap item is written, it names the persona it serves. A persona nobody references is dead weight; delete or fix it.

## Accessibility and cognitive load belong here
Every persona carries a "where they are new" section on purpose. webs builds from a universal-design and cognitive-load stance, so a persona should surface where the product risks overwhelming, talking down to, or gatekeeping the person it serves. If a persona could be a person with low prior knowledge, limited time, or an access need, say so, because that shapes the plain-language and inclusive-design work downstream.

## Where the other skills fit
- `steward-the-product` sets the product read this builds on.
- `product-pillars` are tested against these personas; a pillar that serves nobody in the set is suspect.
- `user-journeys` and `bdd-stories` each name the persona they serve, so read them here.
- designer reads these personas to know who its interface is for. It does not author them.

## The one rule
A persona is a decision tool, not a character study. If a detail would not change a product decision, cut it. If a real person the product serves would not recognize themselves in it, it is wrong.
