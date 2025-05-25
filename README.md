# Miui EU Localization Toolbox

This project contains the Android application and Xposed module that help localize MIUI based ROMs.

## Building

The project uses the Gradle wrapper. To compile the APK locally run:

```bash
./gradlew assembleDebug
```

Gradle will download the Android build tools on first use. Make sure a working Internet connection is available during the build step.

## Using the toolbox with Fuxi ROMs

To migrate Chinese ROM features from `fuxi-ota_full-OS2.0.104.0.VMCCNXM-user-15.0-0558a46bb0` to `xiaomi.eu_FUXI_OS2.0.108.0.VMCCNXM_15`:

1. Extract the target Xiaomi EU ROM (`xiaomi.eu_FUXI_OS2.0.108.0.VMCCNXM_15`).
2. Copy the required Chinese only APKs from the 104 package into the extracted EU ROM image.
   Typical locations include `system/app/` and `system/priv-app/`.
3. Repack the ROM and flash it as usual.
4. Install the toolbox APK (and accompanying Magisk module if necessary) to fix permissions and enable extra domestic features after boot.

The toolbox provides buttons to reset permissions, clean package cache, and apply other tweaks. Root access is required for most features.


