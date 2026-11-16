# Particle Emitter

This is a **particle emitter** application built with Kotlin and Android Jetpack Compose. It creates a dynamic background of particles with various customizable properties.

## Demo

Check out this animated demo:

![Animated particle emitter demo](https://github.com/user-attachments/assets/7c229d03-26c9-4812-957a-d9ac3878c5dd)

## Features

- Dynamic particle system using Jetpack Compose
- Multiple emission patterns: right-left fan, right fan, full circle
- Customizable themes (random, brand-specific, sparks)

## Configurable Parameters

The particle emitter is designed to be flexible. Here are the key configurable parameters:

1. **Particle Count (`particleCount`)**
   - **Purpose:** Determines the number of particles generated.
   - **Usage:** Increase this number for a denser effect.
   - **Example:** `particleCount = 50` creates 50 particles.

2. **Emission Variation (`variation`)**
   - **Purpose:** Controls the spread/direction of the particles.
   - **Variants:**
     - **RIGHT_LEFT_FAN:** Particles spread in a fan-like pattern, alternating left and right.
     - **RIGHT_FAN:** Particles spread only to the right.
     - **FULL_CIRCLE:** Particles emit uniformly in all directions (0°–360°).

3. **Particle Style (`particleStyle`)**
   - **Purpose:** Determines the color theme of the particles.
   - **Styles:**
     - **Default/Random:** Completely random colors.
     - **MSBrand:** Colors inspired by the m&S branding (random shades of green and near white).
     - **Sparks:** Golden/yellow hues for a spark-like effect.

4. **Canvas Size & Dynamic Scaling**
   - **Purpose:** Automatically adapts the particle system to the available space.
   - **Usage:** Uses `onSizeChanged` or `BoxWithConstraints` to measure the container and calculate the center dynamically, ensuring that the emitter remains centered regardless of device or screen size.
   - **Customizability:** Modify the `modifier` in the `ParticleBackground` to control the overall size.

5. **Particle Motion Properties**
   - **Trajectory:** Controls how far each particle travels from the center.
   - **Speed:** Determines the duration of each particle's animation cycle.
   - **Diameter:** Sets the size of each particle.
   - **Usage:** These properties are randomized within ranges that are proportional to the canvas size. For styles like *Sparks*, these ranges are adjusted to create a more energetic effect (shorter trajectories, faster speeds, and smaller particles).

6. **Background Integration (`ParticleBackground`)**
   - **Purpose:** Wraps the particle system as a dynamic background for other UI elements.
   - **Usage:** Allows you to overlay content (e.g., centered text) on top of the animated particles.
   - **Customizability:** Use modifiers to adjust the size and alignment of the background container.

## Run the demo

This repository contains an Android demo app, rather than a published library dependency.

### Requirements

- Android Studio with support for Android Gradle Plugin 8.1.4.
- JDK 17 for Gradle.
- Android SDK Platform 33.
- An emulator or Android device running Android 11 (API 30) or later.

### Setup

1. Clone the repository:

   ```bash
   git clone https://github.com/AndriaNjoku/Particle-Emitter.git
   cd Particle-Emitter
   ```

2. Open the repository root in Android Studio.
3. Set `sdk.dir` in `local.properties` to your own Android SDK location. The checked-in value is machine-specific.
4. Sync Gradle, select the `app` run configuration, and run it on your device or emulator.

To build a debug APK from the repository root:

```bash
./gradlew :app:assembleDebug
```

On Windows, use `gradlew.bat :app:assembleDebug` instead.

The SDK requirements above come from [the app configuration](app/build.gradle.kts). The build command is provided for local use; this documentation update does not establish a verified build or device-test result.
