---
name: ask-support
description: View finished or about-to-ship work through the eyes of the support agent who will field the tickets, and ask whether it raises escalation and contact volume, because something is not clear, because someone can accidentally break something, or because a person can get their account into a bad state they cannot get out of. Use as a gate before an increment or a slice ships, when a flow touches destructive actions, money, or account state, or whenever you want to catch the support cost of a design before customers pay it. Produces a short support read: the likely tickets, and for each the fix, routed to stories, edge-cases, or the roadmap. Confirm the work is decided or built before running the gate.
---

# Ask Support

Every unclear label, every irreversible click, and every way to land in a stuck state becomes someone's support ticket. ask-support is the gate that catches that cost before the customer pays it, and before it lands in a support queue. It looks at finished or about-to-ship work the way the support agent will, and asks a different question from "does it work." It asks what people will write in about when it works exactly as built.

This is a gate, so run it on decided or built work, near ship, over the whole slice or increment. It writes its read into the **product's own repo**, next to the work it judges.

## The three questions

Walk the finished work and ask each of these from the support agent's seat.

1. **Is it clear?** Where will a person not understand what something means, what just happened, or what to do next. Unclear labels, silent results, jargon before the plain idea, and a state the person cannot read all become "how do I," "what does this mean," and "why did it do that" tickets.
2. **Can they break it?** Where can a person, acting in good faith, destroy or lose something they wanted. An irreversible delete with no confirmation, an action whose effect is bigger than it looks, and a default that quietly discards work all become "I did not mean to" and "can you undo this" tickets.
3. **Can they get stuck?** Where can a person land in an account or data state they cannot get out of on their own. A half-finished setup with no way back, a setting that locks them out, a record in a state no screen can edit, and a dead end with no next move all become escalations, because only a human with backend access can free them.

## Fix in order of preference

For each risk the three questions surface, pick the earliest fix that applies. A ticket that never happens beats a ticket that resolves fast.

1. **Remove it.** Make the bad state unreachable, or the action non-destructive. The risk that cannot occur needs no support.
2. **Make it recoverable, self-serve.** Give the person the way out: an undo, an edit, a clear path back, a self-serve reset. A person who can fix it themselves does not contact anyone.
3. **Make it clear.** Plain copy, a confirmation on the destructive step, a visible and readable state, the plain idea before the jargon. A question that never arises files no ticket.
4. **Document the answer, last resort.** When a risk cannot be removed, recovered, or clarified, give support a written answer so the ticket resolves in one reply instead of an investigation. This is the floor, not the goal.

## The support read

Write a short read with the likely tickets and their fixes, using `support-read-template.md`. Route each fix to where it belongs: a clarity fix is usually a copy or state change in the `bdd-stories`, a recoverability fix is often a new story or an `edge-cases` scenario, and a larger safety or bad-state fix is a `roadmap` item. Close with the net effect on ticket volume, and whether it is lower, neutral, or higher than before the work shipped.

## The relationship to edge-cases

`edge-cases` hardens the build against failure modes: the empty state, the invalid input, the third party that is down, the permission the person lacks. ask-support looks one step later, at the human cost after the work ships even when it works: the confusion, the self-inflicted damage, and the stuck states that generate contact. The two overlap and feed each other. Run `edge-cases` to harden the build, and ask-support to protect the support queue and the person's trust.

## The relationship to designer

ask-support names the support risk and the outcome the fix has to reach; it does not draw the confirmation dialog or write the final microcopy. When the fix is "make the destructive step confirm" or "make this state readable," name that outcome and hand the craft to designer. Keep the gate at the product altitude: which risks raise contact volume, and what has to change to lower it.

## Keep it proportional

A read-only view that cannot change anything carries little support risk, so a light pass is enough. Spend the gate where the cost lives: anything that deletes, charges, changes account state, or sets up something the person depends on later. The more a screen can do to a person's data or money, the harder this gate should look.

## Where the other skills fit
- `value-increments` and `deliver-a-slice` run this gate before an increment ships.
- `bdd-stories` carry the clarity and recoverability fixes as scenarios and acceptance criteria.
- `edge-cases` harden the failure modes this gate's stuck-states point at.
- `roadmap` holds the larger safety and recoverability work the gate surfaces.
- designer crafts the confirmations, states, and copy the fixes call for.

## The one rule
Every risk the support agent can name gets removed, made recoverable, or made clear before ship, or it is accepted with a reason written down. If the only answer to a risk is "support will explain it," the design is not done.
