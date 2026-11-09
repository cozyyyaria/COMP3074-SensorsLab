# COMP3074 — Lab 7: Reading Android Device Sensors

Android application built with Kotlin and Jetpack Compose that reads device hardware and virtual sensors.

## Features
- **Ambient Temperature Sensor (`Sensor.TYPE_AMBIENT_TEMPERATURE`)**:
  - Automatically checks hardware availability.
  - Gracefully displays an unavailable status when the sensor is absent (e.g. on Android Emulators or phones without ambient temperature chips).
- **Gyroscope (`Sensor.TYPE_GYROSCOPE`)**:
  - Live angular velocity readouts across X, Y, and Z axes in rad/s.
- **Accelerometer (`Sensor.TYPE_ACCELEROMETER`)** *(Part 18 Extension)*:
  - Dynamic acceleration readouts across X, Y, and Z axes in m/s².
  - Real-time calculation and display of total acceleration magnitude ($\approx 9.8\text{ m/s}^2$ at rest due to gravity).

## Architecture & Lifecycle
- Implements `SensorEventListener` on `MainActivity`.
- Registers listeners in `onResume()` and unregisters in `onPause()` to prevent battery drain.
- Real-time reactivity powered by Jetpack Compose `mutableStateOf`.

## Tech Stack
- **Language:** Kotlin
- **UI Framework:** Jetpack Compose (Material Design 3)
- **Minimum SDK:** 24 (Android 7.0)
- **Target/Compile SDK:** 35 (Android 15)
