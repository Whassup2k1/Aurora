<p align="center">
  <img src="images/aurora-logo.png" alt="Aurora" width="420">
</p>

<p align="center">
  <strong>Your media. Your server. Your world.</strong>
</p>

<p align="center">
  Native installation guide for Aurora on macOS Apple Silicon.
</p>

<p align="center">
  <strong>Private. Local. Yours.</strong>
</p>

<hr>

<div align="center">

<h2>🍎 Aurora for macOS</h2>

<p>
Aurora can run natively on Apple Silicon Macs through the official macOS ARM64 installer.
</p>

<p>
The package includes the Aurora frontend, backend, PostgreSQL runtime,<br>
media tools and the services required to run Aurora locally.
</p>

<p>
<strong>Apple Silicon · ARM64 · Native macOS Installer</strong>
</p>

</div>

<hr>

<p align="center">
  <a href="#requirements">Requirements</a> •
  <a href="#installation">Installation</a> •
  <a href="#open-aurora">Open Aurora</a> •
  <a href="#updating-aurora">Update</a> •
  <a href="#uninstalling-aurora">Uninstall</a> •
  <a href="#purging-aurora">Purge</a> •
  <a href="#troubleshooting">Troubleshooting</a>
</p>

---

## 💻 Requirements

Aurora for macOS currently supports:

- Apple Silicon Macs
- ARM64 architecture
- Administrator access on macOS
- A modern browser such as Safari, Chrome, Firefox or Edge

> [!NOTE]
> The current Aurora macOS package is built for **Apple Silicon / ARM64**.
>
> Intel-based Macs are not currently supported by this package.

Aurora includes the runtime components required to operate the server.

You do **not** need to manually install:

- Node.js
- PostgreSQL
- FFmpeg
- Aurora backend dependencies

Everything required by the standard Aurora macOS installation is included in the package.

---

## 📦 Download Aurora

Download the latest Aurora macOS ARM64 package from the Aurora GitHub Releases page.

The installer filename will look similar to:

```text
AuroraInstaller-<version>.pkg
```

Example:

```text
AuroraInstaller-27.01.999.pkg
```

The version number will depend on the Aurora release you download.

---

# 🚀 Installation

Aurora can be installed using either the standard macOS Installer or Terminal.

---

## Option 1 — Install with Finder

1. Download the Aurora `.pkg` installer.
2. Open the package from Finder.
3. Follow the macOS installation wizard.
4. Enter your administrator password when requested.
5. Wait for the installation to complete.

Aurora will automatically configure its runtime and start the required services.

---

## Option 2 — Install from Terminal

If the Aurora package is located in your Downloads folder, run:

```bash
sudo installer -pkg "$HOME/Downloads/AuroraInstaller-<version>.pkg" -target /
```

Replace `<version>` with the version you downloaded.

Example:

```bash
sudo installer -pkg "$HOME/Downloads/AuroraInstaller-27.01.999.pkg" -target /
```

A successful installation should end with:

```text
installer: The install was successful.
```

Aurora will then start automatically.

---

# 🌌 Open Aurora

Once the installation is complete, open Aurora in your browser:

### http://127.0.0.1:3302

On first launch, Aurora will guide you through the initial setup.

You can then configure:

- your Aurora administrator account
- integrations and API keys
- music libraries
- movie and series libraries
- artwork and metadata services
- TV / IPTV sources
- karaoke
- guitar tools
- other Aurora features

---

## 🧩 What Aurora Installs

Aurora stores its main runtime and persistent application data under:

```text
/Library/Application Support/Aurora
```

Aurora logs are stored under:

```text
/Library/Logs/Aurora
```

Aurora also creates a dedicated macOS system account:

```text
_aurora
```

This dedicated account allows Aurora services to run independently from your personal macOS user account.

---

## ⚙️ Aurora Services

Aurora uses macOS `launchd` to manage its server processes.

| Service | Address |
|---|---|
| Aurora Web Interface | `http://127.0.0.1:3302` |
| Aurora Backend API | `http://127.0.0.1:3303` |

The normal Aurora interface should be accessed through:

### http://127.0.0.1:3302

The backend API is used internally by Aurora and normally does not need to be accessed directly.

---

## 🗄️ PostgreSQL

Aurora includes and manages its own PostgreSQL runtime.

You do not need to install PostgreSQL separately.

During a new installation, Aurora automatically initializes its PostgreSQL database.

PostgreSQL communicates locally using a Unix socket located under:

```text
/var/run/aurora/postgres
```

