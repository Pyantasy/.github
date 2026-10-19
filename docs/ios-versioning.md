# Pyantasy iOS versioning (SemVer)

Company standard for every first-party iOS app. Source of truth for App Store Connect marketing versions and build numbers.

## Mapping

| Concept | Xcode / plist | Required form |
| --- | --- | --- |
| Marketing version | `MARKETING_VERSION` → `CFBundleShortVersionString` | SemVer **`MAJOR.MINOR.PATCH`** only |
| Build number | `CURRENT_PROJECT_VERSION` → `CFBundleVersion` | Monotonically increasing **integer** (not SemVer) |

Shipped App Store / TestFlight marketing versions must **not** include SemVer pre-release (`-beta.1`) or build metadata (`+sha`). Apple rejects non-numeric marketing versions. Track pre-release intent with git tags, TestFlight groups, or internal changelogs.

## Bump rules

| Change | Bump |
| --- | --- |
| Breaking UX / API / contract for users or clients | **MAJOR** |
| Backward-compatible feature | **MINOR** |
| Bug fix / internal hardening only | **PATCH** |
| Every archive / CI release candidate | Increment **build** (`CURRENT_PROJECT_VERSION`) |

## Defaults for new apps

- Prefer XcodeGen `project.yml` as source of truth; regenerate `project.pbxproj` after bumps.
- New apps start at **`0.1.0`** (pre-1.0) unless intentionally GA-ready, then **`1.0.0`**. Document the choice in the app README.
- Build starts at **`1`**.
- Info.plist must reference `$(MARKETING_VERSION)` and `$(CURRENT_PROJECT_VERSION)` — never hard-code `1.0` / two-part versions when using a custom plist (`GENERATE_INFOPLIST_FILE: NO`).

## Scaffold

Use the org template: [`templates/ios-app/`](../templates/ios-app/).

```bash
# From a product repo root (example):
cp -R path/to/Pyantasy/.github/templates/ios-app/. .
# Edit PRODUCT_BUNDLE_IDENTIFIER / PRODUCT_NAME in project.yml
xcodegen generate
```

## Per-app README pointer

Add a short “Versioning” section linking here:

`https://github.com/Pyantasy/.github/blob/main/docs/ios-versioning.md`

## Out of scope

- Android / Flutter marketing schemes (unless the shipping iOS target is native XcodeGen)
- ASC listing copy / ASO
- Board-owned secrets and privacy URLs
