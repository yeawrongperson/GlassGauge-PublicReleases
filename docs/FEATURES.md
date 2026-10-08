# Features and monitoring guide

[Home](../README.md) / Features

GlassGauge is designed to show useful Mac performance information, explain the limitations of hardware telemetry, and stay legible while the machine is busy.

> **Pre-beta note:** This document describes capabilities present in the reviewed development source and qualifies what has not been verified for distribution. A feature appearing in the interface does not guarantee supported data on every Mac.

## Live overview

The current development source provides an overview with dashboard tiles for:

| Metric | What it represents | Important limitation |
| --- | --- | --- |
| CPU | Overall processor activity | Overall percent is normalized to the machine; it is not a per-process percentage |
| GPU | GPU activity when the system exposes a readable source | Some devices/providers return no verified GPU utilization |
| Memory | Active, wired, and compressed memory accounting | Not an exact clone of Activity Monitor's memory-pressure statistic |
| Disk | Read/write throughput | **Not** disk capacity or free-space monitoring |
| Network | Incoming and outgoing traffic | Interface selection and counter behavior need testing on different setups |
| Battery | Charge percentage and available battery/AC context | Machines without batteries will not expose laptop battery measurements |
| Fans | Actual fan RPM where a supported sensor exists | Fanless models and unsupported providers have no RPM to show |
| Power | Selected hardware power-related values | A particular SMC register is not a calibrated whole-system wattmeter by default |
| Temperatures | Available hardware thermal readings | Sensor names, counts, and visibility differ by model |

## Graphs and history

- Periodic system sampling drives metric graphs; the reviewed development implementation polls at about one-second intervals.
- Detail views expand on individual metrics, with a dedicated split network in/out visualization.
- Time-range controls are present in the interface, but **persistent long-term storage is not advertised as complete**. History in the reviewed implementation is session-oriented; the existence of a `24h` label alone does not guarantee 24 hours of saved data.

## Menu bar and appearance

- A menu-bar panel presents compact metric tiles and mini-charts.
- The main interface uses SwiftUI plus native AppKit materials for a glass-like window backdrop.
- A background-transparency setting controls the tint over the native blur.
- The development project includes a reduced-motion preference; individual animations and interactions still require beta testing.

## Understanding reading states

The refreshed monitoring design distinguishes:

| State | Meaning |
| --- | --- |
| **Measured** | A usable reading was obtained from the selected data source |
| **Unavailable** | This provider or machine cannot provide the reading |
| **Error** | The attempt failed or yielded invalid data |
| **Stale** | A previously sampled reading is too old or conflicts with the current state |
| **Estimated** | A value inferred rather than directly measured; not used as a substitute for a real hardware measurement by the updated production provider |

A real `0` can be a valid measurement. **Missing data is not zero.** Sensor source and age can affect how much confidence is appropriate.

## Why CPU usage can exceed 100% elsewhere

Overall CPU usage and per-process CPU usage use different scales on macOS. An app using approximately two full logical CPUs may display around `200%` in a per-process tool, while the *whole machine* is far below 100% if it contains more logical CPUs. GlassGauge should explain the scale rather than imply that either tool is broken.

## Understanding watts and battery power

Battery current multiplied by battery voltage can estimate **power entering or leaving the battery**. That value is not interchangeable with total platform consumption or electricity drawn from an outlet. The current SMC PSTR value's electrical boundary remains unverified on the tested Intel model and is labeled conservatively in development.

## What's not a promised beta feature

The following should be regarded as planned or requiring further verification, **not shipped guarantees**:

- A fully validated Apple Silicon hardware-temperature/fan/power backend.
- Full per-core and per-process CPU drilldowns.
- Durable days-long history and exportable analytics.
- Fan speed control or hardware tuning.
- A universal set of temperature, fan, and GPU readings on every Mac.

See [Compatibility](COMPATIBILITY.md) and the [Roadmap](ROADMAP.md).
