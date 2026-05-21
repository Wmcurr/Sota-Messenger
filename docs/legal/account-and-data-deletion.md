# Account and Data Deletion

Last updated: May 21, 2026

This page explains how Sota users can delete local app data and request deletion of server-side data associated with their Sota identity.

Developer contact: wmcurrency@zohomail.eu

## Does Sota Have Traditional Accounts?

Sota does not use phone-number, email, username/password, or social-login account registration.

Instead, Sota creates a cryptographic identity on your device. Your public key, also called your Sota ID or node ID, is used as your identity in the messenger.

Because the identity is controlled by your private key, Sota cannot reset your password or recover your identity if you lose your device keys and do not have a recovery phrase or encrypted backup.

## Delete Data From Your Device

To delete local Sota data from your device:

1. Open Sota.
2. Open Settings.
3. Open Privacy.
4. Choose "Reset all data".
5. Confirm the reset.

This deletes local chats, contacts, media, settings, and identity keys from that device.

You can also uninstall Sota or clear app data from Android system settings.

## Request Server-Side Deletion

To request deletion of server-side data associated with your Sota identity, email:

wmcurrency@zohomail.eu

Include:

- your Sota public ID, if you can access it;
- a short statement that you want server-side Sota data deleted;
- any additional information needed to identify the relevant relay/bootstrap environment, if you used a test server.

Because Sota does not use email or phone-number login, the public Sota ID is the practical identifier for server-side deletion requests.

## What Can Be Deleted

Depending on what exists on the server at the time of the request, deletion may include:

- public peer reachability records;
- public profile or status records;
- temporary offline inbox records;
- temporary relay mailbox records;
- server-side routing metadata linked to the Sota ID.

Sota server-side records are designed to be temporary or bounded. For example, the reviewed server code limits offline message lifetime to a maximum of 30 days and uses short-lived temporary mailbox entries.

## What Cannot Be Deleted By The Developer

The developer cannot delete data from:

- another user's device;
- backups you created and stored outside Sota;
- screenshots, exports, or copies made by recipients;
- third-party storage locations chosen by you;
- local files that remain on a device the developer cannot access.

The developer also cannot recover or delete a lost private key if you no longer have access to it.

## Expected Processing Time

Deletion requests are normally reviewed within 30 days.

Some temporary server records may expire automatically before the request is processed.

