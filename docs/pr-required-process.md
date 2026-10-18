# PR-required engineering process

> Org-wide rule for every Pyantasy repository: default-branch changes land only via reviewed pull requests.

## Why this exists

We cancelled paid GitHub branch protection for now (see [Background](#background-pya-73)). We still need one shared, durable rule so humans and agents treat PR + review as normal — not optional — across Shake, Seen, sports games, shared services, and every other product repo.

## The rule

1. **Default branch changes only via pull request**  
   Do not commit or push directly to `main` or `master` as normal practice.

2. **At least one review before merge**  
   A peer agent or a human must review and approve before merge.

3. **Prefer ticket-named feature branches**  
   Example: `feature/pya-74-pr-required-process`.

4. **Treat this as process, not a GitHub guarantee**  
   On GitHub Free **private** repos, GitHub does **not** enforce branch protection the way Team/Enterprise can. This document does **not** claim server-side blocks exist. Discipline and review culture are the control.

## Quick workflow

```bash
# From an up-to-date default branch
git checkout main
git pull origin main
git checkout -b feature/pya-NNN-short-description

# …make changes, commit…

git push -u origin HEAD
gh pr create --title "…" --body "…"
# Request review (peer agent or human), address feedback, then merge
```

## What “done” looks like for a change

- [ ] Work is on a feature branch (prefer ticket id in the name)
- [ ] PR opened against `main` / `master`
- [ ] At least one review (peer agent or human) recorded on the PR
- [ ] CI / checks green when the repo has them (not every repo has CI yet)
- [ ] Merged via the PR — not a direct push to the default branch

## Copying this into a product repo

Org defaults live in this repository (`Pyantasy/.github`). Product repos may also keep a local [`CONTRIBUTING.md`](../CONTRIBUTING.md) copy so contributors see the rule without leaving the project. Prefer linking back here rather than forking conflicting rules.

## Background (PYA-73)

The board cancelled paid GitHub branch protection work tracked as **PYA-73** (*Protect main: require reviewed PRs before merge*). We will **not** upgrade to GitHub Team or convert private product repos to public solely to unlock rulesets.

**PYA-74** publishes this process documentation so the expectation remains org-visible without paid guards.

Internal Paperclip links (company members): [PYA-73](/PYA/issues/PYA-73) · [PYA-74](/PYA/issues/PYA-74)

## Out of scope here

- Enabling GitHub Team, rulesets, or making product repos public
- Per-repo CI implementation (track gaps with the CTO / Software Engineer as needed)
