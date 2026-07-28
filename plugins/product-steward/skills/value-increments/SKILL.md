---
name: value-increments
description: Slice product work into increments that each deliver something the customer can feel, name the delight before the tasks, and set a capacity-based, sustainable delivery date. Use when shaping a release, deciding what goes in the next slice, cutting a big feature down to a shippable first piece, or forecasting when something will land. Slices vertically so every increment is a whole thin experience, writes a plan of intent before the build, and sets dates from real capacity and the owner's sustainable sense of enough, never manufactured crunch. Confirm the product read, and draw stories from bdd-stories.
---

# Value Increments

A value increment is the smallest whole slice of work that the customer can actually feel: a thin complete experience that makes the person's day with the product better than it was. It cuts through the whole stack and stands on its own, a finished small thing the customer can use the day it lands. Packaging work this way is how the steward keeps the product owner from shipping activity instead of value: every increment has to answer, before anything is built, what the customer feels when it lands.

Increments are the product's, and the plan for each one is written into the **product's own repo** before the code, the way a disciplined product owner already works in the product's `docs/`.

## The packaging loop

### 1. Name the delight first
Before listing a single task, say what the customer feels when this increment ships:
> *"When this lands, [persona] can [do the thing] and feels [the change], where before they [the old pain]."*

If you cannot fill that in with a real feeling, the increment is not shaped yet. The feeling is the point of the slice; the tasks are just how you get there. The rule generalizes: if a piece of work does not move something the customer can feel, the increment does not need it yet.

### 2. Slice vertically, keep it whole
Cut the work so the increment is a thin slice through the whole experience:
- **Vertical.** "The person can log one real engagement and see her number move" is a whole slice. "Build the database schema" is a layer that delivers nothing feelable on its own.
- **Whole.** The increment stands on its own. A customer using only this increment gets a real, if small, improvement, with no dead ends that say "coming soon."
- **Thin.** Push the second and third refinements to later increments. The first one earns the right to exist by being feelable.

Find the slice by walking the `user-journey`: the drop point that hurts most, or the moment that matters that is not yet served, is usually the first increment.

### 3. Fill the increment with stories
Draw the `bdd-stories` that make up the increment, each with its persona, its "so that," and its unhappy paths. The increment is done when its stories pass and the delight statement holds true, whatever remains on a task list.

### 4. Set a capacity-based, sustainable date
A delivery date is a forecast built from real capacity, sized so a normal week can carry it. This is where the steward honors sustainable delivery instead of fighting it:
- **Estimate the work in whole increments,** not hours of heroics. Size each story, sum the increment, and be candid about the unknowns.
- **Divide by real, sustainable capacity,** the hours the owner actually has for this product in a normal week alongside everything else they run. The owner's sustainable sense of enough is the input here: the date has to fit inside a week they can repeat without grinding.
- **State the date as a range with its assumption:** *"Landing around [date], assuming [capacity] and no surprise from [the biggest unknown]."* A date is a promise to the customer about when, and a truthful one has its assumption attached.
- **A slip is information.** If reality diverges, move the date and say why in the repo. Do not absorb the slip by working the weekend. The win is hitting the number in fewer hours, so a date that only holds through crunch is the wrong date.

### 5. Write the plan of intent, before the code
For any real increment, write a short plan-of-intent doc in the product's `docs/` before it gets built, using `plan-of-intent-template.md`. This is a disciplined way to work: the doc gives the build a clear aim and lets the next session see the whole shape. It captures the problem this solves, what already exists and stays, the decided approach, the delight, the stories, and the date. Keep it accurate as the build teaches you things; a plan that no longer matches the code is worse than none.

Record the increment itself with `increment-template.md`, and park anything deliberately deferred in the product's dated `docs/backlog.md`, newest first.

## Sequencing across increments
When several increments compete for "next," order them by the precedence in `steward-the-product`: the customer's real experience first, then the pillars, then value delivered per increment, then effort. Prefer the slice that gets a feelable win to the customer soonest. Two small increments that each land a real improvement beat one big one that lands nothing until the end.

## The relationship to designer
An increment is a unit of customer value; it is not a design. Once the steward has shaped and sequenced an increment and written its stories, it hands the increment to designer to craft the interface for the decided work, and to the design jam if the interface needs exploring. The steward says what ships and when and why; designer says how it looks and feels.

## Where the other skills fit
- `user-journeys` shows where the first increment should cut.
- `bdd-stories` fill the increment and define its done.
- `edge-cases` harden it before it ships.
- `roadmap` sequences increments into now, next, later.
- designer and its design jam craft the decided increment.

## The one rule
Every increment names the delight before the tasks, and ships whole. If you cannot say what the customer feels when it lands, do not build it yet; shape it until you can.
