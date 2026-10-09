# GlassGauge Roadmap

**Updated October 8, 2026**

GlassGauge is an independent macOS system monitor. This page explains what is already working in development, what needs to happen before the first public beta, and what I would like to build next.

**The first public beta is not available yet.** You can follow progress here, and the first download will appear on the [Releases page](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases) when it is ready.

[Back to GlassGauge](../README.md) | [Known limitations](KNOWN_ISSUES.md) | [Report an issue](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues)

## At a glance

**Built in development:** The main dashboard, live graphs, menu bar panel, glass appearance, battery information, and several hardware readings are implemented.

**Preparing for beta:** I'm verifying accuracy, stability, compatibility, and the actual installable app.

**Planned next:** Broader Mac support, more detailed CPU information, better power and battery views, and useful history.

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

**Important:** This section describes the development application. None of it is a claim that a public beta has already shipped.

## 2. What needs to happen before the first beta

This is the current priority.

1. **Prepare the app for download.** Build an installable release, then verify its signing, notarization, and installation steps.
2. **Check compatibility.** Confirm which macOS versions and Intel Mac models have actually been tested. Publish a clear minimum requirement.
3. **Test the everyday experience.** Check startup, live updates, charts, window resizing, menu bar behavior, and resource usage.
4. **Double check sensor accuracy.** Make sure unsupported or outdated readings are explained rather than displayed as believable numbers. Continue testing battery charging and power interpretation.
5. **Review permissions and privacy.** Confirm that normal monitoring does not unexpectedly request administrator access and that any diagnostic behavior is clearly explained.
6. **Prepare beta feedback.** Publish fresh screenshots, installation instructions, release notes, and a straightforward way to report problems.

There is no announced beta date. I'd rather publish a useful test build than give people a date I might not meet.

## 3. Planned improvements after the initial beta

These are the next areas I want to explore and develop. Their order may change based on testing and feedback.

### Broader Mac compatibility

Expand testing across more Intel Macs and develop dedicated hardware sensor support for Apple Silicon where reliable access is possible. Basic macOS system metrics and direct hardware sensors are separate things, and both will need their own validation.

### Deeper CPU and process information

Explore more detailed views for individual CPU cores and running applications. The goal is to show which workloads are using your Mac's resources, with CPU percentages explained correctly.

### Better battery and power information

Continue improving how GlassGauge explains charging, battery use, available watt readings, and the differences between them. If a measurement's meaning cannot be verified, it should be labeled cautiously or left unavailable.

### More useful performance history

Work toward saving performance history across app restarts, with clearer time ranges and possible retention controls. Current development graphs should not be mistaken for completed long term storage.

### UI polish and accessibility

Keep refining layout, readability, reduced motion behavior, window effects, and how the app behaves on different screen sizes and displays.

## 4. Possibilities for later

These are ideas, not confirmed features or commitments.

* Configurable alerts for supported metrics.
* More ways to organize or personalize the dashboard.
* Optional exports and longer term performance reports.
* Additional tools that help explain unusual system behavior.

If something matters to you, please suggest it through [GitHub Issues](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues). Feedback can help decide what comes next.

## 5. What are the current limitations?

**Apple Silicon hardware sensors:** The reviewed development version does not yet have a dedicated sensor reader for Apple Silicon Macs. Some general macOS metrics may still work, but full hardware monitoring is not verified.

**Sensor availability:** GPU activity, disk temperature, fan readings, and some power measurements may be unavailable depending on the Mac. A Mac without physical fans will not have a fan speed to report.

**Battery and power:** Battery power flow and a hardware power reading are not the same thing as total electricity drawn from an outlet. Some electrical readings still need further interpretation and testing.

**History:** The app has live charts and history in memory, but reliable saved history across restarts is not a completed feature.

**Public download:** There is no signed and verified beta installer available yet.

For a clearer explanation of what is a limitation, what is expected behavior, and what should be reported as a bug, see [Known Issues and Limitations](KNOWN_ISSUES.md).

## 6. How to follow progress

The [Releases page](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases) will host public beta downloads when available.

The [Changelog](../CHANGELOG.md) covers work already completed, while this roadmap explains where the project is headed.

For suggestions, compatibility questions, or future beta bug reports, visit [GitHub Issues](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues).

**Thanks to everyone who followed GlassGauge after the original r/macapps preview. The project is still being developed, and I want to make its progress easier to follow.**
