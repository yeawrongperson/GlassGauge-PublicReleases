# Alpha feedback guide

[Home](../README.md) / Alpha Feedback

A useful report helps distinguish an app bug from a model specific hardware limitation. **GlassGauge 0.1.1 Alpha is available now** for Intel Macs: [download it here](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.1-alpha).

## Before opening an issue

1. Check the [FAQ](FAQ.md) and [Compatibility](COMPATIBILITY.md) page.
2. Look through [existing issues](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues) for a matching report.
3. Make sure you are testing an official versioned build from the [Releases page](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases).

## Suggested bug report

Copy this into a [new GitHub Issue](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues/new):

```markdown
### Summary
A short explanation of the problem.

### GlassGauge version
Example: 0.1.1 Alpha (include build number if available)

### Mac and macOS
Model/year, Intel or Apple Silicon chip, and macOS version.
Do not include the serial number.

### Steps to reproduce
1.
2.
3.

### Expected behavior
What should have happened?

### Actual behavior
What happened instead?

### Affected metric or screen
CPU / GPU / Memory / Disk / Network / Battery / Fans / Power / Temperature / Other

### Frequency
Always / Sometimes / Once

### Screenshots or diagnostics
Attach only redacted screenshots and logs.

### Additional context
Anything that changes the result, such as plugging in power or resizing the window.
```

## Especially valuable tests

* Sensor availability on different Mac models.
* Battery charging, power source transitions, and reading freshness.
* CPU and GPU values compared at matching sampling times with other tools.
* Performance overhead and idle resource usage.
* Window blur, appearance, resizing, multiple monitors, and accessibility.
* Install/open/relaunch reliability and permission prompts.

## Optional diagnostic reports

GlassGauge 0.1.1 adds **Export Diagnostic Report** and **Copy Diagnostic Summary**. Reports are generated locally and **not uploaded automatically**. They contain selected hardware and sensor support information and intentionally exclude personal files, credentials, and network identifiers. If needed, manually attach a saved report to your GitHub issue after reviewing it.

## Protect your information

Before uploading logs or screenshots, remove serial numbers, usernames, file paths, passwords, credentials, IP addresses where sensitive, and unrelated application content. If unsure, describe the behavior in text without attaching raw dumps.
