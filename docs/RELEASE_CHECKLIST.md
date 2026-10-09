# Public release checklist

[Home](../README.md) / Release Checklist

GlassGauge 0.1.0 Alpha has shipped as an unsigned, not notarized Intel ZIP. This list is a continuing maintainer checklist for future release improvements, not a claim that every item was completed for 0.1.0 Alpha.

## Build and package

* [ ] Freeze the intended release source revision and record its commit.
* [ ] Confirm the app's minimum macOS version and architecture support.
* [ ] Verify Release configuration, code signing, entitlements, and any helper bundling.
* [x] Package the 0.1.0 Alpha `.app` inside the published Intel `.zip`.
* [ ] Validate installation and launch on a clean test environment.
* [ ] Future goal: Developer ID signing and notarization. **0.1.0 Alpha is unsigned and not notarized.**
* [x] Publish and verify the SHA256 checksum for the 0.1.0 Alpha ZIP.

## Function and accuracy

* [ ] Test CPU, GPU, memory, disk, and network values.
* [ ] Validate battery/AC state on a supported portable Mac.
* [ ] Verify supported fan/thermal readings; show unsupported as unavailable.
* [ ] Confirm no guessed/wrongly labeled power readings are published.
* [ ] Test idle usage, prolonged sampling, history, graphs, and menu bar controls.
* [ ] Test cold launch, window resizing, multiple displays, and app quitting/reopening.
* [ ] Validate helper/authorization behavior with a standard user account.

## Trust and communication

* [ ] Finish privacy/data flow audit and update [Privacy & Security](PRIVACY_AND_SECURITY.md).
* [ ] Expand the compatibility matrix beyond the primary validated MacBookPro16,1; minimum macOS version is not yet published.
* [ ] Capture final interface screenshots from the same beta build.
* [ ] Publish versioned release notes and a real known issues list.
* [ ] Provide installation and removal instructions.
* [x] Create GitHub Release with the exact 0.1.0 Alpha Intel ZIP and checksum.
* [ ] Verify the public link in a logged out browser session.

## After publishing

* [ ] Monitor GitHub Issues for installation, security, and data accuracy problems.
* [ ] Update compatibility information based on confirmed reports.
* [ ] Keep [CHANGELOG.md](../CHANGELOG.md) tied to *actual* tagged releases.
