# Common Agent Guidelines

This document contains shared guidelines that apply to all projects. It is automatically referenced by AGENTS.md and should always be loaded.

## Task Sizing

Estimate the size of every change using t-shirt sizing:

| Size | Lines of change | Action |
|------|----------------|--------|
| XS | < 50 | Proceed directly |
| S | 50–250 | Proceed directly |
| M | 250–750 | Proceed directly |
| L | 750–2,500 | Proceed directly |
| XL | > 2,500 | **Stop — split into increments first** |

If the estimate is XL, create a work file in `work/` that decomposes the task into L-or-smaller increments, then work through them one PR at a time. See [incremental-work.md](incremental-work.md) for the work file format.

## Work Files

Check `work/` for an active task file on the same topic before starting new work. If one exists, resume from the first unchecked task. **Never pick up a work file unless the user explicitly asks you to work on that topic.**

## Git Commits

- Never auto-commit changes. Always ask the user before committing.
- Before committing, re-read `AGENTS.md` to load any required context documents for the changes being committed.

## Git Push

Always push using the HTTPS URL directly (SSH keys are typically not available):

```bash
git push https://github.com/[ORG]/[REPO].git
```

Replace `[ORG]/[REPO]` with the actual repository path. Check `git remote -v` if unsure.
