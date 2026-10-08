# From the 2025 preview to the 2026 refresh

[Home](../README.md) / Project History

GlassGauge started in 2025 with a simple idea: a Mac performance monitor with useful telemetry and an interface that feels like part of macOS rather than a separate diagnostics utility.

## 2025: the concept and early foundation

The original implementation explored a glass-inspired UI for a live system-monitoring dashboard. The development foundation included major performance tiles, chart views, network traffic presentation, and a native-feeling layout.

A GlassGauge preview shared in r/macapps received approximately **146,000 views and 137 shares**, according to the developer's reported post statistics. People continued asking about the project's status afterward. That preview was **not** a general public release of an installer.

## 2026: accuracy, meaning, and native presentation

Rather than only adding more panels, recent work focused on the reliability and semantics of the values already shown.

### Sensor truth

On the tested Intel MacBook Pro, development work moved toward reading real AppleSMC hardware data and explicitly reporting where sensors are missing, stale, or inaccessible. It also separated the ability to *read* an SMC number from the much harder task of proving precisely what that number measures.

### Battery and power accuracy

Battery current, voltage, power-source changes, and charging state were audited. A battery-current calculation can describe energy entering or leaving a battery; it cannot simply be renamed “system power.” Similarly, an SMC register sometimes labeled as total power by other tools is not automatically a verified whole-Mac or wall-power measurement for every board.

### The glass window

The native window backdrop was revised to use a persistent AppKit visual-effect layer beneath SwiftUI content, with configurable tint transparency. Testing verified important implementation details, but visual behavior on different monitors and hardware still needs beta testing.

### Honest platform scope

The Intel hardware-sensor path has direct development evidence on one tested model. Apple Silicon hardware-sensor support remains a development target, not a claim that all sensors already work on M-series devices.

## What's next

The goal is to turn a promising development project into a safe, signed, well-documented early beta, then expand support with real compatibility reports. This releases repository will be the public record of what actually ships, with versioned packages and limitations stated clearly.

Read the [Changelog](../CHANGELOG.md) for dated milestones and the [Roadmap](ROADMAP.md) for the next steps.
