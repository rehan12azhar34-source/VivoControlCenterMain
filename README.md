# Vivo Shortcut Center

An Android app project that builds a **debug APK** for a Vivo-inspired shortcut center. The app provides an overlay panel with quick-control styling, vertical brightness and volume sliders, and a flashlight control.

> This is an independent Android project inspired by a shortcut-center interface; it is not an official Vivo app.

## Build the APK with GitHub Actions

The included workflow builds the APK when code is pushed and can also be started manually:

1. Open the repository’s **Actions** tab.
2. Select **Build Vivo Shortcut Center APK**.
3. Choose **Run workflow** to start a manual build, or push a change to trigger one.
4. Open the completed workflow run and download the **Vivo-Shortcut-Center-EN** artifact.

The APK is built with `assembleDebug` and uploaded from `app/build/outputs/apk/debug/`.

## What the app includes

- A bottom-edge gesture trigger for opening the overlay panel.
- A custom shortcut-center panel layout.
- Vertical sliders for media volume and screen brightness.
- A flashlight toggle using the device camera flash, when available.
- A small setup screen for requesting overlay and system brightness access.

Some displayed quick-setting tiles are currently interface elements and may not perform their labeled system action.

## Install and use

1. Download the APK artifact from a successful GitHub Actions run.
2. Install the APK on an Android device. You may need to allow installation from your download source.
3. Open **Shortcut Center** and grant floating-window permission.
4. Grant brightness permission if you want to use the brightness slider.
5. Tap **Start Shortcut Center**, then swipe up from the bottom edge to open the panel.

Android may show additional security prompts. Only grant permissions you understand and want this app to use.

## Build details

The workflow sets up JDK 17 and the Android SDK, generates the Gradle project and app source files, then runs the debug build. The generated app uses Kotlin, Android Gradle Plugin 8.1.1, and compile/target SDK 33 (minimum SDK 26).

Because project files are generated during the workflow, review `.github/workflows/build-apk.yml` when changing the app or build configuration.

## Permissions

The app requests capabilities needed for the described features:

- **Display over other apps** — show the shortcut panel above other apps.
- **Modify system settings** — adjust screen brightness.
- **Camera/flash access** — operate the flashlight where available.

## Disclaimer

This project is provided as-is. Device behavior and permission availability can vary by Android version and manufacturer.
