# emulatorhacks
Simple APK to disable all animations on your device. Useful for UI tests.

Download [emulatorhacks.apk](emulatorhacks.apk) and get going:

```bash
adb install -g -r emulatorhacks.apk
adb shell pm grant de.marcreichelt.emulatorhacks android.permission.SET_ANIMATION_SCALE
adb shell am broadcast --include-stopped-packages -n de.marcreichelt.emulatorhacks/.DisableAnimationsReceiver
```

Quick tip: Check in the APK in your SCM so it's there when you need it. Also, on Jenkins you might want to select the current jobs' AVD device (because multiple emulators might be running):

```bash
adb -s $ANDROID_AVD_DEVICE install -g -r emulatorhacks.apk
adb -s $ANDROID_AVD_DEVICE shell pm grant de.marcreichelt.emulatorhacks android.permission.SET_ANIMATION_SCALE
adb -s $ANDROID_AVD_DEVICE shell am broadcast --include-stopped-packages -n de.marcreichelt.emulatorhacks/.DisableAnimationsReceiver
```

Enjoy!
