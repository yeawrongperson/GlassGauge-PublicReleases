<div align="center">
  <h1>GlassGauge</h1>
  <h3>A clearer window into your Mac.</h3>
  <p>A native macOS hardware and performance monitor with a glass-inspired interface, live system graphs, and a focus on <strong>real measurements over guesswork</strong>.</p>
  <p>
    <a href="https://github.com/yeawrongperson/GlassGauge-PublicReleases"><img alt="Status: Pre-beta" src="https://img.shields.io/badge/status-pre--beta-6d5dfc?style=for-the-badge"></a>
    <a href="docs/COMPATIBILITY.md"><img alt="Platform: macOS" src="https://img.shields.io/badge/platform-macOS-24292f?style=for-the-badge"></a>
    <a href="docs/FEATURES.md"><img alt="Built with Swift and SwiftUI" src="https://img.shields.io/badge/built%20with-Swift%20%2B%20SwiftUI-f05138?style=for-the-badge"></a>
  </p>
  <p><a href="docs/FEATURES.md">Features</a> · <a href="docs/COMPATIBILITY.md">Compatibility</a> · <a href="docs/ROADMAP.md">Roadmap</a> · <a href="docs/FAQ.md">FAQ</a> · <a href="CHANGELOG.md">Updates</a></p>
</div>

---

> [!IMPORTANT]
> **Public beta in preparation — no download available yet.** GlassGauge is in active development. This repository is the home for future signed beta builds, release notes, documentation, and feedback. No release date has been announced. Check **[Releases](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases)** for packages once they are published.

## Meet GlassGauge

GlassGauge is being built for people who want to understand what their Mac is doing without digging through technical utilities or deciphering a wall of raw sensor values.

The goal is simple: put everyday performance metrics and the hardware readings your Mac actually exposes in one readable place. Keep it native. Keep it responsive. Make the difference between **measured**, **unavailable**, and **unverified** data clear.

GlassGauge began as a personal macOS project in 2025. After the original preview received an unexpected amount of interest on Reddit, development continued through a substantial 2026 refresh focused on sensor accuracy, battery/power interpretation, and the window's glass appearance.

## At a glance

| Performance | Hardware | Experience |
| :--- | :--- | :--- |
| CPU activity | Temperature readings, where exposed | Translucent, glass-inspired macOS design |
| Memory usage | Fan speeds, where exposed | At-a-glance live dashboard |
| Disk read/write activity | Battery and charging state | Metric detail views and time-series graphs |
| Network download/upload traffic | Selected power-related sensor readings | Menu-bar overview |
| GPU activity, when supported | Clear unavailable/stale states | Adjustable background transparency |

**Important:** Available readings depend on the Mac model and sensor provider. A visible panel does not guarantee that its hardware reading is supported on every machine. See the [feature guide](docs/FEATURES.md) and [compatibility notes](docs/COMPATIBILITY.md).

## Built around the details

### 01 / Everything in one view

A dashboard for CPU, GPU, memory, disk, network, battery, fans, temperature, and selected power readings. The development implementation includes periodic sampling and live charts, with detail views for deeper inspection.

### 02 / Designed to feel like macOS

GlassGauge combines SwiftUI with AppKit window materials for a transparent, blurred presentation. The current development build includes adjustable background transparency and a compact menu-bar view.

### 03 / Readings you can trust — or clearly identify as missing

Not every sensor exists on every Mac. GlassGauge's newer monitoring work distinguishes a real measured value from an unavailable, stale, or failed reading instead of quietly inventing a plausible-looking number.

### 04 / Context matters

CPU percentages, battery current, and power readings can be surprisingly easy to misinterpret. GlassGauge's direction is to explain the meaning of a number rather than merely display it. For example, **battery power flow is not the same thing as total Mac power consumption**.

## Preview

**Screenshots and a short demo are coming with the first public beta.** The current development UI has been revised since the original 2025 preview; images will be added here after a release-candidate build is selected. We don't want to show an obsolete or misleading interface.

<!-- Add approved release-candidate screenshots under assets/ before publishing a downloadable beta. -->

## Beta availability

| Item | Current status |
| :--- | :--- |
| First downloadable beta | **Not published** |
| macOS app package (`.dmg` or `.zip`) | Packaging and release validation pending |
| Code signing / notarization | To be verified before distribution |
| Intel Macs | Development hardware readings tested on an Intel MacBook Pro; broader testing required |
| Apple Silicon Macs | General feature compatibility needs testing; dedicated hardware-sensor backend not yet implemented in the verified development snapshot |
| Minimum supported macOS version | To be confirmed against the release build |
| Public source code | Not distributed through this releases repository |

When the beta is ready, a versioned release will include the installer, supported-system requirements, known issues, and instructions. We will **not** ask users to bypass macOS security protections as a substitute for proper release preparation.

See [Getting Started](docs/GETTING_STARTED.md) for the current installation status and the future download process.

## Where the project stands

GlassGauge is **not abandoned**. Development resumed and evolved beyond the 2025 concept, but it is also **not yet a finished public product**.

Recent development work includes:

- Refactoring hardware-sensor handling to distinguish measured data from missing readings.
- Testing actual Intel SMC temperature, fan, and selected power-related readings on a specific Intel MacBook Pro.
- Reworking the glass window's native backdrop and transparency controls.
- Revisiting CPU metric interpretation and battery/charging power semantics.
- Preparing the first public beta packaging, validation, and documentation process.

These are **development updates**, not a promise that each feature is complete or will work on all supported Macs. For a dated record, read the [changelog](CHANGELOG.md) and [project history](docs/PROJECT_HISTORY.md).

## Help shape the beta

Once testing opens, reports about crashes, missing hardware sensors, confusing values, and visual issues will be extremely useful — particularly across different Intel and Apple Silicon Macs.

- **[Report a bug](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues/new)** or ask a question through Issues.
- Read the [beta feedback guide](docs/BETA_FEEDBACK.md) before submitting logs or system details.
- Check the [roadmap](docs/ROADMAP.md) for current priorities and longer-term ideas.

Please avoid posting serial numbers, passwords, private file paths, or unredacted system logs.

## Back from Reddit?

If you saw GlassGauge in **r/macapps** in 2025: thank you. That early post reached roughly **146,000 views and 137 shares**, and people were still checking in about the project months later. The interest has meant a lot. This repository is where real public release updates will live going forward.

No crowdfunding, waitlist, or release date is being announced here. When there's an actual build to try, it will appear under [GitHub Releases](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases).

## Documentation

| Guide | What's inside |
| :--- | :--- |
| [Features](docs/FEATURES.md) | Detailed metrics, views, and the meaning of sensor statuses |
| [Compatibility](docs/COMPATIBILITY.md) | Intel vs. Apple Silicon and what has actually been tested |
| [Getting Started](docs/GETTING_STARTED.md) | Beta download and installation status |
| [FAQ](docs/FAQ.md) | Answers to common questions |
| [Roadmap](docs/ROADMAP.md) | Current priorities and possible future directions |
| [Project History](docs/PROJECT_HISTORY.md) | The 2025 concept and 2026 engineering work |
| [Privacy & Security](docs/PRIVACY_AND_SECURITY.md) | Permissions, telemetry claims, and distribution safeguards |
| [Beta Feedback](docs/BETA_FEEDBACK.md) | How to write a useful report without exposing private data |
| [Changelog](CHANGELOG.md) | Public-facing development and release history |

---

<div align="center">
  <p><strong>GlassGauge</strong> — built for macOS, with clarity at its core.</p>
  <p><em>Independently developed. Currently in pre-beta.</em></p>
</div>
