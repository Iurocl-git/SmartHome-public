# Project: Smart Home Mobile Application

**Author:** Ioan Motrescu

**Status:** In Development (Core functionality implemented, UI/UX refinement ongoing)

## Overview

This is a mobile application designed for convenient control and monitoring of smart home devices. The project aims to provide users with a single, intuitive interface to interact with various smart devices, including lighting, climate control, security sensors, and integrated IP video cameras using the ONVIF standard. The application is built using modern technologies with a focus on a comfortable and seamless user experience.

## Key Features

*   **Device Control:**
    *   Toggle device power states (lights, switches, etc.).
    *   Adjust device modes (e.g., "eco", "turbo", "normal" for climate devices).
    *   Set specific parameters (e.g., target temperature for thermostats).
*   **Sensor Monitoring:**
    *   Real-time display of data from various sensors (temperature, humidity, motion, smoke, gas, CO2, air quality, light, window/door status, etc.).
    *   Comparison of sensor data between different rooms over a selected time period.
*   **Video Surveillance (ONVIF/WebRTC):**
    *   **ONVIF Camera Integration:** Connects to ONVIF-compliant IP cameras on the local network.
    *   **Live Video Streaming:** Displays real-time video feeds within the app using WebRTC. Video streams (e.g., RTSP) from cameras are processed by a dedicated **`deepch/rtsptoweb` Docker container**, transforming them into WebRTC for efficient mobile viewing.
    *   **Basic Camera Commands:** Sends simple ONVIF commands to cameras (e.g., potential for basic PTZ controls if supported by the camera).
*   **Notifications:**
    *   Integrated push notification system using **Expo Push Notifications** and **Firebase Cloud Messaging (FCM)**.
    *   Alerts for critical events like motion detection, smoke/gas alerts, sensor thresholds, device status changes, etc.
*   **Home Structure:**
    *   Support for managing multiple distinct "Homes".
    *   Device organization by rooms ("Locations") within each home.
    *   Easy navigation between homes and rooms.
*   **User Features:**
    *   Secure user authentication (Login/Registration).
    *   User profile management (username, email, avatar).
    *   "Favorite Devices" section for quick access.

## Technology Stack

*   **Client (Mobile App):**
    *   **Framework:** React Native (Expo Managed Workflow)
    *   **Language:** TypeScript
    *   **Styling:** NativeWind v4 (Tailwind CSS for React Native)
    *   **Navigation:** Expo Router
    *   **State Management:** Zustand
    *   **Video:** `react-native-webrtc`
    *   **Notifications:** `expo-notifications`, FCM
*   **Backend:**
    *   **Platform:** Node.js
    *   **Framework:** Express.js
    *   **Language:** TypeScript
    *   **Database:** PostgreSQL
    *   **Session Management:** `express-session`
*   **Video Transformation Server:**
    *   **Software:** `deepch/rtsptoweb`
    *   **Deployment:** Docker Container
    *   **Protocols:** ONVIF/RTSP (Input) -> WebRTC (Output)

## Design & UX

The interface design emphasizes cleanliness, intuitiveness, and consistency. It utilizes a custom design system built with NativeWind v4, featuring a defined color palette (supporting light and dark modes), the **Inter** typeface, and unified styles for components (buttons, cards, input fields, etc.).

*(Note: Accompanying screenshots showcase the current user interface across various application screens, including login, home/room selection, device control, video streaming, and profile.)*

## Key Aspects & Challenges

*   **ONVIF & WebRTC Integration:** Implementing reliable live video streaming from diverse IP cameras via the `deepch/rtsptoweb` transformation server was a key technical focus.
*   **Device Capability Handling:** Designing the system to flexibly handle various device types and their specific capabilities (`capabilities` data structure).
*   **Modern Stack:** Leveraging current technologies like Expo, TypeScript, NativeWind v4, Zustand, and WebRTC.
---
**(Screenshots showcasing various application screens are provided alongside this description.)**
