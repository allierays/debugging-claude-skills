# Debugging Skills for Claude Code

Three skills that help you debug with Claude Code. Install them globally and use them in any project.

## Skills

### `/source-of-truth [feature-name]`

Research best practices and write a persistent plan file. The file captures how a feature should work, what files are involved, what's been tried, and what works. Context windows compress, but files don't.

```
/source-of-truth login-form
```

### `/unstuck [what you're stuck on]`

Break out of a debugging loop. Reads the source of truth file if one exists, traces the full data flow, and proposes the right solution instead of another quick fix.

```
/unstuck auth callback keeps failing
```

### `/review`

Review your uncommitted changes like a senior engineer with fresh eyes. Runs in a forked context so it has no investment in your approach. Checks for bugs, edge cases, side effects, and missing pieces.

```
/review
```

## Install

Copy the skills to your personal Claude Code skills directory:

```bash
git clone git@github.com:allierays/debugging-claude-skills.git
cp -r debugging-claude-skills/skills/* ~/.claude/skills/
```

Or add the repo as an additional directory so skills stay in sync:

```bash
git clone git@github.com:allierays/debugging-claude-skills.git ~/debugging-claude-skills
claude --add-dir ~/debugging-claude-skills
```

## Requirements

- [Claude Code](https://code.claude.com) v2.1.32 or later

## Related

- [5 Techniques to Debug Claude Code](https://allierays.com/posts/5-techniques-to-debug-claude-code) — the article these skills came from
- [Claude Code Skills Docs](https://code.claude.com/docs/en/slash-commands) — how to create your own skills

## License

MIT
