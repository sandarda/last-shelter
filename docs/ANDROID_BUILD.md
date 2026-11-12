# Android build preparation — v0.23

## Included
- Android export preset: `export_presets.cfg` (package `com.lastshelter.game`, ARM64).
- Landscape layout with canvas stretch for varying Android screens.
- Original application icon.
- Automatic save every 60 seconds and on Android pause/close notifications.
- GitHub Actions workflow at `.github/workflows/android-build.yml`; it exports and uploads an APK artifact.

## Build locally
1. Install Godot 4.3.x and matching export templates.
2. Install Android SDK/JDK and configure them in Editor Settings → Export → Android.
3. Open `project.godot`, confirm the Android preset, then export `build/LastShelter.apk`.
4. Install on a device and test touch controls, screen safe areas, resume/pause, save/load, and performance.

## GitHub build
Push the complete project to a GitHub repository. The workflow runs on pushes to `main`/`master` or manually from Actions. Download the `LastShelter-Android` artifact from the workflow run.

## Signing
The included preset is for a development build. Before Play Store distribution, configure a private release keystore and signing credentials in GitHub Secrets; never commit keystore files or passwords.

## Important limitations
This environment does not contain Godot or Android export templates/SDK. The project has not yet been parsed or run by Godot, and no APK is claimed as built. The workflow is the reproducible next build path, but its first GitHub run is still required to validate the export preset and toolchain.
