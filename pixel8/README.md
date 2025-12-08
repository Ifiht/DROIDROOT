# Pixel 8

1. Go to the android images site: https://developers.google.com/android/ota
2. Download the file link (full OTA image) for the Pixel 8 with the correct major version.
3. extract boot.img with https://github.com/tobyxdd/android-ota-payload-extractor
4. Send boot.img to your phone, and patch with Magisk
5. Send patched image back to the PC, and patch the phone:
  - connect with USB debugging and confirm with `adb devices`
  - `adb reboot bootloader`
  - verify with `fastboot devices`
  - `fastboot flash init_boot`

NOTE: if the version currently running and the version hosted by google are not IDENTICAL, sideload of the full OTA image will be required first.
