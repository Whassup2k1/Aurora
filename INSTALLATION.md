# Aurora Installation

> Aurora is currently preparing for its first public beta.
> Installation packages are not yet publicly available.

Aurora is designed to provide a simple self-hosted installation experience
without requiring users to manually configure databases, containers or
individual backend services.

**Install Aurora. Add your media. Start streaming.**

---

## Supported Platforms

### Aurora Server

Aurora Server is currently being validated for:

- Ubuntu Linux

Additional server platforms are under evaluation and development.

### Aurora Clients

Aurora is designed to expand across:

- Linux
- Windows
- macOS
- Android
- iPhone & iPad
- Android TV / Google TV
- Apple TV

Platform availability will expand progressively during development.

---

## Before You Install

Aurora is currently Early Access software.

Before installing a beta build:

- Keep backups of important server data.
- Do not expose Aurora directly to the public Internet unless explicitly documented as safe.
- Expect installation and update procedures to evolve during Early Access.
- Report unexpected behavior so it can be investigated before stable release.

---

## Ubuntu / Linux

Aurora Server is being prepared as a native Linux package.

The installation is designed to configure the services required by Aurora
without requiring a normal user to manually install or configure its internal
database and application services.

Detailed installation commands will be published when the first beta package
is released.

### First Start

After installation, Aurora Server will guide the user through the initial
setup process.

The initial setup is designed to cover:

- Server configuration
- Administrator account
- Media libraries
- Storage locations
- Optional integrations
- Initial library scan

Once Aurora Server is running on the local network, supported devices can
connect to Aurora using:

`http://aurora.local`

Aurora will guide the device through any additional steps required to establish
a secure local connection.

---

## iPhone & iPad

Aurora can be installed on an iPhone or iPad as a Progressive Web App (PWA).

The following procedure has been validated on a physical iPhone during Aurora's
pre-beta testing.

The device must be connected to a network where the Aurora Server is reachable.

### 1. Open Aurora in Safari

On the iPhone or iPad, open Safari and visit:

`http://aurora.local`

Aurora will detect that the device does not yet trust the local secure
connection and display the secure connection setup.

### 2. Download the Aurora Profile

Select the option to download the Aurora profile.

If iOS asks where the profile should be downloaded, choose the iPhone or iPad
being configured.

iOS may confirm that the profile has been downloaded.

### 3. Install the Aurora Profile

Open:

**Settings → General → VPN & Device Management**

Select the downloaded Aurora profile and follow the iOS instructions to install
it.

The device passcode may be required by iOS.

### 4. Enable Full Trust

After installing the profile, open:

**Settings → General → About → Certificate Trust Settings**

Locate the Aurora Local Root CA and enable full trust.

Confirm the iOS warning when prompted.

This allows the device to establish a trusted HTTPS connection directly with
the local Aurora Server.

### 5. Return to Aurora

Return to Safari and Aurora.

Aurora should now report that the connection is secure.

You can also access Aurora securely at:

`https://aurora.local`

If the connection still appears untrusted, close and reopen the Aurora page
after confirming that full trust is enabled.

### 6. Install Aurora on the Home Screen

Open Aurora's installation page if it is not already displayed.

In Safari:

1. Tap the **Share** button.
2. Choose **Add to Home Screen**.
3. Tap **Add**.

Aurora will appear on the Home Screen like an installed application.

Launch Aurora using this new Home Screen icon to use it in standalone mode
without the normal Safari interface.

> On iPhone and iPad, adding a web application to the Home Screen is controlled
> by iOS and cannot be completed automatically by Aurora.

### After Installation

The Aurora profile normally only needs to be installed and trusted once on
that device.

Updating Aurora Server does not normally require reinstalling the Home Screen
application or repeating the certificate setup.

During pre-beta real-device testing, an installed Aurora PWA successfully
continued across multiple Aurora Server updates without being reinstalled.

---

## macOS

Native macOS support is currently under development and validation.

Installation instructions will be published when a supported macOS build
becomes available.

---

## Windows

Windows support is planned.

Installation instructions will be published when a supported Windows build
becomes available.

---

## Adding Your Media

Aurora is designed around media that you control.

After installation, media libraries can be added through Aurora's
administration interface.

Aurora does not provide commercial media catalogs.

Users are responsible for the media and sources they choose to configure.

---

## Updates

Aurora's update system is being designed around safe, versioned releases.

The update architecture includes or is being developed for:

- Pre-update backups
- Database migrations
- Health validation
- Persistent configuration
- Previous-release tracking
- Rollback and recovery

Detailed update procedures will be documented before public release.

---

## Backup & Recovery

Aurora is designed to keep server configuration and application data
separate from the user's media libraries.

During Early Access, users should maintain their own backup of important
Aurora configuration and data in addition to Aurora's built-in recovery
mechanisms.

Detailed backup and restore documentation will be published as the beta
program progresses.

---

## Uninstallation

Platform-specific uninstall instructions will be provided with each
supported Aurora package.

Aurora will not intentionally delete the user's original media libraries
during uninstallation.

---

## Troubleshooting

If Aurora does not install or start correctly, please include the following
when reporting the problem:

- Aurora version
- Operating system and version
- Hardware architecture
- Installation method
- Relevant Aurora logs
- Exact error message
- Steps that led to the problem

Never include passwords, API keys, private tokens or other credentials in
a public GitHub Issue or Discussion.

---

## Early Access

Aurora is approaching its first public beta.

If you would like to help test Aurora on real hardware and real media
libraries, join the Aurora Beta Testing Program through the project's
GitHub Discussions.

Early Access builds may change frequently and should not yet be considered
production-ready.

---

**Your media. Your server. Your world.**

**Private. Local. Yours.**
