# Journey slice: [capability]

> Persona: [name, from personas]. Journey: [journey and moment, from user-journeys].
> Roadmap subsection: [what was chosen]. Status: [now / next / later]. Date: [range].

**The capability:** When this lands, [persona] can [do the thing] so that [outcome they
feel], where before they [the old pain or gap].

## Before and after

- **Before:** what the customer cannot do, or what they feel, at the start of this path.
- **After:** what they can do, or feel, once the slice lands. The delta is the capability.

## The path

The steps of the journey this slice touches, in order, front to back. Only the steps the
capability needs; everything else belongs to another slice.

| step | what the customer does | what the product does in return |
|---|---|---|
| [step 1] | | |
| [step 2] | | |
| [...] | | |

## The stories in this slice

The `bdd-stories` that together deliver the whole path. The slice is done when all pass and
the capability holds.

- [ ] [story 1: as persona, I want ... so that ...]
- [ ] [story 2 ...]
- [ ] [...]

## Not in this slice

The refinements pushed to a later slice, so this one stays thin and whole.

- [deferred piece], parked in `backlog.md`.

## Done when

- [ ] Every story's scenarios pass.
- [ ] The accessibility and cognitive-load bar is met.
- [ ] The `ask-support` read is clean, or each support risk is accepted with a reason.
- [ ] A real [persona] can walk the path end to end and reach the capability, with no dead end.
- [ ] The capability sentence above holds true, stated back in the customer's words.
- [ ] The roadmap subsection is moved to shipped.
