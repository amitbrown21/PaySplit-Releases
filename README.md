# EvenApp (PaySplit) — Android releases

Signed release builds of **EvenApp** (package `com.evenapp.app`).
The application source lives in a **private** repository; this repository only
publishes installable APKs.

## Download

Get the latest APK from the **[Releases](../../releases/latest)** page.

| Version | versionCode | File |
|---|---|---|
| 1.1.6 | 26 | `PaySplit-1.1.6-release.apk` (93.3 MB) |

Direct link:
`https://github.com/amitbrown21/PaySplit-Releases/releases/download/v1.1.6/PaySplit-1.1.6-release.apk`

## Install

**On the phone**

1. Download the `.apk` and open it.
2. If prompted, allow your browser/file manager to install unknown apps.
3. Tap **Install**. (You can disable that permission again afterwards.)

**Over adb**

```bash
adb install -r PaySplit-1.1.6-release.apk
```

## About the build

- Release-signed with the EvenApp key (`CN=PaySplit`). The signing certificate
  only changes if the app is reinstalled from a different source — updates over
  the top work normally.
- `minSdk 24` (Android 7.0+), `targetSdk 36`.
- The app is **online-only**: expenses need a connection; nothing is queued
  offline.
- The Play Store build uses the same code; this APK is the sideload equivalent.

## What's new in 1.1.6

- **Swipe group rows** in the groups list: swipe left to reveal **Delete** (a
  group where you're the only member) or **Leave** (any shared group). Both ask
  for confirmation, and leaving is blocked while you still have an outstanding
  balance.
- Deleting a group now removes its expenses and members with it — no orphaned
  expense rows left behind.
- Includes 1.1.5's balance fix and the 1.1.4 photo-picker fix.

### 1.1.5 highlights

- **Fixed:** group balances were calculated from only the first 50 expenses, so
  groups with more history showed a much smaller amount inside the group than in
  the groups list (e.g. 328 ILS vs 2,481 ILS). The group screen now reads every
  expense in the group.
- Includes the 1.1.4 photo-picker fix (group, profile and receipt photos).

### 1.1.4 highlights

- **Fixed:** the Android photo picker failed in release builds
  (`cannot be cast to ImagePickerOptions` / `NullPointerException`). Group
  photos, profile photos and expense receipts now open the picker and upload.
- Receipt uploads retry in place and report failure instead of silently queueing.
- Group expenses and the activity feed are paginated; deleting an expense offers
  a 5-second undo.
- Deleting a receipt now removes it from Storage and the database.
- Hebrew category detection fixed for `מלון`.
- Removed dead code and unused dependencies; TypeScript/lint clean.

## Previous versions

| Version | versionCode | Notes |
|---|---|---|
| 1.1.5 | 25 | Group balances read all expenses (pagination fix) |
| 1.1.4 | 24 | Photo picker fixed in release builds |
| 1.1.3 | 23 | Superseded — photo picker broken in release builds |
| 1.1.2 | 22 | Photo picker JS fix + hardening |
| 1.1.1 | 21 | Group navigation fix |

Only the latest build is published on this page.
