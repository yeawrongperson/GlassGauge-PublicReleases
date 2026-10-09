# Getting started with GlassGauge 0.1.0 Alpha

[Home](../README.md) / Getting Started

**GlassGauge 0.1.0 Alpha is available for Intel Macs.** This is an early test release. Hardware compatibility beyond the primary tested machine is not guaranteed.

## Download

Get the official [GlassGauge 0.1.0 Alpha Intel ZIP](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/download/v0.1.0-alpha/GlassGauge-0.1.0-alpha-intel.zip) from the [GitHub release page](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.0-alpha).

The file is named `GlassGauge-0.1.0-alpha-intel.zip`. This release provides a ZIP, not a DMG.

**SHA-256:** `d2576a2ab17042c879fb75d68bdafb35275b3641273fc5e343cd78e2cf984a63`

## Install on an Intel Mac

1. Download the ZIP from the official GitHub release.
2. In Finder, double click the ZIP to extract **GlassGauge.app**.
3. Move **GlassGauge.app** into your Applications folder if you want to keep it there.
4. Open GlassGauge. Because **0.1.0 Alpha is unsigned and not notarized**, macOS may warn you or prevent the first launch.
5. If macOS blocks it, find GlassGauge.app in Finder, **right click the app and choose Open**, then confirm the option to open if offered.
6. Alternatively, after attempting to open the app, go to **System Settings > Privacy & Security** and choose **Open Anyway** for GlassGauge if macOS offers that option. Confirm only if you intentionally downloaded the official file.
7. Open the app and review the available monitoring views. **Normal monitoring does not require administrator access.**

The exact wording of macOS security prompts can vary by OS version. **Do not disable Gatekeeper globally, run terminal commands to remove quarantine, or install unrelated software** to open GlassGauge. If macOS still refuses to launch it, [report the issue](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues) with your Mac model and macOS version.

## Compatibility

The alpha is built for **Intel Macs (x86_64)**. Hardware sensor testing has focused on the **16 inch 2019 Intel MacBook Pro (MacBookPro16,1)**. Other Intel Macs may work, but individual readings can differ. Dedicated Apple Silicon hardware sensor support is not implemented. A minimum supported macOS version has not yet been established for general release claims.

Read [Compatibility](COMPATIBILITY.md) and [Known Issues](KNOWN_ISSUES.md) before reporting a missing sensor.

## What to expect

* Live CPU, GPU, memory, disk, network, battery, fan, temperature, and selected power monitoring, when supported by your Mac.
* Separate Intel and Radeon GPU utilization on compatible dual GPU Intel systems.
* Now, 1h, and 24h views with SQLite history retained for up to approximately 48 hours. Periods when the app was not recording remain gaps.
* A persistent Logs feed for significant power, sleep, launch, and sensor events.
* Early alpha bugs and model specific missing sensors are possible.
* Battery flow and Intel SMC PSTR are **not** confirmed whole system or wall outlet power readings.

## Optional download integrity check

You can compare the SHA-256 value of the ZIP with the published checksum. The release includes a `.sha256` companion asset.

[See the release notes](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.0-alpha) | [Report an issue](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues/new)
