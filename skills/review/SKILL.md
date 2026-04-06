---
name: review
description: Review the current changes like a senior engineer would. Checks the git diff for bugs, edge cases, missing error handling, and things that might break downstream. Use after implementing a feature or fix, before committing.
context: fork
agent: Explore
---

# Code Review

Review the current uncommitted changes with fresh eyes. You have no context about why these changes were made. Judge them purely on quality.

## Steps

1. **Read the diff.** Run `git diff` to see all uncommitted changes. If there are staged changes, also run `git diff --cached`.

2. **Understand what changed.** For each modified file, read enough of the surrounding code to understand the context. Don't just look at the changed lines.

3. **Review for these issues:**

   **Correctness**
   - Does the logic actually do what it appears to intend?
   - Are there off-by-one errors, null checks, or race conditions?
   - Does it handle edge cases (empty inputs, large inputs, concurrent access)?

   **Side effects**
   - Could these changes break something in another part of the codebase?
   - Are there callers of modified functions that might not expect the new behavior?
   - Do database or API contract changes affect other consumers?

   **Quality**
   - Is the approach the right one, or is it papering over a deeper issue?
   - Is there duplicated logic that should be extracted?
   - Are error messages helpful for debugging?

   **Missing pieces**
   - Are there tests for the new behavior?
   - Are there edge cases that aren't covered?
   - Is there error handling that should exist but doesn't?

4. **Report your findings.** Be specific. Reference file names and line numbers. For each issue, explain:
   - What the problem is
   - Why it matters
   - What the fix should be

If the changes look good, say so. Don't invent problems.
