# Better Vivo

[![Hits](https://hitscounter.dev/api/hit?url=https%3A%2F%2Fgithub.com%2Fspike0en%2Fbetter-vivo&label=Hits&icon=github&color=%23b02a37&labelColor=2E2E3F)](https://github.com/spike0en/better-vivo)
[![Stars](https://img.shields.io/github/stars/spike0en/better-vivo?logo=github&color=D4AF37)](https://github.com/spike0en/better-vivo/stargazzers)

[![Vivo X200 FE](https://img.shields.io/badge/Device-Vivo%20X200%20FE-blue.svg)](https://www.vivo.com/in/products/param/x200-fe)
[![OriginOS](https://img.shields.io/badge/OS-OriginOS%206-orange.svg)](https://www.vivo.com/en/originos)

---

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
   - Import package names from [the provided debloat list](assets/preset/V2503-debloat.txt).
   - Review the selection and click **Disable** or **Uninstall**.
2. **UAD-NG**:
   - [Usage Guide](https://github.com/Universal-Debloater-Alliance/universal-android-debloater-next-generation/wiki/Usage)
   - Connect device and apply the recommended presets.

### Method B: Canta (No PC Required)
1. Set up Shizuku and grant access to Canta.
2. Select the desired packages for removal carefully and proceed with uninstallation.
3. Users can refer to [this guide](https://www.youtube.com/watch?v=CFXRR-3pgBo) for more info.

---

## Photography

### Google Camera (GCAM) Ports

GCAM ports provide superior image processing, avoiding the aggressive sharpening and post-processing found in stock camera apps.  

> [!NOTE]
> - Try different configurations and variants to find what works for your style. There is no single "best" XML or camera version.
> - `Snapcam`, `awememe`, `scan3d`, `ruler`, `iris`, etc., are variants of the same GCAM with different package names. Use different variants to prevent installation conflicts (e.g., use `awememe` for one version and `ruler` for another).
> - You must restart the camera app after switching from the rear lens to the front lens for configurations to apply properly on LMC.
> - Configs often default to Google Photos. To use the stock album or other gallery apps, disable the option in settings: 
> **LMC**: Settings > LMC tweaks > Turn off "Use Google Photos" | 
> **AGC**: Settings > Advanced > Turn off "Use Google Photos"


#### Config Setup for AGC (BigKaka)
1. Download the XML file (.agc).
2. Move the file to: `Internal storage/download/AGC/AGC 8.4/configs/`
3. Open the AGC camera app.
4. Click on the **More settings** icon from the top or bottom bar and grant necessary permissions.
5. Click on the **Settings** icon from the top or bottom bar.
6. Click **Load config**.
7. Select the XML file you saved in the AGC configs folder and click **Save**.
8. Switch between profiles from the top bar for different shooting scenarios.
9. Import additional library (.so) files if available and required from the settings.

---

#### Config Setup for LMC (Hasli)
1. Install the camera app.
2. Place the XML (.xml) file in: `Internal Storage/LMC8.4/`
3. If the app crashes by default: 
   - Close the app.
   - Long-press the app icon in the app drawer and select the **Video** shortcut.
   - Navigate to **Settings > More Settings > Config Settings > Save settings**.
4. Return to the video section and tap the blank space on the left or right side of the shutter button to open the config selection menu.
5. Load the desired configuration.

---

#### Downloads

| GCAM Version | Configs / XML | Libraries | Credits |
| :--- | :--- | :--- | :--- |
| [LMC 8.4 vR18F1](https://www.celsoazevedo.com/files/android/google-camera/dev-hasli/f/dl14/) | [TALHA Classic V1](assets/xml/TALHA_X200FE_Classic_V1_LMC8.4_R18F1.xml) <br> [TALHA Bright V1](assets/xml/TALHA_X200FE_Bright_V1_LMC8.4_R18F1.xml) | N/A | Creator - [zZeRoZzAnDoNeZz](https://t.me/zZeRoZzAnDoNeZz) <br> Adapted by: [Talha](https://t.me/i_m_talhakhan) | 
| [AGC 8.4.300 v9.6](https://www.celsoazevedo.com/files/android/google-camera/dev-BigKaka/f/dl18/) | [TALHA x EGO V1](assets/xml/TALHA%20x%20EGO_V1_X200FE_AGC8.4.300_9.6.agc) | [shgv1.2k16 Lib](https://pixeldrain.com/u/yJ5NxJf4) | Creator - [EGO](https://t.me/EGOIST23) <br> Adapted by: [Talha](https://t.me/i_m_talhakhan) | 

---

## Performance Optimization Tweaks

### Dexopt
Force-compiles system packages to improve app launch speeds. Run these after system updates or on demand after extended periods of system operation.
```bash
# Step 1: Force compile all packages
adb shell cmd package compile -m speed -f -a

# Step 2: Run background optimization job
adb shell cmd package bg-dexopt-job
```

### Restricting OEM Apps
Use the [Digital Wellbeing trick](https://www.reddit.com/r/Vivo/comments/1m68zx8/finally_i_found_a_new_loophole_to_stop_bloatware/) to soft freeze OEM apps that OriginOS prevents from being disabled normally:
1. Open the **Digital Wellbeing** app.
2. Find the system apps you want to disable and set their **App Timer** to 0 minutes.
3. The app icons will turn grayscale, and the apps will be prevented from launching.
4. The app may still continue to run in background.
5. It is recommended to clear data and remove all permissions from those apps from App Info before performing the steps listed above.

### One-Tap Force Stop
- [Hail Visual Guide](https://www.youtube.com/watch?v=xmiUNFKbb58)
- Use **Hail** with Shizuku mode enabled to force-stop selected apps instantly via a Quick Tile or home screen shortcut.
- Note: Auto-freeze on device lock may not work reliably on all versions; manual intervention via the shortcut is recommended.

### Background Process Control
- Use **AppControl-X** (Shizuku mode) to restrict background activity for system and user apps.
- Combine this with the system's "Restrict battery usage" setting for non-essential apps.
- Note: Restricting background activity may prevent notifications; skip these settings for messaging or critical apps.

---

## Blocking Ads and Telemetry

### A. DNS Method (Recommended)
This method allows you to block ads and control telemetry sent to OEM servers.

- **[Adguard DNS](https://adguard-dns.io/en/public-dns.html)** - 300k free queries per month.
- **[NextDNS](https://nextdns.io/)** - 300k free queries per month.
- **[ControlD](https://controld.com/)** - Paid DNS with advanced filtering features.

### B. Local VPN / Firewall
- **[AdGuard](https://adguard.com/en/adguard-android/overview.html)**: Comprehensive local filtering and ad-blocking.
- **[RethinkDNS](https://rethinkdns.com/)**: Firewall + DNS to block individual apps from accessing the internet.

---

## Recommended System Settings

| System Setting | Value | Notes |
| :--- | :--- | :--- |
| **AI Acceleration Engine** | Off | Avoids AI-driven scheduling behavior. |
| **ART++ Turbo** | On / Off | Test both options to determine what works best for your device. |
| **Autostart** | Allow / Not Allowed | Allow for apps requiring persistent notifications; disable others to reduce background battery drain. |
| **Bypass Charging** | On | Use during gaming to reduce thermal throttling and help preserve battery health. |
| **Smart Services** | Off | Enable only when using Office Kit. |

---
