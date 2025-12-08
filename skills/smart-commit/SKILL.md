---
name: smart-commit
description: Handle git commits interactively with message suggestions. Use when user asks to commit changes, create branches, squash commits, or stage files. Generates 2-3 commit message options and commits WITHOUT Claude attribution footer.
allowed-tools: Bash, Read, Grep, AskUserQuestion
---

# Smart Git Commit Skill

Guide user through git commit process with intelligent defaults.

## Workflow

1. Run `git status` and `git diff --staged` to understand changes
2. If unstaged changes exist, ask which files to stage using AskUserQuestion
3. Generate 2-3 commit message options:
   - Option 1: Concise (1 line summary)
   - Option 2: Detailed (summary + bullet points)
   - Option 3: Conventional commit format (feat/fix/refactor:)
4. User picks a message or provides their own
5. Commit WITHOUT Claude attribution (no 🤖 emoji, no Co-Authored-By footer)

## Supported Operations

- Simple commits
- Create new branch before commit
- Squash with previous commits (interactive rebase)
- Exclude specific files/patterns
- Amend previous commit

## Message Style

Generate messages that:
- Focus on "why" not "what"
- Use imperative mood ("Add feature" not "Added feature")
- Keep first line under 72 characters

## Example Commit Message Options

For a change that refactors session handling:

**Option 1 (Concise):**
```
refactor: simplify session initialization sequence
```

**Option 2 (Detailed):**
```
refactor: simplify session initialization sequence

- Move TCPDirect attribute config to gateway level
- Remove duplicate validation logic
- Consolidate stack manager setup
```

**Option 3 (Conventional):**
```
refactor(session): consolidate initialization logic

Reduces code duplication between TCPDirectStackManager
and TCPDirectInitializer by centralizing attribute config.
```
