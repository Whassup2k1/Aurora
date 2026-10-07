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
