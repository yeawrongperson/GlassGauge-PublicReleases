# Compatibility and known limitations

[Home](../README.md) / Compatibility

**GlassGauge 0.1.2 Alpha is publicly available for Intel Macs.** This is the third public alpha, and broad device compatibility has not yet been established.

## Current support

| Hardware or requirement | Status |
| --- | --- |
| Intel MacBook Pro `MacBookPro16,1` (16 inch, 2019) | Primary validated development hardware |
| Intel Macs with supported Intel and Radeon GPUs | Separate integrated and discrete GPU utilization and history verified on the tested model; results vary elsewhere |
| Internal NVMe SSD temperature | Native NVMe SMART composite temperature verified on the tested internal SSD |
| Other Intel Macs | May work, but compatibility and available sensors vary by model |
| Apple Silicon Macs | Not a supported target for this Intel x86_64 build; dedicated Apple Silicon hardware sensor provider not implemented |
| Macs without an internal battery | Laptop battery measurements do not apply |
| Fanless models | No physical fan RPM to report |
| macOS | **13.5 or later**, as specified in the 0.1.2 release notes; wider device validation needed |
| Installer | [0.1.2 Alpha Intel ZIP](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/download/v0.1.2-alpha/GlassGauge-0.1.2-alpha-intel.zip) |
| Code signing and notarization | **Unsigned and not notarized** |
| Administrator access | Not needed for normal monitoring |
| Development source | Private |

## Why sensor availability varies

Hardware readings depend on Mac model, firmware, processor, macOS version, hardware components, and accessible system APIs. A missing reading is not automatically an app bug.

On the primary tested Intel Mac, development has verified independent Intel and Radeon GPU usage and history, as well as the internal SSD's composite temperature through NVMe SMART. This does not guarantee identical sensors on other Intel Macs.

Battery power flow indicates energy moving into or out of the battery. The Intel SMC **PSTR** value is available, but its precise measurement boundary has not been verified. Neither should be advertised as confirmed whole system or wall power.

## Installing the alpha

Read [Getting Started](GETTING_STARTED.md) for ZIP extraction and first launch guidance. Because this alpha is unsigned and not notarized, you may need Finder's **Open** option or **System Settings > Privacy & Security > Open Anyway**. Do not disable macOS security globally.

## Reporting a compatibility issue

When reporting a problem with **0.1.2 Alpha**, include:

1. Your Mac model and year.
2. Processor type and GPU details, if known.
3. Your macOS version.
4. GlassGauge version and build number, if visible.
5. The missing, incorrect, or unstable view.
6. Steps to reproduce and optionally redacted screenshots.

Never post device serial numbers or unredacted diagnostic logs. See [Feedback](BETA_FEEDBACK.md) and [Known Issues](KNOWN_ISSUES.md).

[Download 0.1.2 Alpha](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.2-alpha)
