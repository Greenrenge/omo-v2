---
name: no-pr-to-upstream
description: Contribution rule for this machine. Contributions to fazulfi/omo-v2 are fork-branch pull requests from the Greenrenge account — push branches to the fork origin (https://github.com/Greenrenge/omo-v2.git), then gh pr create against fazulfi/omo-v2. Direct pushes to fazulfi/omo-v2 are pull-only and stay forbidden, as does anything toward code-yeongyu/oh-my-openagent. Use when about to create a PR, push a branch, or commit to a shared remote.
---

# PRs TO UPSTREAM VIA THE FORK — fazulfi/omo-v2

## The rule

**Contributions to `fazulfi/omo-v2` go through pull requests from the
`Greenrenge` fork. Push branches to the fork, open PRs from it.**

**Updated 2026-11-04 by the user: PRs upstream CAN be done on the Greenrenge
account.** Opening pull requests on `fazulfi/omo-v2` from
`Greenrenge/<branch>` heads is allowed. The GitHub access level is unchanged:
direct pushes to `fazulfi/omo-v2` are still rejected (pull-only), which is why
every contribution is a fork-branch PR.

## What this allows

- `git push origin <branch>` where `origin` =
  `https://github.com/Greenrenge/omo-v2.git` (the account's own fork).
- `gh pr create --repo fazulfi/omo-v2 --head Greenrenge:<branch> ...`
- Commenting on, editing, closing and reopening PRs on `fazulfi/omo-v2`
  (including the earlier PRs #1–#3, which are legitimate under this rule).

## What is still forbidden

- Any direct push to `fazulfi/omo-v2` (GitHub rejects it; fetch is fine).
- Any push or PR to `code-yeongyu/oh-my-openagent` (the true upstream) —
  extend this rule explicitly if that ever changes.
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
