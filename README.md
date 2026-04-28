# AERA Android Application

AERA (Artificial Emotion and Reasoning Architecture) is an advanced Android application that serves as a mobile neural interface for the AERA cognitive system. It features a unique, highly immersive Jetpack Compose UI with real-time tracking of simulated neuro-chemicals and emotional states, coupled with a persistent background voice service.

## 🚀 Features

- **Neural Interface Access:** A custom login screen simulating a secure, defense-grade neural authentication matrix.
- **Cognitive HUD Interface:** A dynamic dashboard built with Jetpack Compose featuring:
  - **Emotional Status:** Real-time waveform visualization of simulated emotional states.
  - **Neuro-Chemical Matrix:** Live tracking of system 'Dopamine', 'Serotonin', and 'Cortisol' levels.
  - **Cognition Stream:** Live logs of the system's thought process and matrix sync status.
- **Persistent Voice Service:** Background service (`AERAVoiceService`) for continuous audio capture and voice command processing, ensuring the system remains responsive even when minimized.
- **Dynamic UI Elements:** Interactive `OrbitalCore` and `WaveformWidget` animations that react to the system's state.

## 🛠️ Technology Stack

- **Language:** Kotlin
- **UI Framework:** Android Jetpack Compose (Material 3)
- **Networking:** OkHttp3 & Jsoup
- **Asynchronous Processing:** Kotlin Coroutines
- **Local Storage:** DataStore Preferences
- **JSON Parsing:** Gson
- **Minimum SDK:** 26 (Android 8.0)
- **Target SDK:** 34 (Android 14)

## 📁 Project Structure

```text
app/src/main/java/com/aera/agi/
├── brain/          # Logic for the simulated chemical matrix (Dopamine, Serotonin, Cortisol)
├── core/           # AERAController and core system management
├── data/           # Data classes representing ChatMessages, configurations, etc.
├── ui/             # Jetpack Compose UI components (OrbitalCore, WaveformWidget, themes)
├── voice/          # AERAVoiceService for background audio capturing and TTS
└── MainActivity.kt # Entry point, permission handling, HUD implementation
```

## ⚙️ Setup and Installation

### Prerequisites

- [Android Studio](https://developer.android.com/studio) (Latest version recommended)
- JDK 17 (or newer)
- An Android Device or Emulator running Android 8.0 (API 26) or higher.

### Building the APK

1. Clone or download this repository.
2. Open the project in Android Studio.
3. Wait for Gradle to finish syncing the project dependencies.
4. Build the application by navigating to **Build > Build Bundle(s) / APK(s) > Build APK(s)** in the Android Studio menu.
5. The compiled APK will be located in the `app/build/outputs/apk/debug/` directory.

### Permissions Required

For AERA to function correctly, the following permissions must be granted:
- `INTERNET`: For syncing with the external AERA neural matrix and fetching data.
- `RECORD_AUDIO`: For real-time voice command processing.
- `FOREGROUND_SERVICE` & `FOREGROUND_SERVICE_MICROPHONE`: Ensures the system can listen for wake words and voice commands in the background without being terminated by the OS.
- `POST_NOTIFICATIONS`: For displaying background service status (Required for Android 13+).

## 🔒 Security & Deployment Notes

This application utilizes a foreground service to maintain an active, real-time auditory interface. When deploying outside the Google Play Store, the `release` signing config in `app/build.gradle` has been prepared with a keystore (`aera-release.jks`) to ensure smooth installation.
