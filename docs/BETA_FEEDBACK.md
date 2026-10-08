# Beta feedback guide

[Home](../README.md) / Beta Feedback

A useful report helps distinguish an app bug from a device-specific hardware limitation. Beta builds are **not available yet**, but the reporting format below will be used once testing begins.

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
Example: v0.x.x-beta.x (include build number)

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

- Sensor availability on different Mac models.
- Battery charging, power-source transitions, and reading freshness.
- CPU/GPU values compared at matching sampling times with other tools.
- Performance overhead and idle resource usage.
- Window blur, appearance, resizing, multiple monitors, and accessibility.
- Install/open/relaunch reliability and permission prompts.

## Protect your information

Before uploading logs or screenshots, remove serial numbers, usernames, file paths, passwords, credentials, IP addresses where sensitive, and unrelated application content. If unsure, describe the behavior in text without attaching raw dumps.
