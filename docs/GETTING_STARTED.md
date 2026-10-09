# Getting started with GlassGauge 0.1.1 Alpha

[Home](../README.md) / Getting Started

**GlassGauge 0.1.1 Alpha is available for Intel Macs.** This is an early test release. Hardware compatibility beyond the primary tested machine is not guaranteed.

## Download

Get the official [GlassGauge 0.1.1 Alpha Intel ZIP](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/download/v0.1.1-alpha/GlassGauge-0.1.1-alpha-intel.zip) from the [GitHub release page](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.1-alpha).

The file is named `GlassGauge-0.1.1-alpha-intel.zip`. This release provides a ZIP, not a DMG.

**SHA-256:** `fb00686f46ba6672d82df7db21ec355989cb94530ed45a5e3040b557943e35e5`

## Install on an Intel Mac

1. Download the ZIP from the official GitHub release.
2. In Finder, double click the ZIP to extract **GlassGauge.app**.
3. Move **GlassGauge.app** into your Applications folder if you want to keep it there.
4. Open GlassGauge. Because **0.1.1 Alpha is unsigned and not notarized**, macOS may warn you or prevent the first launch.
5. If macOS blocks it, find GlassGauge.app in Finder, **right click the app and choose Open**, then confirm the option to open if offered.
6. Alternatively, after attempting to open the app, go to **System Settings > Privacy & Security** and choose **Open Anyway** for GlassGauge if macOS offers that option. Confirm only if you intentionally downloaded the official file.
7. Open the app and review the available monitoring views. **Normal monitoring does not require administrator access.**

The exact wording of macOS security prompts can vary by OS version. **Do not disable Gatekeeper globally, run terminal commands to remove quarantine, or install unrelated software** to open GlassGauge. If macOS still refuses to launch it, [report the issue](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues) with your Mac model and macOS version.

## Compatibility

The alpha is built for **Intel Macs (x86_64)**. Hardware sensor testing has focused on the **16 inch 2019 Intel MacBook Pro (MacBookPro16,1)**. Other Intel Macs may work, but individual readings can differ. Dedicated Apple Silicon hardware sensor support is not implemented. The 0.1.1 release specifies **macOS 13.5 or later**. Compatibility testing beyond the primary validated Intel Mac remains limited.

Read [Compatibility](COMPATIBILITY.md) and [Known Issues](KNOWN_ISSUES.md) before reporting a missing sensor.

## New in 0.1.1

Settings includes local **Export Diagnostic Report**, **Copy Diagnostic Summary**, and **Report an Issue** tools. Reports are not automatically uploaded. Choose whether to save or attach a report, and review it before sharing. Personal files, credentials, and network identifiers are intentionally excluded.

Appearance settings offer **Glass** and **Solid** backgrounds, an option to keep charts updating when GlassGauge is inactive, and optional **Reduce Energy Use on Battery**. While running on battery, the energy setting can temporarily switch to Solid and pause inactive chart rendering. Telemetry collection and stored history continue, and normal preferences return when external power is connected.

You can separately clear graph history and the event log, or use the Overview Clear History shortcut.

## What to expect

* Live CPU, GPU, memory, disk, network, battery, fan, temperature, and selected power monitoring, when supported by your Mac.
* Separate Intel and Radeon GPU utilization on compatible dual GPU Intel systems.
* Now, 1h, and 24h views with SQLite history retained for up to approximately 48 hours. Periods when the app was not recording remain gaps.
* A persistent Logs feed for significant power, sleep, launch, and sensor events.
* Early alpha bugs and model specific missing sensors are possible.
* Battery flow and Intel SMC PSTR are **not** confirmed whole system or wall outlet power readings.

## Optional download integrity check

You can compare the SHA-256 value of the ZIP with the published checksum. The release includes a `.sha256` companion asset.

[See the release notes](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.1-alpha) | [Report an issue](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues/new)
