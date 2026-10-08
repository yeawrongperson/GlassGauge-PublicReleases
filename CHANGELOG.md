# GlassGauge — Changelog

This file covers **publicly relevant development milestones**. A development milestone is not a publicly shipped version. Actual downloadable releases will be identified by their version numbers and links once packages are available.

## Unreleased — Preparing the first public beta

**Status as of October 8, 2026:** no distributable build has been published in this repository.

### In progress

- Preparing an external beta packaging and installation workflow.
- Validating macOS compatibility, code signing, notarization, and hardware requirements before publishing an installer.
- Organizing public documentation, known issues, feedback, and release notes.
- Identifying unsupported or hardware-specific data sources so beta testers have accurate expectations.

### Known constraints

- The current Intel hardware-sensor path has been tested on an Intel MacBook Pro, but cannot be treated as a compatibility guarantee for every Intel Mac.
- The verified development snapshot does **not** include a dedicated Apple Silicon hardware-sensor backend.
- Some metrics may be unavailable on specific hardware; unavailable is not a zero reading.
- Selected SMC power readings cannot yet be labeled as verified total Mac or wall-outlet power.
- A signed and notarized public beta artifact has not been verified or published.

## October 2026 — Development refresh (not a public release)

### Monitoring and sensor accuracy

- Introduced clearer handling of measured, unavailable, stale, and failed sensor readings.
- Refined Intel AppleSMC hardware-sensor reads and tested real fan, temperature, and selected power-related data on an Intel MacBook Pro (MacBookPro16,1).
- Revised reporting so a missing sensor is not represented as a fabricated number.
- Revisited CPU-utilization presentation and the difference between overall CPU use and per-process percentages.
- Audited battery current and voltage interpretation, along with charging and external-power state changes.
- Avoided treating an unverified SMC power key as a confirmed total system-power meter.

### Interface and experience

- Reworked the native AppKit glass backdrop used under SwiftUI views.
- Added or refined a background transparency adjustment.
- Continued tuning the dashboard, metric panels, and native window behavior.

### Existing functionality retained

The live overview, chart-based historical samples, detail views, and network traffic presentation were already part of the project's earlier monitoring foundation. They should not all be described as newly invented in October 2026.

## 2025 — Original development and community preview

- GlassGauge began as a modern, glass-inspired macOS system-monitoring project.
- Early development established a live overview for major performance metrics, graph views, and a native desktop presentation.
- A preview shared with the r/macapps community reached approximately 146,000 views and 137 shares, according to the original post's reported statistics.
- The project was still under development; the initial public preview was **not** a downloadable general-release milestone.

## Future version entries

When a packaged beta actually ships, add an entry using this structure:

```markdown
## [v0.x.x-beta.1] — YYYY-MM-DD

### Added
- ...

### Changed
- ...

### Fixed
- ...

### Known issues
- ...

### Tested on
- Model, processor, macOS version, build identifier

[Download this release](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/ACTUAL-TAG)
```

Do not turn this template into a live release link until the tag exists.
