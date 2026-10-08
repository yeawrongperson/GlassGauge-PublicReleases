# Frequently asked questions

[Home](../README.md) / FAQ

### Is GlassGauge available to download?

**Not yet.** The project is in pre-beta development. Official public builds will appear on [GitHub Releases](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases) when ready.

### Was GlassGauge abandoned after the 2025 Reddit post?

No. Work continued, including a substantial monitoring and interface refresh in 2026. The project still needs release packaging, compatibility testing, and beta validation before a public installer can be offered.

### Is the app free? Is it open source?

Pricing and licensing for the eventual release have **not been announced**. This public repository hosts release information and future downloads; the development source is not being offered here. A public releases repository is not automatically an open-source license.

### Will it work on my M-series Mac?

Apple Silicon is part of the wider compatibility goal, but the sensor coordinator reviewed in October 2026 has **no dedicated Apple Silicon hardware-sensor provider**. Do not assume complete M-series temperature, fan, and power coverage in the first beta. The official compatibility list will be published with the build.

### Will it work on an Intel Mac?

Real Intel SMC readings have been tested in development on an Intel MacBook Pro (`MacBookPro16,1`). Other machines require testing, and not all Intel Macs expose identical sensors.

### Why is a fan, GPU, or temperature reading missing?

Sensor data is hardware- and API-specific. A missing value might mean the physical component doesn't exist, a driver doesn't expose the value, the chosen provider doesn't support it, or a read failed. GlassGauge aims to show unavailable/error states instead of invented readings.

### Why is CPU usage different from Activity Monitor?

Per-process CPU percentages can exceed 100% when a process uses multiple logical CPUs. Whole-machine CPU percentages are normalized differently. Different sampling windows can also produce slightly different readings. See [Features](FEATURES.md).

### Does GlassGauge control fans or overclock the Mac?

**No fan-control or overclocking feature is promised.** GlassGauge is being developed primarily as a monitoring application, not a hardware-tuning utility.

### Does it require an administrator password?

The current Intel sensor-reading path was designed to collect normal measurements without an automatic administrator prompt. Legacy helper diagnostics exist in the development project and may request authorization if invoked explicitly. The final packaged beta permission flow will be documented and verified before release.

### Does it send my data to a server?

A final, audited privacy statement for the public beta has not yet been published. The monitoring design uses macOS hardware and OS sources, but we will not make an unverified blanket claim about analytics, crash reports, storage, or network transmission. See [Privacy & Security](PRIVACY_AND_SECURITY.md).

### Can I help test it?

When a build becomes available, testing and feedback — especially across different Mac models — will be welcome. Read [Beta Feedback](BETA_FEEDBACK.md) for a reporting format.

### When will the beta release?

There is **no announced release date**. The [Roadmap](ROADMAP.md) lists work that should happen before public distribution.
