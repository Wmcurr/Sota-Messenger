# Sota legal and Google Play preparation

This folder contains the working legal and policy documents for publishing Sota on Google Play.

Developer:

- Name: Mykola Tolochko
- Contact: wmcurrency@zohomail.eu
- App: Sota
- Android package: com.wmcurr.sota
- Last reviewed against the local codebase: May 21, 2026

Recommended publishing flow:

1. Review and edit these Markdown files until the technical statements match the release build.
2. Publish the public-facing pages through GitHub Pages, not a raw branch URL.
3. Put the GitHub Pages URLs into Play Console.
4. Keep Play Console declarations consistent with these documents and the app behavior.

Suggested public URLs once GitHub Pages is enabled:

- Privacy Policy: `https://wmcurr.github.io/sota/privacy.html`
- Terms of Use: `https://wmcurr.github.io/sota/terms.html`
- Account and Data Deletion: `https://wmcurr.github.io/sota/delete-data.html`
- Permissions: `https://wmcurr.github.io/sota/permissions.html`

Important implementation notes checked in the code:

- Sota does not use phone-number or email registration.
- A cryptographic identity is generated on-device.
- Recovery is possible only with the user's own 24-word recovery phrase, encrypted backup, or device pairing flow.
- The developer cannot reset, recover, or replace a lost private key.
- The server folder implements bootstrap, relay, temporary mailbox, DHT, and offline inbox behavior; it is not a classic account server.
- Location permission is used both for user-initiated location sharing and nearby device discovery needed for offline mesh communication.
- Foreground services are used for connected-device mesh transport, active call media capture, and live location sharing.

