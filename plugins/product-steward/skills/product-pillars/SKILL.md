---
name: product-pillars
description: Name the few enduring commitments a product stands for, so every feature has something concrete to be tested against and the roadmap has a spine. Use when a product's decisions feel scattered, when scope keeps creeping, or when the team cannot say what the product is and is not. Grounds in the product's promise and personas, proposes a small set of pillars each stated as a commitment with its trade-off, and writes them into the product's repo. Confirm the product read and personas first.
---

# Product Pillars

A product pillar is a commitment the product makes to itself, durable enough that every feature can be tested against it. Pillars are how a product says what it is and, just as usefully, what it is willing to give up to stay that. Without them, a roadmap becomes a pile of good ideas with no way to choose between them, and the product drifts toward whatever was easiest to build that week.

Pillars are the product's, grounded in its promise and its personas, and written into the **product's own repo**. `tide`'s pillars (time is the scarce thing, value over hours, a floor that pays her worth, teach don't gatekeep) are `tide`'s. Do not carry them to another product.

## The build loop

### 1. Ground in the promise and the people
- Read the product's stated promise or thesis, its README, and its `docs/`. Many of webs's products already state their spine in prose; `tide`'s thesis is an explicit set of commitments. Start by finding what is already there.
- Read the `personas`. A pillar exists to serve the people in the set. A proposed pillar that serves nobody in the set is suspect.

### 2. Propose a small set, each as a commitment with a cost
Offer **three to five** candidate pillars, no more. A product with ten pillars has none. Each pillar is:
- **A commitment, stated plainly.** What the product will reliably do or protect for its customer. Write it as something you could hold a feature against and get a yes or no.
- **Paired with its trade-off.** A real pillar gives something up. If a pillar costs nothing to hold, it is only a slogan. Name what the product will decline in order to keep it.
- **Tied to a persona and an outcome.** Say which person it serves and what they get.

State each in one or two sentences, concrete enough to decide with. "Fast, simple, and elegant" is not a pillar; it is three adjectives. "The customer hits her number in fewer hours, never more" is a pillar, because you can test a feature against it.

### 3. Pressure-test the set
For each candidate, run it against reality:
- **Can it say no?** A pillar that never rejects a feature is not doing its job. Find a plausible feature it should reject, and confirm it does.
- **Does it fight another pillar?** Some tension is healthy and worth stating, but if two pillars routinely contradict, the set needs work.
- **Would the product still be itself without it?** If removing the pillar changes nothing about what gets built, cut it.

### 4. Write them down and put them to work
- Write the pillars into the product's `docs/` (a `pillars.md`, or a section of a product doc), each with its commitment, its trade-off, and the persona it serves.
- Reference them from the roadmap and from stories. When a feature is proposed, the first question is which pillar it serves, and the second is which pillar it strains.
- A pillar is allowed to change, but only on purpose. If the product decides to drop or rewrite one, that is a real decision recorded in the repo.

## The relationship to designer
Pillars are product commitments held at the product altitude. designer has its own prime directive (honor each project's own vibe), and the two reinforce each other: the steward's pillars say what the product is for, and designer expresses that in the interface. Keep pillars at the product altitude. "The interface feels calm" is a design outcome; "the customer is never made to feel behind" is a product pillar that designer then expresses.

## Where the other skills fit
- `steward-the-product` puts pillars second in the precedence order, just under the customer's real experience. They are the standing test for everything below.
- `personas` are who the pillars serve.
- `roadmap` and `value-increments` are organized so the work visibly advances the pillars.

## The one rule
A pillar has to be able to reject a feature. If it cannot say no to anything, it is decoration. Cut it or sharpen it until it can.
