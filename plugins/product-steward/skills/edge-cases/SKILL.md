---
name: edge-cases
description: Surface the unhappy paths, failure modes, and edge conditions for a story or feature before they surface in production, so the product holds up when things go wrong instead of only when they go right. Use when hardening a BDD story, reviewing a value increment before it ships, blueprinting a flow with fragile links, or whenever a feature has only been described in its happy path. Works a structured checklist across input, state, people, systems, time, and access, and feeds the real risks back as unhappy-path scenarios and hardening work. Confirm the story or flow first.
---

# Edge Cases

Most product work is described in its happy path: the person does the expected thing, in the expected state, and gets the expected result. Production is where the other paths show up, the empty account, the double-click, the expired session, the third party that is down, the person using a keyboard and a screen reader, the value that is zero or negative or enormous. Thinking about edge cases early is one of the specific product-ownership moves webs does by habit, and the one this skill exists to make sure never gets skipped.

Edge cases are found against a specific story or flow, and the results are written into the **product's own repo** as unhappy-path scenarios and hardening work.

## The pass

Take one story (`bdd-stories`) or one flow (`user-journey` and `service-blueprint`) and walk it against the checklist in `edge-cases-checklist.md`. The checklist runs across the places failures actually come from:

- **Input.** Empty, missing, malformed, too long, too short, zero, negative, enormous, duplicate, the wrong type, an injection attempt, a paste of unexpected content.
- **State.** First-run and empty state, the account with nothing in it yet, the half-finished action, the stale view, the concurrent edit, the action taken twice, the back button mid-flow, the resumed session.
- **People.** The person without permission, the person who owns nothing, the person on their first day, the person who has been away for a month, the person who does not know the jargon, the person who needs a keyboard, a screen reader, more time, or reduced motion.
- **Systems.** The third party that is down, slow, or rate-limited, the integration that changed, the failed write, the queued email that never sent, the sync that silently failed, the dependency with no owner (draw these from the `service-blueprint` fragile links).
- **Time.** The timezone, the daylight-saving boundary, the expired token, the thing that happens at midnight, the long-running job, the race between two events, the "what happens on the second of the month."
- **Money and integrity, where they apply.** The rounding, the currency, the partial payment, the refund, the number that must always reconcile, the data that must never silently corrupt.

For each place, ask the plain question: what happens if this goes wrong here, and does the product handle it in a way the customer can live with?

## From risk to work

Not every edge case is worth building for. Triage each one:
- **Handle now.** It is likely, or its failure is unacceptable (lost money, corrupted data, a person locked out, a broken moment that matters). This becomes an unhappy-path scenario in the story and part of its acceptance criteria.
- **Handle later.** It is real but rare and survivable. Park it in the dated `backlog.md` with a one-line why, so the repo remembers.
- **Accept.** It is not worth guarding against, and that is a decision recorded on purpose, not an oversight. Say so, so no one relitigates it later.

Write the "handle now" cases back into the `bdd-stories` as their own Given, When, Then scenarios. A story is not done when the happy path works; it is done when it holds up when things go wrong.

## Keep the customer in it
An edge case handled badly is still a customer experience. The empty state is a real screen a real new person sees, and it is a chance to teach rather than to show a blank. The error message is copy a stressed person reads. The steward names what the product should do in each case (recover, explain, prevent, degrade gracefully); designer crafts how that recovery looks and reads. The unhappy path is not an exception to the customer experience; it is part of it.

## Where the other skills fit
- `bdd-stories` receive the "handle now" cases as scenarios.
- `service-blueprint` supplies the systems and integration failures.
- `value-increments` include the hardening work in the increment's done.
- `backlog.md` holds the "handle later" cases.
- designer crafts the empty, loading, and error states the steward specifies.

## The one rule
Every story and every increment gets at least one real pass against the checklist before it ships. The happy path is the smaller half of the work; the product earns trust in the other half.
