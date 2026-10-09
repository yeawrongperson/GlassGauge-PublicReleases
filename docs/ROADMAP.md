# GlassGauge Roadmap

**Updated October 9, 2026**

GlassGauge is an independent macOS system monitor. This page explains what is already working in development, what is planned after the first public alpha, and what I would like to build next.

**GlassGauge 0.1.2 Alpha is available now for Intel Macs.** [Download the latest public alpha](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.2-alpha) and follow this roadmap for upcoming work.

[Back to GlassGauge](../README.md) | [Known limitations](KNOWN_ISSUES.md) | [Report an issue](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues)

## At a glance

**Built in development:** The main dashboard, live graphs, menu bar panel, glass appearance, battery information, and several hardware readings are implemented.

**Public alpha available:** 0.1.2 Alpha is the third Intel alpha. It fixes Battery Energy Cell inactive presentation behavior. The diagnostics, appearance controls, battery energy options, and history features introduced earlier remain available. I'm gathering compatibility reports and improving stability.

**Planned next:** Broader Mac support, more detailed CPU information, better power and battery views, and improvements to persistent history.

**Ideas for later:** More personalization, alerts, and deeper reports.

These are development stages, not promised release dates. A feature can work on my Mac and still need testing before it is ready for yours.

## 1. What works in development

### Live Mac performance

GlassGauge already has a dashboard for CPU activity, memory usage, disk activity, network traffic, battery charge, and other available system information. You can open individual views for more detail, including separate incoming and outgoing network activity.

### Live charts and menu bar monitoring

Performance readings update over time, with graphs that help make changes easier to spot. A compact menu bar panel provides another way to check important numbers.

### A native glass interface

The current app uses SwiftUI and AppKit, with a glass inspired appearance and an adjustable background transparency setting. Recent development has focused on keeping the window effect stable while the dashboard updates.

### Hardware readings on a tested Intel Mac

Development testing on an Intel MacBook Pro has verified access to supported fan speeds, temperatures, battery information, and selected power related readings. Different Macs expose different sensors, so these results do not guarantee that every reading works on every Intel model.

### Clearer information when a sensor is missing

The monitoring system now distinguishes a real measurement from information that is unavailable, outdated, or failed to load. A missing reading should not pretend to be zero, and GlassGauge should never invent fan speeds or temperatures to fill a blank space.

**Public release note:** These foundation features are present in 0.1.1 Alpha where supported, but individual hardware sensors vary by Mac.

## 2. Following up on the first public alpha

**0.1.1 Alpha has shipped as the second public alpha.** The work below describes next steps, not conditions that prevent the download.

1. **Improve distribution.** The Intel ZIP is already available, but future builds can improve signing, notarization, and first launch.
2. **Expand compatibility testing.** Gather reports from additional Intel Macs and validate the stated macOS 13.5 or later requirement.
3. **Test the everyday experience.** Check startup, live updates, charts, window resizing, menu bar behavior, and resource usage.
4. **Double check sensor accuracy.** Make sure unsupported or outdated readings are explained rather than displayed as believable numbers. Continue testing battery charging and power interpretation.
5. **Review permissions and privacy.** Confirm that normal monitoring does not unexpectedly request administrator access and that any diagnostic behavior is clearly explained.
6. **Respond to alpha feedback.** Collect reproducible reports, publish updated screenshots, and keep installation and release notes accurate.

There is no announced date for the next release. I'd rather improve the alpha based on real testing than promise a schedule I might not meet.

## 3. Planned improvements after the initial alpha

These are the next areas I want to explore and develop. Their order may change based on testing and feedback.

### Broader Mac compatibility

Expand testing across more Intel Macs and develop dedicated hardware sensor support for Apple Silicon where reliable access is possible. Basic macOS system metrics and direct hardware sensors are separate things, and both will need their own validation.

### Deeper CPU and process information

Explore more detailed views for individual CPU cores and running applications. The goal is to show which workloads are using your Mac's resources, with CPU percentages explained correctly.

### Better battery and power information

Continue improving how GlassGauge explains charging, battery use, available watt readings, and the differences between them. If a measurement's meaning cannot be verified, it should be labeled cautiously or left unavailable.

### More useful performance history

SQLite history already persists across relaunches in 0.1.1 Alpha. Normal telemetry is retained for approximately 48 hours and can be viewed using Now, 1h, and 24h ranges. Future work may expand retention options, performance, and exporting.

### UI polish and accessibility

Keep refining layout, readability, reduced motion behavior, window effects, and how the app behaves on different screen sizes and displays.

## 4. Possibilities for later

These are ideas, not confirmed features or commitments.

* Configurable alerts for supported metrics.
* More ways to organize or personalize the dashboard.
* Optional export of historical metrics and longer term performance reports. Local diagnostic report export is already available in 0.1.1.
* Additional tools that help explain unusual system behavior.

If something matters to you, please suggest it through [GitHub Issues](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues). Feedback can help decide what comes next.

## 5. What are the current limitations?

**Apple Silicon hardware sensors:** The reviewed development version does not yet have a dedicated sensor reader for Apple Silicon Macs. Some general macOS metrics may still work, but full hardware monitoring is not verified.

**Sensor availability:** Independent Intel and Radeon GPU activity and internal NVMe SSD composite temperature are verified on the tested Mac, but these and other sensors can be unavailable on different models. A Mac without physical fans will not have a fan speed to report.

**Battery and power:** Battery power flow and a hardware power reading are not the same thing as total electricity drawn from an outlet. Some electrical readings still need further interpretation and testing.

**History:** SQLite history persists across app relaunches, retains up to approximately 48 hours, and leaves real collection gaps visible.

**Public download:** 0.1.2 Alpha is available as an Intel ZIP, but it is unsigned and not notarized.

For a clearer explanation of what is a limitation, what is expected behavior, and what should be reported as a bug, see [Known Issues and Limitations](KNOWN_ISSUES.md).

## 6. How to follow progress

The [Releases page](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.2-alpha) hosts 0.1.2 Alpha for Intel Macs and will host subsequent builds.

The [Changelog](../CHANGELOG.md) covers work already completed, while this roadmap explains where the project is headed.

For suggestions, compatibility questions, or alpha bug reports, visit [GitHub Issues](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues).

**Thanks to everyone who followed GlassGauge after the original r/macapps preview. The project is still being developed, and I want to make its progress easier to follow.**
