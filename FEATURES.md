Aurora — Features & Capabilities
Your media. Your server. Your world.

Aurora is an independently developed, self-hosted entertainment ecosystem. It brings personal media, discovery, playback, and administration together across a server and multiple connected experiences.
Development notice: Aurora is in private development and validation. This page describes current internal capabilities and directions—not a promise of public availability. No public application downloads or source-code releases are offered here.

[← Overview](README.md) · [Roadmap](ROADMAP.md) · [Installation status](INSTALLATION.md) · [Early Access](EARLY_ACCESS.md)
At a glance
Component	Purpose	Current status
Aurora Server	Libraries, catalog, metadata, streaming, administration and system services	🧪 Private validation on Linux and macOS
Aurora Desktop	Full personal-media experience in the browser/desktop environment	🧪 Functional internally; evolving
Aurora Experience	Immersive, fullscreen, remote-friendly interface	🧪 Functional internally; integration and TV experience being refined
Aurora Android	Dedicated Android client	🧪 Functional internal builds; validation ongoing
Aurora Cinema Engine	Aurora's video playback and media-processing work	🚧 Active development and testing
Aurora Server for Windows	Windows installation and integration	🗺️ Planned / not publicly available


Status key: ✅ Implemented in the internal environment · 🧪 Implemented but still being validated · 🚧 In active development · 🗺️ Planned

These are development indicators, not public download or support guarantees. Capabilities and status may differ across platforms and clients.
One ecosystem, different experiences
Aurora Server
Aurora Server is the self-hosted foundation of the ecosystem. It organizes personal libraries and provides services to connected clients.
- ✅ Local media-library indexing and catalog management
- 🧪 Metadata and artwork enrichment, with optional external providers
- 🧪 Music and video delivery to supported clients
- 🧪 User accounts, administration, monitoring and diagnostics
- 🧪 Persistent configuration, database migrations and backup workflows
- 🚧 Safe installation, updates, recovery, and cross-platform packaging
Aurora Desktop
The complete everyday interface for exploring and enjoying your library, including music, films, series and complementary media tools.
- ✅ Music navigation, artists, albums, tracks, playlists and favorites
- ✅ Search, playback queue and fullscreen music player
- 🧪 Movies and series discovery, artwork-rich browsing and playback
- 🧪 TV, karaoke, tablature, news and other integrated sections
- ✅ Dark, light and premium visual themes; dynamic accents
- 🧪 Ongoing user-experience, accessibility and cross-module refinements
Aurora Experience
A dedicated fullscreen environment designed for a living-room-style experience while remaining connected to Aurora Server.
- 🧪 Immersive browsing and navigation designed for larger screens
- 🧪 Keyboard, controller and remote-style directional navigation
- 🧪 Movies, series and television experiences under active refinement
- 🚧 Final TV-guide performance, IPTV integration and visual polish
- 🚧 Packaging and device-by-device compatibility validation
Aurora Android
A dedicated Android client sharing the Aurora ecosystem rather than being a separate media server.
- 🧪 Internal Android application builds and media interaction
- 🧪 Connection to Aurora Server
- 🧪 Client-side navigation and playback testing
- 🚧 Integration, performance, signing, reproducible builds and broader device validation
An internal working client does not mean a public Android release is available.
Aurora Cinema Engine
Aurora Cinema Engine is the ongoing work on the video playback and processing pipeline used by the Aurora ecosystem.
- 🚧 Playback reliability and startup behavior
- 🚧 Media compatibility, seeking and streaming behavior
- 🚧 Transcoding and platform-specific acceleration paths where supported
- 🚧 Testing across browsers, devices and operating systems
Performance, codec support, hardware acceleration and concurrent-stream limits will only be documented as guarantees after repeatable validation. Hardware and media formats affect the results.
Media experiences
Music & audio
Music remains one of Aurora's most mature areas.
Capability	Status
Native library with artists, albums and tracks	✅
Playlists, favorites and recently played	✅
Search and playback queue	✅
Persistent player bar and fullscreen player	✅
FLAC playback and seeking on supported clients	🧪
Artwork and metadata enrichment	🧪
Audio enhancements and advanced controls	🧪


