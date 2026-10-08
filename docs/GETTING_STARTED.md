# Getting started

[Home](../README.md) / Getting Started

## Current status: no installer yet

The first public beta package has **not been uploaded**. There is currently no official GlassGauge download in this repository. Please don't use an unrelated installer or a file passed around as though it were an official build.

When an official beta exists, it will appear under **[GitHub Releases](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases)** with a version number, date, compatibility requirements, checksums if published, and known issues.

## How installation will work after a release

These steps describe the intended user flow, **not a current download instruction**:

1. Open the official GitHub Releases page.
2. Select a beta whose release notes identify your Mac and macOS version as supported.
3. Download the attached `.dmg` or `.zip` from that release.
4. Follow the specific to that release installation steps (typically placing the application in Applications).
5. Open GlassGauge and review any macOS permissions request before approving it.
6. Verify the application version against the release notes.

The release workflow will be evaluated for appropriate Developer ID signing and notarization before distribution. No step here requires disabling Gatekeeper or stripping quarantine attributes.

## What to expect in an early beta

* Some metrics may appear as unavailable on your machine.
* Sensor labels may be refined as readings are validated.
* Layout and performance may change between beta builds.
* Testing may begin with a narrower supported device list than the eventual goal.
* Early builds may have bugs and should not be relied upon for important hardware decisions.

For the scope and limitations of individual readings, see [Features](FEATURES.md) and [Compatibility](COMPATIBILITY.md).
