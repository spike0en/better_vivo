# Better Vivo

[![Hits](https://hitscounter.dev/api/hit?url=https%3A%2F%2Fgithub.com%2Fspike0en%2Fbetter-vivo&label=Hits&icon=github&color=%23b02a37&labelColor=2E2E3F)](https://github.com/spike0en/better-vivo)
[![Vivo X200 FE](https://img.shields.io/badge/Device-Vivo%20X200%20FE-blue.svg)](https://www.vivo.com.cn/)
[![OriginOS](https://img.shields.io/badge/OS-OriginOS%206-orange.svg)](https://www.vivo.com.cn/originos)

## Overview
- A curated collection of tweaks, tips, and system optimizations designed to enhance performance, usability, and the overall user experience on the Vivo X200 FE (V2503).  
- While this guide focuses on the X200 FE, most optimizations are compatible with other Vivo and iQOO devices running OriginOS 6.

---

## Disclaimer

- The author of this guide is NOT responsible for bricked devices, dead SD cards, or your phone going crazy. Please do your own research before applying these tweaks. Always maintain a backup of your important data.
- Prior knowledge and research of the tools, utilities, and methods listed in this guide is expected from the users.

---

## Pre-Requisites

To implement these tweaks, you will need the following tools:

### Desktop Tools
- **[ADB App Control](https://adbappcontrol.com/en/#download)** - A powerful desktop app for managing Android applications.
- **[UAD-NG](https://github.com/Universal-Debloater-Alliance/universal-android-debloater-next-generation)** - Universal Android Debloater Next Generation.
- **[Platform Tools](https://developer.android.com/tools/releases/platform-tools)** - Official Google ADB/Fastboot binaries.

### On-Device Tools
- **[Shizuku Fork](https://github.com/thedjchi/Shizuku)** - Provides elevated permissions to apps without root.
- **[Canta](https://github.com/samolego/Canta)** - A Shizuku-powered uninstaller to remove any app.
- **[AppControl-X](https://github.com/risunCode/AppControl-X)** - Advanced app management and background control.
- **[aShell](https://f-droid.org/en/packages/in.sunilpaulmathew.ashell/)** - A modern local ADB shell for Shizuku.
- **[Hail](https://github.com/aistra0524/Hail)** - Freeze or force-stop apps to save resources.

---

## ADB Environment Setup

Ensure you have the Android Debug Bridge (ADB) installed and configured on your system.

### Windows
Using [WinGet](https://github.com/microsoft/winget-cli):
```powershell
winget install --id Google.PlatformTools --source winget
```

### Linux
```bash
# Ubuntu/Debian
sudo apt install android-tools-adb
# Fedora
sudo dnf install android-tools
# Arch Linux
sudo pacman -S android-tools
```

### macOS
Using [Homebrew](https://brew.sh/):
```bash
brew install android-platform-tools
```

### Device Drivers
If your PC fails to recognize the device on Windows, install the official [Vivo MTP USB Driver](https://easyshare.vivo.com/drivers/driver_ex.exe).

---

## Debloating

Removing unnecessary system bloat helps to improve battery life and performance.

### Debloat List
- The recommended packages for removal are provided in form of a [debloat preset](assets/preset/V2503-debloat.txt).
- If you use the AI related features, remove them manually from list.

### Method A: Desktop Tools (PC Required)
1. **ADB App Control**: 
   - [Official Docs](https://adbappcontrol.com/en/docs/) | [Setup Guide](https://www.youtube.com/watch?v=yGhM3gI5p4k)
   - Import package names from [assets/preset/V2503-debloat.txt](assets/preset/V2503-debloat.txt).
   - Review the selection and click **Disable** or **Uninstall**.
2. **UAD-NG**:
   - [Usage Guide](https://github.com/Universal-Debloater-Alliance/universal-android-debloater-next-generation/wiki/Usage)
   - Connect device and apply the recommended presets.

### Method B: Canta (No PC Required)
1. Set up Shizuku and grant access to Canta.
2. Open [assets/preset/V2503-debloat.txt](assets/preset/V2503-debloat.txt) and copy the package names.
3. In Canta: **Settings > Import > Paste from clipboard**.
4. Review and execute removal.

---
