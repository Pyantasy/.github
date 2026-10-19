# Contributing to Pyantasy repos

> One rule for every Pyantasy project: **change the default branch only through a reviewed pull request.**

## 5-second version

| Do | Don’t |
|----|--------|
| Branch from `main` / `master` | Push commits straight to `main` / `master` |
| Open a PR | Merge your own unreviewed work as normal practice |
| Get ≥1 review (peer agent or human) | Assume GitHub will block a direct push |
| Prefer `feature/pya-…` branch names | Invent a different merge path per product |

Full process: [docs/pr-required-process.md](docs/pr-required-process.md).

## Workflow

1. Sync the default branch and create a feature branch named for the ticket when you have one:

   ```bash
   git checkout main && git pull
   git checkout -b feature/pya-NNN-short-description
   ```

2. Commit focused changes. Keep secrets out of the tree.

3. Push and open a pull request:

   ```bash
   git push -u origin HEAD
   gh pr create
   ```

4. Request review from a peer agent or human. Address feedback.

5. Merge only after review approval (and after repo checks pass, when CI exists).

## Honest limit (GitHub Free)

Private repos on **GitHub Free** do **not** get enforceable branch protection / required-review rulesets without a paid upgrade. This contributing guide is **process**, not a claim that GitHub will reject direct pushes. Follow it anyway.

Paid guards were deferred after [PYA-73](/PYA/issues/PYA-73). See [docs/pr-required-process.md](docs/pr-required-process.md#background-pya-73).

## Using this file in another repo

You can copy this `CONTRIBUTING.md` into a product repository, or add a short local stub that links to:

`https://github.com/Pyantasy/.github/blob/main/CONTRIBUTING.md`

Keep product-specific build/test steps in that repo’s README; keep this merge process consistent org-wide.

## iOS versioning

Native iOS apps use SemVer for marketing versions. See [docs/ios-versioning.md](docs/ios-versioning.md) and start new apps from [templates/ios-app/](templates/ios-app/).
