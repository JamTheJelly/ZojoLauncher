# ZOJO LAUNCHER

An Android home screen in the ZOJO RIG design language: paper-black background with a dot grid, module cards,
dot-ring knobs, dot-matrix display type, Space Mono / Space Grotesk, and the same colour-coded accents.

| ZOJO RIG                   | ZOJO LAUNCHER                                                |
|----------------------------|--------------------------------------------------------------|
| Amp-model display + chips  | **01 NOW**: dot-matrix clock, weekday chips, next alarm      |
| I/O meters + volume knob   | **02 I/O**: battery & storage dot meters, live media-volume knob |
| Stompbox pedals            | **03 RIG**: up to 8 favourite apps as pedals with accent LEDs |
| Preset browser             | **ALL APPS** drawer with search, A–Z sections                |
| Tuner overlay              | Hold-an-app sheet: add to rig, reorder, app info, uninstall   |

## Getting the app (no coding tools needed)
Every push builds an APK on GitHub:
1. Open the **Actions** tab and click the latest **Build ZOJO LAUNCHER** run.
2. When it shows a green check (about 5 minutes), download **ZOJO-LAUNCHER-Android** under **Artifacts**.
3. Unzip it and read `GETTING-STARTED.txt`.

## Building locally (optional)
Open the folder in Android Studio (Ladybug or newer) and press Run, or with the Android SDK and Gradle 8.10+:
```
gradle assembleRelease
```
Output: `app/build/outputs/apk/release/app-release.apk`

## Project layout
- `app/src/main/java/com/zojo/launcher/ui/Theme.kt` – the ZOJO palette and fonts (same values as `ZojoLookAndFeel.h`)
- `ui/Primitives.kt` – module card, knob, dot-matrix text, dot meter, keys/chips, LEDs, section labels
- `ui/Launcher.kt` – home screen, app drawer, app sheet
- `ui/DeviceState.kt` – clock, battery, storage, alarm, media volume
- `data/Apps.kt` – installed-app list, rig storage, launching
- `MainActivity.kt` – the HOME activity

Requires Android 8.0+. Release builds are signed with the debug key so they install directly; use your own
keystore before distributing.

Fonts: Space Mono and Space Grotesk (SIL Open Font License, see `docs/fonts`).
