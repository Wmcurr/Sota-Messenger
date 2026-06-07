# Privacy Policy

Last updated: May 26, 2026

This Privacy Policy explains how Sota handles information when you use the Sota Android app.

Sota is published by Mykola Tolochko. For privacy questions, contact: wmcurrency@zohomail.eu.

## Summary

Sota is a messenger designed for direct, relay-assisted, and offline nearby communication. Sota does not require a phone number or email address to create an identity. Instead, the app creates a cryptographic identity on your device.

Your Sota identity is controlled by your device keys, recovery phrase, encrypted backups, or device-pairing backup flow. If you lose access to your device keys and do not have a recovery phrase or backup, Mykola Tolochko cannot recover your identity for you.

## Information Sota Uses

### Cryptographic identity

Sota creates and stores a public/private key pair on your device. Your public key, also called your node ID or Sota ID, is used so other users can find, verify, message, and call you.

Your private key is stored on your device using Android-protected storage. Sota may show you a 24-word recovery phrase so you can restore your identity later. Sota does not receive or store your recovery phrase on a central server.

### Profile information

You may set a display name, avatar, profile details, or similar public profile information. This information may be shared with your contacts or published through Sota's discovery mechanisms so other Sota users can recognize you.

### Messages, calls, media, and files

Sota processes messages, voice messages, calls, photos, videos, documents, stickers, stories, and other content that you choose to send or receive.

Content may be stored locally on your device. Depending on network availability and recipient reachability, content may be transmitted directly, through nearby mesh transports, through relay transport, or through temporary offline delivery mechanisms.

Sota's relay and bootstrap server is designed for routing and temporary delivery. It is not designed as a user account database. Some delivery metadata and encrypted or encoded payload records may pass through the server when needed to deliver messages or maintain connectivity.

### Location

Sota uses location permission for two user-visible purposes:

- Current or live location sharing, when you explicitly choose to send your location or start live location sharing.
- Nearby device discovery for offline mesh communication over Bluetooth, Wi-Fi Direct, or related Android nearby technologies. Android may require location permission to scan for nearby Bluetooth or Wi-Fi devices, even when Sota is not using GPS tracking for that feature.

Sota does not use GPS for background tracking as part of mesh discovery. Live location sharing is used only when started by you and is shown with an ongoing notification.

### Camera and microphone

Sota uses the camera and microphone for features you start, such as voice calls, video calls, video notes, voice messages, walkie-talkie, QR scanning, photos, and videos.

Sota does not use the camera or microphone for advertising.

### Bluetooth, Wi-Fi, and nearby connectivity

Sota uses Bluetooth, BLE, Wi-Fi Direct, Wi-Fi Aware, local network, and internet connectivity to discover nearby users, route messages, maintain mesh connections, make calls, and transfer media.

These features are central to Sota's purpose of communication when internet access is unavailable, unreliable, or blocked.

### Media library and file access

Sota may request access to photos, videos, audio, and files so you can send media, save received media, create stories, export chats, or create and restore encrypted backups.

When Android provides a system picker, photo picker, or document picker, Sota uses the item you selected and the temporary or persistent URI access granted by Android. The Google Play release is intended to avoid broad media-library permissions unless a future build adds a verified core workflow that cannot be implemented through user-selected picker access.

### Backups and recovery

Sota supports recovery phrases, encrypted backup export/import, backup to Saved Messages, and device-pairing restore flows.

Backup files may contain your identity, chats, settings, and selected media categories, depending on the backup options you choose. Encrypted backups are protected by the password you set. Sota cannot reset that password for you.

## Server and Relay Processing

The Sota server components may perform bootstrap, relay, DHT, temporary mailbox, offline inbox, and TURN-related functions.

The server may process:

- public node IDs and peer reachability records;
- IP addresses and ports needed for connectivity;
- temporary routing metadata;
- public profile or status records that the app publishes;
- temporary offline delivery records;
- relay payloads needed to deliver traffic between peers;
- anti-abuse metadata such as timestamps, nonces, proof-of-work checks, and rate-limit counters.

Offline delivery records are bounded and temporary. The server code limits offline record lifetime to a maximum of 30 days, and temporary mailbox items are short-lived.

The server is not a password account server and does not have the ability to recover your private key or recovery phrase.

## Data Sharing

Sota shares information only as needed to provide messenger features:

- with the people or groups you communicate with;
- with nearby peers when using mesh communication;
- with Sota relay/bootstrap infrastructure when routing, discovery, TURN, or offline delivery is needed;
- with Android system components when you use permissions, notifications, media picker, camera, microphone, Bluetooth, Wi-Fi, storage, or location features.

Sota does not sell your personal data.

Sota does not use advertising SDKs, advertising ID, or third-party analytics SDKs in the reviewed local codebase.

## Reports and Safety Requests

If you report abuse, request moderation review, or contact support, you may choose to send information such as your email address, Sota public ID, another user's Sota ID, group or channel identifiers, public handles, timestamps, message details, screenshots, exported evidence, and a description of the issue.

This information is used to review the report, respond to you, prevent abuse, comply with law, and protect Sota infrastructure. Depending on the report, the developer may restrict public directory entries, relay/offline delivery, bootstrap/DHT participation, or other infrastructure access for abusive Sota IDs, groups, channels, handles, or traffic patterns.

## Data Security

Sota uses cryptographic identity, Android Keystore-backed local protection, encrypted local storage mechanisms, transport protection, request signatures, and anti-replay checks where applicable in the protocol.

No system is perfect. Sota is in beta, and reliability and security properties may evolve as the app is tested.

## Retention and Deletion

Data stored on your device remains until you delete it, reset app data, delete chats, remove media, uninstall Sota, or restore from a backup that replaces local data.

Sota includes a "Reset all data" option that deletes local chats, contacts, media, and identity keys from the device.

Temporary server-side delivery records expire or may be deleted after successful retrieval, depending on the delivery mechanism. Some information that you sent to other users may remain on their devices unless they delete it.

For deletion requests involving server-side data, contact wmcurrency@zohomail.eu and include your Sota public ID if you can access it.

## Account Recovery Limitation

Sota does not use a phone number or email account login. Your identity is based on cryptographic keys.

If your private key, recovery phrase, encrypted backup, and paired-device backup are all lost, the developer cannot restore your identity. You can create a new identity, but other users will see it as a different Sota ID.

## Children

Sota is not intended for children. Do not use Sota if you are not old enough to consent to digital communication services in your country or region.

## Changes

This Privacy Policy may be updated as Sota changes. The latest version should be available through the public policy URL used in Google Play.

## Contact

Mykola Tolochko  
wmcurrency@zohomail.eu
