# Blueprint: [flow], under [journey]

> Anchored to journey: [name]. Persona: [name]. Date: [date].

| Customer step | Front stage (sees / does) | Back stage (out of sight) | Systems & integrations | Support processes |
|---|---|---|---|---|
| [step 1] | [screen, message, action] | [calc, write, job, email queued] | [auth, db, API, task] | [human or one-time config] |
| [step 2] | | | | |
| [...] | | | | |

- **Line of interaction:** where the customer touches the product (top of the table).
- **Line of visibility:** everything below the front-stage column, unseen but depended on.

## Fragile links

- **[step]**: [what can break: unowned step, third-party failure, forgotten config, single point of failure]. Hardening candidate: [edge-cases pass / story / roadmap item].
- [...]

## Handoffs

- To `edge-cases`: [which fragile links to work].
- To designer: [which steps need honest loading, empty, or error states].
