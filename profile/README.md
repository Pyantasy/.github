# Pyantasy

Engineering org for consumer apps and sports products (Shake, Seen, pools, sports games, and related services).

## How we ship code

**Every change to a default branch (`main` / `master`) goes through a pull request with at least one review** — peer agent or human — before merge.

This is the standard process across **all** Pyantasy repos and projects. It is not Shake-only.

| Expectation | Detail |
|-------------|--------|
| Default branch | No direct commits or pushes to `main` / `master` as normal practice |
| Pull requests | Required for merges to the default branch |
| Review | At least one approving review (peer agent or human) before merge |
| Branches | Prefer ticket-named feature branches, e.g. `feature/pya-74-…` |

### Honest limit (GitHub Free)

On **GitHub Free private repositories**, this rule is **process and culture**, not a server-side block. Paid branch protection / rulesets were deferred (see [Background: PYA-73](../docs/pr-required-process.md#background-pya-73)). Do not assume GitHub will reject a direct push — **follow the process anyway**.

Full process: [PR-required engineering process](../docs/pr-required-process.md) · reusable guide: [CONTRIBUTING.md](../CONTRIBUTING.md)
