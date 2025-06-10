<p align="center">
  <a href="" rel="noopener">
 <img width=200px height=200px src="https://i.imgur.com/QbFEss8.png" alt="Project logo"></a>
</p>

<h3 align="center">Plot Observer</h3>

<div align="center">

[![Status](https://img.shields.io/badge/status-active-success.svg)]()

</div>

---

<p align="justify"> Plot Observer is Flutter mobile application project with iOS and Android operating systems in mind. Has the following features and more:
</p>
<p align="left">
- Google Maps<br>
- Text Recognition<br>
- Thermal Printing<br>

## 📝 Table of Contents

- [About](#about)
- [Getting Started](#getting_started)
- [Deployment](#deployment)
- [Usage](#usage)
- [Built Using](#built_using)
- [TODO](../TODO.md)
- [Contributing](../CONTRIBUTING.md)
- [Authors](#authors)
- [Acknowledgments](#acknowledgement)

## 🧐 About <a name = "about"></a>

Plot Observer is an iOS and Android hybrid application developed using Flutter and Dart. It's purpose is to quickly scan the high amounts of vehicles inside parking lots to be able to effectively and efficiently create tickets for the vehicles that are causing parking violations.

## 🏁 Getting Started <a name = "getting_started"></a>

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See [deployment](#deployment) for notes on how to deploy the project on a live system.

## Architecture <a name = "architecture"></a>

| Layer                         | Component                 |
| ----------------------------- | ------------------------- |
| Presentation (UI Layer)       | auth_screen.dart          |
| Presentation (UI Layer)       | plot_rules_dialog.dart    |
| Business (State Management)   | auth_service.dart         |
| Business (Service Layer)      | auth_cubit.dart           |
| Persistence (Data Layer)      | auth_endpoint.dart        |
| Database/API (Infrastructure) | MsSQL, Firebase, REST API |

### Prerequisites

## Flutter Version

```bash
Flutter 3.24.5 • channel stable • https://github.com/flutter/flutter.git
Framework • revision dec2ee5c1f (4 months ago) • 2024-11-13 11:13:06 -0800
Engine • revision a18df97ca5
Tools • Dart 3.5.4 • DevTools 2.37.3
```

Follow the steps on:

```bash
https://docs.flutter.dev/get-started/install
```

### Setting Up The Environment

```

1. Set up your .env using the variables inside the .env.example

Make sure you are using a secure SSH key.

```

## 🔧 Running the tests <a name = "tests"></a>

There are two types of tests for Plot Observer,

1. Automated tests that doesn't require an emulator to be tested (marked with _filename_\_test.dart)
2. Automated tests that require an emulator to be tested (marked with _filename_\_notest.dart)

### Break down into end to end tests

```

flutter test

```

### Coding Style

Dart is a very simple and straight forward programming language inspired by TypeScript and C.

[Effective Dart: Style](https://dart.dev/effective-dart/style)

Understanding Flutter's Widgets and how they are shown to the UI might be a little confusing but with practice it'll fit in.

[Flutter](https://docs.flutter.dev/get-started/learn-flutter)

## 💻 Usage <a name="usage"></a>

### 🖶 Printer

- Printer business layer is separated to two components. Zebra Programming Language (ZPL) Service and Zebra Printer Service.
- Zebra printers act as BLE Peripherals so the Flutter application must act as a BLE Central. You can use [this](https://pub.dev/packages/flutter_blue_plus) package to connect & send commands to the Zebra Printer.
- On iOS, apps can only access devices they have connected to in the current session.

1. [Zebra Printer Service](lib/services/zebra_service.dart)
2. [ZPL Service](lib/services/zpl_service.dart)

### 🎥 Scanner

Scanner uses `ResolutionPreset.medium`, using anything higher than this can cause lag and even crashes.

There is a certain delay manually applied to the scanner logic to make sure that the `CameraPreview` doesn't freeze but continues without making the necessary operations too many times.

To be able to apply OCR to the taken image we need to convert the `CameraImage` (package:camera) instance to different formats depending on the platform that the application is running on. For more details please see [Camera Service](lib/services/camera_service.dart)

https://chatgpt.com/c/67c82843-915c-8005-a291-196ffd318867
https://chatgpt.com/c/2817a89c-889b-4c00-b484-e5507357c352

## 🚘 Supported Countries

- Denmark
- Poland
- Sweden
- Germany
- Germany Electric Vehicles
- Netherlands
- Great Britain
- Custom License Plates (look: `freePlateDetectionMode`)

### 🧂 Flavor

```dart
  /// Developer Environment
  FlavorConfig(
    name: "DEV",
    color: AppColors.red,
    location: BannerLocation.topStart,
    variables: {
      "apiUrl": "https://example.apiurl.en/",
      "locale": "en_US",
    },
  );
  /// Production Environment
  FlavorConfig(
    variables: {
      "apiUrl": "https://example.apiurl.en/",
      "locale": "da_DK",
    },
  );
```

### 📴 Offline mode

> [!NOTE]  
> Currently in offline mode the Observer can do the following:

a. scan license plates

b. see the vehicles that he scanned

c. see Case Files that were previously loaded.

d. cache pictures to be uploaded later.

e. can see the latest opened case files details (marked with purple)

# 🚀 Deployment <a name = "deployment"></a>

## 1. Android

```bash
.\build_apk.sh
.\build_apk.bat
```

## 2. iOS

We use different flavors for dev & prod: [Flutter Flavor](https://pub.dev/packages/flutter_flavor) for more.

```bash
.\build_ipa_testflight.sh dev
.\build_ipa_testflight.sh prod
```

## ⛏️ Built Using <a name = "built_using"></a>

- [Flutter](https://flutter.dev/) - Mobile App Framework
- [Dart](https://dart.dev/) - Programming Language
- [REST API](https://restfulapi.net/) - Communication Protocol
- [Cubit](https://pub.dev/packages/flutter_bloc) - State Management
- [Dio](https://pub.dev/packages/dio) - HTTP Client for API calls
- [Firebase](https://pub.dev/packages/firebase_core) - Firebase Core
- [Firebase Messaging](https://pub.dev/packages/firebase_messaging) - Firebase Messaging
- [Get It](https://pub.dev/packages/get_it) - Service Locator
- [Flutter Flavor](https://pub.dev/packages/flutter_flavor) - Dev / Prod

## ✍️ Authors <a name = "authors"></a>

- [@utkuvrs](https://github.com/utkuvrs)
