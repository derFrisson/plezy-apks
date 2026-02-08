# Plezy APK Releases

[![Extract Plezy APKs](https://github.com/derFrisson/plezy-apks/actions/workflows/extract-apk.yml/badge.svg)](https://github.com/derFrisson/plezy-apks/actions/workflows/extract-apk.yml)

Standalone `.apk` files automatically extracted from [edde746/plezy](https://github.com/edde746/plezy) releases — ready to install or use with [Obtainium](https://github.com/ImranR98/Obtainium).

## Install via Obtainium

1. Open Obtainium
2. Tap **Add App**
3. Paste this URL:
   ```
   https://github.com/derFrisson/plezy-apks
   ```
4. Set **APK filter regex** to match your device:
   - `arm64-v8a` — most modern phones *(recommended)*
   - `armeabi-v7a` — older 32-bit devices
   - `x86_64` — emulators / ChromeOS
5. Done — Obtainium will auto-update Plezy for you

## Direct Download

Head to the [Releases](https://github.com/derFrisson/plezy-apks/releases/latest) page and grab the APK for your architecture.

| File | Architecture | Devices |
|------|-------------|---------|
| `plezy-android-arm64-v8a.apk` | ARM 64-bit | Most modern phones & tablets |
| `plezy-android-armeabi-v7a.apk` | ARM 32-bit | Older Android devices |
| `plezy-android-x86_64.apk` | x86_64 | Emulators, ChromeOS |

> **Not sure which one?** Almost all modern Android phones use `arm64-v8a`.

## Why?

Since Plezy v1.13.0, Android builds are packaged as `.tar.gz` archives. This breaks Obtainium auto-updates and makes manual installation inconvenient. This repo automatically extracts the APKs daily and publishes them as proper GitHub releases.

## How it works

A GitHub Action runs daily and on-demand:
1. Checks the latest [Plezy release](https://github.com/edde746/plezy/releases)
2. Skips if the version is already published here
3. Downloads all Android `.tar.gz` archives
4. Extracts the `.apk` files
5. Creates a new release with standalone APKs + upstream changelog

---

### Self-hosting

Want to run this yourself? Fork this repo or copy `.github/workflows/extract-apk.yml` into a new repo. No configuration needed — it works out of the box with the default `GITHUB_TOKEN`.