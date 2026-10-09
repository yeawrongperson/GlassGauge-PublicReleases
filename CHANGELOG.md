# GlassGauge Changelog

This page tracks development milestones and actual public releases. Features mentioned in older development notes are not automatically supported on every Mac.

## 0.1.0 Alpha: October 9, 2026

The **first public GlassGauge release** is now available: [GlassGauge 0.1.0 Alpha for Intel Macs](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.0-alpha).

### Included in this release

* Live CPU, GPU, memory, disk, network, battery, fan, temperature, and selected power monitoring, where supported.
* Independent **Intel and Radeon GPU utilization and history** on the tested dual GPU Intel Mac.
* Native **NVMe SMART composite temperature** for the tested internal SSD.
* SQLite telemetry history sampled approximately once per second with **Now, 1h, and 24h** views. History persists through relaunches and is retained for up to approximately 48 hours.
* Honest gaps in charts for intervals when GlassGauge was not collecting data.
* Persisted event Logs for significant events such as launch, sleep and wake, AC or charging changes, GPU availability, and sensor availability.
* Improved battery and power state handling, with cautious wording for measurements whose scope has not been verified.
* Refined native glass window rendering, transparency controls, and clearer measurement terminology.
* The first downloadable Intel x86_64 ZIP: `GlassGauge-0.1.0-alpha-intel.zip`.

### Installation and compatibility notes

* The build is **unsigned and not notarized**. See [Getting Started](docs/GETTING_STARTED.md) for safe first launch instructions.
* Normal monitoring **does not require administrator access**.
* Hardware validation primarily covers **MacBookPro16,1**, the 16 inch 2019 Intel MacBook Pro. Other Intel models need broader testing.
* Dedicated Apple Silicon hardware sensor support is not implemented.
* Battery power flow and the Intel SMC `PSTR` value are not verified as total system or wall power.

**ZIP SHA-256:** `d2576a2ab17042c879fb75d68bdafb35275b3641273fc5e343cd78e2cf984a63`

Read [Known Issues](docs/KNOWN_ISSUES.md) and submit findings through [GitHub Issues](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues).

## October 2026: Monitoring and interface refresh

### Sensor readings

* Updated the monitoring design to distinguish measured readings from unavailable, outdated, or failed data.
* Worked on direct AppleSMC readings for supported Intel Macs, including available fan speeds, temperatures, and selected power information.
* Tested those readings on an Intel MacBook Pro identified as `MacBookPro16,1`.
* Reviewed the way CPU percentages are presented so whole machine CPU activity is not confused with process percentages.
* Investigated battery current, voltage, charging state, and changes between battery and external power.
* Updated the handling of uncertain power readings so they are not described as confirmed total Mac power consumption.

### Design and usability

* Reworked the AppKit backdrop underneath the SwiftUI interface.
* Refined the glass appearance and its transparency setting.
* Continued improving the dashboard and individual metric views.

### Features carried forward from earlier development

The original project already had a live performance dashboard, graph history during a session, detail views, and network traffic charts. Those are part of the foundation, rather than entirely new additions in October 2026.

## 2025: The original GlassGauge preview

GlassGauge began as a macOS system monitor with a modern glass inspired interface. Early development included the main performance overview, graph views, and a desktop layout built around native macOS technology.

I shared an early preview in **r/macapps**, where it reached approximately **146,000 views and 137 shares**. People continued checking on the project afterward. That preview was not a public installer release.

## Future releases

New versions will be documented here with their version number, date, download link, improvements, and known limitations. The development source remains private; this repository distributes builds and public documentation.
