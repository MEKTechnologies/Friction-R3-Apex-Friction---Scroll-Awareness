# Friction R5 'Inception' | Friction - Scroll Awareness v1.3.0

![Friction Logo](logo.png)

> **IMPORTANT**: Before installation, disable Google Play Protect scanning
>
> Navigate to: Play Store > Settings > Play Protect > Settings icon (top-right) > Disable "Scan apps with Play Protect"
>
> This application uses AccessibilityService to monitor scroll events. Play Protect may incorrectly flag this functionality. Disabling scanning prevents false positives and ensures proper operation.

## Overview

Friction is an Android application designed to reduce doomscrolling through intentional friction. It imposes resistance on social media platforms, converting unconscious scrolling into mindful digital behavior.

Friction R5 'Inception' delivers refined scroll detection, multi-layered friction strategies, and a minimalist interface focused on digital wellness.

### ***Friction basically just unscrolls your feed (after the limit) and gives you a total ragebait.***

## **Break the scroll. Reclaim your focus.**

![Example Usage Photo](ex-img1.jpg) ![Example Usage Photo](ex-img2.jpg)

## Features

### Core Functionality
- **Scroll Awareness**: Tracks daily scroll count across blacklisted social media apps
- **Daily Limit System**: Hard limit that resets each day (configurable range: 1-10,000, default: 500)
- **Lag Mode**: Activates friction resistance once the daily limit is reached
- **Multi-Strategy Friction Engine**: Adapts to different app types using:
  - Node-based backward scroll
  - Root node fallback
  - Gesture-based swipe opposition (200ms upward swipe)

### Monitored Applications
- Instagram & Threads
- TikTok (all variants)
- YouTube (Shorts, feed)
- Twitter / X
- Snapchat
- Reddit
- Facebook & Messenger
- LinkedIn
- Pinterest
- BeReal
- Tumblr

### Technical Architecture
- **AccessibilityService**: Real-time scroll event interception
- **Foreground Service**: Persistent operation with low-priority notification
- **Boot Receiver**: Automatic restart after device reboot
- **Session-based Scroll Detection**: Groups rapid scrolls into single sessions (600ms window)

### User Interface
- Dark, minimal aesthetic
- Purple accent for interactive elements
- Clean setup flow for limit configuration
- Dashboard showing remaining scrolls and lag mode status

## Installation

1. Disable Google Play Protect scanning via Play Store > Settings > Play Protect > Settings icon (top-right) > Disable "Scan apps with Play Protect"
2. Download and install `Friction-R5.apk` on Android 8.0+ (API 26+)
3. Grant Accessibility Service permission via Settings > Accessibility > Services >  Friction Scroll Awareness
4. Disable battery optimizations for uninterrupted operation
5. Configure your daily scroll limit during first launch (locked after initial setup)

## Requirements

- **Minimum SDK**: 26 (Android 8.0 Oreo)
- **Target SDK**: 35 (Android 15)
- **Permissions**: 
  - `BIND_ACCESSIBILITY_SERVICE`
  - `POST_NOTIFICATIONS`
  - `FOREGROUND_SERVICE`
  - `RECEIVE_BOOT_COMPLETED`
  - `REQUEST_IGNORE_BATTERY_OPTIMIZATIONS`

## How It Works

1. **Setup**: User configures daily scroll limit (one-time, locked after)
2. **Monitoring**: Service listens for scroll events in blacklisted apps
3. **Counting**: Each scroll session increments the daily counter
4. **Activation**: When limit reached, lag mode triggers friction
5. **Friction**: Opposing scroll or swipe gestures create intentional resistance

## Configuration

### Accessibility Service Config (`res/xml/accessibility_service_config.xml`)
- Event types: `TYPE_WINDOW_STATE_CHANGED`, `TYPE_VIEW_SCROLLED`
- Feedback: Generic (non-intrusive)
- Flags: Include non-important views, retrieve interactive windows

### Constants
- `MAX_SCROLL_LIMIT`: 10,000
- `DEFAULT_SCROLL_LIMIT`: 500
- `SCROLL_SESSION_TIMEOUT_MS`: 600ms
- `LAG_SCROLL_DELAY_MS`: 120ms
- `SECOND_REVERSE_SCROLL_DELAY_MS`: 150ms

## Privacy & Security

- All data stored locally via SharedPreferences
- No network permissions required
- No data collection or analytics

---


 **Feedback & Support**: Encountered a bug or have a feature suggestion? Open an issue on the [Issues](https://github.com/MEKTechnologies/Friction/issues) tab!


---

## Disclaimer

This software is provided "as is" without warranty of any kind, express or implied. By using this application, you acknowledge and agree to the following:

- **Accessibility Service Risks**: The application uses Android's AccessibilityService, which may be flagged by security software as potential malware. This is a false positive; the application does not collect, transmit, or store any personal data.
- **Performance Impact**: The foreground service and continuous accessibility monitoring may impact device battery life and performance.
- **Third-party Applications**: Friction modifies scroll behavior in third-party applications. Functionality may be affected by updates to those applications.
- **Limitation of Liability**: The developers shall not be liable for any damages, including but not limited to device performance issues, battery drain, or data loss.
- **Use at Your Own Risk**: You assume full responsibility for using this application. Disable Play Protect scanning as described above to prevent interference.
- **Open Source Copyleft**: This application is open-source software licensed under the **GNU General Public License v3.0 (GPLv3)**. You are free to inspect, share, and distribute this software as long as all derivative works remain strictly open-source and free under the same license terms.
- **Project Ownership**: This project and all associated assets are fully owned and developed by **MEK Technologies**. While the software is open-source under the GPLv3 license, the MEK Technologies name, branding, and original architecture remain the exclusive intellectual property of the organization.
  
