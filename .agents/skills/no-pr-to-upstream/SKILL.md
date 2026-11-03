---
name: no-pr-to-upstream
description: Hard rule for this machine. NEVER open a pull request, push a branch, or in any way deliver code or docs back to the upstream repos fazulfi/omo-v2 and code-yeongyu/oh-my-openagent. Work stays strictly local (local branches + local worktrees). Use when about to create a PR, push a branch, or commit to a shared remote.
---

# NO PRs TO UPSTREAM — fazulfi/omo-v2

## The rule

**NEVER open a pull request, push a branch, or deliver anything back to
`fazulfi/omo-v2` (or the upstream `code-yeongyu/oh-my-openagent`). Not even
a "harmless" docs PR. Not even if the maintainer seemingly invited PRs.**

The account `Greenrenge` has **pull-only access** to `fazulfi/omo-v2` — the
earlier attempt to `git push` was rejected by GitHub ("Permission to
fazulfi/omo-v2.git denied to Greenrenge"). Pushing there is impossible anyway;
the fork `Greenrenge/omo-v2` and any PRs from it are also FORBIDDEN by the
user's standing instruction as of 2026-11-03.

## What this forbids

- `gh pr create --repo fazulfi/omo-v2 ...`
- `gh pr create --repo code-yeongyu/oh-my-openagent ...`
- Creating a fork of either repo.
- `git push` to any remote of those repos (`origin`, `fork`, anything).
- Opening PRs on any mirror/vendor of the plugin (`oh-my-opencode`,
  `oh-my-openagent`, `lazycodex` npm/GitHub identities).
- Reopening the three PRs this session created (#1, #2, #3 on
  `fazulfi/omo-v2`).

## What to do instead

Work strictly locally:

- Keep every change in a local branch on the local clone
  `~/.local/...`/`ghq/github.com/fazulfi/omo-v2` or its local worktrees under
  `ghq/github.com/fazulfi/omo-v2-wt/`.
- If the user asks to "share" something, hand over a patch file
  (`git format-patch`) or a plain diff — do NOT push, do NOT open a PR.
- If a task seems to require an upstream change, stop and ask the user.

## Enforcement

Any assistant or script in this environment MUST refuse and stop when a
requested action matches the forbidden list above. Say the rule, refuse, and
offer the local alternative (patch file or local branch).

## Cross-references

- `docs/v2-report-gap.md` in the local worktree
  `ghq/github.com/fazulfi/omo-v2-wt/fix/v2-lsp-mcp-report` — the re-port
  roadmap. Local only; never opened as an upstream PR.
- User instruction 2026-11-03: "change the AGENTS.md or skills that we do not
  never open pr or do anything back to fazulfi/omo-v2!!!!!!!!!!!!"
