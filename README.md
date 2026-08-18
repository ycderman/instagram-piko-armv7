# Instagram Piko ARMv7

Minimal Piko-patched Instagram build for older `armeabi-v7a` / Android 9 devices.

## Goals

- `armeabi-v7a` only
- low overhead / minimal patch surface
- Instagram ads blocked
- media download enabled
- clone package (`com.instagram.android.piko`)
- no theme / AMOLED / debug extras
- no forced high media quality

## Why minimal?

Applying every Piko patch increases the amount of modified Instagram code and increases the chance of runtime incompatibilities on old ARMv7/Android 9 devices. This repository intentionally uses the smallest useful patch set.

## Input

Place an original, unmodified Instagram `armeabi-v7a` APKM at:

`input/instagram-armv7.apkm`

Do not use an already-patched APK.

## Build

Open **Actions → Build Piko ARMv7 → Run workflow**.

The workflow:

1. verifies the original APKM,
2. fetches the latest stable Piko patch bundle,
3. fetches the latest stable Morphe Desktop,
4. applies only the minimal patch profile,
5. strips all native architectures except `armeabi-v7a`,
6. verifies the output,
7. uploads an Actions artifact,
8. commits the generated APK under `apk/`.

## Minimal patch profile

- Disable ads
- Download media
- Clone

Additional UI/theme/quality patches are intentionally omitted for performance and stability.

## Device target

- Android 9+
- ARMv7 / `armeabi-v7a`

## Output

`apk/instagram-piko-armv7-minimal.apk`

## Notes

Piko is developed by `crimera/piko` and Morphe Desktop by `MorpheApp/morphe-desktop`. Their upstream source code is not vendored here.
