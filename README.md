# Instagram Piko ARMv7

Minimal Piko-patched Instagram build for older `armeabi-v7a` / Android 9 devices.

## Goals

- `armeabi-v7a` only
- low overhead / minimal patch surface
- Instagram ads blocked
- media download enabled
- clone package (`com.instagram.android.piko`)
- no theme / AMOLED / debug / telemetry extras
- no forced high media quality

## Why minimal?

Applying every Piko patch increases the amount of modified Instagram code and makes old ARMv7/Android 9 devices more likely to hit runtime incompatibilities. This repository intentionally starts with the smallest useful patch set.

## Build

Open **Actions → Build Piko ARMv7 → Run workflow** and provide a direct URL to the original Instagram `armeabi-v7a` APKM file.

The workflow downloads the original APKM, fetches the selected Piko release and Morphe Desktop, patches it, verifies that an APK was produced, uploads an Actions artifact, and commits the generated APK under `apk/`.

> Do not provide an already patched/modded APK as input. Piko/Morphe expects the original Instagram APKM.

## Current profile

- Disable ads
- Download media
- Clone

Additional UI/theme/quality patches are intentionally omitted for performance and stability.

## Device target

- Android 9+
- ARMv7 / `armeabi-v7a`

## Notes

Piko is developed by `crimera/piko` and Morphe Desktop by `MorpheApp/morphe-desktop`. This repository does not contain their source code.
