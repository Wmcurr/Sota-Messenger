# Google Play Declaration Drafts

Last updated: May 26, 2026

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

### Release decision

```text
The Google Play release should not declare READ_MEDIA_IMAGES, READ_MEDIA_VIDEO, READ_MEDIA_AUDIO, or READ_EXTERNAL_STORAGE unless a future build adds a verified broad-library workflow that cannot be implemented through Android Photo Picker, ACTION_GET_CONTENT, ACTION_OPEN_DOCUMENT, MediaStore write APIs, or user-granted URI access.
```

### Current lower-risk approach

The current release uses system pickers and SAF-style URI grants for user-selected media and files. Public saves use MediaStore write flows. If Play Console still shows broad media permissions for an uploaded artifact, inspect the merged manifest for transitive SDK declarations and remove them before submitting.

## User-Generated Content / Stories / Public Channels

### Declaration and reviewer note

```text
Sota lets users create messages, media, stories, groups, channels, comments, public handles, and invitations. Sota provides local user blocking and moderation controls for groups/channels. Users can report abuse to wmcurrency@zohomail.eu with the relevant Sota ID, group/channel ID, public handle, story/message details, timestamp, and optional screenshots or exported evidence. Because Sota is peer-to-peer and relay-assisted, the developer cannot delete content already delivered to other users' devices, but may restrict public directory entries, handles, relay/offline delivery, bootstrap/DHT participation, and other infrastructure access for abusive Sota IDs, groups, channels, handles, or traffic patterns.
```

### Public standards for child safety

```text
Sota's public Terms of Use explicitly prohibit Child Sexual Abuse and Exploitation (CSAE), grooming, sexual exploitation of minors, and content that endangers or abuses minors. Sota provides in-app reporting for users, messages, stories, groups, and channels, and may restrict or permanently block abusive Sota IDs, groups, channels, handles, relay/offline delivery, bootstrap/DHT participation, or other infrastructure access.
```

### Evidence to prepare

Record or screenshot:

1. The blocked-users control in Settings.
2. Blocking a user from a profile/contact/chat surface.
3. Group/channel owner moderation controls for members or comments.
4. Terms of Use showing the UGC, blocking, and reports section.
5. Server-side moderation denylist path or internal moderation procedure.
