# Public release checklist

[Home](../README.md) / Release Checklist

GlassGauge 0.1.0, 0.1.1, and 0.1.2 Alpha have shipped as unsigned, not notarized Intel ZIP releases. This remains a maintainer checklist for future improvements, not a claim that every item has been completed.

## Build and package

* [ ] Freeze the intended release source revision and record its commit.
* [ ] Confirm the app's minimum macOS version and architecture support.
* [ ] Verify Release configuration, code signing, entitlements, and any helper bundling.
* [x] Package the 0.1.0, 0.1.1, and 0.1.2 Alpha `.app` builds inside their published Intel `.zip` files.
* [ ] Validate installation and launch on a clean test environment.
* [ ] Future goal: Developer ID signing and notarization. **All three published Alpha builds are unsigned and not notarized.**
* [x] Publish and verify the SHA256 checksums for the 0.1.0 and 0.1.1 Alpha ZIPs.

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
* [ ] Expand the compatibility matrix beyond the primary validated MacBookPro16,1 and test the stated macOS 13.5 or later requirement more broadly.
* [ ] Capture current alpha screenshots from the same public build.
* [ ] Publish versioned release notes and a real known issues list.
* [ ] Provide installation and removal instructions.
* [x] Publish all three alpha releases with their exact ZIPs and checksums. Keep 0.1.0 available as the historical first release.
* [ ] Verify the public link in a logged out browser session.

## After publishing

* [ ] Monitor GitHub Issues for installation, security, and data accuracy problems.
* [ ] Update compatibility information based on confirmed reports.
* [ ] Keep [CHANGELOG.md](../CHANGELOG.md) tied to *actual* tagged releases.
