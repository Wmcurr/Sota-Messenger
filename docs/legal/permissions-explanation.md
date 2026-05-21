# Sota Permissions Explanation

Last updated: May 21, 2026

This document explains why Sota requests sensitive Android permissions. It can be used as source material for Google Play declarations, support answers, and in-app explanations.

## Location

Permissions:

- `ACCESS_FINE_LOCATION`
- `ACCESS_COARSE_LOCATION`
- `FOREGROUND_SERVICE_LOCATION`

Sota uses location for:

- sending current location when the user chooses the location attachment;
- live location sharing when the user starts a live location session;
- nearby mesh discovery on Android devices where Bluetooth or Wi-Fi discovery requires location permission.

Sota does not use GPS for background tracking as part of mesh discovery. Mesh discovery uses nearby radio technologies such as Bluetooth, BLE, Wi-Fi Direct, and Wi-Fi Aware.

Suggested disclosure:

```text
Sota needs Location permission to find nearby devices for offline communication over Bluetooth/Wi-Fi and to let you send your location when you choose that feature. Sota does not use this permission for background GPS tracking.
```

## Bluetooth and Nearby Wi-Fi

Permissions:

- `BLUETOOTH`
- `BLUETOOTH_ADMIN`
- `BLUETOOTH_CONNECT`
- `BLUETOOTH_SCAN`
- `BLUETOOTH_ADVERTISE`
- `NEARBY_WIFI_DEVICES`
- `ACCESS_WIFI_STATE`
- `CHANGE_WIFI_STATE`
- `CHANGE_WIFI_MULTICAST_STATE`
- `CHANGE_NETWORK_STATE`

Sota uses these permissions for nearby communication, peer discovery, mesh routing, offline messaging, nearby voice paths, and media transfer when internet access is unavailable or unreliable.

This is core Sota functionality. Without nearby device discovery, Sota cannot reliably provide its offline messenger purpose.

## Camera

Permission:

- `CAMERA`

Sota uses camera access for:

- video calls;
- video notes;
- taking photos or videos to send;
- QR code scanning for adding contacts or pairing devices.

## Microphone

Permission:

- `RECORD_AUDIO`

Sota uses microphone access for:

- voice calls;
- video calls;
- voice messages;
- walkie-talkie;
- voice channels.

## Media and Files

Permissions:

- `READ_EXTERNAL_STORAGE` on older Android versions;
- `READ_MEDIA_IMAGES`;
- `READ_MEDIA_VIDEO`;
- `READ_MEDIA_AUDIO`.

Sota uses media access so users can select, preview, send, receive, save, and manage photos, videos, audio, documents, voice messages, stories, and backups.

If a release can rely entirely on Android's system photo picker and document picker, broad media permissions should be reduced. If broad permissions remain in the release, the Play Console explanation should tie them to core messenger media functionality.

## Notifications

Permission:

- `POST_NOTIFICATIONS`

Sota uses notifications for incoming messages, incoming calls, active calls, foreground services, live location sharing, and ongoing communication status.

## Full-Screen Intent

Permission:

- `USE_FULL_SCREEN_INTENT`

Sota uses full-screen intent only for incoming voice or video calls so the recipient can answer or decline immediately, including when the phone is locked.

Suggested declaration:

```text
Sota uses full-screen intent only for incoming voice and video calls. Calls are a core communication feature of the app. Without full-screen call UI, users may miss time-sensitive incoming calls when the device is locked or another app is open.
```

## Foreground Services

Permissions:

- `FOREGROUND_SERVICE`
- `FOREGROUND_SERVICE_CONNECTED_DEVICE`
- `FOREGROUND_SERVICE_MICROPHONE`
- `FOREGROUND_SERVICE_CAMERA`
- `FOREGROUND_SERVICE_LOCATION`

Sota uses foreground services for user-visible communication features:

- connected-device mesh communication over Bluetooth/Wi-Fi;
- active voice and video calls;
- active microphone/camera capture during calls;
- live location sharing started by the user.

These services show notifications and are necessary for real-time communication reliability.

## Boot Completed

Permission:

- `RECEIVE_BOOT_COMPLETED`

Sota may use this to restore communication readiness after device restart, depending on user settings and Android restrictions.

## Wake Lock

Permission:

- `WAKE_LOCK`

Sota may briefly wake or keep the device responsive for incoming calls, urgent call UI, active communication, and notification behavior.

## Biometrics

Permissions:

- `USE_BIOMETRIC`
- `USE_FINGERPRINT`

Sota uses biometrics for optional app lock, recovery phrase viewing, and security-sensitive settings.

