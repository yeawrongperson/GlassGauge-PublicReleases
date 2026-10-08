# Privacy and security notes

[Home](../README.md) / Privacy & Security

> **Before release notice:** This is a transparency and preparation document, **not yet a final audited privacy policy** for a downloadable app. The first public beta has not been released.

## Monitoring and permissions

GlassGauge is built around operating system performance APIs and, where supported, Mac hardware sensor interfaces. Some system monitoring can be done without elevated privileges; other tools and older helper experiments can require specific authorizations.

The reviewed October 2026 development design:

* Uses a normal Intel AppleSMC reader for available hardware metrics, without an automatic administrator prompt during standard monitoring.
* Represents unsupported, failed, and outdated hardware readings explicitly.
* Contains an optional **legacy helper diagnostic** path in Settings that may request administrator credentials when the user chooses to invoke it.
* Does not use that optional legacy helper as the normal sensor sampling path in the current reviewed design.

These observations are specific to the reviewed code and must be validated again on the packaged beta.

## No unverified privacy promises

Before the first release, the project needs to verify and document:

* Whether any analytics, crash reports, update checks, or other network communications exist.
* Whether logs, metrics, or settings are persisted to disk, for how long, and how to delete them.
* Whether any external services are used.
* Which permissions a user actually sees, and why they are requested.
* How signing, notarization, and the download's authenticity are verified.

Until that audit is complete, **do not interpret the absence of a privacy claim as proof of zero data collection**.

## Official downloads only

Future installers should come from the project's official [GitHub Releases](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases), with clearly identified versions and release notes. The release process will assess appropriate Developer ID signing and notarization. Users will not be instructed to defeat macOS security checks to install an unverified package.

## Public bug reports

Please **redact** personal details from logs and screenshots. Never upload passwords, authentication tokens, device serial numbers, full home directory paths, or private documents to a GitHub Issue.

If sensitive security behavior is discovered, avoid publishing exploitable details or credentials in a public issue; request an appropriate private reporting channel from the maintainer.
