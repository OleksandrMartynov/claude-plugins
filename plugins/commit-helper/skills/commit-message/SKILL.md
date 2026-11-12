---
name: commit-message
description: Write a Conventional Commits message for the currently staged git changes. Use when the user asks for a commit message, wants help describing their changes, or says "commit message" / "what should I write for this commit".
---

# Commit message

Generate a concise, accurate commit message for the user's staged changes.

## Steps

1. Run `git diff --staged --stat` and `git diff --staged` to see what is staged.
   - If nothing is staged, tell the user and offer to look at `git diff` (unstaged) instead. Do not stage files yourself.
2. Run `git log -5 --oneline` to match the repository's existing style and scopes.
   - Also check for project conventions in `CLAUDE.md` or `CONTRIBUTING.md` (message language, allowed scopes, ticket-ID prefixes) and follow them. If recent commits are written in a language other than English, write the message in that language.
   - If the current branch name contains a ticket ID (e.g. `feature/ABC-123-login`) and recent commits reference ticket IDs, add it to the footer as `Refs: ABC-123`.
3. Decide the commit type: `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, or `chore`.
4. Write the message in this format:

   ```
   <type>(<optional scope>): <summary in imperative mood, max 72 chars>

   <optional body: what changed and why, wrapped at ~72 chars>
   ```

## Rules

- Summary: imperative mood ("add", not "added"), no trailing period, lowercase after the colon.
- Explain the *why* in the body when it is not obvious from the diff; skip the body for trivial changes.
- Mark breaking changes with `!` after the type/scope and a `BREAKING CHANGE:` footer.
- Describe only what is actually in the diff — never invent changes.
- Avoid vague summaries such as "update code", "fix stuff" or "misc changes": name the concrete behavior or component that changed.
- Mention in the body when the diff includes added or changed tests, or when it changes behavior without any test changes.
- If the diff mixes unrelated changes, say so and suggest splitting into separate commits.

## Output

Show the proposed message in a code block. Do not run `git commit` unless the user asks you to.
