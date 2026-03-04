<h1 align="center">iOS Test</h1>

<p align="center">
  Native capability harness built with Expo + React Native<br>
  Fast, category-based validation of real device APIs across iOS, Android, and Web
</p>
<p align="center">
  <img src="assets/demo.png" alt="iOS Test banner" width="100%" />
</p>

## Overview

`iOS Test` is a practical testbed for validating mobile-native capabilities with a lightweight, modern UI.
It uses Expo Router for navigation, NativeWind for styling, React Native Paper for theming/typography,
and RN Primitives-based reusable components.

## Current App Structure

```text
ios-test/
├── app/
│   ├── _layout.tsx          # Root providers + Stack navigation
│   ├── index.tsx            # Home dashboard with capability categories
│   └── category/[id].tsx    # Dynamic category detail and test execution
├── components/
│   ├── screens/home/
│   └── ui/                  # RN Primitives wrappers and shared UI
├── lib/
│   ├── IOSTestContext.tsx   # Test state + run/reset logic
│   ├── categories.ts        # Category metadata and feature grouping
│   ├── theme.ts
│   └── utils.ts
└── assets/
```

## Capability Coverage

The app currently covers **18 features** across **9 categories**:

- Core Experience: notifications, biometrics, haptics
- Hardware & Sensors: camera, location, brightness, device info
- Media & Audio: audio recording/playback
- Networking: network request, network status
- Storage & Files: file storage, clipboard
- Motion Sensors: accelerometer, gyroscope
- UI & System: share sheet, action sheet
- Maps & Navigation: native maps launch
- Accessibility: screen reader and reduce motion status

## Tech Stack

- Expo SDK 54 + React Native 0.81
- Expo Router (file-based routing)
- NativeWind (Tailwind for React Native)
- React Native Paper (MD3 theme + typography)
- Lucide + Tabler icons
- TypeScript + ESLint + Prettier

## Getting Started

### Prerequisites

- Node.js 18+
- npm
- Xcode (for iOS Simulator) and/or Android Studio (for Android Emulator)

### Install

```bash
npm install
```

### Run

```bash
# Development server
npm run dev

# iOS simulator
npm run ios

# Android emulator
npm run android

# Web
npm run web
```

## Quality Checks

```bash
# Lint
npm run lint
npm run lint:fix

# Format
npm run format:check
npm run format

# TypeScript
npm run type-check
```

## Build & Deploy (EAS)

```bash
# Build
eas build --platform ios
eas build --platform android

# Submit
eas submit --platform ios
eas submit --platform android
```

If EAS is not initialized yet:

```bash
eas build:configure
```

## Notes

- Fonts are configured in `app/_layout.tsx` using Inter via `@expo-google-fonts/inter`.
- This repo is focused on capability verification and rapid iteration, not production app scaffolding.