---
name: git-backup
description: Commits and pushes wiki changes to the git repository with a descriptive, diff-based commit message — checking for remote conflicts first and confirming with the user before staging any deletion or pushing. Use whenever the user asks to back up, save a version, commit changes, or sync the wiki repository.
---

# Git Backup Skill

> The safety rule "never delete wiki pages" (see `../_shared/wiki-conventions.md`) extends here to git history: never run destructive git commands without explicit confirmation.

## Purpose
Backup and version control the knowledge wiki.

## Trigger
Use when the user asks to: back up, save a version, commit changes, or sync the repository. Run this when explicitly asked — don't auto-run it after every Ingest/Research/Maintenance run, though it's fine to ask "want me to back this up to git now?" once one of those finishes.

## Assumptions
- The repository root is the wiki root (same folder as `index.md`).
- Default branch is whatever `git status` reports as currently checked out — don't switch branches.
- Assume the remote repository is private unless the user says otherwise. If this is the first push to a given remote, say so and let the user confirm visibility before proceeding.

## Workflow
1. **Check status.** Run `git status`. If this isn't a git repository, stop and tell the user (don't auto-run `git init`).
2. **Sync first.** Run `git fetch` and compare local vs. remote. If the local branch has diverged from the remote (remote has commits you don't have), stop and report this to the user — do not merge, rebase, or force-push automatically.
3. **Review changes.**
   - List modified, added, and deleted files from `git status`.
   - If any files show as `deleted:`, stop and list them explicitly — ask the user to confirm before staging, since this will permanently record the deletion in git history. This applies even though deletions might be legitimate (e.g. the user actually removed a file on purpose) — the point is to never silently commit a deletion.
4. **Stage** the confirmed changes (`git add` on the specific files, or `git add .` only once deletions have been confirmed or there are none).
5. **Generate a descriptive commit message from the actual diff**, not a fixed string — e.g. "Add 3 entity pages, update index.md and log.md" or "Update concepto/inteligencia-artificial.md, fix frontmatter". Never use a generic placeholder like `"update wiki"`.
6. **Commit.**
7. **Confirm before push.** Pushing sends data to a remote/external location — tell the user what's about to be pushed (commit message + file count) and wait for a go-ahead, unless the user has already given a standing instruction to always push automatically.
8. **Push** to the current branch's remote.
9. **Report the result**: commit message, files included, and whether the push succeeded.

## Recommended repository hygiene
- Suggest adding `raw/` to `.gitignore` if it isn't already — original source documents (especially copyrighted ones) usually shouldn't be committed to version control history.

## Rules
- Never delete user data — this includes never running destructive commands (`git reset --hard`, `git push --force`, `git clean`) without an explicit, separate confirmation from the user for that specific command.
- Always check changes before committing (step 3) — never blindly stage everything.
- Keep commit messages descriptive and generated from the actual change, never a fixed placeholder.
- Always confirm before push (step 7).
