# Pixel 8

1. Go to the android images site: https://developers.google.com/android/ota
2. Download the file link (full OTA image) for the Pixel 8 with the correct major version.
3. extract boot.img with https://github.com/tobyxdd/android-ota-payload-extractor
    - Example: `./android-ota-payload-extractor ~/Downloads/shiba-ota-cp1a.260305.018-592992df/payload.bin init_boot`
5. Send boot.img to your phone, and patch with Magisk
6. Send patched image back to the PC, and patch the phone:
  - connect with USB debugging and confirm with `adb devices`
  - `adb reboot bootloader`
  - verify with `fastboot devices`
    - OPTIONAL STEPS:
    - `fastboot flashing unlock`
    - `fastboot getvar current-slot`
    - `fastboot getvar all`
  - `fastboot flash init_boot /PATH/TO/PATCH_FILE.img`
  - `fastboot reboot`

NOTE: if the version currently running and the version hosted by google are not IDENTICAL, sideload of the full OTA image will be required first.