Aurora does not require PostgreSQL to be exposed publicly over TCP.

---

## 📂 Aurora Data

Aurora stores its main application data under:

```text
/Library/Application Support/Aurora
```

Depending on the features being used, Aurora may maintain directories such as:

```text
artwork/
backups/
config/
installer-state/
pki/
playlists/
postgres/
releases/
secrets/
stream-cache/
tabs/
tv-live-cache/
tv-logos/
tv-vod-cache/
updates/
video-cache/
```

These directories are managed automatically by Aurora and should normally not be modified manually.

---

## 🎵 Your Media Files

Your personal media does **not** need to be stored inside the Aurora application directory.

Aurora can scan supported media from locations accessible to the server, including:

- local folders
- external drives
- mounted volumes
- supported network storage

Removing Aurora does **not** automatically delete your original media files.

Your music, movies, series and other external media remain where you stored them.

---

# 🔄 Updating Aurora

To upgrade Aurora, download the newer macOS `.pkg` installer and install it normally.

From Terminal:

```bash
sudo installer -pkg "$HOME/Downloads/AuroraInstaller-<new-version>.pkg" -target /
```

Aurora detects the existing installation and performs an upgrade.

During an upgrade, Aurora preserves the persistent data required by your server.

Aurora uses versioned internal releases and switches the active runtime to the newly installed version after installation and validation.

Your media libraries and original media files are not removed during a normal upgrade.

---

# 🗑️ Uninstalling Aurora

Aurora includes an official macOS uninstall script.

There are currently two supported removal modes:

- **Standard Uninstall**
- **Purge**

These two options are intentionally different.

---

## Standard Uninstall

Use the standard uninstall when you want to remove Aurora but may reinstall it later.

Run:

```bash
sudo bash "/Library/Application Support/Aurora/installer-engine/"*/installer/uninstall.sh
```

The standard uninstall stops Aurora and removes the active runtime components while preserving persistent server data.

Data preserved by a normal uninstall can include:

- PostgreSQL database
- backups
- configuration
- installer state
- PKI data
- secrets
- update state
- logs
- the `_aurora` system account

This is the recommended removal method when you may want to reinstall Aurora later.

> [!TIP]
> Use **Standard Uninstall** when troubleshooting, reinstalling Aurora, or temporarily removing the application without intentionally destroying your server data.

---

# ⚠️ Purging Aurora

Aurora also provides a destructive purge mode.

> [!CAUTION]
> **Purge permanently deletes important Aurora server data.**
>
> This includes the Aurora PostgreSQL database and Aurora backups.
>
> Do not use this option unless you intentionally want to destroy that data.

Run:

```bash
sudo bash "/Library/Application Support/Aurora/installer-engine/"*/installer/uninstall.sh \
  --purge \
  --i-understand-this-deletes-the-aurora-database-and-backups-permanently
```

The explicit confirmation argument is required intentionally to help prevent accidental data loss.

A purge removes persistent Aurora data including:

- PostgreSQL database
- Aurora backups
- application configuration
- installer state
- Aurora secrets
- update data
- application logs
- installed Aurora releases
- runtime state

Your original external media files are **not** deleted.

---

## Uninstall vs Purge

| Component / Data | Standard Uninstall | Purge |
|---|:---:|:---:|
| Stop Aurora services | ✅ | ✅ |
| Remove Aurora runtime | ✅ | ✅ |
| Remove installed releases | ✅ | ✅ |
| Keep PostgreSQL database | ✅ | ❌ |
| Keep Aurora backups | ✅ | ❌ |
| Keep configuration | ✅ | ❌ |
| Keep secrets | ✅ | ❌ |
| Keep logs | ✅ | ❌ |
| Keep PKI | ✅ | ✅ |
| Keep `_aurora` system account | ✅ | ✅ |
| Delete external media files | ❌ | ❌ |

---

## ⚠️ Purge Is Not a Factory Reset

The current macOS purge does **not** represent a complete factory reset.

It intentionally preserves some machine-level Aurora state.

This includes:

```text
/Library/Application Support/Aurora/pki
```

and the macOS system account:

```text
_aurora
```

Because of this, `--purge` should not currently be considered equivalent to:

> Aurora has never been installed on this Mac.

A dedicated factory-reset option may be introduced separately in a future Aurora release.

---

# 📜 Logs

Aurora stores its main macOS logs under:

```text
/Library/Logs/Aurora
```

The main log files are:

```text
backend.log
frontend.log
supervisor.err.log
supervisor.out.log
postgres.log
```

