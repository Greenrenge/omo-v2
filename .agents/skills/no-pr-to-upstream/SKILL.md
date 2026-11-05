---
name: no-pr-to-upstream
description: Private-work rule for this machine (2026-11-05). All omo-v2 work is PRIVATE and lives on the Greenrenge fork origin (https://github.com/Greenrenge/omo-v2.git) — push branches there, integrate by merging them into the fork port/v2 locally. NEVER open PRs on, push to, or comment-deliver to fazulfi/omo-v2 or code-yeongyu/oh-my-openagent; closing our own already-open PRs there is the one allowed exception. Use when about to create a PR, push a branch, or commit to a shared remote.
---

# PRIVATE WORK — the Greenrenge fork is canonical

## The rule

**Updated 2026-11-05 by the user: this work is the private side now. Do not
keep anything inherited from the genuine repos that blocks us, and do not
touch the genuine repos anymore.**

`origin` = `https://github.com/Greenrenge/omo-v2.git` is the canonical
private remote. Feature branches push there and integrate by merging into
the fork's `port/v2` locally (validated: tsgo + build + v2 tests) — no
pull requests anywhere.

## What is allowed

- `git push origin <branch>` and merging validated branches into `origin/port/v2`.
- Fetching from anywhere (read-only).

## What is forbidden

- Opening, reopening, commenting on, or editing PRs on `fazulfi/omo-v2` or
  `code-yeongyu/oh-my-openagent`. (PRs #1–#6 there are closed and stay
  closed; closing our own strays was the one cleanup exception.)
- Any push to `fazulfi/omo-v2` or `code-yeongyu/oh-my-openagent`.
- PRs to mirror/vendor identities of the plugin (`oh-my-opencode`,
  `oh-my-openagent`, `lazycodex` npm/GitHub identities).

## What to do for local work

- Keep every change in a local branch on the local clone
  `~/.local/...`/`ghq/github.com/fazulfi/omo-v2` or its local worktrees under
  `ghq/github.com/fazulfi/omo-v2-wt/`, and share via `origin` pushes when asked.
- If a task seems to require an upstream change, stop and ask the user.

## Enforcement

Any assistant or script in this environment MUST refuse and stop when a
requested action matches the forbidden list above. Say the rule, refuse, and
offer the sanctioned alternative (push to the origin fork) or a patch file.

## Cross-references

- `docs/v2-report-gap.md` (branch `docs/v2-report-gap`, pushed to `origin`) —
  the re-port roadmap.
- User instruction 2026-11-03: "change the AGENTS.md or skills that we do not
  never open pr or do anything back to fazulfi/omo-v2!!!!!!!!!!!!"
- Follow-up 2026-11-03: remote switched to the fork; fork pushes sanctioned.
