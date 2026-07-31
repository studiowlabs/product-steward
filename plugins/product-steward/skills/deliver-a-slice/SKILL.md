---
name: deliver-a-slice
description: Take a subsection of the roadmap and drive it end to end into a delivered value increment anchored in a new customer capability, by cutting it into a thin user-journey slice, turning that slice into BDD stories, packaging it as one value increment, and handing it to the build. Use at the start of a body of work or a build conversation, when you want the session to end with something the customer can now do rather than a pile of half-built features, or when a roadmap "next" item needs to become buildable, capability-anchored work. Reads the roadmap, cuts a journey slice, draws its stories, sets the delight and the date, and closes on the capability. Confirm the product read and the roadmap first, and draw stories from bdd-stories.
---

# Deliver a Slice

A body of work should end with a sentence a customer would recognize: "now I can do the thing I could not do before." This skill is the through-line that makes that happen. It takes a subsection of the `roadmap`, cuts it into a thin slice of a `user-journey`, turns that slice into `bdd-stories`, packages it as one `value-increment`, and hands it to the build, so the work is organized around a capability the customer gains rather than a collection of features that may never add up to one.

The other product-steward skills each own a step. This skill owns the line through them. It starts at the roadmap and does not stop until there is a delivered capability, or a clear plan of intent for one, written into the **product's own repo**.

## Why this skill exists

Feature-first delivery fails in a specific way. The team ships a schema, then a form, then an endpoint, and three weeks later the customer still cannot do anything new, because no single slice ever cut through the whole stack. Work measured in features rewards motion. Work measured in capabilities rewards the customer. This skill holds the second measure by refusing to start a build until the capability it delivers is named, and refusing to call it done until the customer can feel that capability.

## The delivery loop

### 1. Read the roadmap and choose one subsection
Start from the product's `roadmap`. Pick one coherent subsection to deliver: often the top "next" item, or a small set of "next" items that together add up to a single capability. The test of a good subsection is that you can name, in one sentence, the customer capability it produces:
> *"This subsection delivers: [persona] can now [capability] so that [outcome they feel]."*

If the subsection is a grab bag of unrelated items, it is not a slice, so narrow it until it names one capability. If you cannot write that sentence at all, the roadmap subsection is not ready to build, and the work is to shape it here before any story is written.

### 2. Cut the journey slice
A journey slice is a thin vertical cut of a `user-journey`: the specific path the customer walks to get the new capability, from the moment they need it to the moment they have it. It is one path through the journey, and it cuts through the whole stack. Take the relevant journey, or the drop point or moment that matters the subsection serves, and trace only the steps this capability touches, front to back, using `journey-slice-template.md`.

- **Anchor it.** Name the persona (from `personas`) and the journey moment (from `user-journeys`) the slice cuts through, so it stays attached to a real experience.
- **State the before and the after.** The slice is defined by the change: what the customer could not do, or felt, at the start, and what they can do, or feel, at the end. That delta is the capability.
- **Keep it whole and thin.** The slice stands on its own with no "coming soon" dead end inside it, and it pushes every refinement the capability does not need to a later slice.

### 3. Turn the slice into stories
Draw the `bdd-stories` that make the slice real, each with its persona, its "so that," its Given, When, Then scenarios, and its unhappy paths from an `edge-cases` pass. The stories are the buildable behaviors, and together they have to deliver the whole slice, with no step of the customer's path left unbuilt. A story that does not move the customer along the slice belongs to a different piece of work.

### 4. Package it as one value increment
Hand the slice and its stories to `value-increments`: name the delight as the specific sentence of what the customer feels, confirm the increment ships whole, and set a capacity-based, sustainable date. The slice and the increment are the same body of work seen two ways, the slice as the customer's path and the increment as the shippable unit. Write the plan of intent (`plan-of-intent-template.md`) before the build, so the developer has a clear aim and the next session can see the whole shape.

### 5. Hand it to the build, and close on the capability
Hand the increment to the developer with its stories, its acceptance criteria, and its journey context intact, and to designer for the interface. The steward says what ships and why; designer says how it looks and feels. The body of work is done when the stories pass and the capability sentence from step 1 holds true for a real person, not when a task list is empty. Close by stating the delivered capability back in the customer's words, and update the `roadmap` to move the subsection from next to shipped.

## The unit of done is a capability, not a task list

A slice is finished when the customer can do the new thing end to end. A slice that shipped three of its five stories delivered no capability, so it delivered nothing the customer can feel yet, whatever code landed. When capacity runs short, cut the slice thinner, a smaller capability that is still whole, rather than shipping a partial path that dead-ends. A thin whole slice beats a wide broken one.

## Keep it proportional

Not every roadmap item needs the full loop. A one-line copy fix or a config change ships on its own. Reach for this skill when a subsection is big enough that feature-first delivery would lose the customer in the middle of it, which is most work worth planning. When a slice turns out to be two capabilities wearing one name, split it and deliver the one that lands soonest first.

## Where the other skills fit
- `roadmap` is where the slice is chosen from, and where the delivered capability is recorded.
- `user-journeys` is the map the slice is cut from; the slice is one thin path through it.
- `personas` supplies the person the slice serves.
- `bdd-stories` turn the slice into buildable, verifiable behaviors.
- `edge-cases` supply the unhappy paths the stories have to hold.
- `value-increments` package the slice into a shippable unit with a sustainable date.
- `steward-the-product` sets the precedence order when subsections compete for next, and the voice every artifact follows.
- designer takes the decided slice and crafts its interface.

## The one rule
Never start a build until you can name the capability the slice delivers, and never call it done until a real customer can do that thing end to end. If the work does not add up to something the customer can now do, it is a pile of features, and the slice is not shaped yet.
