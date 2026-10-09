# Frequently asked questions

[Home](../README.md) / FAQ

### Is GlassGauge available to download?

**Yes.** [GlassGauge 0.1.1 Alpha for Intel Macs](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.1-alpha) is available now. This is an unsigned, not notarized ZIP release. See [Getting Started](GETTING_STARTED.md).

### Was GlassGauge abandoned after the 2025 Reddit post?

No. Work continued, including a substantial monitoring and interface refresh in 2026. The first Intel alpha has now shipped. Wider compatibility testing and further improvements are ongoing.

### Is the app free? Is it open source?

Future pricing and licensing plans have **not been announced**. The current 0.1.1 Alpha ZIP is publicly downloadable. This public repository hosts release information and future downloads; the development source is not being offered here. A public releases repository is not automatically an open source license.

### Will it work on my Apple Silicon Mac?

Apple Silicon is part of the wider compatibility goal, but the sensor coordinator reviewed in October 2026 has **no dedicated Apple Silicon hardware sensor provider**. The current 0.1.1 Alpha targets Intel x86_64 only. Do not expect this build to support Apple Silicon hardware monitoring.

### Will it work on an Intel Mac?

Real Intel SMC readings have been tested in development on an Intel MacBook Pro (`MacBookPro16,1`). Other machines require testing, and not all Intel Macs expose identical sensors.

### Why is a fan, GPU, or temperature reading missing?

Sensor data is specific to the hardware and API. A missing value might mean the physical component doesn't exist, a driver doesn't expose the value, the chosen provider doesn't support it, or a read failed. GlassGauge aims to show unavailable or error states instead of invented readings.

### Why is CPU usage different from Activity Monitor?

Individual process CPU percentages can exceed 100% when a process uses multiple logical CPUs. Overall computer CPU percentages are normalized differently. Different sampling windows can also produce slightly different readings. See [Features](FEATURES.md).

### Does GlassGauge control fans or overclock the Mac?

**No fan control or overclocking feature is promised.** GlassGauge is being developed primarily as a monitoring application, not a hardware tuning utility.

### Does it require an administrator password?

The current Intel sensor reading path was designed to collect normal measurements without an automatic administrator prompt. Legacy helper diagnostics exist in the development project and may request authorization if invoked explicitly. Normal monitoring in 0.1.1 Alpha does not require administrator access.

### Can I export a diagnostic report?

Yes. In 0.1.1 you can export a local report containing selected hardware, sensor, and support details, copy a shorter summary, and open GitHub Issues from the app. Reports are not automatically uploaded. You choose whether to save or share them, and should review a report before attaching it to a public issue. Personal files, credentials, and network identifiers are intentionally excluded.

### What does Reduce Energy Use on Battery do?

This optional feature can temporarily use a Solid background and pause inactive chart rendering when external power is disconnected. Normal readings and saved telemetry history continue. Your normal appearance preferences return on external power reconnection. It looks at external power connection, not whether the Mac is actively charging.

### Can I clear my graph history or Logs?

Yes. 0.1.1 includes separate Clear Graph History and Clear Event Log actions plus an Overview Clear History shortcut.

### Does it send my data to a server?

A complete independent privacy audit has not been established for 0.1.1 Alpha. The monitoring design uses macOS hardware and OS sources, but we will not make an unverified blanket claim about analytics, crash reports, storage, or network transmission. See [Privacy & Security](PRIVACY_AND_SECURITY.md).

### Can I help test it?

0.1.1 Alpha is available, and testing and feedback across Intel Mac models are welcome. Read [Alpha Feedback](BETA_FEEDBACK.md) for a reporting format.

### When will the next version release?

**0.1.1 Alpha is already available.** No date has been announced for the next build. See the [Roadmap](ROADMAP.md) for current priorities.
