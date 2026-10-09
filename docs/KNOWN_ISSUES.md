# Known Issues and Limitations

**Updated October 8, 2026**

This page explains what GlassGauge can and cannot do right now, and which behaviors deserve a bug report.

**No public beta is available yet.** The notes below describe the current development version and the testing still needed before release.

[Back to GlassGauge](../README.md) | [Roadmap](ROADMAP.md) | [Report an issue](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues)

## Known limitations

### Apple Silicon hardware support is not ready

The current hardware sensor system is designed around a tested Intel Mac. A dedicated Apple Silicon sensor implementation is not yet in place. Some general macOS information may still be available, but temperature, fan, and power support is not guaranteed.

**Plan:** Add and test a reliable hardware provider for supported Apple Silicon Macs.

### Some readings may not be available

Different Mac models expose different hardware information. GPU usage and disk temperature were unavailable through the verified reading path on the Intel Mac used for current development tests. Some Macs also have no fans or no internal battery.

**Plan:** Test more models, use additional reliable data sources where possible, and always explain missing data clearly.

### Power readings need careful labels

An available battery watt reading describes energy entering or leaving the battery. It is not automatically the Mac's total power use. The meaning of one Intel SMC power measurement still needs more validation.

**Plan:** Keep source information clear and avoid calling a value total system power unless its meaning is verified.

### History is not fully saved between launches

Live charts and time range controls are present, but reliable saved history across app restarts has not been finished. A visible 24 hour option does not mean 24 hours of stored data is always available.

**Plan:** Add reliable history storage and explain exactly how much information is retained.

### Compatibility has not been broadly verified

Current sensor testing centers on one Intel MacBook Pro. Supported macOS versions and wider device compatibility still need to be confirmed using the actual release build.

**Plan:** Test more Mac models and publish a compatibility list before beta distribution.

### The downloadable beta is not ready

Packaging, signing, notarization, and installation testing are part of the release checklist. There is no verified public installer to download yet.

**Plan:** Publish the installer and installation instructions on the GitHub Releases page after validation.

## Things still being checked

**Window appearance:** The glass rendering system was revised after an earlier visual artifact. The revised design has passed some development checks, but appearance during window resizing, display changes, and real use still needs manual testing.

**Battery behavior:** Battery and charging data can update at different speeds inside macOS. The app has improved how it handles this, but unusual power transitions still need more testing.

**Startup and permissions:** Normal monitoring is designed to run without installing a privileged helper. Optional legacy helper controls are separate. The packaged beta still needs a complete permissions and startup review.

These are testing areas. They are not claims that every user will experience a problem.

## What is normal and not necessarily a bug?

**A missing fan reading:** Many Macs do not have a fan, and not every model exposes fan information.

**An unavailable sensor:** A blank or unavailable value can be the correct result when the Mac does not provide a reliable measurement. It is better than a made up number.

**Different CPU percentages:** An individual application may use more than 100 percent of one CPU core's capacity while total Mac CPU use remains below 100 percent. Those views measure different things.

**Charts without older data:** Until persistent history is implemented, information from a previous app session may not be available.

## What should I report as a bug?

When beta testing begins, reports like these will be especially useful:

* GlassGauge crashes, freezes, or becomes unresponsive.
* Charts stop updating even though the rest of the app is running.
* A value looks clearly wrong or is labeled as measured when the reading is unavailable.
* Battery or charging labels contradict a reliably observed state.
* The window, menus, or controls render incorrectly or cannot be used.
* Installation fails on a Mac model and macOS version listed as supported.

These are examples of reportable behavior, not a statement that each bug has been reproduced.

When reporting a problem, please include your Mac model, processor, macOS version, GlassGauge version, a short description, and steps to reproduce. A screenshot can help.

Please **do not post your serial number, personal information, passwords, or unedited diagnostic logs** in a public issue.

[Open GitHub Issues](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues)

## The approach

GlassGauge should be useful even when it cannot show everything. If a measurement is unavailable or uncertain, it should say so. Accuracy and clear explanations matter more than filling every tile with a number.
