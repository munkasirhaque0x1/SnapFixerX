# 🛠️ SnapFixerX

> **A lightweight Bash utility for Kali Linux that restores missing Snap application icons in the desktop menu.**

[![Platform](https://img.shields.io/badge/platform-Kali%20Linux-blue?style=flat-square&logo=linux)](https://www.kali.org/)
[![Shell](https://img.shields.io/badge/shell-Bash-green?style=flat-square&logo=gnu-bash)](https://www.gnu.org/software/bash/)
[![License](https://img.shields.io/badge/license-MIT-lightgrey?style=flat-square)](LICENSE)
[![Environment](https://img.shields.io/badge/environment-XFCE-orange?style=flat-square)](https://www.xfce.org/)

---

## 📌 Description

SnapFixerX is a minimal, no-dependency Bash utility designed for Kali Linux (XFCE) that resolves a common issue where applications installed via **Snap** fail to appear in the desktop application menu.

It works by detecting and copying missing `.desktop` entries from Snap's internal application directory (`/var/lib/snapd/desktop/applications/`) into the system-wide applications folder (`/usr/share/applications/`), effectively restoring GUI visibility for all affected Snap packages — no reboot required.

---

## ✨ Features

- **Automatic detection** — Scans for `.desktop` files registered by Snapd but absent from the system menu
- **Non-destructive operation** — Only copies missing entries; never overwrites existing files
- **Instant fix** — Restores Snap application icons without restarting the session or system
- **Lightweight** — Pure Bash, zero external dependencies
- **XFCE-optimized** — Designed and tested on Kali Linux with the XFCE desktop environment
- **Root-aware** — Validates sudo privileges before making any system-level changes
- **Verbose output** — Clearly reports which files were copied and confirms successful completion

---

## ⚙️ Requirements

- **Operating System:** Kali Linux (XFCE environment recommended)
- **Shell:** Bash 4.0 or higher
- **Snapd:** Must be installed and running (`sudo apt install snapd`)
- **Privileges:** `sudo` / root access required
- **Git:** Required only for installation via clone

---

## 📥 Installation

Follow these steps to install SnapFixerX on your system:

**1. Clone the repository**

```bash
git clone https://github.com/yourusername/SnapFixerX.git
```

**2. Navigate into the project directory**

```bash
cd SnapFixerX
```

**3. Make the script executable**

```bash
chmod +x mysnapfix
```

**4. Install it system-wide (optional but recommended)**

```bash
sudo cp mysnapfix /usr/bin/mysnapfix
```

Once installed, `mysnapfix` will be available as a global command from any terminal session.

---

## 🚀 Usage

Run the tool with superuser privileges:

```bash
sudo mysnapfix
```

That's it. SnapFixerX will handle the rest — scanning, comparing, and copying any missing `.desktop` files automatically.

---

## 📟 Example

```
$ sudo mysnapfix

[*] SnapFixerX — Snap Desktop Entry Fixer
[*] Scanning: /var/lib/snapd/desktop/applications/
[+] Copying: brave.desktop → /usr/share/applications/
[+] Copying: discord.desktop → /usr/share/applications/
[+] Copying: spotify.desktop → /usr/share/applications/
[✓] Fix complete. 3 desktop entries restored.
[*] Your Snap applications should now appear in the menu.
```

If all entries are already present, the tool will confirm no action was needed:

```
[✓] All Snap desktop entries are already in place. Nothing to do.
```

---

## ⚠️ Warning / Disclaimer

- **Snap-only:** SnapFixerX is designed exclusively to fix desktop integration issues caused by **Snap packages**. It will not resolve missing icons for applications installed via `apt`, `flatpak`, `dpkg`, `AppImage`, or any other package manager.
- **Flatpak / APT:** If your missing application was installed via Flatpak or APT, this tool will have no effect. Use the appropriate integration tool for those package managers.
- **System modification:** This tool writes files to `/usr/share/applications/`. Always review scripts before running them with `sudo`.
- **XFCE focus:** While the core logic may work on other desktop environments, it has only been tested under XFCE on Kali Linux. Behavior on GNOME, KDE, or other DEs is not guaranteed.

---

## 👤 Author

| Field    | Detail                                      |
|----------|---------------------------------------------|
| Author   | `Md. Munkasir Haque`                                 |
| Linkedin   | [@munkasirhaque0x1](https://www.linkedin.com/in/munkasirhaque0x1/) |
| Contact  | `munkasir210@gmail.com`                    |

---

## 📄 License

This project is licensed under the **MIT License**.
See the [LICENSE](LICENSE) file for full terms.

```
MIT License

Copyright (c) 2025 Your Name

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

<p align="center">
  Built for the terminal. Designed for Linux. ⚡
</p>