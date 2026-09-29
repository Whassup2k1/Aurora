<p align="center">
  <img src="images/aurora-logo.png" alt="Aurora" width="420">
</p>

<p align="center">
  <strong>Local streaming for your world.</strong>
</p>

<p align="center">
  Your self-hosted multimedia hub for music, karaoke, guitar tabs, news, movies, series, TV and more.
</p>

<p align="center">
  <strong>Modern. Private. Self-hosted.</strong>
</p>

<hr>

<div align="center">

<h2>🧪 Aurora Early Access</h2>

<p>
Aurora is getting closer to its first public release.
</p>

<p>
We're looking for early testers who want to experience Aurora,<br>
share feedback and help us polish the experience before launch.
</p>

<p>
<strong>Music · Movies · Series · TV · Karaoke · Guitar Tabs · News</strong>
</p>

<h3>🌌 Be among the first to experience Aurora.</h3>

<p>
<a href="https://github.com/Whassup2k1/Aurora/discussions/1">
<strong>→ Join the Aurora Beta Testing Program</strong>
</a>
</p>

</div>

<hr>

<p align="center">
  <a href="#installation">Installation</a> •
  <a href="#screenshots">Screenshots</a> •
  <a href="#roadmap">Roadmap</a> •
  <a href="#contributing">Contribute</a> •
  <a href="#support-aurora">Support Aurora</a>
</p>

---

<p align="center">
  <img src="images/hero-dashboard.png" alt="Aurora Dashboard" width="100%">
</p>

---

## ✨ What is Aurora?

Aurora is a modern, self-hosted multimedia platform designed to bring your personal media into one unified experience.

It started as a music player.

It is becoming much more.

Aurora is being built as a complete home entertainment hub combining music, movies, series, live TV, karaoke, guitar tools, news and server management inside one modern interface.

Instead of feeling like a traditional media server control panel, Aurora is designed to feel like a real streaming product — while keeping your library and infrastructure under your control.

> **Your media. Your server. Your experience.**

---

## 🎵 Built for music first

Music is at the heart of Aurora.

Aurora includes a native music library and playback architecture designed for local, high-quality audio.

Current and planned music features include:

- Native music library
- Album and artist browsing
- FLAC and high-quality audio playback
- HTTP Range streaming and seeking
- Play queue
- Favorites
- Playlists
- Global search
- Rich artist and album artwork
- Metadata enrichment
- Advanced audio processing
- Equalizer
- Master Reference audio mode
- Fullscreen player
- Multi-user support

Aurora is powered by its own native Aurora Server architecture for media management, streaming, metadata, administration and platform services.

---

## 🎤 Karaoke

Aurora is also being designed as a complete karaoke environment.

The goal is to provide:

- synchronized lyrics
- fullscreen karaoke mode
- queue management
- singer rotation
- local music integration
- party-friendly controls

Karaoke remains under active development.

---

## 🎸 Guitar Tabs & Practice

Aurora includes a dedicated guitar practice experience powered by AlphaTab.

Features currently being developed include:

- Guitar Pro file support
- tablature
- standard notation
- track selection
- playback transport
- speed control
- metronome
- count-in
- A/B looping
- tuning information
- transposition
- MIDI support
- print support
- practice mode

Aurora aims to combine music listening and music practice in the same environment.

---

## 📰 Music News

Aurora includes an editorial music news system designed to keep the reading experience inside Aurora.

The long-term goal includes:

- local article storage
- source attribution
- multilingual translation
- editorial validation
- artist-related news
- personalized discovery

---

## 🎬 Movies, Series & TV

Aurora is evolving beyond music.

The multimedia roadmap includes:

- Movies
- Series
- Live TV
- IPTV
- rich metadata
- posters and backdrops
- trailers
- watch progress
- unified search
- home dashboard recommendations

The goal is not to simply reproduce another media server interface.

Aurora is designed around a unified streaming-style experience.

