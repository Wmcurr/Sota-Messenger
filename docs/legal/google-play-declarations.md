# Google Play Declaration Drafts

Last updated: May 21, 2026

These are draft texts for Google Play Console declarations. They should be copied into the relevant Play Console forms only after final review against the exact release build.

## Foreground Service: connectedDevice

### App functionality

```text
Sota uses the connected-device foreground service type to maintain user-visible nearby communication over Bluetooth, BLE, Wi-Fi Direct, Wi-Fi Aware, and related peer-to-peer transports. Offline and nearby communication is a core feature of Sota. The service allows the app to discover nearby Sota users, maintain mesh connectivity, route messages, and support communication when internet access is unavailable or unreliable.
```

### User impact if delayed

```text
If this work is delayed, nearby users may not be discovered in time, offline messages may not route, and mesh-based communication may fail or become unreliable.
```

### User impact if interrupted

```text
If this work is interrupted, active nearby communication may disconnect, messages may be delayed, and calls or walkie-talkie sessions that depend on nearby transport may fail.
```

### Suggested use case

Continuous data transfer or interaction with an external/nearby device over Bluetooth or network connection.

### Video to prepare

Record a short screen video showing:

1. Opening Sota.
2. Enabling or using nearby/offline communication.
3. Two devices discovering each other or exchanging a message without internet.
4. The foreground notification while mesh connectivity is active.

## Foreground Service: microphone

### App functionality

```text
Sota uses the microphone foreground service type only during user-started voice communication features, including voice calls, video calls, walkie-talkie, voice messages, and voice channels. The microphone is needed to transmit the user's voice during active communication.
```

### User impact if delayed

```text
If microphone foreground work is delayed, the user may answer a call or start a voice feature but the other participant may not hear audio immediately.
```

### User impact if interrupted

```text
If microphone foreground work is interrupted, active call or voice communication audio may stop.
```

### Video to prepare

Record:

1. Starting or answering a Sota call.
2. Showing the active call UI.
3. Showing the ongoing call notification.

## Foreground Service: camera

### App functionality

```text
Sota uses the camera foreground service type only during user-started video communication features, such as video calls or video capture features. The camera is needed to transmit video when the user enables camera during a call or starts video capture.
```

### User impact if delayed

```text
If camera foreground work is delayed, the user's video may not start when expected.
```

### User impact if interrupted

```text
If camera foreground work is interrupted, the user's video stream may stop during an active video call.
```

### Video to prepare

Record:

1. Starting a video call.
2. Turning camera on.
3. Showing the active call UI and notification.

## Foreground Service: location

### App functionality

```text
Sota uses the location foreground service type only for live location sharing that the user explicitly starts. The service keeps sending location updates to the selected chat while live sharing is active and shows an ongoing notification with a stop action.
```

### User impact if delayed

```text
If live location sharing is delayed, recipients will not receive timely location updates.
```

### User impact if interrupted

```text
If live location sharing is interrupted, recipients may see stale or missing location updates until the user starts sharing again.
```

### Video to prepare

Record:

1. Opening a chat.
2. Choosing location attachment.
3. Starting live location.
4. Showing the ongoing live location notification.
5. Stopping live location.

## Full-Screen Intent

### Declaration text

```text
Sota uses USE_FULL_SCREEN_INTENT only for incoming voice and video calls. Receiving calls is a core communication feature of Sota. The full-screen call UI lets the recipient answer or decline immediately when the device is locked or another app is open. Sota does not use full-screen intent for ads, promotions, ordinary messages, or non-call notifications.
```

### User impact if not allowed

```text
If full-screen intent is not allowed, incoming calls may only appear as regular notifications. Users may miss time-sensitive calls, especially when the device is locked or in another app.
```

### Video to prepare

Record:

1. Device B locked or on another app.
2. Device A starts a Sota call.
3. Device B receives the incoming full-screen call UI.
4. Device B answers or declines.

## Location Permission Declaration

### Declaration text

```text
Sota uses location permission for two user-visible purposes. First, users can explicitly send current location or start live location sharing in a chat. Second, Sota uses location permission for nearby device discovery required by Android Bluetooth/Wi-Fi scanning APIs. Nearby mesh communication is a core feature of Sota because the app is designed to work when internet connectivity is unavailable or unreliable. Sota does not use GPS for background tracking as part of mesh discovery.
```

### Prominent disclosure text

```text
Sota needs Location permission to find nearby devices for offline communication over Bluetooth/Wi-Fi and to let you send your location when you choose that feature. Sota does not use this permission for background GPS tracking.
```

## Broad Media Permissions

### Declaration text if broad media permissions remain

```text
Sota requests media permissions so users can select, preview, send, receive, save, and manage photos, videos, audio files, voice messages, stories, documents, and encrypted backups within the messenger. Media transfer and received-media management are core messenger features.
```

### Lower-risk alternative

If the release can use Android system Photo Picker and document picker for all user-selected media flows, remove broad media permissions where possible and document picker-based access instead.

