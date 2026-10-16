# Improve an agent from evidence

Changing a prompt or instruction file can make behavior easier to steer. It does not retrain the model, create new tool access, or guarantee a future result.

## A small review loop

1. **Choose one observable mismatch.** State what was expected, what happened, and the practical impact. Avoid labels such as “bad” or “lazy.”
2. **Find the controlling source.** Check the current user request, project source, active instruction, and actual tool behavior. Do not assume the first cause that sounds plausible.
3. **Separate the cause.** Was the miss about intent, stale context, source selection, authority, tool capability, execution, verification, or communication?
4. **Change the smallest canonical source.** Fix a confusing instruction or context route in place. Do not add another policy layer if the existing one already says the right thing.
5. **Rerun the same scenario.** Use a short, private or synthetic example. Check that the fix helps without changing a nearby settled behavior.
6. **Retire stale guidance.** Preserve history for lookup, but make clear which source is current.
7. **Measure over time.** Track first-pass acceptance, avoidable rework, human interventions, and mistakes where the data is available. Keep estimates separate from measured results.

## Patterns worth checking

These are useful evaluation scenarios for any assistant, not claims that every assistant has these failures:

- It polishes a response before checking the real source or intended outcome.
- A stale note competes with a newer instruction.
- It loads a large, unrelated record when a small status summary would do.
- It asks for approval to do ordinary work that was already authorized.
- It assumes a connected tool can perform an action or treats a submitted action as verified success.
- It reports certainty where the evidence supports only a hypothesis.

## Keep reviews useful

- Save raw chats and sensitive examples only in the owner's private system.
- Preserve what is still uncertain; do not turn one incident into a universal rule.
- Compare before and after with the same scenario when possible.
- Do not claim improvement from a document edit alone. Look for fewer repeated misses in later work.
