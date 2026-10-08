# Roadmap

[Home](../README.md) / Roadmap

This roadmap is a **direction of work**, not a release schedule. Priorities can change as testing reveals issues. Items described as completed in development have not necessarily been included in a publicly released build.

## Foundation: present in the reviewed development project

* [x] Native macOS application using SwiftUI and AppKit.
* [x] Live overview for major system metrics.
* [x] Time series metric charts and individual detail views.
* [x] Compact menu bar overview.
* [x] Adjustable glass background transparency.
* [x] Hardware reading states that distinguish measurement from missing/error/stale data.
* [x] Intel hardware sensor provider tested on one Intel MacBook Pro.

## Before the first public beta: active priorities

* [ ] Complete a release candidate Xcode build and smoke test.
* [ ] Determine and publish supported macOS versions and Mac hardware models.
* [ ] Test packaging, Developer ID signing, and notarization.
* [ ] Verify the app's permissions, helper behavior, and launch experience.
* [ ] Validate app stability, sampling overhead, chart behavior, and startup time.
* [ ] Prepare actual dashboard screenshots and installation instructions.
* [ ] Audit privacy and any diagnostic data collection or transmission.
* [ ] Publish versioned beta notes, known issues, and verified installer checksums when applicable.
* [ ] Open a structured path for bug reports and compatibility feedback.

## Next: after initial testing (tentative)

* [ ] Extend verified hardware sensor support to additional Intel models.
* [ ] Investigate and implement an Apple Silicon hardware sensor backend where technically feasible.
* [ ] Improve explanations and provenance for advanced temperature and power metrics.
* [ ] Refine battery, power source, and charging state UI based on beta reports.
* [ ] Add deeper CPU and individual process views once performance and correctness are validated.
* [ ] Improve historical storage, retention options, and export if appropriate.
* [ ] Continue accessibility, reduced motion, and native window refinements.

## Not on the promised first beta list

Fan control features, universal sensor support, hard real time hardware accuracy, and long term analytics are **not guaranteed**. Items above will only be called shipped when they appear in a tested release.

Suggest an improvement or report a gap under [Issues](https://github.com/yeawrongperson/GlassGauge-PublicReleases/issues).
