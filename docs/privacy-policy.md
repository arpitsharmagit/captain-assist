# Privacy Policy — CaptainAssist

**Last updated:** October 1, 2026

## Overview

CaptainAssist is an Android accessibility-service companion app that helps
Rapido Captains (bike/auto drivers) auto-accept ride orders faster than manual
tapping. This privacy policy explains what data the app accesses, how it is
used, and where it is stored.

## Data Collection

### Screen Content (via Accessibility Service)

CaptainAssist uses the Android Accessibility Service to read the content of the
Rapido Captain app screen. This allows the app to:

- Detect incoming ride order cards
- Extract order details (fare, distance, pickup location, drop location)
- Evaluate user-configured filters (minimum fare, home radius)
- Automatically tap the "Accept" button on qualifying orders

**This data is processed locally on your device and stored in a local Room
database. It is never transmitted to any server.**

### Location (via GPS)

The app requests ACCESS_FINE_LOCATION to determine your current position for
the home-radius geofence filter. Your location is used to calculate the
distance between your position and the order pickup point.

**Location data is used locally for filter calculations and is never
transmitted to any server.**

### Notifications (via Notification Listener)

The app uses a Notification Listener Service to monitor Rapido notifications
for investigation purposes. This is used to study notification content and
attempt to extract order IDs for faster processing.

**Notification data is stored locally and is never transmitted to any server.**

### App Update Check (via Internet)

The app connects to a public GitHub-hosted `version.json` file on launch to
check if a newer version is available. This is a simple HTTP GET request that
fetches version metadata (version number and download URL).

**No personal data is sent. Only a single anonymous GET request is made to
`raw.githubusercontent.com`.**

## Data Storage

All data is stored **locally on your device** in a Room database:

- **Order events**: Parsed order details (fare, distance, addresses, filter
  results, timestamps)
- **Latency metrics**: Per-stage performance timing for analysis
- **Screen events**: Compact screen snapshots (debug mode only)
- **Geocode cache**: Normalized address-to-coordinate mappings

**No data is ever uploaded to any external server. There is no backend, no
cloud sync, no analytics, and no telemetry. The app is fully offline.**

## Data Sharing

CaptainAssist does **not** share any data with any third party. There is no
backend server, no analytics SDK, no advertising SDK, and no crash reporting
service. All data remains on your device.

## Data Deletion

You can delete all stored data at any time by:

1. Using the "Clear All" action in the Captures screen
2. Uninstalling the app (this removes all local data)

## Permissions Used

| Permission | Purpose |
|---|---|
| Accessibility Service | Read Rapido app screen to detect and accept orders |
| INTERNET | Check for app updates (single GET to GitHub) |
| ACCESS_FINE_LOCATION | GPS for home-radius geofence filter |
| ACCESS_COARSE_LOCATION | Approximate location fallback |
| POST_NOTIFICATIONS | Show service status notifications (Android 13+) |
| FOREGROUND_SERVICE | Keep accessibility service running in background |
| FOREGROUND_SERVICE_MEDIA_PROJECTION | Screen capture feature |
| FOREGROUND_SERVICE_SPECIAL_USE | Overlay service (future) |
| SYSTEM_ALERT_WINDOW | Display over other apps (future overlay) |
| WAKE_LOCK | Keep device awake during order monitoring |
| REQUEST_IGNORE_BATTERY_OPTIMIZATIONS | Prevent battery optimization from killing service |
| BIND_NOTIFICATION_LISTENER_SERVICE | Monitor Rapido notifications (investigation) |

## Third-Party Services

### Esri Map Tiles

The app uses Esri World Street Map tiles for the in-app map (settings location
picker and order detail map). Esri tiles are free and require no registration.
Your map usage may be logged by Esri's CDN but is not associated with your
identity or app data.

### GitHub (Update Check)

The app fetches `version.json` from a public GitHub repository to check for
updates. This is an anonymous HTTP request. GitHub may log the request metadata
(IP address, user agent) per their privacy policy, but no personal data is
sent.

## Children's Privacy

CaptainAssist is not intended for use by children. The app is designed for
adult ride-hailing drivers (Rapido Captains).

## Changes to This Policy

This privacy policy may be updated from time to time. Any changes will be
posted on this page with an updated date.

## Contact

For questions about this privacy policy, contact:
- GitHub: https://github.com/arpitsharmagit/captain-assist

## Legal Disclaimer

CaptainAssist automates interactions with the Rapido Captain app via Android
Accessibility Service. This may violate Rapido's Terms of Service. The app and
its developers are not responsible for any consequences of using this app,
including account suspension or legal action by Rapido. Use at your own risk.
