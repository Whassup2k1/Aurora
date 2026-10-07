# Install Aurora on macOS — Apple Silicon

Aurora provides a native macOS installer for Apple Silicon Macs.

The macOS package includes everything required to run Aurora locally, including the Aurora frontend, backend, PostgreSQL runtime, media processing tools, service supervisor, and required runtime components.

> [!NOTE]
> The current macOS package is built for **Apple Silicon / ARM64**.
>
> Intel-based Macs are not supported by this package.

---

## Requirements

Before installing Aurora, make sure you have:

- A Mac with Apple Silicon
- macOS with administrator access
- Enough free disk space for Aurora and your media-related cache/data
- A modern web browser such as Safari, Chrome, Firefox, or Edge

Aurora does not require you to install PostgreSQL, Node.js, FFmpeg, or other server dependencies manually.

The required runtime components are included with the Aurora macOS package.

---

# Download Aurora

Download the latest macOS ARM64 package from the Aurora GitHub Releases page.

The installer file will have a name similar to:

```text
AuroraInstaller-<version>.pkg

For example:
AuroraInstaller-27.01.999.pkg

The exact version number will depend on the release you downloaded.
Install Aurora
Aurora can be installed using the standard macOS installer or directly from Terminal.
Option 1 — macOS Installer
Locate the downloaded .pkg file in Finder and open it.
Follow the macOS installation steps and enter your administrator password when requested.
Aurora will install its runtime and automatically configure the services required to run the server.
When the installation is complete, Aurora starts automatically.
Option 2 — Terminal
Aurora can also be installed using the macOS installer command.
For example, if the package is in your Downloads folder:
sudo installer -pkg "$HOME/Downloads/AuroraInstaller-<version>.pkg" -target /

Replace <version> with the version you downloaded.
For example:
sudo installer -pkg "$HOME/Downloads/AuroraInstaller-27.01.999.pkg" -target /

A successful installation should end with:
installer: The install was successful.

Open Aurora
Once the installation is complete, open Aurora in your browser:
http://127.0.0.1:3302

On the first launch, Aurora will guide you through the initial setup.
You can then configure your administrator account, integrations, media libraries, and other Aurora features.
What the Installer Creates
Aurora installs its persistent application data under:
/Library/Application Support/Aurora

Application logs are stored under:
/Library/Logs/Aurora

Aurora also creates a dedicated macOS system account:
_aurora

This account is used to run Aurora services with their own permissions instead of running the application permanently as your personal macOS account.
Aurora Services
Aurora uses macOS launchd to manage its server processes.
The main local services are:
Service	Port
Aurora Web Interface	3302
Aurora Backend API	3303


Aurora should normally be accessed using:
http://127.0.0.1:3302

The backend port is used internally by Aurora and normally does not need to be accessed directly.
PostgreSQL
Aurora includes and manages its own PostgreSQL runtime.
You do not need to install PostgreSQL separately.
Aurora initializes its database automatically during the first installation.
PostgreSQL communicates locally using a Unix socket located under:
/var/run/aurora/postgres

Aurora does not require PostgreSQL to be exposed publicly through a TCP port.
Aurora Data Directories
The main Aurora directory is:
/Library/Application Support/Aurora

Depending on the features being used, Aurora may maintain directories such as:
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

These directories are managed automatically by Aurora and should normally not be edited manually.
Media Libraries
Your personal media does not need to be stored inside the Aurora application directory.
Aurora can scan media from locations accessible to the server, including local storage and mounted volumes.
Removing Aurora does not automatically delete your original music, movies, television files, or other external media libraries.
Updating Aurora
Aurora can be upgraded by installing a newer macOS .pkg.
Download the newer version and run the installer normally.
From Terminal:
sudo installer -pkg "$HOME/Downloads/AuroraInstaller-<new-version>.pkg" -target /

The installer detects the existing Aurora installation and performs an upgrade.
During an upgrade, Aurora preserves the persistent application data required by the server.
Aurora uses versioned internal releases and activates the new runtime only after the package has been installed and validated.
Uninstall Aurora
Aurora includes an official macOS uninstall script.
There are two supported removal modes:
1. Standard uninstall
2. Purge
These modes are intentionally different.
Standard Uninstall
Use the standard uninstall when you want to remove Aurora but may reinstall it later.
Run:
sudo bash "/Library/Application Support/Aurora/installer-engine/"*/installer/uninstall.sh

The uninstaller stops Aurora services and removes the active application/runtime components.
Persistent server data is intentionally preserved.
This includes data such as:
- PostgreSQL data
- backups
- configuration
- installer state
- PKI data
- secrets
- update data
- logs
- the _aurora system account
This makes a later Aurora reinstall or recovery possible without intentionally destroying the existing server state.
[!TIP]
Use the standard uninstall if you are troubleshooting Aurora, replacing the application, or think you may reinstall it later.

Purge Aurora
Aurora also provides a destructive purge mode.
[!CAUTION]
Purge permanently deletes important Aurora data.
This includes the Aurora PostgreSQL database and Aurora backups.
Do not use this option unless you intentionally want to destroy the Aurora server data.

Run:
sudo bash "/Library/Application Support/Aurora/installer-engine/"*/installer/uninstall.sh \
  --purge \
  --i-understand-this-deletes-the-aurora-database-and-backups-permanently

The long confirmation argument is required intentionally to help prevent accidental data loss.
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
Your original external media files are not deleted by the Aurora purge process.
Purge Is Not Currently a Factory Reset
The current macOS purge intentionally preserves some machine-level Aurora state.
In particular, it preserves:
/Library/Application Support/Aurora/pki

and the macOS system account:
_aurora

Because of this, --purge should not currently be considered equivalent to:
"Aurora has never been installed on this Mac."

This behavior is intentional and allows Aurora to preserve certain machine identity and security-related information.
A dedicated factory-reset mechanism may be provided separately in a future version.
Uninstall vs Purge
Action	Standard Uninstall	Purge
Stop Aurora services	✅	✅
Remove active Aurora runtime	✅	✅
Remove installed releases	✅	✅
Keep PostgreSQL database	✅	❌
Keep backups	✅	❌
Keep configuration	✅	❌
Keep secrets	✅	❌
Keep logs	✅	❌
Keep PKI	✅	✅
Keep _aurora account	✅	✅
Delete your external media	❌	❌


Logs
Aurora stores its main macOS logs under:
/Library/Logs/Aurora

Important log files include:
/Library/Logs/Aurora/backend.log
/Library/Logs/Aurora/frontend.log
/Library/Logs/Aurora/supervisor.err.log
/Library/Logs/Aurora/supervisor.out.log
/Library/Logs/Aurora/postgres.log

Check the Backend Log
sudo tail -n 100 "/Library/Logs/Aurora/backend.log"

Check the Frontend Log
sudo tail -n 100 "/Library/Logs/Aurora/frontend.log"

Check the Aurora Supervisor
sudo tail -n 100 "/Library/Logs/Aurora/supervisor.err.log"

You can also inspect the supervisor output:
sudo tail -n 100 "/Library/Logs/Aurora/supervisor.out.log"

Check PostgreSQL
sudo tail -n 100 "/Library/Logs/Aurora/postgres.log"

A healthy PostgreSQL startup normally contains a message similar to:
database system is ready to accept connections

Check Whether Aurora Is Running
To verify that the web interface is listening:
lsof -nP -iTCP:3302 -sTCP:LISTEN

To verify the Aurora backend:
lsof -nP -iTCP:3303 -sTCP:LISTEN

If Aurora is running correctly, both services should appear as listening locally.
Check the Active Aurora Release
Aurora uses a versioned release directory.
The currently active runtime is referenced by:
/Library/Application Support/Aurora/current

You can inspect it with:
ls -l "/Library/Application Support/Aurora/current"

The link should point to the currently installed Aurora release.
Security
Aurora automatically creates installation-specific secrets required by its internal services.
These secrets are stored under:
/Library/Application Support/Aurora/secrets

They can include internal authentication and encryption material used by Aurora.
Do not:
- publish these files
- copy them into GitHub issues
- commit them to Git
- share them in screenshots
- copy them between Aurora servers unless specifically instructed by Aurora documentation
Aurora creates and manages these values automatically.
API Keys
Some optional Aurora integrations may require third-party API keys.
These keys can be configured through Aurora after installation.
API keys are personal credentials and should never be posted publicly.
When reporting a problem, never include:
- API keys
- Aurora internal secrets
- administrator tokens
- TV credential encryption keys
- session cookies
- authentication tokens
FFmpeg
The macOS Aurora package includes the media-processing binaries required by Aurora.
You do not need to install FFmpeg manually for the standard Aurora installation.
The Apple Silicon package uses native ARM64-compatible media components.
Apple Silicon Support
The current Aurora macOS package targets:
Apple Silicon / ARM64

This includes Apple Silicon Mac models using Apple-designed processors.
The ARM64 package is not intended for Intel/x86_64 Macs.
Troubleshooting Installation
If installation fails, first review the macOS installer output and Aurora logs.
If Aurora was installed but the web interface does not open, check:
lsof -nP -iTCP:3302 -sTCP:LISTEN

and:
lsof -nP -iTCP:3303 -sTCP:LISTEN

Then inspect:
sudo tail -n 100 "/Library/Logs/Aurora/supervisor.err.log"

and:
sudo tail -n 100 "/Library/Logs/Aurora/backend.log"

For database-related startup problems:
sudo tail -n 100 "/Library/Logs/Aurora/postgres.log"

Reporting a Problem
When opening an Aurora GitHub issue for a macOS installation problem, please include:
- Aurora version
- macOS version
- Mac model
- Apple Silicon processor generation if known
- whether this was:
  - a new installation
  - an upgrade
  - an uninstall
  - a purge
- the relevant error message
- relevant Aurora log lines
Do not upload an entire secrets directory or configuration containing credentials.
Before posting logs publicly, verify that they do not contain personal paths, media names, API keys, authentication data, or other information you do not want to share.
Quick Reference
Install
sudo installer -pkg "$HOME/Downloads/AuroraInstaller-<version>.pkg" -target /

Open Aurora:
http://127.0.0.1:3302

Upgrade
sudo installer -pkg "$HOME/Downloads/AuroraInstaller-<new-version>.pkg" -target /

Standard Uninstall
sudo bash "/Library/Application Support/Aurora/installer-engine/"*/installer/uninstall.sh

Destructive Purge
sudo bash "/Library/Application Support/Aurora/installer-engine/"*/installer/uninstall.sh \
  --purge \
  --i-understand-this-deletes-the-aurora-database-and-backups-permanently

Aurora
Your media. Your server. Your world.
```