---

## 🏠 One Home. Multiple Worlds.

Aurora's long-term interface is built around a global dashboard.

From there, each major section becomes its own experience:

**Home → Music → Movies & Series → TV → News → Karaoke → Guitar**

The main dashboard will be able to mix content from different parts of Aurora while dedicated dashboards provide deeper experiences for each type of media.

---

## 🖥 A modern interface

Aurora is built around a premium, adaptive interface designed for desktop computers, televisions and other screen sizes.

The interface is inspired by the usability of modern streaming applications without trying to copy any particular service.

Aurora focuses on:

- large artwork
- immersive layouts
- adaptive navigation
- dynamic visual accents
- dark interface
- readable typography
- simple controls
- minimal technical clutter

> A home media server should not have to look like a server.

---

<a id="screenshots"></a>

## 📸 Screenshots

### Music Home

<p align="center">
  <img src="images/music-home.png" alt="Aurora Music Home" width="100%">
</p>

### Album

<p align="center">
  <img src="images/album-page.png" alt="Aurora Album Page" width="100%">
</p>

### Fullscreen Player

<p align="center">
  <img src="images/fullscreen-player.png" alt="Aurora Fullscreen Player" width="100%">
</p>

### Search

<p align="center">
  <img src="images/search.png" alt="Aurora Search" width="100%">
</p>

### Movies

<p align="center">
  <img src="images/movies.png" alt="Aurora Movies" width="100%">
</p>

### Administration

<p align="center">
  <img src="images/admin-dashboard.png" alt="Aurora Admin Dashboard" width="100%">
</p>

---

## ⚙️ Aurora Server

Aurora is more than a frontend.

Aurora Server provides the local backend responsible for:

- media libraries
- scanning and indexing
- PostgreSQL catalog
- users
- authentication
- streaming
- metadata
- artwork
- integrations
- backups
- updates
- diagnostics
- local HTTPS
- local network discovery

Aurora is designed so that users should not need to manually configure Docker containers, databases or internal services just to get started.

---

## 🔌 API & Services

Aurora can use external services to enrich your library.

Current or planned integrations include:

**Automatic services**

- MusicBrainz
- Wikidata
- Wikipedia
- Wikimedia Commons
- Cover Art Archive

**Optional services**

- TheAudioDB
- Fanart.tv
- YouTube Data API
- TMDB
- Setlist.fm

API credentials are designed to remain server-side and can be stored using Aurora's encrypted local secret vault.

---

## 🔒 Privacy & Local-First

Aurora is designed around a local-first philosophy.

Your media library remains on your infrastructure.

Aurora does not require a mandatory cloud account for basic local use.

Where external APIs are enabled, Aurora connects to those services only for the features that require them.

Sensitive integration credentials are stored server-side rather than being exposed to the browser.

---

## 🛠 Administration

Aurora includes its own administration environment for managing the server.

The Admin interface includes or is being developed for:

- Libraries
- Scan jobs
- Catalog
- Artwork
- API & Services
- Metadata
- Users
- System health
- Server diagnostics
- Updates
- Backup and recovery

The goal is to make Aurora manageable without requiring users to understand the internal server architecture.

---

<a id="installation"></a>

## 📦 Installation

> **Aurora is currently under active development and preparing for its first public release.**

The objective is to make installation extremely simple.

On supported Ubuntu systems, Aurora is being packaged as a native `.deb` package.

Example:

```bash
sudo apt install ./aurora-server_xxx_amd64.deb
```

After installation, Aurora initializes its required services and can be accessed through a web browser.

Example local address:

```text
https://aurora.local
```

The installer is designed to configure Aurora's own:

- application runtime
- PostgreSQL database
- migrations
- media services
- HTTPS proxy
- local network identity
- update system
- backup system

No manual PostgreSQL or Docker configuration should be required for a normal installation.

---

## 🐧 Platform Support

