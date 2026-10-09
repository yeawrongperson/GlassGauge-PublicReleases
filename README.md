<div align="center">
  <h1>GlassGauge</h1>
  <h3>A clearer window into your Mac.</h3>
  <p>See what your Mac is doing in real time. GlassGauge brings performance metrics, hardware readings, and live charts into a native macOS app with a clean glass inspired interface.</p>
  <p>
    <a href="https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.2-alpha"><img alt="0.1.2 Alpha available" src="https://img.shields.io/badge/0.1.2%20Alpha-Available-6d5dfc?style=for-the-badge"></a>
    <a href="docs/COMPATIBILITY.md"><img alt="Platform: macOS" src="https://img.shields.io/badge/Platform-macOS-24292f?style=for-the-badge"></a>
    <a href="docs/FEATURES.md"><img alt="Made with Swift and SwiftUI" src="https://img.shields.io/badge/Made%20with-Swift%20%26%20SwiftUI-f05138?style=for-the-badge"></a>
  </p>
  <p>
    <a href="docs/FEATURES.md">Features</a> ·
    <a href="docs/COMPATIBILITY.md">Compatibility</a> ·
    <a href="docs/ROADMAP.md">Roadmap</a> ·
    <a href="docs/KNOWN_ISSUES.md">Known limitations</a> ·
    <a href="CHANGELOG.md">Development updates</a> ·
    <a href="docs/FAQ.md">FAQ</a>
  </p>
</div>

> [!IMPORTANT]
> **GlassGauge 0.1.2 Alpha, build 3, is available for Intel Macs.** [Download the Intel ZIP](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/download/v0.1.2-alpha/GlassGauge-0.1.2-alpha-intel.zip) from the [0.1.2 Alpha release page](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.2-alpha). The app is **unsigned and not notarized**, so macOS may require you to confirm the first launch. See [Getting Started](docs/GETTING_STARTED.md) for safe instructions. Dedicated Apple Silicon hardware sensor support is not implemented yet.

## What is GlassGauge?

GlassGauge is a macOS system monitor built for people who want a useful picture of their Mac's performance without opening several different utilities just to understand what's happening.

The idea started with a simple question: what if you could keep an eye on your hardware and system activity in one place, in an app that actually feels at home on macOS?

GlassGauge brings together a live overview, readable graphs, hardware information when available, and a customizable glass appearance. The interface matters, but the numbers matter more. A sensor that isn't available should say so instead of showing a believable number that wasn't really measured.

## What can it show?

| Performance | Hardware information | Interface |
| :--- | :--- | :--- |
| CPU activity | Temperatures where supported | Live dashboard |
| Memory use | Fan speed where supported | Individual metric views |
| Disk activity | Battery charge and power source | Live graphs |
| Network traffic | Selected power readings | Menu bar overview |
| GPU activity where supported | Clear measurement status | Adjustable glass background |
| Separate Intel and Radeon GPU usage where supported | Internal SSD composite temperature where supported | Saved history and event Logs |

The exact readings depend on your Mac. Some sensors are only available on certain models, and some hardware monitoring features are still being developed. The [features guide](docs/FEATURES.md) explains the current alpha's features and where hardware support still needs testing.

## A closer look

### A dashboard you can actually read

GlassGauge puts the main metrics together so you can quickly see what your Mac is doing. You can open individual views when you want more detail, including a dedicated view for network traffic.

### A native macOS feel

The interface uses SwiftUI and AppKit, with a translucent background and adjustable transparency. The goal is something that looks good on the desktop without getting in the way of the information.

### Easier support and diagnostics

Introduced in 0.1.1, the app includes a local diagnostic report, a quick copyable support summary, and a link to report an issue on GitHub. The diagnostic report contains selected hardware and sensor information. Reports are generated locally, are **not automatically uploaded**, and are saved or shared only when you choose. Personal files, credentials, and network identifiers are intentionally excluded. Review a report before posting it publicly.

You can clear saved graph history and the event log separately, with a Clear History shortcut on the Overview.

### Choose your glass appearance

Switch between **Glass** and **Solid** window backgrounds. Visible charts can continue refreshing while GlassGauge is open but another app has focus, if you enable that behavior.

The optional **Reduce Energy Use on Battery** setting can temporarily use a Solid background and pause inactive chart rendering when external power is disconnected. Telemetry sampling and history recording continue. When the Mac reconnects to external power, your normal presentation preferences return. The decision is based on whether external power is connected, not whether the battery is actively charging.

### Real readings, with their limits made clear

One of the biggest areas of work in the 2026 refresh has been sensor accuracy. On supported Intel hardware, GlassGauge reads available information from the Apple System Management Controller. The app also distinguishes measured readings from missing, outdated, and failed measurements.

That matters because Macs do not all expose the same sensors. An unavailable GPU reading, for example, is not the same thing as zero GPU use.

### Independent GPU monitoring and saved history

On the tested Intel Mac, GlassGauge can show integrated Intel and discrete Radeon GPU activity separately when both sources are available. The Overview keeps their usage history independent.

Normal telemetry is stored in SQLite, with **Now, 1h, and 24h** views and retention of up to approximately **48 hours**. History survives relaunches. If GlassGauge was not running, the missing time remains a gap rather than a fabricated measurement. The persisted Logs view records important transitions such as launches, sleep and wake, power source changes, and sensor availability.

