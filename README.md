# Skywalker mobile app

[![Flutter](https://img.shields.io/badge/Flutter-3.8.0%2B-blue)](https://flutter.dev)
[![Build](https://img.shields.io/badge/build-passing-brightgreen)](#)
[![License](https://img.shields.io/badge/license-MIT-lightgrey)](#)

---

## Overview

This mobile application is my new project to explore the possibilities of intergrating space obvervation visualisation, I implemented user authentication and database integration with Firebase.

I want to build an app that teaches users about space, the solar system, planets, stars, and other astronomy concepts. I also plan to integrate real-time sky data so users can see:

- What celestial objects are visible right now from their location

- Real-time positions of planets and the Moon

- Upcoming astronomical events (meteor showers, eclipses, ISS flyovers, etc.)

- A live sky map they can explore or point their phone at

- Space weather alerts (e.g., aurora activity)

I’ve just finished the first stage of our authentication process and will be moving on to the next phase.
Looking for team members for this porject

## Authentication

- **Login Page**

  - Email and password login with validation
  - Error handling for invalid credentials and non-existent users
  - Password visibility toggle
  - Button to trigger login or registration
  - Checks for email and password match in Firestore collection "users"

- **Signup Page**

  - First name, last name, email, and password fields
  - Strong validation for all fields (length, format, allowed characters)
  - Checks for existing email in Firestore database users collection
  - Register new users and store their full name and email
  - Success and error feedback via SnackBar

- **Home Page**

  - Personalized welcome message ("Hey, <user name>, you are successfully logged in!") from Firestore
  - Drawer with user info, navigation, and logout
  - Bottom navigation bar (Dashboard, Explore, Profile)
    - Profile displays user info

- **Firebase Integration**

  - Uses `firebase_auth` for authentication
  - Uses `cloud_firestore` for user data
  - Ready for analytics with `firebase_analytics`

- **Testing**
  - Widget and unit tests for login and signup validation
  - Widget test for login with mocked FirebaseAuth and Firestore
  - Uses `mockito` for dependency injection and mocking

---

## Screenshots

Login page
![Login Screen](screenshots/login.jpg)
Sign up page
![Signup Screen](screenshots/signup.jpg)
Log out page

![Drawer Screen](screenshots/logout.png)
Login and Sign up page
![Login Validation Screen](screenshots/validation.jpg)

---

## Getting Started

### Prerequisites

- **Flutter SDK** (>=3.8.0): [Install Flutter](https://docs.flutter.dev/get-started/install)
- **Dart SDK** (comes with Flutter)
- **Firebase Project**: [Firebase Console](https://console.firebase.google.com/)
- **Platform Tools:**
  - **Android:** Android Studio, Android SDK, emulator/device
  - **iOS/macOS:** Xcode, CocoaPods, simulator/device (macOS only runs on Mac)

### 1. Clone the Repository

```sh
git clone <https://github.com/lingjiang9/babylon-radio-app.git>
cd babylon_flutter_app
```

### 2. Install Dependencies

```sh
flutter pub get
```

This will fetch all Dart and Flutter dependencies listed in `pubspec.yaml`.

### 3. Configure Firebase

1. **Create a Firebase project** in the [Firebase Console](https://console.firebase.google.com/).
2. **Register your app** for each platform (iOS, Android, macOS) in the Firebase Console.
3. **Download configuration files:**
   - `google-services.json` → Place in `android/app/`
   - `GoogleService-Info.plist` → Place in `ios/Runner/` and `macos/Runner/`
4. **Generate `firebase_options.dart`:**
   - Install the FlutterFire CLI if you haven't:
     ```sh
     dart pub global activate flutterfire_cli
     ```
   - Run:
     ```sh
     flutterfire configure
     ```
   - This will generate `lib/firebase_options.dart` for your project.

### 4. Platform-Specific Setup

- **Android:**

  - Open Android Studio emulator or connect a device.

- **iOS/macOS:**
  - Run `cd ios && pod install` and `cd macos && pod install` if needed.
  - Open Xcode and accept any prompts for signing/certificates.

### 5. Run the App

- **Android/iOS:**
  ```sh
  flutter run
  ```
  then select your desired connected device from the list
- **macOS**
  ```sh
  flutter run -d macos
  ```

---

## Project Structure

```
babylon_flutter_app/
├── lib/
│   ├── main.dart                # App entry point
│   ├── firebase_options.dart    # Firebase config (auto-generated)
│   └── pages/
│       ├── login_page.dart      # Login screen
│       ├── signup_page.dart     # Signup screen
│       └── home_page.dart       # Home screen
├── assets/
│   └── fonts/
│       └── roboto/              # Roboto font files
├── test/
│   ├── login_page_test.dart     # Widget/validation tests
│   ├── signup_validation_test.dart
│   └── login_logic_unit_test.dart
├── pubspec.yaml                 # Project config (dependencies, assets, fonts)
├── README.md                    # Project documentation
├── android/                     # Android native code (auto-generated)
├── ios/                         # iOS native code (auto-generated)
├── macos/                       # macOS native code (auto-generated)
└── screenshots/                 # (Optional) App screenshots for README
```

---

## Running Tests

To run all tests:

```sh
flutter test
```

- Tests cover form validation, error handling, and Firebase/Firestore integration (with mocks).
- To regenerate mocks after changing test annotations:
  ```sh
  flutter pub run build_runner build
  ```

---

## Troubleshooting

- **Firebase errors:** Ensure your Firebase config files are in the correct platform folders and `firebase_options.dart` is up to date.
- **Tests fail due to mocks:** Run `flutter pub run build_runner build` to regenerate mock files after changing test annotations.
- **Platform-specific issues:** Make sure you have the correct platform SDKs and emulators installed.
- **Hot reload not working:** Try `flutter clean` and restart your IDE.

---

## Future Improvements

- Add password reset functionality.
- Improve accessibility and localization.
- Add integration tests for navigation flows.
- Improve code quality.
- Add CI/CD pipeline for automated testing and builds.
- Add user profile editing and avatar upload.

---

## Contact

For questions, contact **Ling Jiang** at [jiangling9981@gmail.com].

---

## License

© 2025 Ling Jiang. All rights reserved.
This project is licensed under the MIT License.
