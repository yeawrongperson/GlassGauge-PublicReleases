# From the 2025 preview to the 2026 refresh

[Home](../README.md) / Project History

GlassGauge started in 2025 with a simple idea: a Mac performance monitor with useful telemetry and an interface that feels like part of macOS rather than a separate diagnostics utility.

## 2025: the concept and early foundation

The original implementation explored a glass inspired UI for a live system monitoring dashboard. The development foundation included major performance tiles, chart views, network traffic presentation, and a native feeling layout.

A GlassGauge preview shared in r/macapps received approximately **146,000 views and 137 shares**, according to the developer's reported post statistics. People continued asking about the project's status afterward. That preview was **not** a general public release of an installer.

## 2026: accuracy, meaning, and native presentation

Rather than only adding more panels, recent work focused on the reliability and semantics of the values already shown.

### Sensor truth

On the tested Intel MacBook Pro, development work moved toward reading real AppleSMC hardware data and explicitly reporting where sensors are missing, stale, or inaccessible. It also separated the ability to *read* an SMC number from the much harder task of proving precisely what that number measures.

### Battery and power accuracy

Battery current, voltage, power source changes, and charging state were audited. A battery current calculation can describe energy entering or leaving a battery; it cannot simply be renamed “system power.” Similarly, an SMC register sometimes labeled as total power by other tools is not automatically a verified entire Mac or power measurement from a wall outlet for every board.

### The glass window

The native window backdrop was revised to use a persistent AppKit visual effect layer beneath SwiftUI content, with configurable tint transparency. Testing verified important implementation details, but visual behavior on different monitors and hardware still needs beta testing.

### Honest platform scope

The Intel hardware sensor path has direct development evidence on one tested model. Apple Silicon hardware sensor support remains a development target, not a claim that all sensors already work on Apple Silicon devices.

## What's next

GlassGauge's first public Intel build, [0.1.0 Alpha](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.0-alpha), shipped on October 9, 2026. It is unsigned and not notarized. Next steps include wider hardware testing, continued monitoring improvements, and future distribution refinements. This repository records actual shipped packages and their known limitations.

The second public build, [0.1.1 Alpha](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.1-alpha), was published on October 9, 2026. It adds local diagnostic reporting, more control over saved history and event logs, Glass and Solid backgrounds, and optional battery energy behavior. The original 0.1.0 release remains available.

The third public build, [0.1.2 Alpha](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.2-alpha), followed on October 9, 2026 with a small fix to the Battery Energy Cell's inactive window animation behavior. No hardware or telemetry features changed in this hotfix.

Read the [Changelog](../CHANGELOG.md) for dated milestones and the [Roadmap](ROADMAP.md) for the next steps.

The fourth public build, [0.1.3 Alpha](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.3-alpha), followed on October 9, 2026. It introduces the redesigned GlassGauge application icon inspired by its telemetry and charts. This branding update makes no intentional changes to sensor collection, monitoring, charts or history, Battery Energy Cell behavior, power settings, window rendering, or diagnostics. Earlier alpha releases remain available.
