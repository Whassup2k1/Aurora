Installing Aurora
<p align="center"><strong>Your media. Your server. Your world.</strong></p>

[!IMPORTANT]
Aurora is currently in private development and validation. There are no public installers, release packages, or download links at this time. This document describes the intended installation experience and the current platform status; it is not a procedure for installing unreleased software.

Aurora is a self-hosted entertainment ecosystem: one Aurora Server organizes your personal media and makes it available to compatible Aurora clients on your devices.

The goal: Install Aurora Server, connect your media library, then enjoy it across your screens—without requiring a mandatory cloud account for ordinary local playback.
Installation at a glance
Component	Current status	What it does
Aurora Server — Linux (Ubuntu)	Working internally; packaging and validation ongoing	Hosts libraries, application services, accounts, metadata, and streaming
Aurora Server — macOS (Apple silicon)	Working internally; installation and updates under validation	Runs Aurora Server on a Mac
Aurora Server — Windows	Planned / in development	Future Windows server installation
Aurora Desktop	Working internally	Full desktop-oriented web experience
Aurora Experience	Working internally; optimization and integration ongoing	Immersive, fullscreen, controller/remote-friendly interface
Aurora Android	Working internally; private validation ongoing	Android client for the Aurora ecosystem
Aurora Cinema Engine	Active development and testing	Playback and media-processing capabilities used by Aurora
iPhone / iPad web experience	Private-device experiments; distribution not announced	Browser / home-screen experience where supported


These statuses describe development progress, not public availability. A working internal build does not mean a package is ready for external installation. Platform support, hardware requirements, and rollout order may change before beta.
1. Aurora Server
Aurora Server is the central component. It manages your media library, users, metadata, artwork, streaming endpoints, and the services needed by connected Aurora clients.

Aurora aims to provide an installer that configures the necessary application services rather than asking everyday users to assemble and maintain a database and individual service containers manually. The exact requirements and supported installation methods will be published with the first testable packages.
Linux / Ubuntu
The Linux server build is operational in private environments. Packaging, upgrade behavior, security, media compatibility, and clean-install testing are being finalized.

Public installation commands: not available yet. Please do not run installation scripts or download packages from unofficial sources claiming to be Aurora releases.
macOS
Aurora Server has a working private Apple silicon implementation. Native installation, service management, backup, migrations, and upgrade/recovery behavior are being validated.

Public macOS installer: not available yet. Final minimum hardware and macOS requirements will be announced with the supported release.
Windows
A Windows Server package is planned. Its installation procedure and system requirements will be published after development and validation.

Public Windows installer: not available yet.
2. Aurora Clients
Aurora is built around multiple ways to enjoy the same personal library.
Aurora Desktop
The desktop-oriented Aurora interface provides library browsing, playback, discovery, and access to the available modules. It connects to an Aurora Server. Access and setup details for external testers will be supplied with supported builds.
Aurora Experience
Aurora Experience is the immersive, fullscreen interface designed for living-room-style interaction, including keyboard and compatible controller/remote navigation. It is undergoing integration and performance validation alongside the rest of Aurora.

It is an experience connected to Aurora Server, not a separate replacement server.
Aurora Android
The dedicated Android client is functional in private testing. Device compatibility, packaging, playback, and integration are being validated before any public distribution.

No public APK or Play Store listing is announced here. Only install packages from official Aurora distribution channels once available; do not use third-party APK mirrors.
Other devices
Browser-based access and home-screen experiences are being explored for supported devices. Support for iOS/iPadOS, Android TV / Google TV, Apple TV, and other platforms will be confirmed individually as official builds or supported browser workflows become available.
3. First-time setup (planned workflow)
When a supported Aurora Server installer is released, the expected setup will broadly follow these steps:
1. Install Aurora Server using the official package for your operating system.
2. Complete the initial administrator and server configuration.
3. Choose the folders or storage locations containing your own media.
4. Let Aurora scan and catalog the selected libraries.
5. Open a supported Aurora interface or connect a compatible client on your local network.
6. Configure optional integrations only if you choose to use them.
The actual screens, addresses, and options may differ by platform and beta build. A hostname such as aurora.local is not guaranteed to work on every home network; use the address or discovery instructions provided by your own Aurora installation.
4. Your media and storage
Aurora is designed to work with personal media hosted on storage you control, including appropriately mounted local drives and other server-accessible storage.
- Keep media files separate from the operating system and application data where practical.
- Ensure the Aurora Server process has the necessary read permissions; writing permissions are needed only for operations that require them.
- Do not move, reformat, or delete an existing media drive without verifying your backups and mount configuration.
- Actual library and storage support will depend on the server build and filesystem permissions.
Aurora does not supply commercial movie, television, or music catalogs. Users are responsible for their media and any sources they configure.
5. Languages
Aurora's interface currently supports French and English in private development builds. More languages are planned, but their availability and quality will be announced only after translation and validation.
6. Network and security
Aurora is being designed for local-first, self-hosted use.
- Start on a trusted home network.
- Do not expose Aurora Server directly to the public Internet unless an officially documented, supported, and secured remote-access method is available.
- Protect administrator credentials and keep the host operating system updated.
- Follow the certificate and HTTPS guidance shipped with the actual release; do not install unknown root certificates or configuration profiles obtained from unverified sources.
- Optional external metadata services may require network access; these are different from mandatory cloud hosting of your local library.
See [Security](SECURITY.md) and [Privacy](PRIVACY.md).
7. Updates, backups, and recovery
Aurora's installation architecture is being developed and tested with attention to preserving configuration and media libraries during updates. Backup, migration verification, and recovery behavior remain part of release validation.

Before installing or updating a future beta:
1. Make independent backups of irreplaceable media and configuration.
2. Read the release-specific installation or update notes.
3. Verify the installer comes from an official Aurora source.
4. Retain a recovery path for the server and its application data.
Do not assume that rollback or unattended recovery is guaranteed in every beta build. Detailed backup and restore procedures will accompany supported releases.
8. Uninstallation
Platform-specific uninstallation instructions will be published alongside each supported installer. Aurora's design aims to keep the user's original media separate from the application, but you should always confirm the uninstaller's behavior and safeguard your files before removing software.
9. Troubleshooting and bug reports
When official beta testing begins, useful reports will include:
- Operating system and hardware architecture
- Aurora component (Server, Desktop, Experience, Android, Cinema Engine)
- Build identifier if one is provided with your test build
- Expected behavior versus actual behavior
- Steps to reproduce the problem
- Relevant redacted logs and screenshots, when appropriate
Never share passwords, tokens, private keys, account cookies, or unredacted private network details in public issues or discussions. For vulnerabilities, follow [SECURITY.md](SECURITY.md).

See [Support](SUPPORT.md) for general assistance and reporting guidance.
10. Early Access
Aurora is preparing for a limited Early Access program. Interest in testing does not guarantee immediate access, and not every platform or feature will be included in the first testing group.

[Learn about Aurora Early Access](EARLY_ACCESS.md)
Join the Aurora Beta Testing Program discussion
Explore: [Overview](README.md) · [Features](FEATURES.md) · [Roadmap](ROADMAP.md) · [Privacy](PRIVACY.md) · [Security](SECURITY.md)
<p align="center"><strong>Your media. Your server. Your world.</strong></p>
