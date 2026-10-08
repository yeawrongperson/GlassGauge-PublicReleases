<div align="center">
  <h1>GlassGauge</h1>
  <h3>A clearer window into your Mac.</h3>
  <p>See what your Mac is doing in real time. GlassGauge brings performance metrics, hardware readings, and live charts into a native macOS app with a clean glass inspired interface.</p>
  <p>
    <a href="https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases"><img alt="Public beta: coming soon" src="https://img.shields.io/badge/Public%20Beta-Coming%20Soon-6d5dfc?style=for-the-badge"></a>
    <a href="docs/COMPATIBILITY.md"><img alt="Platform: macOS" src="https://img.shields.io/badge/Platform-macOS-24292f?style=for-the-badge"></a>
    <a href="docs/FEATURES.md"><img alt="Made with Swift and SwiftUI" src="https://img.shields.io/badge/Made%20with-Swift%20%26%20SwiftUI-f05138?style=for-the-badge"></a>
  </p>
  <p>
    <a href="docs/FEATURES.md">Features</a> ·
    <a href="docs/COMPATIBILITY.md">Compatibility</a> ·
    <a href="docs/ROADMAP.md">Roadmap</a> ·
    <a href="CHANGELOG.md">Development updates</a> ·
    <a href="docs/FAQ.md">FAQ</a>
  </p>
</div>

> [!IMPORTANT]
> **The first public beta is not available to download yet.** I'm preparing a proper macOS build and verifying installation, compatibility, and the hardware readings before sharing it. The official download will appear on the [Releases page](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases) when it's ready. No release date has been announced.

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

The exact readings depend on your Mac. Some sensors are only available on certain models, and some hardware monitoring features are still being developed. The [features guide](docs/FEATURES.md) explains what the current development version does and what still needs testing.

## A closer look

### A dashboard you can actually read

GlassGauge puts the main metrics together so you can quickly see what your Mac is doing. You can open individual views when you want more detail, including a dedicated view for network traffic.

### A native macOS feel

The interface uses SwiftUI and AppKit, with a translucent background and adjustable transparency. The goal is something that looks good on the desktop without getting in the way of the information.

### Real readings, with their limits made clear

One of the biggest areas of work in the 2026 refresh has been sensor accuracy. On supported Intel hardware, GlassGauge reads available information from the Apple System Management Controller. The app also distinguishes measured readings from missing, outdated, and failed measurements.

That matters because Macs do not all expose the same sensors. An unavailable GPU reading, for example, is not the same thing as zero GPU use.

### More care with battery and power information

Battery charge, power source, charging state, and selected electrical readings are useful, but easy to label incorrectly. Recent work has focused on separating battery power flow from a Mac's total power consumption and making the source of a reading clearer.

## Screenshots and demo

I'm saving the updated screenshots for a build that matches what beta testers will actually receive. The app has changed quite a bit since the original 2025 preview, and I'd rather show the current interface than recycle old images.

Screenshots and a short demonstration will be added here before the public beta.

## Public beta status

| Item | Status |
| :--- | :--- |
| Downloadable beta | Not released yet |
| App installer | Packaging and verification in progress |
| Code signing and notarization | Must be checked before distribution |
| Intel Mac hardware readings | Development testing completed on one Intel MacBook Pro; broader testing needed |
| Apple Silicon hardware sensors | Dedicated sensor support is not implemented in the reviewed development version |
| Minimum macOS version | Will be confirmed with the release build |
| Public source code | Not included in this public releases repository |

I'm keeping the development source private for now. This repository is where the public downloads, updates, and feedback will live. See [Compatibility](docs/COMPATIBILITY.md) for more detail.

## Still working on it

GlassGauge first caught people's attention after I shared an early preview in **r/macapps** in 2025. That post reached about **146,000 views and 137 shares**, and I've continued seeing people ask whether the app is still being developed.

It is.

The project has gone through a lot of work since that original preview. I've been revisiting the monitoring system, testing actual Intel hardware readings, improving the window design, and digging into tricky battery and power measurements. Some of that work was already part of the original foundation, while other parts are newer. The [development history](docs/PROJECT_HISTORY.md) and [changelog](CHANGELOG.md) go through the details.

There's still work to finish before I'd feel comfortable putting an installer out for everyone. I'd like the first build people try to be useful, reasonably stable, and honest about what it can and cannot read.

## Follow development and share feedback

You can watch this repository for updates or check the [Releases page](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases) when the first beta is published.

* [View the roadmap](docs/ROADMAP.md) for current priorities.
* [Read the FAQ](docs/FAQ.md) for common questions about compatibility and availability.
* [Open an issue](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues/new) to suggest an improvement or report a problem when beta testing begins.
* [Read the feedback guide](docs/BETA_FEEDBACK.md) before attaching logs or screenshots.

Please avoid sharing serial numbers, credentials, private file paths, or unedited diagnostic logs in public issues.

## Documentation

| Guide | Contents |
| :--- | :--- |
| [Features](docs/FEATURES.md) | What the app measures and how to interpret the values |
| [Compatibility](docs/COMPATIBILITY.md) | Hardware testing, Intel support, and Apple Silicon limitations |
| [Getting started](docs/GETTING_STARTED.md) | Where the beta will be available and how installation will work |
| [FAQ](docs/FAQ.md) | Common questions |
| [Roadmap](docs/ROADMAP.md) | Development priorities |
| [Project history](docs/PROJECT_HISTORY.md) | How the app has changed since 2025 |
| [Privacy and security](docs/PRIVACY_AND_SECURITY.md) | What has been reviewed and what still needs verification |
| [Beta feedback](docs/BETA_FEEDBACK.md) | How to submit useful reports |
| [Changelog](CHANGELOG.md) | Development milestones and eventual release history |

<div align="center">
  <p><strong>GlassGauge</strong></p>
  <p><em>Built for macOS. Developed independently. Public beta in preparation.</em></p>
</div>
