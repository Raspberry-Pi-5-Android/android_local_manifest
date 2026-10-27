# android_local_manifest

Local manifest that adds the Raspberry Pi 5 repositories to an AOSP checkout.

## Build (Android 15)

```bash
repo init -u https://android.googlesource.com/platform/manifest -b android-15.0.0_r1
git clone -b android-15 https://github.com/Raspberry-Pi-5-Android/android_local_manifest .repo/local_manifests
repo sync -c -j8

source build/envsetup.sh
lunch rpi5-ap3a-userdebug
m
m rpibootimage
```

Images are written to `out/target/product/rpi5/`: `rpiboot.img` (boot), `system.img` and
`vendor.img`.

## License

Apache 2.0.
