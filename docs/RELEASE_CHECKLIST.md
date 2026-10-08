# Public beta release checklist

[Home](../README.md) / Release Checklist

This is a project-maintenance checklist, not a claim that the first beta has already passed these gates.

## Build and package

- [ ] Freeze the intended release source revision and record its commit.
- [ ] Confirm the app's minimum macOS version and architecture support.
- [ ] Verify Release configuration, code signing, entitlements, and any helper bundling.
- [ ] Create the public `.app` package and installer archive (`.dmg` or `.zip`).
- [ ] Validate installation and launch on a clean test environment.
- [ ] Complete the Developer ID notarization workflow, if applicable, and verify Gatekeeper behavior.
- [ ] Generate and verify an SHA-256 checksum for the final artifact.

## Function and accuracy

- [ ] Test CPU, GPU, memory, disk, and network values.
- [ ] Validate battery/AC state on a supported portable Mac.
- [ ] Verify supported fan/thermal readings; show unsupported as unavailable.
- [ ] Confirm no guessed/wrongly labeled power readings are published.
- [ ] Test idle usage, prolonged sampling, history, graphs, and menu-bar controls.
- [ ] Test cold launch, window resizing, multiple displays, and app quitting/reopening.
- [ ] Validate helper/authorization behavior with a standard user account.

## Trust and communication

- [ ] Finish privacy/data-flow audit and update [Privacy & Security](PRIVACY_AND_SECURITY.md).
- [ ] Publish a specific supported-device/macos matrix.
- [ ] Capture final interface screenshots from the same beta build.
- [ ] Publish versioned release notes and a real known-issues list.
- [ ] Provide installation and removal instructions.
- [ ] Create GitHub Release with the exact installer and checksum.
- [ ] Verify the public link in a signed-out browser session.

## After publishing

- [ ] Monitor GitHub Issues for installation, security, and data-correctness problems.
- [ ] Update compatibility information based on confirmed reports.
- [ ] Keep [CHANGELOG.md](../CHANGELOG.md) tied to *actual* tagged releases.
