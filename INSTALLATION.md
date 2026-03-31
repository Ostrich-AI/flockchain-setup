# Remote Node – Installation Guide

Installation and removal for **Desktop** (GUI) and **CLI** builds of Remote Node, including Linux `.deb` packages and Windows executables.

**Current bundled artifacts (example):** development **v1.1.0** under `binary/development/v1.1.0/`.  
**Author:** Kishan Sakhiya <kishan.sakhiya@smartsensesolutions.com>

---

## Table of Contents

- [Artifacts in this repository](#artifacts-in-this-repository)
- [System Requirements](#system-requirements)
- [Desktop – Ubuntu / Debian (.deb)](#desktop--ubuntu--debian-deb)
- [Desktop – Windows (.exe)](#desktop--windows-exe)
- [CLI – Ubuntu / Debian (.deb)](#cli--ubuntu--debian-deb)
- [CLI – Windows (.exe)](#cli--windows-exe)
- [Post-Installation](#post-installation)
- [Verification](#verification)
- [Usage](#usage)
- [Uninstallation](#uninstallation)
- [Troubleshooting](#troubleshooting)
- [Advanced Topics](#advanced-topics)

---

## Artifacts in this repository

Builds are organized by **channel**, **semantic version**, **variant** (desktop vs CLI), and **platform**:

```text
binary/
├── development/          # Development / nightly-style builds
├── qa/                   # QA builds (same layout when published)
└── production/           # Release builds (same layout when published)

    └── v1.1.0/
        ├── desktop/
        │   ├── ubuntu/
        │   │   ├── remote-node_1.1.0-dev_amd64_22.04.deb   # Ubuntu 22.04–aligned .deb
        │   │   └── remote-node_1.1.0-dev_amd64_24.04.deb   # Ubuntu 24.04–aligned .deb
        │   └── windows/
        │       └── remote-node-1.1.0-dev-windows-amd64.exe
        └── cli/
            ├── ubuntu/
            │   └── remote-node-cli_1.1.0-dev_amd64.deb
            └── windows/
                └── remote-node-cli.exe
```

**Choosing a desktop `.deb`:** Use the **22.04** package on Ubuntu 22.04 LTS (and similar era). Use the **24.04** package on Ubuntu 24.04 LTS. If unsure, prefer the package that matches your distribution’s base Ubuntu version.

**Version strings:** Filenames use `1.1.0-dev` for development channel builds. Production filenames will typically omit `-dev` (for example `1.1.0`).

---

## System Requirements

### Supported operating systems

**Desktop & CLI**

- **Ubuntu:** 20.04 LTS, 22.04 LTS, 24.04 LTS (use the matching desktop `.deb` for 22.04 vs 24.04 when both are provided)
- **Debian:** 11 (Bullseye), 12 (Bookworm)
- **Linux Mint:** 20.x, 21.x
- **Pop!\_OS:** 20.04+
- **Other Debian-based distributions** with compatible dependencies
- **Windows:** 64-bit (amd64), Windows 10 or later (for `.exe` builds)

### Hardware

- **Architecture:** 64-bit (amd64) Intel or AMD (Linux `.deb` and Windows `.exe` in this layout)
- **RAM:** Minimum 2 GB for desktop (4 GB recommended); CLI is lighter
- **Disk:** ~150 MB for the application plus space for runtime data
- **Desktop GUI only:** X11 or Wayland

### Software dependencies (Linux desktop `.deb`)

The package manager installs most dependencies. Typical pulls include:

**Required**

- `libc6` (>= 2.31)
- `libgtk-3-0`
- `libwebkit2gtk-4.1-0` or `libwebkit2gtk-4.0-37`

**Recommended**

- `ca-certificates`
- `docker.io` or `docker-ce` (job execution / benchmarks)
- `python3`, `python3-pip` (benchmark scripts)

**Suggested**

- `redis-tools` (debugging)

---

## Desktop – Ubuntu / Debian (.deb)

### Method 1: `dpkg` (recommended)

From the directory that contains the downloaded `.deb` (adjust the filename to your Ubuntu series):

```bash
sudo dpkg -i remote-node_1.1.0-dev_amd64_22.04.deb
# or
sudo dpkg -i remote-node_1.1.0-dev_amd64_24.04.deb
```

If dependency reports errors:

```bash
sudo apt-get install -f
```

**One-liner:**

```bash
sudo dpkg -i remote-node_1.1.0-dev_amd64_24.04.deb && sudo apt-get install -f -y
```

### Method 2: `apt`

```bash
sudo apt install ./remote-node_1.1.0-dev_amd64_24.04.deb
```

Use `./` for a local file. On older systems use `apt-get install ./file.deb`.

### Method 3: `gdebi`

```bash
sudo apt-get update && sudo apt-get install -y gdebi
sudo gdebi remote-node_1.1.0-dev_amd64_24.04.deb
```

---

## Desktop – Windows (.exe)

1. Copy `remote-node-1.1.0-dev-windows-amd64.exe` to a folder of your choice (for example `%USERPROFILE%\Apps\RemoteNode\`).
2. Double-click the executable to launch, or run it from PowerShell / Command Prompt:

```powershell
.\remote-node-1.1.0-dev-windows-amd64.exe
```

There is no separate installer in this layout; updates replace the `.exe` file.

**Optional:** Pin a shortcut to the Start menu or taskbar from the file’s context menu.

---

## CLI – Ubuntu / Debian (.deb)

Install the CLI package the same way as any `.deb`:

```bash
sudo dpkg -i remote-node-cli_1.1.0-dev_amd64.deb
sudo apt-get install -f -y
```

Or:

```bash
sudo apt install ./remote-node-cli_1.1.0-dev_amd64.deb
```

The installed command is expected to be available as `remote-node-cli` (verify with `which remote-node-cli` after install).

---

## CLI – Windows (.exe)

1. Place `remote-node-cli.exe` in a directory included in your `PATH`, **or** invoke it with a full path.
2. Run from PowerShell:

```powershell
.\remote-node-cli.exe --help
```

---

## Post-Installation

### User data directory (Linux desktop package)

On first launch:

```text
~/.config/flockchain/
├── database/
├── logs/
└── cache/
```

CLI or Windows may use the same or an equivalent path under the user profile; if documentation ships with the binary, prefer that for exact paths.

### Desktop integration (Linux `.deb`)

- **Menu:** Development → Remote Node (or search “Remote Node”)
- **Desktop entry** and icon are provided by the package

---

## Verification

### Linux – desktop package

```bash
dpkg -l | grep remote-node
dpkg -L remote-node
which remote-node
remote-node --version
remote-node
```

### Linux – CLI package

```bash
dpkg -l | grep remote-node-cli
which remote-node-cli
remote-node-cli --version
```

### Windows – desktop

- Run the `.exe` and confirm the UI opens.
- From the install folder:

```powershell
.\remote-node-1.1.0-dev-windows-amd64.exe --version
```

(if `--version` is supported; otherwise rely on the About dialog in the app)

### Windows – CLI

```powershell
.\remote-node-cli.exe --version
```

---

## Usage

### Desktop

**Application menu:** Search for “Remote Node” and launch.

**Terminal (Linux):**

```bash
remote-node
```

**Terminal (Windows):** run the `.exe` path as above.

### CLI

Use `remote-node-cli` on Linux and `remote-node-cli.exe` on Windows. See `--help` for subcommands and flags.

---

## Uninstallation

### Linux – remove desktop `.deb`

**Remove package (keep user data):**

```bash
sudo apt-get remove remote-node
```

**Purge package:**

```bash
sudo apt-get purge remote-node
```

**Remove user data:**

```bash
rm -rf ~/.config/flockchain/
```

### Linux – remove CLI `.deb`

```bash
sudo apt-get remove remote-node-cli
# or
sudo apt-get purge remote-node-cli
```

### Windows

- **Desktop:** Delete the `.exe` (and any shortcuts you created). Remove application data under your user profile if you want a full reset (exact folder may match `flockchain` under `%APPDATA%` or `%LOCALAPPDATA%` depending on the build).
- **CLI:** Delete `remote-node-cli.exe` and any config/cache folders the tool created.

### Cleanup (Linux)

```bash
sudo apt-get autoremove
sudo apt-get clean
```

---

## Troubleshooting

- **`dpkg` dependency errors:** Always run `sudo apt-get install -f` after a failed `dpkg -i`.
- **Wrong WebKit / GTK on Debian/Ubuntu:** Install the variant your distro expects (`libwebkit2gtk-4.1-0` vs `4.0-37`).
- **Desktop won’t start on Linux:** Check logs under `~/.config/flockchain/logs/` if present.
- **Windows SmartScreen:** Unsigned or new builds may trigger a warning; use “Run anyway” only for artifacts you trust.

---

## Advanced topics

- **Channels:** Prefer `binary/production/...` for stable releases when those artifacts exist; use `binary/development/...` for prerelease testing.
- **CI / headless:** The CLI build is better suited for servers and automation than the GUI desktop binary.

---

**Last updated:** March 2026  
**Documented layout version:** 1.1.x (development filenames shown as examples)  
**Document version:** 1.1
