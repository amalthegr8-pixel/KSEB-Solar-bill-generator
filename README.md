# KSEB Solar Net Meter & Bill Calculator (Android Project)

Complete Capacitor + Web Android project for tracking KSEB bi-directional net meter readings, solar generation, banked energy credits, and KSERC LT-1 Domestic bills.

## Folder Structure
- `www/index.html` — Complete mobile app source (UI, KSERC slab engine, local storage, CSV/JSON export).
- `package.json` — Capacitor dependencies (`@capacitor/core`, `@capacitor/cli`, `@capacitor/android`).
- `capacitor.config.json` — Android app ID (`in.kseb.solartracker`) and build config.
- `.github/workflows/build-apk.yml` — GitHub Actions workflow that automatically builds `app-debug.apk` in the cloud on push.

## Option A: Build APK Automatically on GitHub (No Local Android SDK Required)
1. Create a new GitHub repository and push all files from this folder to the `main` branch.
2. Open the **Actions** tab in your GitHub repository and wait for **Build Android APK** to finish (~2 minutes).
3. Download **`kseb-solar-tracker-debug-apk`** from the **Artifacts** section at the bottom of the workflow run and install `app-debug.apk` on your Android phone.

## Option B: Build APK Locally on Ubuntu / Windows
```bash
npm install
npx cap add android
npx cap sync android
cd android
./gradlew assembleDebug   # On Windows: .\gradlew.bat assembleDebug
```
Your installable APK will be generated at:
`android/app/build/outputs/apk/debug/app-debug.apk`
