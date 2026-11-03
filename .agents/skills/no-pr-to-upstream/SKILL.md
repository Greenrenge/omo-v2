---
name: no-pr-to-upstream
description: Hard rule for this machine. NEVER open a pull request, push a branch, or in any way deliver code or docs back to the upstream repos fazulfi/omo-v2 and code-yeongyu/oh-my-openagent. The sanctioned shared remote is the origin fork https://github.com/Greenrenge/omo-v2.git — push local branches there, never PR/merge into the upstreams. Use when about to create a PR, push a branch, or commit to a shared remote.
---

# NO PRs TO UPSTREAM — fazulfi/omo-v2

## The rule

**NEVER open a pull request, push a branch, or deliver anything back to
`fazulfi/omo-v2` (or the upstream `code-yeongyu/oh-my-openagent`). Not even
a "harmless" docs PR. Not even if the maintainer seemingly invited PRs.**

The account `Greenrenge` has **pull-only access** to `fazulfi/omo-v2` — the
earlier attempt to `git push` was rejected by GitHub ("Permission to
fazulfi/omo-v2.git denied to Greenrenge").

**Updated 2026-11-03 by the user:** the fork `Greenrenge/omo-v2` is the ONE
sanctioned shared remote. The local `origin` now points at
`https://github.com/Greenrenge/omo-v2.git` and pushing local branches there is
allowed (and expected as the backup/share channel). Opening or merging PRs on
`fazulfi/omo-v2` or `code-yeongyu/oh-my-openagent` remains forbidden.

## What this forbids

- `gh pr create --repo fazulfi/omo-v2 ...`
- `gh pr create --repo code-yeongyu/oh-my-openagent ...`
- Any push to `fazulfi/omo-v2` or `code-yeongyu/oh-my-openagent` (fetch is fine).
- Opening PRs on any mirror/vendor of the plugin (`oh-my-opencode`,
  `oh-my-openagent`, `lazycodex` npm/GitHub identities).
- Reopening the three PRs this session created (#1, #2, #3 on
  `fazulfi/omo-v2`).

## What is allowed (and expected)

- `git push origin <branch>` where `origin` =
  `https://github.com/Greenrenge/omo-v2.git` (the account's own fork).

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
