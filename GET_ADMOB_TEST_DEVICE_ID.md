# How to Get Your AdMob Test Device ID (Windows)

## Prerequisites

- Android device connected via USB with USB debugging enabled
- Android SDK installed (comes with Android Studio)

## Steps

### 1. Verify your device is connected

```powershell
$adb = "$env:LOCALAPPDATA\Android\Sdk\platform-tools\adb.exe"
& $adb devices
```

Expected output:
```
List of devices attached
R5CW13SJ58N    device
```

If it says `unauthorized`, unlock your phone and tap **Allow** on the USB debugging prompt.

### 2. Stream logcat and filter for AdMob

```powershell
$adb = "$env:LOCALAPPDATA\Android\Sdk\platform-tools\adb.exe"
& $adb logcat -T 1 2>&1 | Select-String -Pattern "RequestConfiguration|testdevice|test ads" | Select-Object -First 5
```

- `-T 1` — only shows logs from the moment the command runs (skips old buffer)
- `Select-String` — filters lines containing AdMob-related keywords
- `Select-Object -First 5` — stops after capturing the first 5 matches

### 3. Open your app on the phone

After running the command, open the app on your device. When AdMob initializes, it prints a line like:

```
Use RequestConfiguration.Builder().setTestDeviceIds(Arrays.asList("2CCC6BEBF1D2ADB85A4799D0C345E6A3")) to get test ads on this device.
```

The hex string is your test device ID.

## Using the ID in your app

```kotlin
val config = RequestConfiguration.Builder()
    .setTestDeviceIds(listOf("2CCC6BEBF1D2ADB85A4799D0C345E6A3"))
    .build()
MobileAds.setRequestConfiguration(config)
```

Call this before `MobileAds.initialize()`.

## Notes

- The test device ID is unique per physical device.
- Using test ads prevents invalid click charges to your AdMob account.
- PowerShell exits with code 255 when the pipeline is broken by `Select-Object -First` — this is expected and harmless.
