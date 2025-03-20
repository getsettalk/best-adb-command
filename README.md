# ADB (Android Debug Bridge) - Most Useful Commands

ADB (Android Debug Bridge) is a command-line tool that allows developers, testers, and normal users to interact with Android devices. Below is a list of the most commonly used and useful ADB commands.

## 📌 **Setup ADB**

1. Enable **Developer Options** on your Android device.
2. Enable **USB Debugging** in Developer Options.
3. Install ADB on your PC:
   - **Windows**: Install ADB from [Android SDK Platform Tools](https://developer.android.com/studio/releases/platform-tools)
   - **macOS/Linux**: Use Homebrew: `brew install android-platform-tools`
4. Connect your device via USB and verify with:
   ```sh
   adb devices
   ```
   If prompted, allow USB debugging on your device.

---

## 🔍 **Basic ADB Commands**

### 1️⃣ **Check Connected Devices**
```sh
adb devices
```
🔹 Lists all connected devices with ADB access.

### 2️⃣ **Restart ADB Server**
```sh
adb kill-server
adb start-server
```
🔹 Restarts the ADB server in case of issues.

### 3️⃣ **Reboot Device**
```sh
adb reboot
```
🔹 Restarts the device normally.

```sh
adb reboot recovery
```
🔹 Boots into recovery mode.

```sh
adb reboot bootloader
```
🔹 Boots into fastboot mode.

---

## 📸 **Take Screenshots & Record Screen**

### 4️⃣ **Take a Screenshot**
```sh
adb shell screencap -p /sdcard/screenshot.png
adb pull /sdcard/screenshot.png
```
🔹 Takes a screenshot and saves it on your PC.

### 5️⃣ **Record Screen**
```sh
adb shell screenrecord /sdcard/record.mp4
adb pull /sdcard/record.mp4
```
🔹 Records the screen (Ctrl+C to stop).

---

## 📂 **File Management**

### 6️⃣ **Push File to Device**
```sh
adb push file.txt /sdcard/
```
🔹 Sends a file from PC to Android.

### 7️⃣ **Pull File from Device to PC**
```sh
adb pull /sdcard/file.txt
```
🔹 Retrieves a file from Android to PC.

### 8️⃣ **Delete File on Device**
```sh
adb shell rm /sdcard/file.txt
```
🔹 Deletes a file from the Android device.

---

## 📱 **App Management**

### 9️⃣ **Install an APK**
```sh
adb install app.apk
```
🔹 Installs an APK file.

### 🔟 **Uninstall an App**
```sh
adb uninstall com.example.app
```
🔹 Uninstalls an app (use `-k` to keep data).

### 1️⃣1️⃣ **Extract Installed APK**
```sh
adb shell pm path com.example.app
adb pull /data/app/com.example.app-1/base.apk
```
🔹 Gets the APK file of an installed app.

---

## 🛠 **Debugging & System Info**

### 1️⃣2️⃣ **View Device Log (Live)**
```sh
adb logcat
```
🔹 Streams live system logs.

### 1️⃣3️⃣ **Check Device Info**
```sh
adb shell getprop
```
🔹 Displays all system properties.

### 1️⃣4️⃣ **Battery & Network Info**
```sh
adb shell dumpsys battery
adb shell dumpsys wifi
```
🔹 Shows battery and network details.

---

## 🔐 **Control Device & Security**

### 1️⃣5️⃣ **Grant App Permissions**
```sh
adb shell pm grant com.example.app android.permission.CAMERA
```
🔹 Grants a permission manually.

### 1️⃣6️⃣ **Revoke App Permissions**
```sh
adb shell pm revoke com.example.app android.permission.CAMERA
```
🔹 Revokes a permission.

### 1️⃣7️⃣ **Factory Reset Device**
```sh
adb shell recovery --wipe_data
```
🔹 Performs a factory reset (⚠️ Be careful!).

---

## 🔄 **Screen Mirroring & Input**

### 1️⃣8️⃣ **Mirror Android Screen to PC**
```sh
scrcpy
```
🔹 Uses [scrcpy](https://github.com/Genymobile/scrcpy) for screen mirroring.

### 1️⃣9️⃣ **Simulate Touch Input**
```sh
adb shell input tap 500 500
```
🔹 Simulates a touch at coordinates (500, 500).

### 2️⃣0️⃣ **Simulate Key Press**
```sh
adb shell input keyevent 26
```
🔹 Simulates pressing the Power button.

---

## 🎯 **Extra Commands**

### 2️⃣1️⃣ **Turn Off Device Screen**
```sh
adb shell input keyevent 223
```
🔹 Turns the screen off (lock screen).

### 2️⃣2️⃣ **Turn On Device Screen**
```sh
adb shell input keyevent 224
```
🔹 Wakes the device up.

### 2️⃣3️⃣ **Copy Text to Clipboard**
```sh
adb shell am broadcast -a clipper.set -e text 'Hello World'
```
🔹 Copies text to the clipboard.

---

## 🏁 **Conclusion**
These ADB commands help developers, testers, and even normal users to interact with Android devices efficiently. 🚀

If you found this useful, feel free to star ⭐ this repository and share it! 😊
