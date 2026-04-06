---
name: unstuck
description: Break out of a debugging loop. Reads the source of truth file if one exists, examines the full data flow, and proposes the right solution rather than another quick fix. Use when you've been going in circles or when fixes keep breaking other things.
argument-hint: "[what you're stuck on]"
disable-model-invocation: true
---

# Get Unstuck

Stop fixing the symptom. Think holistically about what's actually going wrong.

## Steps

1. **Check for a source of truth file.** Look in `docs/plans/` for any file related to `$ARGUMENTS`. If one exists, read it first. Pay attention to the "What We've Tried" section so you don't repeat failed approaches.

2. **Read the full data flow.** Don't just look at the file with the error. Trace the complete flow end to end. Read every file involved in `$ARGUMENTS`. Understand the architecture, not just the stack trace.

3. **Identify the real problem.** Ask yourself:
   - Is this a symptom or the root cause?
   - Would fixing this break something downstream?
   - Is there a wrong assumption buried in the code?
   - Are we patching around a design problem?

4. **Propose the right solution.** Not the fastest fix. The correct, scalable one. Explain:
   - What the root cause actually is
   - Why previous attempts failed (if applicable)
   - What the right fix looks like and why it won't break other things
   - What files need to change

5. **Update the source of truth file** if one exists. Add what you found to the "What We've Tried" section.

## Important

- Do NOT start editing files immediately. Think first, propose, then implement only after explaining your approach.
- If you've already tried fixing this more than twice, something is wrong with the approach, not the implementation. Step back further.
- Use "think hard" if the problem is complex. Take the time to reason through it.
