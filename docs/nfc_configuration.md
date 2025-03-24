---
title: NFC Setup
layout: default
nav_order: 4
---

# Setting Up NFC Capabilities

We use [react-native-nfc-manager](https://github.com/revtel/react-native-nfc-manager) to enable NFC functionality in our application. To use this package, you must configure your project to support NFC on both iOS and Android.

## iOS Setup

1. Enable NFC Capability in Apple Developer Portal
- Go to your Apple Developer Account and enable NFC capability for your app.

2. Modify `Info.plist`
-  Add the NFC usage description in Info.plist:

````xml
<key>NFCReaderUsageDescription</key>
<string>We need to use NFC</string>
````

3. Enable NFC in Xcode 
- Open Xcode → Signing & Capabilities → Add Capability → Near Field Communication Tag Reading.
- This will generate an entitlements file (<your-project>.entitlements) containing:

````xml
<key>com.apple.developer.nfc.readersession.formats</key>
<array>
    <string>NDEF</string>
</array>
````
---

## Android Setup

1. Add NFC Permission in AndroidManifest.xml
- Open android/app/src/main/AndroidManifest.xml and add:

````xml
<uses-permission android:name="android.permission.NFC" />
````

2. Support for Android 12+
-  Open android/app/src/main/AndroidManifest.xml and add:

````gradle
buildscript {
    ext {
        compileSdkVersion = 31
    }
}
````

If you are targeting Android 12+, you need to handle the new PendingIntent mutability requirements.

---

For full details, refer to the official [react-native-nfc-manager](https://github.com/revtel/react-native-nfc-manager) documentation.
