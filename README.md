# ADB (Android Debug Bridge) Commands Cheat Sheet

ADB (Android Debug Bridge) is a powerful tool that allows developers, testers, and even normal users to interact with Android devices via a command-line interface.

## 🔍 Search for a Command
To quickly find a command, use `Ctrl + F` (Windows/Linux) or `Cmd + F` (Mac) and type the keyword.

## 📌 Basic ADB Commands

### 1. Check Device Connection
```sh
adb devices
```
*Lists all connected devices.*

### 2. Restart ADB Server
```sh
adb kill-server
adb start-server
```
*Kills and restarts the ADB server.*

### 3. Connect to a Device Over Wi-Fi
```sh
adb tcpip 5555
adb connect <device-ip>:5555
```
*Connects to a device wirelessly.*

### 4. Install/Uninstall an App
```sh
adb install <apk-file-path>
adb uninstall <package-name>
```
*Installs or uninstalls an APK.*

## 📸 Screenshots & Screen Recording

### 5. Take a Screenshot
```sh
adb shell screencap -p /sdcard/screenshot.png
adb pull /sdcard/screenshot.png
```
*Takes a screenshot and transfers it to the PC.*

### 6. Record Screen
```sh
adb shell screenrecord /sdcard/screen.mp4
adb pull /sdcard/screen.mp4
```
*Records the screen and saves it to the device.*

## 📂 File Management

### 7. Push/Pull Files
```sh
adb push <local-file> <device-path>
adb pull <device-file> <local-path>
```
*Transfers files between the PC and the device.*

## 🛠 Debugging & System Commands

### 8. View Logcat (Real-time Logs)
```sh
adb logcat
adb logcat -s "TAG"
```
*Shows system logs for debugging.*

### 9. Dump Device Info
```sh
adb shell dumpsys
```
*Retrieves detailed system information.*

### 10. Get Specific Device Data (Useful for Testing)
```sh
adb shell dumpsys activity
adb shell dumpsys battery
adb shell dumpsys window
adb shell dumpsys wifi
adb shell dumpsys package <package-name>
```
*Dumps specific data like battery status, running activities, Wi-Fi state, and more.*

### 11. Get Call Logs (For Testing)
```sh
adb shell content query --uri content://call_log/calls
```
*Retrieves recent call logs from the device.*

## 📲 App & UI Navigation

### 12. Launch an App Directly
```sh
adb shell monkey -p <package-name> -c android.intent.category.LAUNCHER 1
```
*Opens a specific app.*

### 13. Open a Specific Screen of an App
```sh
adb shell am start -n <package-name>/<activity-name>
```
*Directly navigates to a particular activity in an app.*

### 14. Force Stop an App
```sh
adb shell am force-stop <package-name>
```
*Forces an app to stop running.*

### 15. Clear App Data and Cache
```sh
adb shell pm clear <package-name>
```
*Resets an app like a fresh install.*

## 🔋 Battery & Performance Testing

### 16. Simulate Low Battery
```sh
adb shell dumpsys battery set level 10
```
*Simulates a low battery scenario for testing.*

### 17. Simulate Different Network Conditions
```sh
adb shell svc wifi disable
adb shell svc wifi enable
adb shell svc data disable
adb shell svc data enable
```
*Disables/enables Wi-Fi and mobile data for testing.*

### 18. Monitor CPU & RAM Usage
```sh
adb shell top -n 1
```
*Displays real-time CPU and memory usage.*

## 🔑 Developer Mode & Permissions

### 19. Grant/Remove App Permissions
```sh
adb shell pm grant <package-name> <permission>
adb shell pm revoke <package-name> <permission>
```
*Manages app permissions programmatically.*

### 20. Enable/Disable Developer Options
```sh
adb shell settings put global development_settings_enabled 1
adb shell settings put global development_settings_enabled 0
```
*Turns developer options on/off.*

## 🚀 Extra Useful Commands

### 21. Simulate a Key Press (Back, Home, Recent Apps)
```sh
adb shell input keyevent KEYCODE_BACK
adb shell input keyevent KEYCODE_HOME
adb shell input keyevent KEYCODE_APP_SWITCH
```
*Simulates hardware button presses.*

### 22. Send a Text Input
```sh
adb shell input text "HelloWorld"
```
*Sends text input to a field.*

### 23. Simulate a Tap at (x,y) Coordinate
```sh
adb shell input tap 500 1000
```
*Mimics a screen touch at a specific location.*

### 24. Reboot Device into Recovery/Bootloader Mode
```sh
adb reboot recovery
adb reboot bootloader
```
*Restarts the device in different modes.*

### 25. Factory Reset a Device
```sh
adb shell recovery --wipe_data
```
*Performs a factory reset (use with caution!).*

## 🔥 Conclusion
These ADB commands are essential for developers, testers, and even power users who want to interact with their Android devices efficiently. Let me know if you need additional commands!

---
✨ **Tip:** You can use `adb shell dumpsys | grep "keyword"` to search for specific system info quickly.
