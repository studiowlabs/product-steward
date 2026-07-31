# Support read: [slice or increment]

> The support agent's view of the finished work. Persona: [name]. Date: [date].
> The question: will this raise escalation and contact volume, and where.

## Is it clear? (confusion tickets)

- **Risk:** [where a person will not understand what something means or what happened].
  **Likely ticket:** "[what they write in]". **Fix:** [remove / recoverable / clear / document], [the change].
- [...]

## Can they break it? (accidental-damage tickets)

- **Risk:** [where a person acting in good faith can destroy or lose something].
  **Likely ticket:** "[what they write in]". **Fix:** [the change, preferring remove or recoverable].
- [...]

## Can they get stuck? (bad-state escalations)

- **Risk:** [where a person can land in a state they cannot get out of on their own].
  **Likely ticket:** "[what they write in]". **Fix:** [the change, preferring a self-serve way out].
- [...]

## Verdict

- **Net effect on ticket volume:** [lower / neutral / higher] than before this shipped, because [why].
- [ ] Every risk is removed, made recoverable, made clear, or accepted with the reason written here.
- [ ] The clarity and recoverability fixes are carried as `bdd-stories` acceptance criteria.
- [ ] Anything that deletes, charges, or changes account state has a confirmation or a way back.
