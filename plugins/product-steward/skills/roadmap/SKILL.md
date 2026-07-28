---
name: roadmap
description: Build and keep a living now, next, later roadmap organized around customer outcomes, so the product has a spine and the sequence of work is a decision instead of a habit. Use when the order of work is unclear, when the backlog has become a flat undifferentiated pile, when planning what comes after the current increment, or when you need to see the whole shape of where the product is going. Organizes value increments by customer outcome and confidence, keeps dates as capacity-based forecasts, and writes the roadmap into the product's repo as a document that stays accurate. Confirm the product read, pillars, and increments first.
---

# Roadmap

A roadmap is the product's plan for the sequence of customer outcomes it will deliver, held at the altitude of "what changes for the person and roughly when," not "which task on which day." Built well, it lets the product owner see the whole shape of where a product is going and lets any session pick up the next right piece of work. Built badly, it becomes a dated chart nobody believes, obsolete the day after it is drawn.

The roadmap is the product's, organized around its `personas` and `product-pillars`, and written into the **product's own repo**. There is no house roadmap to copy; each product gets its own.

## The build loop

### 1. Organize by outcome
The rows of a roadmap are customer outcomes and the value increments that produce them. "The customer can see her number move the day she logs work" is a roadmap item. "Build the API" is a task hiding inside one. Draw each item from `value-increments`, so every row already names the delight it delivers.

### 2. Use now, next, later, and mean it
Sort the work into three truthful horizons instead of false-precision dates across a year:
- **Now.** In progress or committed next, with a capacity-based delivery forecast attached (see `value-increments`). This is where dates are real, because the work is understood.
- **Next.** Shaped enough to know the outcome and roughly the size, not yet dated. These are the increments waiting for a slot.
- **Later.** Directions the product intends to go, held as outcomes without size or date. Candid about being uncertain.

Confidence drops as you move right, and the roadmap should show that instead of hiding it behind a tidy Gantt chart. A "later" item with a hard date is a lie the product will have to walk back.

### 3. Tie every item to a pillar and a persona
For each roadmap item, name the `product-pillar` it advances and the `persona` it serves. An item that advances no pillar and serves no one in the set is a candidate to cut or to question. This is the roadmap doing its real job: not listing everything possible, but choosing.

### 4. Sequence by the precedence order
When ordering items, use the precedence from `steward-the-product`: the customer's real experience first, then the pillars, then value delivered per increment, then effort and dependencies. Effort and dependencies order the work; they never promote work the customer will not feel over work she will. Cheap and pointless loses to valuable and harder.

### 5. Keep it living, and keep dates accurate
- Write the roadmap into the product's `docs/` as a `roadmap.md` the team and future sessions read and update. The repo is the memory.
- Revisit it when an increment ships or reality shifts. A roadmap that is not updated after a release is already wrong.
- Dates stay capacity-based forecasts with their assumptions attached, only on "now" items. Never let a roadmap manufacture crunch by committing to dates the far-out work has not earned.
- Park cut and deferred items in the dated `backlog.md`, newest first, so the roadmap stays about what the product will do.

## The relationship to designer
The roadmap sequences customer outcomes and the increments that deliver them. It does not schedule design work as a separate track; design is how each increment gets crafted once it is "now." When an increment reaches "now," the steward hands it to designer to give it an interface. The roadmap says which outcomes come in what order; designer crafts each one as it arrives.

## Where the other skills fit
- `value-increments` supply the rows and their capacity-based dates.
- `product-pillars` and `personas` are what each row is tested against.
- `steward-the-product` supplies the precedence order for sequencing.
- `backlog.md` holds what the roadmap deliberately leaves out.

## The one rule
A roadmap is a set of choices about customer outcomes. If every item is a feature and every item has a hard date, it is a plan that will be wrong by next week. Organize by outcome, be candid about confidence, and keep dates only where the work has earned them.