Movies & TV series
Aurora's cinematic library experience has evolved well beyond a placeholder, but its interface and playback stack are still being polished.
Capability	Status
Movie and series libraries	🧪
Posters, backdrops and cinematic artwork	🧪
Rich titles, details and metadata	🧪
Video playback	🧪
Browsing rows, discovery and recently added content	🧪
Watch state, progress and cross-client consistency	🚧
Collections, studios and expanded people pages	🚧
Cinema Engine integration and compatibility validation	🚧


Live TV & IPTV
Capability	Status
IPTV/M3U integration	🧪
Channel browsing and management	🧪
EPG / TV guide	🧪
TV playback	🧪
TV guide performance and navigation refinements	🚧
Channel reconciliation, stream reliability and broader validation	🚧


Availability and playback reliability depend in part on the user's own lawful media sources and network conditions. Aurora does not supply IPTV subscriptions or channels.
Karaoke & lyrics
Capability	Status
Lyrics integrated with the music library	🧪
Local lyrics storage and supported synchronization	🧪
Fullscreen lyrics / karaoke experience	🧪
Lyrics retrieval and correction workflows	🚧
Party features, singer queues and rotations	🗺️


Guitar tabs & practice
Aurora integrates a guitar-learning and practice experience using AlphaTab technology.
- 🧪 Supported Guitar Pro file viewing and tablature
- 🧪 Playback and practice controls, depending on file and client support
- 🧪 Musical notation and track-focused practice views
- 🚧 Continued integration and usability refinements
Radio, podcasts & news
- 🧪 Integrated radio and podcast sections
- 🧪 Aurora News and editorial-style presentation
- 🚧 Source enrichment, multilingual content and discovery improvements
Search, personalization & design
- ✅ Music-focused search, artist and album exploration
- 🧪 Broader cross-media discovery
- ✅ Dark, Light and Dark Premium themes
- ✅ Dynamic visual accent behavior, including music-related UI accents
- 🧪 Responsive interfaces designed for desktop and larger-screen experiences
- 🚧 Consistency between Desktop, Experience and Android
Languages
Currently implemented languages: French and English.

Aurora uses a multilingual interface architecture, with translation work extending across navigation, media views and administration. Coverage is being validated as each component evolves.

Additional languages are planned, but no specific language, date or degree of coverage is announced yet. Availability of a translated interface does not imply that third-party metadata or external content is translated.
Administration, reliability & privacy
Server management
Capability	Status
Library scans and catalog administration	🧪
Metadata and artwork administration	🧪
User and system administration	🧪
Server health and diagnostics	🧪
Database migrations and backup mechanisms	🧪
Update validation and recovery / rollback hardening	🚧
Installer, permissions and packaging security reviews	🚧


Local-first approach
Aurora is designed around the principle that your personal media stays on infrastructure you control.
- Personal library storage is self-hosted.
- A mandatory third-party cloud account is not part of the basic local-media vision.
- Certain optional metadata or information features may contact external services when enabled.
- Aurora does not provide movies, music catalogs, television channels or IPTV subscriptions.
For details and limitations, see [Privacy](PRIVACY.md) and [Security](SECURITY.md).
Platform and distribution status
Environment	Current position
Linux server	🧪 Internal deployment and packaging validation
macOS server (Apple Silicon)	🧪 Internal deployment and packaging validation
Windows server	🗺️ Packaging / port planned
Desktop web interface	🧪 Working internal environment
Aurora Experience	🧪 Working internal fullscreen interface; final integration ongoing
Android application	🧪 Internal application under validation
Android TV / Google TV	🚧 Device and living-room integration testing; public support not yet declared
iOS / iPadOS / Apple TV	🗺️ No public release announced


No official public builds are available at this time. The project does not publish source code through this public documentation repository.
Longer-term ideas
The following ideas are not shipping features and are not commitments for the first public beta:
- 🗺️ Shared watching and listening experiences
- 🗺️ Aurora Party / collaborative sessions
- 🗺️ Broader connected-device experiences
- 🗺️ Additional languages and client platforms
For sequencing and priorities, see the [Roadmap](ROADMAP.md). Development priorities may change after testing.
Early Access & feedback
Aurora is being prepared for controlled testing. Feedback on hardware compatibility, usability, accessibility, playback reliability, installation and localization will be valuable when Early Access is announced.

Read [Early Access](EARLY_ACCESS.md) and [Contributing](CONTRIBUTING.md) for current information. Expressing interest does not grant immediate access to private builds.
AURORA
Your media. Your server. Your world.

Independent development · Self-hosted media · Proprietary application code
