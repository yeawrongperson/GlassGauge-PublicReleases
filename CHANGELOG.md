# GlassGauge Changelog

This page tracks development milestones and actual public releases. Features mentioned in older development notes are not automatically supported on every Mac.

## 0.1.3 Alpha: October 9, 2026

Small branding and polish release. [Download GlassGauge 0.1.3 Alpha](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.3-alpha).

### Changed

* Introduced the redesigned GlassGauge application icon.
* Updated the app's visual identity around its telemetry and charting design language for the Dock, Finder, and other macOS surfaces.

No intentional changes to sensor collection, telemetry, chart/history behavior, battery semantics, Energy Cell behavior, energy settings, glass window architecture, or diagnostics. The 0.1.2 Battery Energy Cell fix remains intact.

**Compatibility:** Intel Macs only (`x86_64`), macOS 13.5 or later. Apple Silicon is not supported. Unsigned and not notarized. Sensor availability varies by Intel model.

**ZIP:** `GlassGauge-0.1.3-alpha-intel.zip` (3,159,366 bytes). **SHA-256 (GitHub asset digest):** `0415c742c7586403b9805ea520441f17403af2cbdd097f1061b69191c963f721`.

## 0.1.2 Alpha: October 9, 2026

Small behavioral hotfix. [Download GlassGauge 0.1.2 Alpha](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.2-alpha).

### Fixed

* Battery page Energy Cell shimmer now follows the same inactive window presentation policy as GlassGauge live charts.
* With Live charts while inactive enabled, the shimmer continues while the app is visible but inactive.
* The optional battery energy saving override is respected when configured to pause inactive presentation.
* Hidden, minimized, closed, and fully occluded windows avoid unnecessary animation work.
* Existing Reduce Motion behavior is preserved.

No changes to battery calculations, telemetry/history collection, chart data, hardware sensors, Energy Cell appearance, or Glass/Solid architecture.

**Compatibility:** Intel x86_64; macOS 13.5 or later. Primarily validated on MacBookPro16,1. Unsigned and not notarized; Apple Silicon support is not implemented.

**ZIP:** `GlassGauge-0.1.2-alpha-intel.zip` (991,106 bytes). **SHA-256:** `9b001981ec34bb144fddb08cf54856a432d1d7712971ec3c63732e0a5e915331`.

## 0.1.1 Alpha: October 9, 2026

**GlassGauge's second public alpha** is a smaller update focused on diagnostics, battery energy behavior, and interface polish. [See the 0.1.1 release](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.1-alpha).

### Supportability

* Added **Export Diagnostic Report** to generate a local report with selected hardware and sensor troubleshooting information.
* Added **Copy Diagnostic Summary** to make a short support description easier to share.
* Added **Report an Issue** to open the public GitHub Issues page.
* Reports remain local until the user chooses to save or share one; they are not automatically uploaded. Personal files, credentials, and network identifiers are intentionally excluded.

### Appearance & Energy

* Added **Glass** and **Solid** background modes.
* Added an option for charts to keep updating while GlassGauge is inactive.
* Added opt in **Reduce Energy Use on Battery** behavior. While external power is disconnected, it can temporarily use a Solid background and pause inactive chart rendering while **telemetry collection and history continue**.
* Restores the normal appearance and chart preferences on reconnecting external power.
* Battery energy decisions use actual **external power connection**, not the charging indicator.

### History & Logs

* Added **Clear Graph History**, **Clear Event Log**, and an Overview **Clear History** shortcut.
* Reduced noisy GPU activity switch events without removing meaningful GPU status transitions or GPU telemetry.
* Retained persistent SQLite telemetry history, Now / 1h / 24h views, and approximately 48 hour retention.

### Interface Polish

* Reorganized Settings and improved scrolling cues.
* Refined Overview alignment, toolbar placement, and presentation.
* Preserved independent Intel and Radeon GPU monitoring, SSD SMART composite temperature support, battery and power readings, and the sensor measurement accuracy architecture.

### Compatibility and download

* **Intel x86_64 only**, primarily validated on **MacBookPro16,1**. Other Intel Mac sensors vary.
* **Unsigned and not notarized**; normal monitoring does not require administrator access.
* Apple Silicon dedicated hardware sensor support is not implemented.
* The Intel SMC **PSTR** measurement boundary remains unverified and is not confirmed system or wall power.
* Release ZIP: `GlassGauge-0.1.1-alpha-intel.zip` (**990,851 bytes**).
* **SHA-256:** `fb00686f46ba6672d82df7db21ec355989cb94530ed45a5e3040b557943e35e5`.

The [0.1.0 Alpha](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.0-alpha) remains available as the first public release.

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
