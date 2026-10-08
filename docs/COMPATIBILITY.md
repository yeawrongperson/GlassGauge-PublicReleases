# Compatibility and known limitations

[Home](../README.md) / Compatibility

**The first public beta has not shipped.** Final hardware and operating-system requirements will be published only after validating the actual distributable build.

## Current evidence

| Hardware / requirement | Evidence or status |
| --- | --- |
| Intel MacBook Pro (`MacBookPro16,1`) | Development tests for CPU, fan, temperature, battery, and selected Intel SMC power data |
| Other Intel Macs | Further testing required; individual sensors vary by machine |
| Apple Silicon (M-series) Macs | General/macOS metrics still need beta validation. **Dedicated hardware-sensor support is not implemented in the reviewed sensor coordinator** |
| Mac desktops without internal batteries | Battery-specific readings may not be applicable |
| Fanless models | A fan RPM reading is not expected where no physical fan exists |
| Minimum macOS version | **Not finalized** for the public beta |
| Signed/notarized download | **Not yet available** |

## Why the same metric may differ between Macs

Hardware monitors can read different data depending on the processor family, firmware, chip model, macOS release, drivers, permissions, and sensors exposed by the operating system. GlassGauge intentionally treats an unavailable reading as missing rather than substituting an artificial number.

Some general OS-provided measurements may work on a machine even when its low-level hardware-sensor backend is unavailable. This should not be mistaken for full hardware compatibility.

## Reporting a compatibility issue

When beta testing opens, include:

1. Mac model and year (for example, `MacBook Pro 16-inch, 2019`).
2. Intel or Apple Silicon processor and chip name if known.
3. macOS version (for example, `15.x`).
4. GlassGauge beta version and build number.
5. Which reading or view is missing, incorrect, or unstable.
6. Steps to reproduce, screenshots, and redacted diagnostic logs if requested.

**Never share a device serial number or unredacted diagnostic dump in a public Issue.** See [Beta Feedback](BETA_FEEDBACK.md).
