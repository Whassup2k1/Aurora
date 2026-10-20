# 🔒 Aurora Privacy

**Your media. Your server. Your world.**

> **Development notice:** Aurora is under private development and validation. This document describes the project's privacy design and intended practices, not an independently audited privacy certification. Details may change before public distribution.

## Local-first by design

Aurora is a self-hosted media ecosystem. The Aurora Server is designed to run on equipment you control and store the catalog, configuration and user data required for local use on that server. A mandatory centralized Aurora account is not part of the intended normal local experience.

**Local-first does not mean fully offline.** Some features can contact external providers or online resources, including automatically when a feature is configured to do so. Actual network behavior depends on the build, enabled features and configuration.

## Information stored on your server

Depending on which features are enabled, Aurora may store or process:

- Media-library paths, titles, catalog entries, artwork and metadata
- User accounts, access controls, settings, favorites and playlists
- Playback progress, watch/listen history and application state
- Lyrics, karaoke and guitar-related data
- TV/IPTV source details, guide data and relevant credentials
- Integration settings, API keys or tokens where required
- Local logs, diagnostic information and backups
- Chat or other collaboration data **only if and when such functionality is implemented and enabled**

Your server administrator controls access to the machine, backups and users. Other authorized accounts on the same server may have access to information depending on the configured permissions.

## Information sent to the Aurora project

Aurora is **not designed to require uploading your media library or playback history to a centrally operated Aurora service** for ordinary local use. The project does not currently advertise a mandatory telemetry service.

This is a description of project intent and current design, **not a guarantee that every development build has been independently audited for all outbound traffic**. Network and telemetry behavior should be reviewed and documented for each supported release.

Information you voluntarily post to GitHub Issues, Discussions or other support channels is separate from data held by your Aurora Server and is governed by the policies of those services.

## Optional online integrations

Features involving metadata, artwork, trailers, news, lyrics, updates or other integrations may contact third-party services. Requests may disclose information necessary to complete the operation, such as media titles, search terms, source identifiers, public IP address and technical request metadata. Providers control their own retention and privacy practices.

The availability of a feature, the ability to disable it and the exact information exchanged will be documented as implementations are validated. Do not assume every online connection is optional until the relevant release documentation confirms it.

## Credentials, diagnostics and logs

Aurora may need API tokens and other credentials for integrations. Treat server configuration, logs and backups as sensitive: they can contain tokens, internal addresses, media names, account identifiers or other private data.

Never post unredacted logs, server configuration, screenshots containing keys or copies of databases in public reports.

## Remote access and other clients

Desktop, Experience and Android are designed to work with Aurora Server. Device-to-server communication and any remote access depend on the client, network and configuration. Exposing a private server on the public internet creates security and privacy risks; follow only supported release-specific guidance.

## Backups and deletion

Backup copies may retain application data even after items are removed from the active installation. Users are responsible for managing their own storage, retention and recovery policies. Exact in-app data deletion and uninstall behavior will be documented with released builds; an uninstaller should not be assumed to remove every backup or machine-level file.

## Languages

French and English are supported in private development. Additional languages are planned but not yet announced as available.

## Reporting and changes

For general questions, see [Support](SUPPORT.md). Report security vulnerabilities privately using [Security](SECURITY.md).

This document will be updated as product behavior and distribution practices are verified. It does not replace the privacy policy of any optional third-party provider.

[Overview](README.md) · [Features](FEATURES.md) · [Early Access](EARLY_ACCESS.md) · [Security](SECURITY.md)
