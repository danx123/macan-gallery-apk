# Macan Gallery

<p align="center">
  <img src="https://img.shields.io/badge/Release-v1.8.2-FF9E0B?style=for-the-badge" alt="Release Version" />
  <img src="https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" alt="Platform" />
  <img src="https://img.shields.io/badge/Architecture-Jetpack%20Compose-4285F4?style=for-the-badge" alt="Jetpack Compose" />
</p>

A fast, lightweight, and private gallery app for Android. Macan Gallery reads your photos and videos directly on demand, with **zero background services** and **zero RAM usage after you exit**. Optional **AI Gemini** tools (photo editing, visual search, image description) are available when you sign in with your personal Google account.

Built with Kotlin and Jetpack Compose by **Macan Angkasa**.

| | |
|---|---|
| **Package** | `com.macan.gallery` |
| **Version** | 1.7.0 (build 8) |
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
- **Instant startup:** albums appear on the first frame from a local snapshot while a silent background sync catches up, and the full scan is skipped entirely if nothing on the device changed
- **Search** albums and filenames
- **Flexible sorting:** date taken, date modified, name, size, and item count, with per-album overrides
- **Smart thumbnails:** persistent disk cache, GPU hardware bitmaps (API 26+), and video thumbnails taken from the 3-5 second mark to skip black intro frames
- **Predictive pre-fetching** while you scroll fast
- Scroll positions are preserved when you navigate back

### Full-screen viewer
- Pinch-to-zoom up to 8x, double-tap zoom steps, and pan
- Region-based tile decoding for ultra high-resolution photos (50 MP and above)
- Swipe down to dismiss
- Neighbor pre-loading for instant page swipes
- Optional **auto-maximize brightness** while viewing
- Quick actions: Share, Edit, AI Gemini, Wallpaper, Vault, and Delete
- Supports **JPEG, PNG, WebP, GIF, SVG, HEIC/HEIF, AVIF**, and RAW formats (DNG, CR2, NEF, ARW, ORF, RW2)
- Opens images and videos from other apps via "Open with"

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

### AI Gemini *(optional, requires Google sign-in)*
Powered by Gemini through Firebase AI Logic, with no developer API key shipped in the app. Each user signs in with their own Google account.

- **AI Edit:** describe an edit in plain language (or use a quick preset) and compare the result with the original using an interactive **Before / After** slider
- **Google Lens-style visual search:** identifies the main subject, category, and key objects, reads text (OCR), and suggests Google search queries, with one-tap web and image search
- **Image description:** streaming descriptions in three styles: detailed, social media captions, and accessibility alt-text
- Open the original photo directly in Google Lens when it is installed

### Wallpaper
- Interactive preview with a live selection frame, pan, and zoom
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
| Internet (`INTERNET`, `ACCESS_NETWORK_STATE`) | Used **only** for the optional AI Gemini features and Google sign-in |

Without All Files Access, the app still works using the Android media APIs. If you prefer not to grant broad access, you can also use the built-in **Photo Picker** to open individual items.

## Privacy

- Your library, vault, and recycle bin stay on your device.
- No analytics and no ads.
- No background services.
- **Network access is limited to the optional AI Gemini features.** Nothing is sent unless you sign in with Google and explicitly run an AI action. When you do, a downscaled copy of the selected photo is sent to Gemini through Firebase AI Logic to produce the result.
- You can sign out at any time from **Settings** or from the AI Gemini tab.

## Compatibility notes

- Android 11 and above: some deletions may show the system confirmation dialog unless All Files Access is enabled.
- Hardware-accelerated bitmaps are used on Android 8.0+, with a software fallback on Android 7.x.
- AI Gemini features need an internet connection and are subject to usage quotas.

## Tech stack

Kotlin, Jetpack Compose (Material 3), Room, DataStore, Coil 3 (GIF, SVG, and video frame decoders), Media3 ExoPlayer, AndroidX Biometric and ExifInterface, Firebase (AI Logic, Auth, App Check), and Jetpack Credential Manager for Google sign-in.

## Building from source

1. Open the project in Android Studio and let Gradle sync.
2. Add your own `google-services.json` and Firebase configuration if you want the AI Gemini features to work (Firebase AI Logic, Authentication with Google sign-in, and App Check must be enabled in your Firebase project). The gallery itself builds and runs without them.
3. Provide signing details through the `KEYSTORE_PATH`, `STORE_PASSWORD`, and `KEY_PASSWORD` environment variables to build a release APK.

---

## About

© Macan Angkasa. All rights reserved.
