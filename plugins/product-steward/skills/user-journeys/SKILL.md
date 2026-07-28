---
name: user-journeys
description: Map a customer's path through a product over time, the moments that matter, the emotional arc, and where the experience breaks or drops them. Use when the experience feels scattered, when onboarding or a key flow is being reworked, when a feature needs its context, or to find the gaps between what the product does and what the customer needs at each step. Grounds in a persona, maps the stages with what the customer thinks, does, and feels, marks the moments that matter and the drop points, and writes the map into the product's repo. Confirm the product read and the relevant persona first.
---

# User Journeys

A user journey map follows one persona through the product over time, and shows what they are trying to do, what they actually experience, and how they feel at each step. It is the artifact that catches the gaps a feature list cannot: the moment a new user lands on three empty cards and a silent to-do list and feels lost, or the point where a smooth flow suddenly asks for something the person is not ready to give.

A journey belongs to a persona and to the product. Map it for one specific person from the `personas` set, and write it into the **product's own repo**.

A note for any future voice pass: "journey" is a deliberate domain term of art here, drawn from service-design practice, so keep it. It is the established name of this artifact, and the words "user journey" and "journey map" are the terms a practitioner reaches for.

## The build loop

### 1. Pick one persona and one scope
A journey is for one person doing one thing. Name the persona (from `personas`) and the scope: the whole arc from first hearing about the product to habitual use, or a single flow like onboarding, first real result, or renewal. A map that tries to cover every persona and every flow at once shows nothing clearly.

### 2. Set the stages
Lay out the stages the persona moves through, in order. Common shapes: first contact, deciding to try, setting up, first real use, first real result, habit, and the moments where they might leave. Use the stages that fit this product and this flow. `tide`'s "landing on the product today means three $0 cards and a silent to-do list" is a real stage worth spelling out exactly.

### 3. For each stage, capture the three lines
At every stage, using `journey-map-template.md`, record:
- **Doing.** What the person actually does at this step, and what the product does in return.
- **Thinking.** The question in their head, in their words. Often "what do I do now?" or "did that work?"
- **Feeling.** The emotional read: confident, lost, impatient, relieved, suspicious, proud. Track it as an arc across the stages, because the shape of that arc is the experience.

### 4. Mark the moments that matter and the drop points
- **Moments that matter.** The few steps that carry most of the product's promise: the first time the customer feels the thing the product exists to give them. These deserve the most care and the earliest roadmap attention.
- **Drop points.** Where the person stalls, gets confused, loses trust, or leaves. Each one is a gap between what the product does and what the customer needed at that step, and each is a candidate for a value increment.
- **Gaps.** Anywhere the emotional line dips or the thinking line asks a question the product does not answer.

### 5. Turn gaps into work, and write it down
- Write the map into the product's `docs/` (a `journeys/` folder or a `journey-<flow>.md`).
- Each drop point and gap becomes a candidate for `bdd-stories` and a line in the `roadmap`, aimed at the moments that matter first.
- Hand the map to designer as context. A journey tells designer which moment a screen serves and how the person should feel there. designer decides how the screen looks; the journey says what it is for.

## Keep it truthful
- A journey map built from assumption is a hypothesis, so mark which stages are evidenced (from real use, interviews, or support notes) and which are guessed. Guessed stages are the first to verify with a real person.
- The emotional line is the point of the artifact. If every stage reads "neutral," the map is not finished; the person felt something, and finding it is the work.

## Where the other skills fit
- `personas` supplies the person the journey follows.
- `service-blueprint` is the back-stage companion: the journey is what the customer experiences, the blueprint is the system that has to exist to produce it.
- `bdd-stories`, `value-increments`, and `roadmap` all draw their work from the gaps this map finds.
- designer consumes the map for interface context and does not author it.

## The one rule
A journey map exists to find the gap between what the product does and what the customer needed. If it does not surface at least one real gap, either the product is perfect (it is not) or the map is too shallow. Go back to the feeling line.
