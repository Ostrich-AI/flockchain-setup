\# Remote Node - Installation Guide



Complete installation and removal guide for the Remote Node Debian package.



\*\*Package:\*\* `remote-node\_1.0.0\_amd64.deb`  

\*\*Version:\*\* 1.0.0  

\*\*Architecture:\*\* amd64 (64-bit Intel/AMD)  

\*\*Author:\*\* Kishan Sakhiya <kishan.sakhiya@smartsensesolutions.com>



---



\## Table of Contents



\- \[System Requirements](#system-requirements)

\- \[Installation Methods](#installation-methods)

&nbsp; - \[Method 1: Using dpkg](#method-1-using-dpkg-recommended)

&nbsp; - \[Method 2: Using apt](#method-2-using-apt)

&nbsp; - \[Method 3: Using gdebi](#method-3-using-gdebi)

\- \[Post-Installation](#post-installation)

\- \[Verification](#verification)

\- \[Usage](#usage)

\- \[Uninstallation](#uninstallation)

\- \[Troubleshooting](#troubleshooting)

\- \[Advanced Topics](#advanced-topics)



---



\## System Requirements



\### Supported Operating Systems



\- \*\*Ubuntu:\*\* 20.04 LTS, 22.04 LTS, 24.04 LTS

\- \*\*Debian:\*\* 11 (Bullseye), 12 (Bookworm)

\- \*\*Linux Mint:\*\* 20.x, 21.x

\- \*\*Pop!\_OS:\*\* 20.04+

\- \*\*Other Debian-based distributions\*\* with compatible dependencies



\### Hardware Requirements



\- \*\*Architecture:\*\* 64-bit (amd64) Intel or AMD processor

\- \*\*RAM:\*\* Minimum 2 GB (4 GB recommended)

\- \*\*Disk Space:\*\* 150 MB for application + additional space for runtime data

\- \*\*Display:\*\* X11 or Wayland display server



\### Software Dependencies



The package automatically handles most dependencies. The following will be installed if not present:



\#### Required Dependencies

\- `libc6` (>= 2.31)

\- `libgtk-3-0` - GTK3 libraries

\- `libwebkit2gtk-4.1-0` or `libwebkit2gtk-4.0-37` - WebKit2 for UI rendering



\#### Recommended Dependencies

\- `ca-certificates` - SSL/TLS certificate validation

\- `docker.io` or `docker-ce` - For job execution and benchmarks

\- `python3` - For running benchmark scripts

\- `python3-pip` - Python package management



\#### Suggested Dependencies

\- `redis-tools` - Redis client tools for debugging



---



\## Installation Methods



\### Method 1: Using dpkg (Recommended)



This is the most common method for installing `.deb` packages.





\#### Step 1: Install the Package



```bash

sudo dpkg -i remote-node\_1.0.0\_amd64.deb

```



\#### Step 2: Fix Dependencies (if needed)



If you see dependency errors, run:



```bash

sudo apt-get install -f

```



This will automatically install any missing dependencies.



\#### Complete Installation Command



```bash

\# One-liner that handles everything

sudo dpkg -i remote-node\_1.0.0\_amd64.deb \&\& sudo apt-get install -f -y

```



---



\### Method 2: Using apt



The `apt` command can automatically resolve dependencies during installation.



```bash

\# Install the package with apt (Ubuntu 22.04+, Debian 12+)

sudo apt install ./remote-node\_1.0.0\_amd64.deb



\# For older systems, use apt-get

sudo apt-get install ./remote-node\_1.0.0\_amd64.deb

```



\*\*Note:\*\* The `./` prefix is required when installing a local file with `apt`.



---



\### Method 3: Using gdebi



`gdebi` is a graphical and command-line tool that automatically resolves dependencies.



\#### Install gdebi (if not installed)



```bash

sudo apt-get update

sudo apt-get install gdebi

```



\#### Install the Package



\*\*Command Line:\*\*

```bash

sudo gdebi remote-node\_1.0.0\_amd64.deb

```



\*\*Graphical Interface:\*\*

1\. Double-click the `.deb` file in your file manager

2\. It should open in Software Center or GDebi Package Installer

3\. Click "Install Package"



---



\## Post-Installation



\### User Data Directory



On first launch, the application creates user-specific directories:



```

~/.config/flockchain/                        # User configuration and data

&nbsp; ├── database/                               # SQLite database files

&nbsp; ├── logs/                                   # Application logs

&nbsp; └── cache/                                  # Temporary cache files

```



\### Desktop Integration



The application is automatically registered in your system menu:

\- \*\*Application Menu:\*\* Development → Remote Node

\- \*\*Desktop Entry:\*\* Searchable via system application launcher

\- \*\*Icon:\*\* Displayed in taskbar and window decorations



---



\## Verification



\### Verify Installation



Check if the package is installed:



```bash

dpkg -l | grep remote-node

```



Expected output:

```

ii  remote-node  1.0.0  amd64  A desktop app built with Wails, React, TailwindCSS, and Go

```



\### Check Installed Files



List all installed files:



```bash

dpkg -L remote-node

```



\### Verify Binary Location



```bash

which remote-node

```



Expected output: `/usr/bin/remote-node`



\### Check Version



```bash

remote-node --version

```



\### Test Application Launch



```bash

\# Launch from command line (should open GUI)

remote-node

```



---



\## Usage



\### Starting the Application



\#### Method 1: From Application Menu



1\. Open your system's application menu/launcher

2\. Search for "Remote Node"

3\. Click to launch



\#### Method 2: From Command Line



```bash

remote-node

```



---



\## Uninstallation



\### Method 1: Remove Package (Keep User Data)



This removes the application but preserves your configuration and data.



```bash

sudo apt-get remove remote-node

```



---



\### Method 2: Purge Package (Remove Everything)



This removes the application AND suggests cleaning user data.



```bash

sudo apt-get purge remote-node

```



After purge, you'll see a message about manually removing user data.



\*\*To completely remove all user data:\*\*



```bash

\# Remove user configuration and data

rm -rf ~/.config/flockchain/



\# If multiple users used the app, each user should run:

\# rm -rf ~/.config/flockchain/

```



---



\### Method 3: Complete Clean Removal



Remove everything in one go:



```bash

\# Remove package

sudo apt-get purge remote-node



\# Remove user data

rm -rf ~/.config/flockchain/



\# Remove any leftover dependencies

sudo apt-get autoremove



\# Clean package cache

sudo apt-get clean

```



---



\### Verify Removal



```bash

\# Check if package is removed

dpkg -l | grep remote-node



\# Should show no output or:

\# rc  remote-node  1.0.0  amd64  (removed, config files remain)



\# Check if binary is gone

which remote-node

\# Should show: (nothing found)



\# Check if user data is removed

ls ~/.config/flockchain/

\# Should show: No such file or directory

```



---



\*\*Last Updated:\*\* February 2026  

\*\*Package Version:\*\* 1.0.0  

\*\*Document Version:\*\* 1.0



---



\*\*Happy Installing! 🚀\*\*





