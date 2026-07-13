# product-steward

Your portable **product steward** for Claude Code, a plugin you add to any product's repo to get a product owner's and product manager's craft on tap.

The whole thing is built around one objective:

> **Keep the customer experience at the heart of everything the product builds, and stop webs from having to repeat, by hand, every product-ownership move she already knows.**

It reads what a product already is and who it serves, respects the product decisions already made, and helps make the next ones on purpose: who the build is for, what the product stands for, what to build next, and how the customer will feel the difference. Every artifact lands in the product's own repo.

---

## What it does, and where it stops

The steward and [designer](https://github.com/weberswords/designer) both ride along in a Claude Code session, alongside the product's repo, and both write into that repo. They do not overlap, because they work at different altitudes.

| | **product-steward** | **designer** |
|---|---|---|
| Owns | what to build, why, for whom, and when | how it looks, feels, and behaves |
| Produces | personas, pillars, journeys, blueprints, BDD stories, roadmap, value increments, delivery dates | design system, tokens, brand kit, UX craft, copy, motion, design jam |
| Answers | is this the right thing, and will the customer feel it | is the thing we decided on crafted well |

The handoff runs one way most of the time. The steward decides a piece of work is worth building and hands designer a value increment with its stories, acceptance criteria, and journey context. designer gives that decided work an interface. When designer needs to know who the user is, it reads the steward's persona rather than inventing one. When the steward needs a feature to feel a certain way, it names the outcome and lets designer choose the craft.

---

## What's inside

This repo is a [Claude Code plugin marketplace](https://code.claude.com/docs/en/plugin-marketplaces) that ships one plugin, `ih-product-steward`.

### The `ih-product-steward` skills

- **`steward-the-product`** — the prime directive and entry point. Reads what the product is and who it serves, sets the precedence order for product decisions (the customer's real experience always wins), draws the boundary with designer, and routes to the right skill. Encodes how webs works: plans of intent before the code, a dated backlog, and the repo as the memory. **Start here.**
- **`personas`** — build and maintain the small set of real people the product is for, with their jobs to be done, what they need to trust and do, and what would make them feel behind. Never a stock "Sarah Chen."
- **`product-pillars`** — name the few enduring commitments the product stands for, so every feature has something concrete to be tested against.
- **`user-journeys`** — map the customer's path over time, the moments that matter, the emotional arc, and where the experience breaks or drops them.
- **`service-blueprint`** — map the system behind the experience: front stage, back stage, and the support that has to exist for the experience to hold.
- **`bdd-stories`** — turn decided work into buildable Given, When, Then user stories with acceptance criteria, each tied to a persona and a journey moment.
- **`roadmap`** — build and keep a living now, next, later roadmap organized around customer outcomes, not a dated Gantt chart nobody believes.
- **`value-increments`** — slice work vertically into increments that each deliver something the customer can feel, name the delight before the tasks, and set a capacity-based, sustainable delivery date.
- **`edge-cases`** — surface the unhappy paths, failure modes, and edge conditions for a story or feature before they surface in production.

> **product-steward has no roadmap of its own.** You point it at a product, say a repo called `tide`, and its job is to read `tide`, help shape `tide`'s product decisions, and write the personas, stories, and roadmap into **`tide`'s repository**. Two products the steward touches should end up with their own product thinking, not copies of each other's.

### How the skills work together

```
steward-the-product ─▶ read the product, its customer, and its promise
      │
      │   route to what the product needs next:
      │     who is it for?         ─▶ personas
      │     what does it stand for? ─▶ product-pillars
      │     how does it feel over time? ─▶ user-journeys ─▶ service-blueprint
      │     what do we build?       ─▶ bdd-stories (+ edge-cases to harden)
      │     in what order?          ─▶ roadmap
      │     shipped as what?        ─▶ value-increments (+ capacity-based date)
      │
      │   precedence when product decisions conflict (higher wins):
      │     1. the customer's real experience
      │     2. the product's stated pillars and promise
      │     3. the product's own existing artifacts
      │     4. value delivered per increment
      │     5. effort and sequencing
      ▼
  write it into the product's repo ─▶ hand the crafted work to designer
```

There is no house roadmap in that order. The steward builds each product its own.

---

## Install

In any product where you use Claude Code:

```
/plugin marketplace add studiowlabs/product-steward
```

Then install it:

```
/plugin install ih-product-steward@product-steward
```

Update the catalog later with:

```
/plugin marketplace update product-steward
```

Pair it with designer for the full picture:

```
/plugin marketplace add weberswords/designer
/plugin install ih-designer@designer
```

## Use

Once installed, just do product work and the skills activate by description. Or invoke explicitly:

- `/ih-product-steward:steward-the-product` to start any product task the right way.
- `/ih-product-steward:personas` to define or extend who the product is for.
- `/ih-product-steward:product-pillars` to name what the product stands for.
- `/ih-product-steward:user-journeys` to map the experience over time and find its gaps.
- `/ih-product-steward:service-blueprint` to map the system behind the experience.
- `/ih-product-steward:bdd-stories` to turn decided work into buildable stories.
- `/ih-product-steward:roadmap` to build and keep a living roadmap.
- `/ih-product-steward:value-increments` to package a release and set a sustainable date.
- `/ih-product-steward:edge-cases` to harden a story before it ships.

A typical run: add your product repo alongside `product-steward` and `designer` in a Claude Code session, let the steward read what's there and route to what the product needs next, and let it write the artifacts into your product's `docs/`, ready for designer to craft.

---

## Making it yours

`ih-product-steward` is authored to be edited. It encodes *how webs works*, not a process to impose:

- Tune the questions the skills ask and the templates they write in each skill's `SKILL.md` and its template files.
- Adjust the precedence order and the boundary with designer in `steward-the-product/SKILL.md`.
- Add your own skills under `plugins/ih-product-steward/skills/<name>/SKILL.md` and they ship with the plugin.

It deliberately ships **no default personas, pillars, or roadmap.** The steward builds each product its own.

## License

MIT, see [`LICENSE`](./LICENSE).
