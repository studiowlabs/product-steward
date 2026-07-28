---
name: tidy-the-docs
description: Read an accumulated pile of product documentation, condense the decisions worth keeping into concise records, prune what is no longer needed, and reorganize the rest so a human can actually navigate it. Use when pointing the steward at a repo for the first time, when a docs folder has grown into a heap of stale plans and superseded notes, or when nobody can tell which document still describes how the product works. Produces a structured Docs Read, then a proposed cleanup plan you approve before anything is changed. Condenses without losing the decision or its reasoning, and trusts git for the full history. The product-docs counterpart to designer's detect-design-system.
---

# Tidy the Docs

A product accumulates documentation the way a desk accumulates paper. Plans of intent get written before the code, serve their purpose, and then sit there after the work ships. Decisions get made across three notes that half-contradict each other. A newcomer, or the next session, opens `docs/` and cannot tell which document still describes the product and which is a fossil. This skill is the first-contact pass that turns that pile back into something a human can read, without throwing away the reasoning that makes the repo the memory.

This is the product-docs counterpart to designer's `detect-design-system`. designer reads a project's design system before touching it; this reads a product's decision record before touching it. The two do not overlap: designer tidies tokens and components, the steward tidies plans, decisions, and backlogs.

## The one thing this skill will not do

It will not quietly destroy a decision. Condensing is the point, and condensing means keeping the decision and the reasoning while cutting the scaffolding around them. The thinking stays. Two rules hold the whole skill:

- **Propose before you change.** Produce the Docs Read and the cleanup plan, show them, and get a nod before deleting, merging, or rewriting anything. The product owner did not write these docs for a bot to bulldoze.
- **git is the archive.** The full text of every old doc lives in git history forever. That means a superseded plan can be condensed to its decision and the verbose original removed, without losing anything, and without leaving an `archive/` folder of dead markdown that clutters the repo or leaks onto a deploy. Do not build an archive folder unless the product owner asks for one.

## The loop

### 1. Read the whole pile first
Inventory every document before judging any of it. For each file in `docs/` (and stray `.md` notes elsewhere in the repo), read enough to answer:
- What is this, and when was it written or last touched (from the file and from git log)?
- Does it still describe how the product works or why a decision was made, or has the code moved past it?
- What decision or reasoning does it hold that would be lost if it vanished?
- Does it overlap or conflict with another doc?

Read the git history alongside the files. A plan whose feature shipped three merges ago is historical; a plan for work still in flight is live. The commit log tells you which.

### 2. Produce the Docs Read
Summarize the pile as a compact, structured read, using `docs-read-template.md`. Classify each document:
- **Live.** Still describes the product or a plan in flight. Keep, and only tighten if it has gone loose.
- **Shipped.** A plan of intent whose work is done. The plan is spent, but the *decision and the why* inside it are worth keeping. Condense to a decision record.
- **Superseded.** A later doc or a later decision has overtaken it. Condense anything still-true into the record that replaced it, then remove the original.
- **Reference.** Setup notes, conventions, glossaries that stay useful. Keep, and move to where a human would look for them.
- **Duplicate or conflicting.** Two or more docs covering the same ground. Merge into one true version, and record which decision won.
- **Cruft.** Scratch notes, dead ends, and abandoned drafts that hold no decision worth keeping. Candidate to remove.

The Docs Read ends with a one-line verdict on the whole folder: is it broadly current, partly stale, or a heap that has stopped being read.

### 3. Propose the cleanup plan
Turn the read into a plan of specific actions, each with its reason, and show it before doing any of it:
- **Condense** [doc] into a decision record.
- **Merge** [docs] into one, keeping [which decision].
- **Rewrite** [doc] for a human, cutting [what] and keeping [what].
- **Remove** [doc], because its decision is now captured in [where], and git holds the original.
- **Keep** [doc] as is.

Flag anything you are unsure about rather than deciding it silently. If a doc might still be doing real work, say so and ask. When a removal is the right call, say where its decision now lives, so the plan shows nothing is lost.

### 4. Condense, keeping the why
For each doc being condensed, write a short decision record using `decision-record-template.md`: what was decided, why, what it replaced, and the date. A good record is a few sentences that a person reading the repo in six months can understand without the original ten-page plan. Keep the reasoning that would otherwise have to be reconstructed, and cut the process, the throat-clearing, and the parts the code now documents itself.

Follow the product's conventions while you condense:
- Decision records read in the house voice: complete sentences, the Oxford comma, no em dashes, plain language over jargon.
- Deferred and parked ideas belong in the dated `backlog.md`, newest first, gathered in that one place.
- A plan of intent that is still live stays in the plan-of-intent shape (see `value-increments`); only shipped plans collapse to records.

### 5. Organize for a human
Give the folder a structure someone can navigate, adapted to the repo rather than imposed on it:
- A short **`docs/README.md`** (or index) that says what is in the folder and where to look: the live plans, the decision records, the backlog, the reference notes.
- A **decisions log** (a `decisions.md`, or a `decisions/` folder for a larger product) holding the condensed records, newest first, so the product's reasoning is readable in one place.
- The **live plans** kept where work in flight is easy to find.
- The **`backlog.md`** as the single home for parked and deferred work.
- **Reference notes** grouped where a human would look for them.

Honor whatever organization the repo already has that works. The goal is a folder a newcomer can read top to bottom and understand the product's decisions. Restructure only where it serves that reader.

### 6. Execute and commit in readable steps
Once the product owner approves the plan, make the changes and commit them in logical groups (condense one cluster, merge a set of duplicates, remove the spent originals), so the cleanup itself is a readable diff and any single step can be undone. The repo stays the memory; this pass just makes the memory legible.

## When there is nothing to tidy
If the read shows the docs are already current and legible, say so and stop. A repo with a clean, small `docs/` does not need a reorganization, and inventing one wastes the pass. This skill is worth running only when the pile has gotten ahead of the reader.

## Where the other skills fit
- `steward-the-product` routes here first when a repo arrives with an accumulated doc pile, before building new artifacts on top of an unread one.
- `value-increments` owns the plan-of-intent shape that live plans keep and that shipped plans condense from.
- `roadmap` and `backlog.md` receive any still-open work the cleanup surfaces.
- designer's `detect-design-system` and `design-audit` do the same first-contact and consistency work for the design system. Keep to the product side here.

## The one rule
Condense, do not erase. Every document removed has its decision captured somewhere a human will find it, and its full text still in git. If a cleanup would lose the reasoning behind a decision, it is not a cleanup; it is amnesia.