---

## Backend Log

```bash
sudo tail -n 100 "/Library/Logs/Aurora/backend.log"
```

---

## Frontend Log

```bash
sudo tail -n 100 "/Library/Logs/Aurora/frontend.log"
```

---

## Aurora Supervisor

```bash
sudo tail -n 100 "/Library/Logs/Aurora/supervisor.err.log"
```

Supervisor output:

```bash
sudo tail -n 100 "/Library/Logs/Aurora/supervisor.out.log"
```

---

## PostgreSQL Log

```bash
sudo tail -n 100 "/Library/Logs/Aurora/postgres.log"
```

A healthy PostgreSQL startup normally includes:

```text
database system is ready to accept connections
```

---

# 🔎 Check Aurora Status

To verify that the Aurora web interface is running:

```bash
lsof -nP -iTCP:3302 -sTCP:LISTEN
```

To verify the Aurora backend:

```bash
lsof -nP -iTCP:3303 -sTCP:LISTEN
```

A healthy Aurora installation should show both services listening locally.

---

## Check the Active Aurora Release

Aurora uses versioned runtime releases.

The currently active release is referenced by:

```text
/Library/Application Support/Aurora/current
```

You can inspect it with:

```bash
ls -l "/Library/Application Support/Aurora/current"
```

The symbolic link should point to the currently active Aurora release.

---

# 🔐 Security

Aurora automatically provisions installation-specific credentials and encryption material required by its internal services.

Aurora secrets are stored under:

```text
/Library/Application Support/Aurora/secrets
```

Never publish or share:

- third-party API keys
- Aurora internal secrets
- administrator tokens
- TV credential encryption keys
- session cookies
- authentication tokens

Do not:

- commit Aurora secrets to Git
- include them in public GitHub issues
- publish screenshots containing credentials
- copy installation-specific secrets between Aurora servers unless specifically instructed by Aurora documentation

Aurora creates and manages its internal credentials automatically.

---

## API Keys

Some optional Aurora integrations use third-party API keys.

These can be configured through Aurora after installation.

API keys are personal credentials and should never be included in public logs, screenshots or GitHub issues.

---

# 🎬 Media Processing

Aurora for macOS includes the required media-processing binaries.

You do not need to install FFmpeg manually for the standard Aurora installation.

The macOS package includes native Apple Silicon / ARM64-compatible media components.

---

# 🛠️ Troubleshooting

If Aurora installs successfully but the web interface does not open, first verify that its services are running.

Check the web interface:

```bash
lsof -nP -iTCP:3302 -sTCP:LISTEN
```

Check the backend:

```bash
lsof -nP -iTCP:3303 -sTCP:LISTEN
```

Check the Aurora supervisor:

```bash
sudo tail -n 100 "/Library/Logs/Aurora/supervisor.err.log"
```

Check the backend:

```bash
sudo tail -n 100 "/Library/Logs/Aurora/backend.log"
```

For database-related startup problems:

```bash
sudo tail -n 100 "/Library/Logs/Aurora/postgres.log"
```

---

# 🐛 Reporting a Problem

When reporting a macOS installation problem, please include:

- Aurora version
- macOS version
- Mac model
- Apple Silicon processor generation if known
- whether the problem occurred during:
  - a new installation
  - an upgrade
  - an uninstall
  - a purge
- the relevant error message
- relevant Aurora log lines

Before posting logs publicly, verify that they do not contain private information.

Never include:

- API keys
- passwords
- session cookies
- authentication tokens
- Aurora internal secrets
- encryption keys

---

# ⚡ Quick Reference

## Install

```bash
sudo installer -pkg "$HOME/Downloads/AuroraInstaller-<version>.pkg" -target /
```

## Open Aurora

### http://127.0.0.1:3302

## Upgrade

```bash
sudo installer -pkg "$HOME/Downloads/AuroraInstaller-<new-version>.pkg" -target /
```

## Standard Uninstall

```bash
sudo bash "/Library/Application Support/Aurora/installer-engine/"*/installer/uninstall.sh
```

## Destructive Purge

```bash
sudo bash "/Library/Application Support/Aurora/installer-engine/"*/installer/uninstall.sh \
  --purge \
  --i-understand-this-deletes-the-aurora-database-and-backups-permanently
```

---

<div align="center">

<h2>🌌 Aurora</h2>

<p>
<strong>Your media. Your server. Your world.</strong>
</p>

<p>
Private. Local. Yours.
</p>

</div>
