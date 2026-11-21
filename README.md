# AOD Theme Manager

Pick your favourite **20 Always-On Display themes** and build a custom backup file for **HyperOS** that you can restore from the system settings. 
Stays permanent, no root required

> I am not affiliated with Xiaomi. Use at your own risk, and keep your original backup safe.

## Screenshots

<!--
  Add your screenshots to a folder named "screenshots" in this repository,
  then replace the placeholder filenames below. Delete this comment when done.
-->

<img width="200" height="400" alt="IMG_20261120_222953 (5)" src="https://github.com/user-attachments/assets/15ca7d8d-cc81-4197-8f3e-5db28cc32015" />
<img width="200" height="400" alt="IMG_20261120_222924 (5)" src="https://github.com/user-attachments/assets/7c2f04c9-1c46-4668-9f1e-42c34b1ba09c" />
<img width="200" height="400" alt="IMG_20261120_222850 (5)" src="https://github.com/user-attachments/assets/a45c8d56-ce77-42e6-af32-11abc86eb56a" />

## Features

- Browse all themes with previews, downloaded from this repository's GitHub release
- Pick exactly 20 themes, then tap the bolt button to generate the backup
- Themes download only when you select them, with a live progress bar
- Downloaded themes are kept in **Yours**, so you can reuse them later
- Upload your own `.aodbackup` files (up to 15 at a time, checked before they are added)
- Delete themes from your library, with a confirmation
- Dark and light mode, and an option to hide theme names
- Check for new themes and app updates from Settings

## Requirements

- A phone running **HyperOS** (Xiaomi, Redmi or POCO)
- Android 11 or newer

## Install

1. Open the [Releases](../../releases) page.
2. Download the latest `.apk` and install it.
3. If Android asks, allow installing apps from your browser or file manager.

## How to use

**First time only**

1. Open the app. The setup guide appears.
2. Download the restore zip from the guide and extract the `20240405` folder to `MIUI/backup/AllBackup`.
3. The `20240405` folder **must** contain `descript.xml` from the restore zip, or the backup will not restore.
4. In your phone's restore settings, select *Mobile device* and restore the `February 19 10:48am` file.
5. In the guide, choose the folder `MIUI/backup/AllBackup/20240405` so the app can save backups straight into it.

**Every time**

1. Open **Gallery** and select 20 themes.
2. Tap the bolt button. Progress shows in **Yours**.
3. When it says the backup is ready, open your phone's restore settings and restore it.

If you skipped the folder step, the backup is saved to **Downloads**. Copy it into `MIUI/backup/AllBackup/20240405` yourself. You can change the folder any time in **Settings > Backup folder**.

## Build from source

1. Open the project in Android Studio (JDK 17).
2. Put your original `apps` folder in `tools/input/` and run:
   ```
   python tools/make_reference.py
   ```
   This creates `app/src/main/assets/reference.tar`, which the app needs to build backups.
3. Put the first-time restore zip in `app/src/main/assets/restore_pack/`.
4. Build and run. Pushing to GitHub also builds a debug APK through GitHub Actions.

## Adding themes to the library

Upload new `.aodbackup` files to the `themes` release, regenerate `themes_manifest.json` with `build_manifest.py`, and push it. The app picks up new themes when it launches or when you tap **Check for new themes**.

Project files coming soon!
