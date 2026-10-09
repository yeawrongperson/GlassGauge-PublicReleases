# Features and monitoring guide

[Home](../README.md) / Features

GlassGauge is designed to show useful Mac performance information, explain the limitations of hardware telemetry, and stay legible while the machine is busy.

> **0.1.3 Alpha:** The Intel build is [publicly downloadable](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.3-alpha). Individual readings still depend on the Mac model, and the main validated hardware is MacBookPro16,1.

## Live overview

The current development source provides an overview with dashboard tiles for:

| Metric | What it represents | Important limitation |
| --- | --- | --- |
| CPU | Overall processor activity | Overall percent is normalized to the machine; it is not a individual process percentage |
| GPU | Separate Intel and Radeon GPU utilization and history where supported | Both sources are verified on the primary tested Intel Mac; availability varies elsewhere |
| Memory | Active, wired, and compressed memory accounting | Not an exact clone of Activity Monitor's memory pressure statistic |
| Disk | Read and write throughput | **Not** disk capacity or free space monitoring |
| Network | Incoming and outgoing traffic | Interface selection and counter behavior need testing on different setups |
| Battery | Charge percentage and available battery/AC context | Machines without batteries will not expose laptop battery measurements |
| Fans | Actual fan RPM where a supported sensor exists | Fanless models and unsupported providers have no RPM to show |
| Power | Selected hardware related to power values | A particular SMC register is not a calibrated whole system wattmeter by default |
| Temperatures | Available hardware thermal readings including native NVMe SMART SSD composite temperature on the tested internal drive | Sensor names, counts, and visibility differ by model |

## Graphs and history

* Periodic system sampling drives metric graphs; the reviewed development implementation polls at about one second intervals.
* Detail views expand on individual metrics, with a dedicated split network incoming and outgoing visualization.
* SQLite stores normal telemetry approximately once per second, with **Now, 1h, and 24h** views and up to approximately **48 hours** retention. History persists across restarts. Intervals without collection appear as gaps rather than fabricated data.
* A persisted Logs feed tracks meaningful events such as launch, sleep and wake, power source changes, GPU availability, and sensor availability.

## New in 0.1.3: application icon

GlassGauge's app icon was redesigned around its telemetry and charts. This branding change does not intentionally alter monitoring, battery, Energy Cell, sensors, history, or performance settings. The 0.1.2 Energy Cell fix remains included.

## Battery Energy Cell presentation

Version 0.1.2 fixes the Energy Cell shimmer so that it uses the same effective inactive presentation and battery energy saving policy as the live charts. It can continue when the app remains visible but inactive if that option is enabled, but pauses where the applicable setting or window visibility requires. Reduce Motion is preserved. Battery calculations, telemetry/history, and sensor behavior are unchanged.

## Diagnostics, history controls, and support

Version 0.1.1 adds **Export Diagnostic Report**, **Copy Diagnostic Summary**, and a **Report an Issue** workflow. Diagnostic reports are created locally with selected hardware and sensor support data. They are not uploaded automatically; you choose if and when to save or share them. Personal files, credentials, and network identifiers are intentionally excluded. Review files before sharing.

You can clear graph history and Event Logs separately. An Overview Clear History shortcut is also available.

## Background and battery energy options

Choose **Glass** or **Solid** background styles. When configured, charts may keep updating while GlassGauge is not the active application.

**Reduce Energy Use on Battery** is opt in. When external power is disconnected, it can temporarily use Solid and pause rendering inactive charts. Sensor sampling and persistent history recording continue. When external power reconnects, your presentation choices are restored. The app uses external connection state rather than charging state to determine battery operation.

## Menu bar and appearance

* A menu bar panel presents compact metric tiles and small charts.
* The main interface uses SwiftUI plus native AppKit materials for a glass styled window backdrop.
* A background transparency setting controls the tint over the native blur.
* The development project includes a reduced motion preference; individual animations and interactions still require beta testing.

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

Overall CPU usage and individual process CPU usage use different scales on macOS. An app using approximately two full logical CPUs may display around `200%` in a individual process tool, while the *whole machine* is far below 100% if it contains more logical CPUs. GlassGauge should explain the scale rather than imply that either tool is broken.

## Understanding watts and battery power

Battery current multiplied by battery voltage can estimate **power entering or leaving the battery**. That value is not interchangeable with total platform consumption or electricity drawn from an outlet. The current SMC PSTR value's electrical boundary remains unverified on the tested Intel model and is labeled conservatively in development.

## Features not included or not guaranteed in 0.1.3 Alpha

The following should be regarded as planned or requiring further verification, **not shipped guarantees**:

* A fully validated Apple Silicon backend for hardware temperature, fan, and power readings.
* Full individual core and individual process CPU drilldowns.
* History retention beyond approximately 48 hours and exportable analytics.
* Fan speed control or hardware tuning.
* A universal set of temperature, fan, and GPU readings on every Mac.

See [Compatibility](COMPATIBILITY.md) and the [Roadmap](ROADMAP.md).
