# 📱 Awesome — React Native Core Fundamentals

[![React Native](https://img.shields.io/badge/React_Native-v0.87.1-61DAFB?logo=react&logoColor=black)](https://reactnative.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-v5.0+-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Platform](https://img.shields.io/badge/Platform-Android_%7C_iOS-brightgreen)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A foundational React Native application built with React Native CLI and TypeScript. This project demonstrates core mobile development concepts including environment setup, component primitives, safe area handling, and dynamic system-level Light/Dark theme detection.

---

## 🎯 Key Concepts Covered

- ⚙️ **CLI Environment & Architecture**: Understanding project setup, entry points (`index.js`), and component registration via `AppRegistry`.
- 🧱 **Core Primitives**: Building UI using fundamental components like `<View>`, `<Text>`, and `<SafeAreaView>` for notch and boundary safety.
- 🌓 **Dynamic Theme Handling**: Utilizing the `useColorScheme()` hook to automatically adapt layout and typography styles according to system Light/Dark mode preferences.
- 🎨 **Styling API**: Scoped, type-safe styling using `StyleSheet.create`.
- 🔄 **Component Architecture**: Modular component structure separating basic views (`App.tsx`) and enhanced theme-aware components (`AppPro.tsx`).

---

## 📂 Project Structure

```text
Awesome/
├── index.js              # Application entry point & AppRegistry registration
├── App.tsx               # Basic React Native component setup
├── AppPro.tsx            # Theme-aware functional component
├── app.json              # App configuration metadata
├── babel.config.js       # Babel configuration
├── metro.config.js       # Metro bundler configuration
├── tsconfig.json         # TypeScript configuration
├── package.json          # Project dependencies & scripts
├── android/              # Native Android project configuration
└── ios/                  # Native iOS project configuration
```

---

## 🛠️ Tech Stack & Dependencies

- **Framework**: [React Native](https://reactnative.dev/) (v0.87.1)
- **Library**: [React](https://react.dev/) (v19.2.3)
- **Language**: [TypeScript](https://www.typescriptlang.org/)
- **Safe Area Management**: `react-native-safe-area-context`
- **Build System**: Metro Bundler & React Native CLI

---

## 💻 Code Overview

Below is an excerpt from [`AppPro.tsx`](./AppPro.tsx) illustrating dynamic theme detection and conditional styling:

```tsx
import React, { JSX } from 'react';
import { StyleSheet, Text, useColorScheme, View } from 'react-native';
import { SafeAreaView } from 'react-native-safe-area-context';

const AppPro = (): JSX.Element => {
  const isDarkMode = useColorScheme() === 'dark';

  return (
    <SafeAreaView style={styles.container}>
      <View>
        <Text style={isDarkMode ? styles.whiteText : styles.darkText}>
          Hello world, This is a simple AppPro
        </Text>
      </View>
    </SafeAreaView>
  );
};

export default AppPro;

const styles = StyleSheet.create({
  container: {
    flex: 1,
    alignItems: 'center',
  },
  whiteText: {
    color: 'white',
  },
  darkText: {
    color: 'black',
  },
});
```

---

## 🚀 Getting Started

### Prerequisites

Ensure your environment is configured according to the official [React Native CLI Setup Guide](https://reactnative.dev/docs/set-up-your-environment).

- **Node.js**: `>= 22.11.0`
- **JDK**: `17` or higher
- **Android Studio** (for Android SDK & Emulator setup)
- **Xcode & CocoaPods** (for iOS development on macOS)

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Imtiaz-Ali17314/Awesome-App-React-Native.git
   cd Awesome-App-React-Native
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Install CocoaPods (iOS only)**:
   ```bash
   cd ios && pod install && cd ..
   ```

---

## 🏃 Running the App

1. **Start Metro Dev Server**:
   ```bash
   npm start
   ```

2. **Run on Android**:
   ```bash
   npm run android
   ```

3. **Run on iOS**:
   ```bash
   npm run ios
   ```

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
