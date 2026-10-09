# Known Issues and Limitations

**Updated October 9, 2026**

This page explains what GlassGauge can and cannot do right now, and which behaviors deserve a bug report.

**GlassGauge 0.1.2 Alpha is available now for Intel Macs.** [Download it here](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.2-alpha). These notes describe the current third public alpha, its known limitations, and areas that need additional testing.

[Back to GlassGauge](../README.md) | [Roadmap](ROADMAP.md) | [Report an issue](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues)

## Known limitations

### Apple Silicon hardware support is not ready

The current hardware sensor system is designed around a tested Intel Mac. A dedicated Apple Silicon sensor implementation is not yet in place. Some general macOS information may still be available, but temperature, fan, and power support is not guaranteed.

**Plan:** Add and test a reliable hardware provider for supported Apple Silicon Macs.

### Some readings may not be available

Different Mac models expose different hardware information. On the primary tested Intel Mac, **independent Intel and Radeon GPU utilization/history** and **internal NVMe SMART composite SSD temperature** are available. Those readings may not be supported on other Macs. Some machines also have no fans or internal battery.

**Plan:** Test more models, use additional reliable data sources where possible, and always explain missing data clearly.

### Power readings need careful labels

An available battery watt reading describes energy entering or leaving the battery. It is not automatically the Mac's total power use. The meaning of one Intel SMC power measurement still needs more validation.

**Plan:** Keep source information clear and avoid calling a value total system power unless its meaning is verified.

### History is saved, but has a limited retention window

Normal telemetry is stored using SQLite, approximately once per second. **Now, 1h, and 24h** views are available. Readings persist across app relaunches, with retention of up to approximately **48 hours**. If GlassGauge was not collecting readings, the missing period is shown as a gap, not invented data.

**Plan:** Continue verifying history retention, chart performance, and how the app handles interruptions on more Macs.

### Compatibility has not been broadly verified

Hardware sensor validation primarily centers on the 16 inch 2019 Intel MacBook Pro (MacBookPro16,1). The release specifies macOS 13.5 or later, but broader Intel model compatibility still needs verification.

**Plan:** Test more Intel Mac models and expand the published compatibility guidance based on confirmed results.

### The first alpha is unsigned and not notarized

**0.1.2 Alpha is already downloadable** as an Intel ZIP. It is unsigned and not notarized, so macOS may block first launch. Read [Getting Started](GETTING_STARTED.md) for the Finder and Privacy & Security options.

**Plan:** Continue improving the release and distribution process. Do not disable Gatekeeper globally to install the alpha.

### Local diagnostics and saved history

GlassGauge can generate local diagnostic reports. Nothing is uploaded automatically, and the user decides whether to save or share a report. Reports deliberately exclude personal files, credentials, and network identifiers, but review the generated content before attaching it to a public issue.

**Clear Graph History** and **Clear Event Log** are separate actions. The Overview also has a Clear History shortcut. Use these deliberately when you no longer want the corresponding saved information.

### Optional battery energy behavior

When enabled, Reduce Energy Use on Battery can temporarily display a Solid background and pause inactive chart rendering while external power is disconnected. **Normal telemetry and history collection continue.** Appearance and chart preferences return on reconnecting external power. This behavior uses the external power connection state, not whether the battery says it is charging.

### Energy Cell inactive presentation hotfix

Version 0.1.2 fixes the Battery Energy Cell shimmer stopping merely because another application gained focus while **Live charts while inactive** was enabled. The animation still pauses when inactive presentation is disabled or the optional battery energy saving override applies. Hidden, minimized, closed, and fully occluded windows should avoid unnecessary animation work. Reduce Motion behavior is unchanged.

## Things still being checked

**Window appearance:** The glass rendering system was revised after an earlier visual artifact. The revised design has passed some development checks, but appearance during window resizing, display changes, and real use still needs manual testing.

**Battery behavior:** Battery and charging data can update at different speeds inside macOS. The app has improved how it handles this, but unusual power transitions still need more testing.

**Startup and permissions:** Normal monitoring does not require administrator access. Optional legacy helper diagnostics, where present, are separate and may request permission if explicitly used. Continue reporting unexpected prompts or launch problems.

These are testing areas. They are not claims that every user will experience a problem.

## What is normal and not necessarily a bug?

**A missing fan reading:** Many Macs do not have a fan, and not every model exposes fan information.

**An unavailable sensor:** A blank or unavailable value can be the correct result when the Mac does not provide a reliable measurement. It is better than a made up number.

**Different CPU percentages:** An individual application may use more than 100 percent of one CPU core's capacity while total Mac CPU use remains below 100 percent. Those views measure different things.

**Gaps in saved charts:** GlassGauge preserves recorded readings across relaunches, but periods when the app was not collecting data remain empty. Data older than the approximately 48 hour retention window is removed.

## What should I report as a bug?

For the public alpha, reports like these are especially useful:

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
