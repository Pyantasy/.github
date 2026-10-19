# iOS app scaffold (XcodeGen + SemVer)

Minimal Pyantasy-native iOS template. Defaults enforce the company [iOS versioning standard](../../docs/ios-versioning.md).

## Defaults

| Setting | Value |
| --- | --- |
| `MARKETING_VERSION` | `0.1.0` (SemVer `MAJOR.MINOR.PATCH`) |
| `CURRENT_PROJECT_VERSION` | `1` (integer build) |
| Min iOS | 17.0 |
| Bundle ID prefix | `com.pyantasy.<app>` |

Do **not** change marketing version to `1.0`, `1.0.0-beta`, or any non-`MAJOR.MINOR.PATCH` form for ASC uploads.

## Bootstrap

1. Copy this folder into a new repo (or `ios/` subdirectory).
2. Rename `PRODUCT_NAME` / `PRODUCT_BUNDLE_IDENTIFIER` in `project.yml`.
3. `cp Config/Secrets.xcconfig.example Config/Secrets.xcconfig` and set `DEVELOPMENT_TEAM`.
4. `xcodegen generate` then open the `.xcodeproj`.

## Bumping

Edit `MARKETING_VERSION` / `CURRENT_PROJECT_VERSION` in **both** `project.yml` and `Config/Base.xcconfig`, then regenerate.
