# Google Play Data Safety Notes

Last updated: May 21, 2026

This is an internal checklist for completing Google Play's Data safety form. It is not a public privacy policy.

Google requires the Data safety form to match the real app behavior, including SDKs and server-side processing. Review again before submitting a production build.

## App Identity Model

Sota does not use phone number, email, username/password, or social-login registration.

Sota creates a cryptographic identity on the device. The public key/node ID is used as the user's Sota identifier. The private key remains on the user's device unless the user exports an encrypted backup, uses a recovery phrase, or pairs another device.

## Likely Data Types To Declare

### Personal info

Display name or nickname:

- Collected/shared: Yes, if the user sets a profile name.
- Purpose: app functionality, user communications.
- Required: optional for profile customization, but a local/default identity may still exist.

Email address:

- App registration: No.
- Support requests: Yes, if the user emails support outside the app.

### Messages

Messages, media messages, voice messages, files, call signaling, stories, groups, channels:

- Collected/transmitted: Yes, as part of messenger functionality.
- Purpose: app functionality.
- Sharing: with selected recipients and Sota service infrastructure as needed for routing/delivery.
- Notes: do not claim server cannot access every possible payload unless the exact release has been verified end-to-end for every message type and transport.

### Photos and videos

- Used when the user selects, captures, sends, receives, saves, edits, or posts media.
- Purpose: app functionality.
- Optional: user initiated.

### Audio files and voice/audio

- Used for voice messages, calls, walkie-talkie, voice channels, media files, and audio playback.
- Purpose: app functionality.
- Optional: user initiated, except active call features require microphone when used.

### Location

Precise and approximate location:

- Used for current location sharing, live location sharing, and Android-required nearby device discovery for mesh.
- Purpose: app functionality.
- Required: required for mesh/nearby discovery and live location features when used.
- Important wording: Sota does not use GPS for background tracking as part of mesh discovery.

### Device or other IDs

Sota public key/node ID:

- Used as the user's Sota identity and routing identifier.
- Purpose: app functionality, security, fraud/abuse prevention, peer discovery.

Do not declare Android Advertising ID unless a future build adds it. The reviewed code did not show AdMob, Firebase Analytics, Crashlytics, or AD_ID usage.

### App activity and diagnostics

If production builds send crash logs, analytics, diagnostics, or server logs off-device, declare them. The reviewed local codebase does not show third-party analytics SDKs, but server logs may include operational connectivity events and IP addresses.

## Data Sharing Notes

Sota transfers user data:

- to selected recipients;
- to nearby mesh peers as needed for routing;
- to Sota relay/bootstrap infrastructure when needed for connectivity, routing, discovery, TURN, or offline delivery.

Sota should not be marked as selling user data.

## Encryption In Transit

Declare encryption in transit only for the exact flows that are protected in the release.

The reviewed server code includes signed requests, sealed relay envelopes, and temporary offline records. The app also uses cryptographic identity and encrypted local storage mechanisms. However, before making a broad "end-to-end encrypted" statement in Google Play, verify each content type and transport path in the release build:

- text messages;
- media messages;
- files;
- calls;
- walkie-talkie;
- stories;
- group/channel control packets;
- relay fallback;
- offline inbox;
- mesh BLE/Wi-Fi paths.

## Data Deletion

The app has "Reset all data" for local deletion. This deletes local chats, contacts, media, and identity keys.

Because Sota uses a cryptographic identity rather than a central login account, the external deletion page should explain:

- there is no phone/email account;
- server-side deletion requests can be sent by email;
- the user should include their Sota public ID;
- data already delivered to other users' devices cannot be deleted by the developer.

## Policy Links To Prepare

Required or recommended public URLs:

- Privacy Policy
- Terms of Use
- Account and Data Deletion
- Permissions Explanation

Use GitHub Pages or another stable public web page. Avoid private repositories, temporary links, raw files, or PDFs.

