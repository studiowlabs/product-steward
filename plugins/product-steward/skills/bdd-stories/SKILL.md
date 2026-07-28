---
name: bdd-stories
description: Turn decided product work into buildable user stories in behavior-driven form, each tied to a persona and a journey moment, with Given/When/Then acceptance criteria a developer and a test can both follow. Use when a feature has been decided and needs to become something a team can build and verify, when acceptance criteria are vague or missing, or when a story needs its unhappy paths spelled out. Writes stories into the product's repo, each with the persona it serves, the value it delivers, the scenarios, and the edge cases. Confirm the work is decided (via steward-the-product and value-increments) before writing stories for it.
---

# BDD User Stories

A user story in behavior-driven form says who the work is for, what they get, and exactly how you would know it works. The Given, When, Then scenarios are the bridge between the product decision and the build: a developer can implement them, a test can assert them, and the product owner can read them and confirm the product does what the customer needed. A story without acceptance criteria is a wish; a story with them is a contract.

Write stories only for work the steward has decided is worth building. Stories are where a `value-increment` becomes buildable, and the scope is already set before they are written. They live in the **product's own repo**.

## The build loop

### 1. Anchor the story
Every story names three things before a single scenario is written, using `story-template.md`:
- **The persona** it serves, from the `personas` set. "As a user" is a smell; name the real person.
- **The journey moment** it belongs to, from the relevant `user-journey`. This keeps the story attached to a real experience instead of floating free.
- **The value**, in the classic frame with a real outcome: *As [persona], I want [capability] so that [outcome they can feel]*. The "so that" is the point. If you cannot state a real outcome, the story is not ready.

### 2. Write the scenarios in Given, When, Then
Each scenario is one concrete path through the story:
- **Given** the starting state, the context that is true before the person acts.
- **When** the person does the thing, a single action.
- **Then** the observable result, what the person sees or gets, stated so a test could check it.

Write the **happy path** first, then the realistic variations. Keep each scenario to one behavior; if a scenario needs three "and then" steps, it is probably two scenarios. Use concrete values so the scenario reads like a real session.

### 3. Spell out the acceptance criteria
The scenarios plus a short checklist are the definition of done for the story:
- The scenarios all pass.
- The accessibility and cognitive-load bar is met, because it is part of the product from the first draft. Plain language, keyboard reach, and clear states where they apply belong in the criteria.
- The story is whole. It delivers the "so that" on its own, with no remainder pending another story.

### 4. Attach the unhappy paths
A story is not done when the happy path works; it is done when it holds up when things go wrong. Pull the relevant failure modes from an `edge-cases` pass into the story as their own Given, When, Then scenarios: empty states, invalid input, the third party that is down, the permission the person lacks, the slow network. A story that only describes success is a story that will break in production.

### 5. Size and write it down
- Keep a story small enough to build and verify in one sitting. If it is not, split it, and keep each split whole, a real vertical slice of value.
- Write stories into the product's `docs/` or its issue tracker, grouped under the value increment they belong to.
- Hand the story to the build with its persona and journey context intact, so whoever builds it, including designer for the interface, knows who it is for and what moment it serves.

## The relationship to designer
A BDD story says what behavior the product must exhibit and how the person should be able to tell it worked. It does not say what the button looks like or where it sits. When a story's scenario says "then she sees her number update," designer decides how that update looks and moves. Keep the story at the behavior altitude; hand the interface to designer.

## Where the other skills fit
- `value-increments` groups stories into a shippable, feelable release.
- `personas` and `user-journeys` anchor every story.
- `edge-cases` feeds the unhappy-path scenarios.
- `roadmap` sequences the increments the stories belong to.

## The one rule
Every story has a "so that" the customer can feel, and every story has at least one unhappy path. A story missing either is not ready to build.
