---
name: source-of-truth
description: Research best practices and write a persistent source of truth file for a feature. Use when starting a new feature, debugging a complex problem, or when context keeps getting lost between sessions.
argument-hint: "[feature-name]"
disable-model-invocation: true
---

# Build a Source of Truth File

Create a persistent plan file that survives context compression. This file becomes the single reference point for how a feature should work, what's been tried, and what we know.

## Steps

1. **Research best practices.** Search the web for how `$ARGUMENTS` is typically implemented. Check official docs, find real-world examples, and identify common patterns and pitfalls.

2. **Read the codebase.** Find all files related to `$ARGUMENTS` in this project. Understand the current implementation, architecture, and dependencies.

3. **Write the source of truth file** to `docs/plans/$ARGUMENTS.md` with these sections:

```markdown
# [Feature Name] — Source of Truth

## Best Practices
Patterns and approaches from research. What the community recommends.

## How It Should Work
End-to-end description of the correct behavior. Expected inputs, outputs, edge cases.

## Files Involved
Each file that touches this feature and its responsibility.

## What We've Tried
Every approach attempted so far and why it failed. Add to this section as work continues.

## What Works
Things we know are correct and should not be changed.
```

4. **Report back** with a summary of what you found and wrote.

## Important

- If `docs/plans/$ARGUMENTS.md` already exists, read it first and update it rather than overwriting.
- Be specific in the "What We've Tried" section. Include file names, line numbers, and error messages.
- The "What Works" section prevents regressions. Don't skip it.
