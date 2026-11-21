# Macan Gallery

<p align="center">
  <img src="https://img.shields.io/badge/Release-v1.5.0-FF9E0B?style=for-the-badge" alt="Release Version" />
  <img src="https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" alt="Platform" />
  <img src="https://img.shields.io/badge/Architecture-Jetpack%20Compose-4285F4?style=for-the-badge" alt="Jetpack Compose" />  
</p>

A fast, lightweight, and private gallery app for Android. Macan Gallery reads your photos and videos directly on demand, with **zero background services** and **zero RAM usage after you exit**.

Built with Kotlin and Jetpack Compose by **Macan Angkasa**.

| | |
|---|---|
| **Package** | `com.macan.gallery` |
| **Min. Android** | 7.0 (API 24) |
| **Target Android** | 16 (API 36) |

---

## Screenshot

<img width="2186" height="1600" alt="macan-gallery-android" src="https://github.com/user-attachments/assets/2c0f41f5-dd35-4f45-92f6-2e93469c57f7" />

---

## Features

### Browse your library
- **Four view modes:** Grid, List, Moments (timeline grouped by date), and Explorer (full storage browser)
- **Pinch to resize** thumbnail grids with haptic feedback
- **Instant startup:** albums appear on the first frame from a local snapshot while a silent background sync catches up
- **Search** albums and filenames
- **Flexible sorting:** date taken, date modified, name, size, and item count, with per-album overrides
- **Smart thumbnails:** persistent disk cache, GPU hardware bitmaps (API 26+), and video thumbnails taken from the 3-5 second mark to skip black intro frames
- **Predictive pre-fetching** while you scroll fast

### Full-screen viewer
- Pinch-to-zoom up to 8x, double-tap zoom steps, and pan
- Region-based tile decoding for ultra high-resolution photos (50 MP and above)
- Swipe down to dismiss
- Neighbor pre-loading for instant page swipes
- Optional **auto-maximize brightness** while viewing
- Supports **JPEG, PNG, WebP, GIF, SVG, HEIC/HEIF, AVIF**, and RAW formats (DNG, CR2, NEF, ARW, ORF, RW2)

### Video player
- Built on Media3 ExoPlayer
- **Gesture controls:** swipe the left side for brightness, the right side for volume, and horizontally to seek
- Double-tap to play or pause, with a mute toggle and seek bar

### Slideshow
- Adjustable interval (2-15 seconds)
- Four transitions: **Crossfade, Push In, Fade In/Out, Checkerboard**

### File management
- Copy, move, rename, and **batch rename** (e.g. `Vacation_001.jpg`)
- **Local Recycle Bin** with restore and empty-all
- Toggle **`.nomedia`** on any folder
- **Exclude folders** from the gallery without touching the files
- Show or hide hidden and `.nomedia` content on demand
- Share multiple items at once

### Private Vault
- Move photos and videos into a hidden internal vault
- Protected by a **4-digit PIN** with optional **fingerprint / face unlock**
- Restore items to their original folder at any time

### Photo editor
- Crop with aspect presets (Free, 1:1, 4:3, 3:2, 16:9, 9:16)
- Rotate in 90-degree steps, flip horizontally or vertically, and straighten (-45 to +45 degrees)
- Resize and adjust JPEG quality
- Save as a new copy or overwrite the original

### Wallpaper
- Interactive preview with a live selection frame
- Apply to **Home Screen, Lock Screen, or both**
- **Static** mode (fixed single-screen crop) or **Scrolling** mode (wide parallax across home pages)
- Compatibility handling for OEM Android ROMs

### EXIF inspector
- Camera, aperture, shutter speed, ISO, focal length, flash, resolution, and megapixels
- GPS coordinates with an **Open in Maps** shortcut

### Appearance
- Light, Dark, or System theme
- **Material You dynamic color** on Android 12+
- **AMOLED pure black** option
- Warm amber and obsidian fallback palette on Android 7-11

---

## Installation

Macan Gallery is distributed as an APK.

1. Download the latest `.apk` file from the release page.
2. On your device, open the downloaded file.
3. If prompted, allow installation from your browser or file manager (**Settings > Install unknown apps**).
4. Tap **Install**, then open **Macan Gallery**.

To update, install the newer APK over the existing one. Your settings, vault, and recycle bin are kept.

## First launch and permissions

| Permission | Why it is needed |
|---|---|
| Photos and videos (`READ_MEDIA_*` / `READ_EXTERNAL_STORAGE`) | Browse your media |
| Media location (`ACCESS_MEDIA_LOCATION`) | Read GPS data in EXIF |
| All Files Access (`MANAGE_EXTERNAL_STORAGE`) | **Optional.** Enables instant move, rename, `.nomedia`, and full Explorer browsing |
| Set wallpaper (`SET_WALLPAPER`) | Apply wallpapers |
| Biometric (`USE_BIOMETRIC`) | Unlock the Private Vault |

Without All Files Access, the app still works using the Android media APIs. If you prefer not to grant broad access, you can also use the built-in **Photo Picker** to open individual items.

## Privacy

- Everything stays on your device.
- No network permissions, no accounts, no analytics, no ads.
- No background services.

## Compatibility notes

- Android 11 and above: some deletions may show the system confirmation dialog unless All Files Access is enabled.
- Hardware-accelerated bitmaps are used on Android 8.0+, with a software fallback on Android 7.x.

---

## About

© Macan Angkasa. All rights reserved.
