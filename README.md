# cw6 - Battery Level

A Flutter application that demonstrates the use of platform channels to retrieve the device battery level across multiple platforms.

## Overview

This app uses Flutter's `MethodChannel` API to communicate with native platform code and display the current battery level. A single "Get Battery Level" button triggers a call to the native layer, which responds with the current percentage.

## Platform Support

| Platform | Language | API Used |
|----------|----------|----------|
| Android  | Kotlin   | `BatteryManager` |
| iOS      | Swift    | `UIDevice.batteryLevel` |
| Windows  | C++      | `GetSystemPowerStatus` |
| macOS    | Swift    | `IOKit.ps` |
| Linux    | C        | UPower (`libupower-glib`) |

## Channel Name

```
samples.flutter.dev/battery
```

## Method

| Method | Returns | Description |
|--------|---------|-------------|
| `getBatteryLevel` | `int` | Battery percentage (0–100), or an error if unavailable |

## Getting Started

### Prerequisites

- [Flutter SDK](https://docs.flutter.dev/get-started/install)
- For Linux: install UPower dev headers — `sudo apt install libupower-glib-dev`

### Run the app

```bash
flutter run
```

### Run on a specific platform

```bash
flutter run -d windows
flutter run -d macos
flutter run -d android
flutter run -d ios
```

## Notes

- On the iOS Simulator, battery APIs are not supported and the app will display "Battery level not available".
- On Windows or macOS desktops without a battery (e.g., desktop PCs), the app will display "Battery level not available".
- On Android Emulator, set the battery level via **Extended Controls ? Battery**.

## Resources

- [Flutter platform channels documentation](https://docs.flutter.dev/platform-integration/platform-channels)
- [Flutter online documentation](https://docs.flutter.dev/)
