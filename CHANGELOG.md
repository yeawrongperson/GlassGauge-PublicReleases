# GlassGauge Changelog

This page tracks development updates and, once there are downloads, public releases. Work completed inside the development project is not necessarily part of a public beta. Each downloadable release will have its own version number and notes.

## Unreleased: Preparing the first public beta

**Updated October 8, 2026.** No downloadable beta has been published yet.

### Current priorities

* Prepare and test a macOS app package that other people can install.
* Check supported hardware and macOS versions before publishing compatibility claims.
* Verify signing, notarization, permissions, and the installation process.
* Prepare screenshots, release notes, known issues, and a way for beta testers to report problems.

### Things to know before testing

* Intel hardware sensor testing has been performed on an Intel MacBook Pro, but other Intel models still need testing.
* The reviewed development version does not have a dedicated Apple Silicon hardware sensor provider.
* Some sensors may not exist or may be unavailable on a particular Mac.
* Selected SMC power readings do not yet have a verified whole system measurement boundary.
* A signed public installer has not been published.

## October 2026: Monitoring and interface refresh

### Sensor readings

* Updated the monitoring design to distinguish measured readings from unavailable, outdated, or failed data.
* Worked on direct AppleSMC readings for supported Intel Macs, including available fan speeds, temperatures, and selected power information.
* Tested those readings on an Intel MacBook Pro identified as `MacBookPro16,1`.
* Reviewed the way CPU percentages are presented so whole machine CPU activity is not confused with process percentages.
* Investigated battery current, voltage, charging state, and changes between battery and external power.
* Updated the handling of uncertain power readings so they are not described as confirmed total Mac power consumption.

### Design and usability

* Reworked the AppKit backdrop underneath the SwiftUI interface.
* Refined the glass appearance and its transparency setting.
* Continued improving the dashboard and individual metric views.

### Features carried forward from earlier development

The original project already had a live performance dashboard, graph history during a session, detail views, and network traffic charts. Those are part of the foundation, rather than entirely new additions in October 2026.

## 2025: The original GlassGauge preview

GlassGauge began as a macOS system monitor with a modern glass inspired interface. Early development included the main performance overview, graph views, and a desktop layout built around native macOS technology.

I shared an early preview in **r/macapps**, where it reached approximately **146,000 views and 137 shares**. People continued checking on the project afterward. That preview was not a public installer release.

## How future releases will be documented

Once the first build is published, each release entry will include its exact version, date, supported Mac models, changes, known issues, and a link to the downloadable package. See the [release notes template](docs/FIRST_BETA_RELEASE_NOTES_TEMPLATE.md) for the format being prepared.
