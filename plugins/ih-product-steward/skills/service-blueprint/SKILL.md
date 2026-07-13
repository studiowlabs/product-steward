---
name: service-blueprint
description: Map the system behind a customer experience, so the front-stage moments a user sees are backed by the back-stage steps, systems, and support that have to exist for the experience to hold. Use when an experience depends on more than the interface (data, integrations, human steps, notifications, third parties), when a flow keeps breaking for reasons the UI cannot explain, or when planning a feature whose value depends on what happens off-screen. Pairs with a user journey, maps front stage, back stage, and support processes against each step, marks the fragile links, and writes the blueprint into the product's repo. Confirm the relevant journey first.
---

# Service Blueprint

A user journey shows what the customer experiences. A service blueprint shows the system that has to exist to produce that experience: the steps the customer sees (front stage), the steps and systems working out of sight (back stage), and the support that both depend on. It is the artifact that catches the failure a screen cannot explain, when the interface is fine but the email never sent, the sync silently failed, or a human step nobody owned was skipped.

Blueprint one flow at a time, anchored to its `user-journey`, and write it into the **product's own repo**.

## The build loop

### 1. Anchor to a journey
A blueprint sits underneath a journey. Take one `user-journey` (or one flow within it) and use its stages as the top row. The customer's steps are the front-stage line; everything below the line is what makes those steps possible.

### 2. Map the layers against each step
For each step the customer takes, using `service-blueprint-template.md`, record what happens across the layers:
- **Front stage.** What the customer sees and does: the screen, the message, the action. This is where the journey and the blueprint meet.
- **Back stage.** What the product does out of sight to serve that step: a calculation, a database write, a job, a state change, an email queued.
- **Systems and integrations.** The technical pieces that carry it: the auth provider, the database, the payment or sheet backend, a third-party API, a scheduled task. Name them, because they are where reality intrudes.
- **Support processes.** Anything a human or an external party has to do for the step to work: a manual review, a configuration webs has to set once (like enabling a sign-in provider in a dashboard), a partner's action.

### 3. Draw the lines
Two lines make a blueprint more than a list:
- **The line of interaction**, between the customer and the front stage: where the person touches the product.
- **The line of visibility**, between front stage and back stage: everything below it, the customer never sees but entirely depends on. Most surprising failures live just below this line.

### 4. Mark the fragile links
Walk the blueprint and flag every place the experience can break:
- A back-stage step with no owner.
- A third-party or integration that can fail, rate-limit, or change.
- A support process that depends on a human remembering, or on a one-time configuration that is easy to forget.
- A single point of failure that takes the whole front-stage promise down with it.

Each fragile link is a candidate for an `edge-cases` pass and, if it matters, a hardening increment on the `roadmap`.

### 5. Write it down and route the work
- Write the blueprint into the product's `docs/` (a `blueprints/` folder or a `blueprint-<flow>.md`), next to the journey it serves.
- Fragile links become `edge-cases` and, where they threaten a moment that matters, `bdd-stories` and roadmap items.
- The boundary with designer holds here too: the blueprint is the product's operating model, not the interface. designer needs to know that a step depends on an email or a slow third party, because that shapes the loading, empty, and error states it designs. The steward maps the system; designer designs how its states appear.

## Keep it proportional
Not every flow needs a blueprint. Build one when the experience depends on more than the screen, especially where money, data integrity, integrations, or a human step are involved. A simple, self-contained interaction does not need one, and forcing it wastes the artifact.

## Where the other skills fit
- `user-journeys` is the front-stage companion this sits beneath.
- `edge-cases` works the fragile links this surfaces.
- `bdd-stories` and `roadmap` carry the hardening work.
- designer consumes the blueprint to design honest loading, empty, and error states.

## The one rule
The line of visibility is the point. If the blueprint only documents what the customer already sees, it has not done its job. The value is in what sits just below that line and can break without the interface ever showing why.
