# Edge-cases checklist

Walk a story or flow against each row. For each hit, decide: handle now (becomes an
unhappy-path scenario and acceptance criterion), handle later (park in `backlog.md`),
or accept on purpose (record the decision).

## Input
- [ ] Empty, missing, or null
- [ ] Malformed, wrong type, or unexpected format
- [ ] Too long, too short, zero, negative, or enormous
- [ ] Duplicate or repeated submit (double-click)
- [ ] Pasted or injected unexpected content

## State
- [ ] First run and empty account (nothing here yet)
- [ ] Half-finished or abandoned action
- [ ] Stale view, concurrent edit, action taken twice
- [ ] Back button mid-flow, resumed or expired session

## People
- [ ] Person without permission, or who owns nothing yet
- [ ] First day vs. returning after a long absence
- [ ] Does not know the jargon (plain-language path)
- [ ] Keyboard only, screen reader, more time, reduced motion

## Systems
- [ ] Third party down, slow, or rate-limited
- [ ] Integration changed or contract broke
- [ ] Failed write, unsent email, silent sync failure
- [ ] Dependency or step with no owner (from the blueprint)

## Time
- [ ] Timezone and daylight-saving boundaries
- [ ] Expired token, midnight, month boundary
- [ ] Long-running job, race between two events

## Money and integrity (where they apply)
- [ ] Rounding, currency, partial payment, refund
- [ ] A number that must always reconcile
- [ ] Data that must never silently corrupt

---

For each "handle now": write it into the story as a Given / When / Then, and say what
the product does (recover, explain, prevent, or degrade gracefully). Hand the look of
that state to designer.