### More care with battery and power information

Battery charge, power source, charging state, and selected electrical readings are useful, but easy to label incorrectly. Recent work has focused on separating battery power flow from a Mac's total power consumption and making the source of a reading clearer.

### 0.1.2 Energy Cell hotfix

The Battery page's Energy Cell shimmer now follows the same inactive window presentation policy as live charts. With **Live charts while inactive** enabled, the shimmer continues while GlassGauge is visible but another app is focused. The optional battery energy setting can pause inactive presentation when configured, while hidden, minimized, closed, and fully occluded windows avoid unnecessary animation work. Reduce Motion remains respected. This fix does not change battery calculations, telemetry, charts, sensors, or window background architecture.

## Screenshots and demo

Screenshots and a short demo matching **0.1.2 Alpha** are coming soon. You can [download the current Intel alpha now](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.2-alpha).

## GlassGauge 0.1.2 Alpha status

| Item | Current status |
| :--- | :--- |
| Latest public release | **[0.1.2 Alpha, build 3](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.2-alpha)**, available now |
| Download | [0.1.2 Intel ZIP](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/download/v0.1.2-alpha/GlassGauge-0.1.2-alpha-intel.zip) |
| Intel Macs | Initial public support, primarily validated on **MacBookPro16,1** (16 inch, 2019); other models need testing |
| Apple Silicon hardware sensors | Dedicated provider not implemented |
| GPU monitoring | Separate Intel and Radeon GPU utilization and history verified on the tested Mac, when available |
| Internal SSD temperature | Native NVMe SMART composite reading verified on the tested internal SSD |
| Persistent history | SQLite, Now / 1h / 24h, retained for approximately 48 hours |
| Event Logs | Stored launch, sleep/wake, power and sensor transition events; clear separately from graph history |
| Diagnostics | Local Export Diagnostic Report, Copy Diagnostic Summary, Report an Issue |
| Appearance | Glass and Solid backgrounds; optional background chart updates |
| Battery energy settings | Optional temporary Solid mode and paused inactive chart rendering without stopping telemetry |
| Signing and notarization | **Unsigned and not notarized** |
| macOS version | Release specifies **macOS 13.5 or later**; broader hardware testing remains limited |
| Source code | Private |
| Feedback | [GitHub Issues](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues) |

The development source remains private. This public repository contains downloads, documentation, release notes, and feedback. Read [Compatibility](docs/COMPATIBILITY.md) and [Known Issues](docs/KNOWN_ISSUES.md) before installing.

## Still working on it

GlassGauge first caught people's attention after I shared an early preview in **r/macapps** in 2025. That post reached about **146,000 views and 137 shares**, and I've continued seeing people ask whether the app is still being developed.

It is.

The project has gone through a lot of work since that original preview. I've been revisiting the monitoring system, testing actual Intel hardware readings, improving the window design, and digging into tricky battery and power measurements. Some of that work was already part of the original foundation, while other parts are newer. The [development history](docs/PROJECT_HISTORY.md) and [changelog](CHANGELOG.md) go through the details.

The first Intel alpha is now available. There's more testing to do across Mac models, and I want to use early feedback to keep improving accuracy, stability, and usability.

## Follow development and share feedback

You can [download 0.1.2 Alpha now](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.2-alpha), watch this repository for updates, or share feedback through GitHub Issues. Both the [original 0.1.0 Alpha](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.0-alpha) and [0.1.1 Alpha](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.1-alpha) remain available as historical releases.

* [View the roadmap](docs/ROADMAP.md) for current priorities.
* [Read the FAQ](docs/FAQ.md) for common questions about compatibility and availability.
* [Open an issue](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues/new) to suggest an improvement or report a problem with the public alpha.
* [Read the feedback guide](docs/BETA_FEEDBACK.md) before attaching logs or screenshots.

Please avoid sharing serial numbers, credentials, private file paths, or unedited diagnostic logs in public issues.

## Documentation

| Guide | Contents |
| :--- | :--- |
| [Features](docs/FEATURES.md) | What the app measures and how to interpret the values |
| [Compatibility](docs/COMPATIBILITY.md) | Hardware testing, Intel support, and Apple Silicon limitations |
| [Getting started](docs/GETTING_STARTED.md) | Download, install, and open the Intel alpha |
| [FAQ](docs/FAQ.md) | Common questions |
| [Roadmap](docs/ROADMAP.md) | Development priorities |
| [Known issues and limitations](docs/KNOWN_ISSUES.md) | Expected behavior, incomplete features, and useful alpha bug reports |
| [Project history](docs/PROJECT_HISTORY.md) | How the app has changed since 2025 |
| [Privacy and security](docs/PRIVACY_AND_SECURITY.md) | What has been reviewed and what still needs verification |
| [Alpha feedback](docs/BETA_FEEDBACK.md) | How to submit useful reports |
| [Changelog](CHANGELOG.md) | Development milestones and published releases |

<div align="center">
  <p><strong>GlassGauge</strong></p>
  <p><em>Built for macOS. Developed independently. Public alpha available now.</em></p>
</div>