### Current focus

Ubuntu Server / Linux

### Planned

Windows  
macOS  
additional Linux distributions  
TV clients  
mobile clients

Aurora's server architecture is being stabilized on Linux before expanding to additional platforms.

---

## 🔄 Updates & Recovery

Aurora's native installation architecture includes support for:

- versioned releases
- automatic pre-upgrade backups
- database backups
- update health validation
- previous-release tracking
- rollback support
- persistent configuration
- server diagnostics

The objective is to make Aurora safe to update without putting an existing library at risk.

---

## 🧪 Project Status

Aurora is currently in **active development**.

Core systems already under development or validation include:

- native Aurora Server
- music catalog
- audio streaming
- global search
- library scanning
- administration
- artwork management
- API integrations
- metadata
- updates
- backups
- local HTTPS
- mDNS discovery

Several major modules remain under active development before the first stable public release.

---

<a id="roadmap"></a>

## 🗺 Roadmap

### Core

- Native Aurora Server
- Universal installer
- Music library
- Audio streaming
- Global search
- Library scanner
- Admin interface
- Metadata providers
- Artwork management
- Multi-user support

### Multimedia

- Movies
- Series
- Live TV / IPTV
- Unified home dashboard

### Music Experience

- Advanced player
- Audio enhancements
- Karaoke
- Guitar Tabs
- Practice tools
- Music News

### Platforms

- Linux
- Windows
- macOS
- Apple TV / TV experience
- additional clients

A more detailed roadmap will be available in [`ROADMAP.md`](ROADMAP.md).

---

## 🏷 Versioning

Aurora's public releases are planned to use a calendar-based version format:

```text
YY.WW.RRR
```

Example:

```text
26.39.001
```

Where:

```text
26  = year 2026
39  = ISO week
001 = release revision during that week
```

So no — you didn't miss 25 major versions. 😄

The version number is designed to make it easy to understand roughly when an Aurora release was produced.

---

## 💡 Philosophy

Aurora is built around a few simple ideas:

**Media should feel beautiful.**

**Self-hosting should not require becoming a system administrator.**

**Local media should feel as polished as commercial streaming services.**

**One server should be able to provide one coherent entertainment experience.**

Aurora is being built with those goals in mind.

---

<a id="contributing"></a>

## 🤝 Contributing

Aurora is still young, and contributions will become increasingly important as the project grows.

Contributions may include:

- bug reports
- testing
- documentation
- translations
- UI/UX improvements
- Linux packaging
- backend development
- frontend development
- metadata providers
- platform clients

See [`CONTRIBUTING.md`](CONTRIBUTING.md) for more information.

---

## 🐛 Bugs & Feature Requests

If you find a bug or have an idea for Aurora, please use GitHub Issues.

When reporting a bug, include as much useful information as possible:

- Aurora version
- operating system
- browser/client
- reproduction steps
- relevant logs
- screenshots when useful

Please never include API keys, passwords or other secrets in public issues.

---

<a id="support-aurora"></a>

## ❤️ Support Aurora

Aurora is an independent project.

If you enjoy Aurora and want to support its development, donation/support options will be added as the project approaches public release.

Support helps with development, testing, infrastructure and the time required to keep improving Aurora.

---

## 📚 Documentation

Documentation will progressively be added under the [`docs`](docs/) directory.

Planned documentation includes:

- Installation
- Server administration
- Libraries
- Metadata
- API integrations
- Backup & restore
- Troubleshooting
- Development
- Architecture

---

## ⚠️ Development Notice

Aurora is under active development.

Interfaces, APIs, installation procedures and features may change before the first stable public release.

Do not consider development builds a replacement for a tested production media server without maintaining backups of your data.

---

## 📄 License

License information will be provided in [`LICENSE`](LICENSE).

---

<p align="center">
  <strong>AURORA</strong><br>
  <em>Music for your world.</em>
</p>
