# Privacy and security notes

[Home](../README.md) / Privacy & Security

> **0.1.1 Alpha notice:** The first public Intel alpha has been released. This page is a transparency note, **not an independently audited privacy policy**.

## Monitoring and permissions

GlassGauge is built around operating system performance APIs and, where supported, Mac hardware sensor interfaces. Some system monitoring can be done without elevated privileges; other tools and older helper experiments can require specific authorizations.

The reviewed October 2026 development design:

* Uses a normal Intel AppleSMC reader for available hardware metrics, without an automatic administrator prompt during standard monitoring.
* Represents unsupported, failed, and outdated hardware readings explicitly.
* Contains an optional **legacy helper diagnostic** path in Settings that may request administrator credentials when the user chooses to invoke it.
* Does not use that optional legacy helper as the normal sensor sampling path in the current reviewed design.

In 0.1.1 Alpha, normal monitoring does not require administrator access. Optional legacy helper diagnostics, where present, are separate and may prompt when explicitly selected.

## No unverified privacy promises

Additional privacy and security documentation work includes verifying:

* Whether any analytics, crash reports, update checks, or other network communications exist.
* Local storage and deletion details. SQLite persists normal telemetry and event Logs, with telemetry retained up to approximately 48 hours.
* Whether any external services are used.
* Which permissions a user actually sees, and why they are requested.
* How signing, notarization, and the download's authenticity are verified.

Until that audit is complete, **do not interpret the absence of a privacy claim as proof of zero data collection**.

## Local diagnostic reports

GlassGauge 0.1.1 can create diagnostic reports locally with selected hardware, sensor, and support information. It does **not** automatically upload those reports. Saving or attaching one to GitHub Issues is a user choice. Personal files, credentials, and network identifiers are intentionally excluded. Review a report before posting it publicly. These are implementation claims, not a guarantee of an independently audited privacy policy.

The separate Clear Graph History and Clear Event Log actions allow users to delete the corresponding stored information.

## Official downloads only

The [official 0.1.1 Alpha Intel ZIP](https://github.com/yeawrongperson/GlassGauge-PublicReleases/releases/tag/v0.1.1-alpha) is already published. **This build is unsigned and not notarized.** macOS may require Finder > Open or System Settings > Privacy & Security > Open Anyway after a blocked launch. See [Getting Started](GETTING_STARTED.md). Do not disable Gatekeeper globally or strip quarantine attributes. Future signing and notarization improvements remain under consideration.

## Public bug reports

Please **redact** personal details from logs and screenshots. Never upload passwords, authentication tokens, device serial numbers, full home directory paths, or private documents to a GitHub Issue.

If sensitive security behavior is discovered, avoid publishing exploitable details or credentials in a public issue; request an appropriate private reporting channel from the maintainer.
