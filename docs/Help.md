# BentoDrop Help

In the app, choose **Help → Bento Drop Help** or press Command-?.

## Contents

- [Welcome](#welcome)
- [Transfer a File](#transfer-a-file)
- [System Requirements](#requirements)
- [Sample Formats](#formats)
- [Getting Started](#getting-started)
- [Sample Sync History](#library)
- [Queue](#queue)
- [Card](#card)
- [Sample Sync](#transfer)
- [Names and Folders](#naming)
- [Keyboard Shortcuts](#shortcuts)
- [Troubleshooting](#troubleshooting)

<a id="welcome"></a>

## Welcome

BentoDrop prepares audio samples on your Mac and transfers them to a 1010music Bento. Open **New Sample Sync…** to choose files or folders, review exclusions, and select a destination under `UserSamples`. Every transferred sample is verified as 48 kHz, 24-bit integer PCM WAV, mono or stereo.

- **Sample Sync History** keeps named jobs, results and exportable logs. Select a job to see its log, or reprocess it from the original files.
- **Queue** shows the next transfer. Preview, inspect or remove individual entries before running.
- **Card** lets you preview, move, rename and delete items under `UserSamples`. It also provides backup, restore, firmware and default card setup tools.

BentoDrop does not build presets, trim or normalize samples, or open proprietary sampler formats. See **Sample Formats** for the input list and **Transfer a File** for the full workflow.

<a id="transfer-a-file"></a>

## Transfer a File

Do this in order. Put the Bento in **SD Reader Mode** and wait for its icon on the Desktop **before** you open Bento Drop. The app can only see the card after macOS has mounted it.

### 1. Put the Bento in SD Reader Mode

Music on the unit stops. Unsaved project changes can be lost, so save first.

1. Save the project on the Bento if you want to keep your work.
2. Connect a USB-C **data** cable from the Bento **Device** port to the Mac. A charge-only cable will not mount the card. If the Bento needs extra power, use the USB-C power/data splitter that shipped with it.
3. Press **PROJ** to open the Project browser.
4. Tap **Menu** (the three lines), then **SD Reader Mode**.
5. If Bento asks about unsaved changes, choose Save or Don’t Save. Cancel stays out of SD Reader Mode.
6. The Bento screen shows **bento microSD File Management Mode**. Leave it there. Do not press Back yet.

### 2. Wait for the card icon on the Desktop

Wait until the Bento card appears as a drive **on the Desktop**. The icon is often named Bento or the card’s volume name. You may also see it in the Finder sidebar.

> Do not launch Bento Drop until that icon is there. A large card can take a minute or more.

If nothing appears:

- Try a different USB-C data cable, and plug into the Mac, not only a hub.
- In Finder → Settings → General, turn on **External disks** so drives show on the Desktop.
- Stay in SD Reader Mode on the Bento. Connecting the cable after you enter the mode is fine; still wait for the icon.

You can also put the microSD card in a USB reader. Wait for that reader’s icon on the Desktop before you open Bento Drop.

### 3. Launch Bento Drop

Open Bento Drop only after the Desktop icon is visible. The Card column should list the volume.

### 4. Grant Access

Choose **Grant Access** and select the Bento volume (the same drive as the Desktop icon). Transfer stays off until this is done. You only need to do this once per card unless you revoke access.

### 5. Set up a sample sync

Open **New Sample Sync…** in the Queue, or press Command-Return. Choose a destination under `UserSamples`, then add files or folders. The wizard lists files it can't queue, including unsupported audio and samples longer than 30 seconds.

Choose **Skip existing** or **Overwrite existing** for this job. Review the destination paths before running. **Clear Queue** discards pending entries without deleting any files.

### 6. Run and review

Choose **Run Sample Sync**. Bento Drop writes 48 kHz 24-bit WAV into `UserSamples`. Keep the card connected until the job finishes.

Select the run in **Sample Sync History** to see the result and the transferred, skipped, excluded, or failed files. Transferred and skipped entries clear from the Queue; failed or unattempted entries remain available for retry.

### 7. Eject, then leave SD Reader Mode

1. In Bento Drop, **Eject** the card when the batch is finished. Use **Eject** on the Card.
2. Confirm the Desktop icon is gone.
3. On the Bento, press **Back** (`<`) to leave SD Reader Mode. The unit reboots and opens the last project.

Then disconnect the cable if you want. Load the new WAVs from `UserSamples` on the Bento.

<a id="requirements"></a>

## System Requirements

### Computer

| Requirement | Detail |
| --- | --- |
| Operating system | macOS 15 Sequoia or later |
| Processor | Apple silicon or Intel Mac that can run macOS 15 |
| Display | 1100 × 640 points or larger. 1280 × 760 is comfortable. |
| Memory | 8 GB recommended when converting long stereo files |
| Disk | Free space for temporary WAV files during transfer |

Bento Drop is a native Mac app. It is sandboxed. You grant access to the selected source locations, backup folder and card. It does not request full-disk access.

### Bento hardware

You need one of the following:

- A 1010music Bento in **SD Reader Mode**, connected with a USB-C data cable to the Device port, with its drive icon on the Desktop.
- A Bento microSD card in a USB card reader, with that reader’s icon on the Desktop.

> Do not launch Bento Drop until the icon is there. See **Transfer a File**.

The volume is treated as a Bento card when the card root contains `Patches`, `UserPatches`, `Projects`, `UserSamples`, `bento1.bin`, or `bento2.bin`. The volume name is ignored, because the card can be renamed.

Transfer stays off until you choose **Grant Access** and pick that volume.

### Bento sample rules this app follows

These come from the Bento user manual. Files written by Bento Drop meet them.

| Rule | Limit |
| --- | --- |
| File type | WAV only on the card |
| Channels | 1 (mono) or 2 (stereo) |
| Bit depth | 16, 24, or 32-bit integer. This app always writes 24-bit. |
| Sample rate | Up to 48 kHz. This app always writes 48 kHz. |
| Path length | Under 256 characters, including `UserSamples/` |
| File name | No `" / \ ? * < > : \|` |

Bento can load samples up to 4 GB on Loop and One-shot tracks. Granular tracks use the first 30 seconds. Bento Drop queues and converts samples **up to 30 seconds**. Longer files are excluded from sync.

### Version

Bento Drop 1.0. Category: Music.

<a id="formats"></a>

## Sample Formats

Bento only plays WAV. Bento Drop converts other pack formats to that WAV on transfer.

### What is written to the card

Every transferred file becomes:

- Extension `.wav`
- 48 kHz
- 24-bit integer PCM (not float)
- 1 channel if the source is mono, 2 if the source is stereo
- More than 2 channels mixed down to stereo

The converted file is checked before copy. If it is not 48 kHz 24-bit integer WAV, that row fails and nothing is written for that file.

### Formats you can transfer

The wizard recognises the extensions below. The actual audio codec must be readable by macOS, and the sample must be nonempty and no longer than 30 seconds. An extension alone does not guarantee conversion.

| Format | Extensions | Typical use |
| --- | --- | --- |
| WAV | `.wav`, `.wave` | Most sample packs. Any rate or bit depth the Mac can read. |
| AIFF | `.aiff`, `.aif`, `.aifc` | Logic and older Mac packs |
| CAF | `.caf` | Apple Core Audio files |
| FLAC | `.flac` | Lossless packs |
| MPEG audio | `.mp3`, `.mp2` | Compressed packs |
| AAC | `.m4a`, `.m4b`, `.aac` | Compressed packs |
| MPEG-4 audio | `.mp4` | Audio-only MP4 |
| 3GPP | `.3gp` | Mobile recordings |
| NeXT / Sun | `.au`, `.snd` | Older studio files |
| Sound Designer II | `.sd2` | Older Pro Tools sessions |

The test suite exercises WAV, AIFF, CAF, FLAC and AAC conversion. Other listed extensions are accepted for inspection; support depends on the encoding and macOS decoder.

### Formats that appear but may not queue

The wizard recognises these extensions but excludes files macOS cannot decode.

| Format | Extensions | Notes |
| --- | --- | --- |
| Ogg Vorbis | `.ogg`, `.oga` | Common in some free packs. Decoder support varies. |
| Opus | `.opus` | Decoder support varies. |

### Formats this app cannot convert

Leave these in their original tools, or export WAV first.

- Native Instruments Kontakt `.nki`, `.ncw`
- Propellerhead Recycle `.rex`, `.rx2`
- Sampler banks: `.sf2`, `.sfz` as instruments (individual WAVs inside a folder are fine)
- Ableton, Logic, or other project files
- Video files that are not audio-only

### Duration

| Length | What happens |
| --- | --- |
| More than 0, up to 30 seconds | Can be queued if readable |
| Longer than 30 seconds | Excluded with a duration warning. |

### After conversion

The Bento name always ends in `.wav`. The wizard shows the destination path under `UserSamples` before the run. The written bytes are verified after staging.

<a id="getting-started"></a>

## Getting Started

1. Save your Bento project, then connect it with a USB-C data cable and enter **PROJ → Menu → SD Reader Mode**. You can also use a microSD card reader.
2. Wait for the card to mount in macOS, then launch BentoDrop.
3. Select the card and choose **Card → Set Up BentoDrop…** to grant read/write access to the card root and save a preferred backup folder. You can also grant card access separately.
4. Open **New Sample Sync…**. Name the job, select a destination, and choose **Add Files or Folders…**.
5. Review exclusions and choose **Skip existing** or **Overwrite existing**. Click **Run Sample Sync**.
6. Check **Sample Sync History** for the result, then eject the card before leaving SD Reader Mode.

The Queue starts empty on each launch. Job history persists.

<a id="library"></a>

## Sample Sync History

The left pane lists previous sync jobs by name, date, card, and outcome. Older unnamed jobs display as **Sample Sync**.

- Click a job to see its **Sync Log**, including transferred, skipped, excluded and failed files. **Save Log…** exports a plain-text copy.
- Choose **Reprocess Job…** from the log toolbar or the job’s right-click menu to review a new run with the original paths and conflict policy. Clear the current queue first. BentoDrop may ask for access to the original files or folders again; missing or unreadable originals are listed as exclusions.
- Right-click a job and choose **Delete Job** to remove its history entry. This leaves source and card files untouched.

Each rerun adds its own history entry. Choose new source files and folders in the **New Sample Sync…** wizard, not in the history pane.

<a id="queue"></a>

## Queue

The middle pane shows samples waiting to be written to the Bento card. Open **New Sample Sync…** to add files or folders and review the paths before running. You can also drop audio files from Finder onto the Queue.

- **Play Preview** plays a queued source file. **File Info** shows its details.
- **Remove from Queue** removes selected entries. **Clear Queue** removes all entries. Neither action deletes files.
- After a sync, transferred and skipped entries clear automatically. Failed or unattempted entries remain for retry during the current session.
- The wand icon checks for Bento firmware updates.

A conflict means the destination already exists. Choose **Skip existing** or **Overwrite existing** for the entire run in the wizard.

<a id="card"></a>

## Card

The right column is the Card: the granted Bento volume, rooted at `UserSamples`.

Put the Bento in **SD Reader Mode** and wait for the card icon on the Desktop before you launch Bento Drop. See **Transfer a File**. The Card picker stays empty until macOS has mounted that drive.

### Choosing a volume

If more than one Bento volume is mounted, use the Card picker. The last used card is remembered.

**Grant Access** opens a folder panel pointed at the volume. Select the root of that card. Another drive or a subfolder is rejected. If an older grant selected a subfolder, grant access again to the card root.

### Setup and file management

**Card → Set Up BentoDrop…** remembers approved access to the card root and a preferred backup folder. The backup folder is offered for regular and firmware backups.

In the Card pane, right-click a sample for **Play Preview** or **Stop Preview**. Drag an item onto a folder to move it, or right-click for **Move to Folder**, **Rename…**, or **Delete…**. Moves and renames do not overwrite. Confirmed deletion permanently removes the item and any folder contents. These actions are limited to `UserSamples`.

### Folders

- The tree updates after transfer.
- **New Folder** creates a folder or nested path under `UserSamples`.
- Select a folder to send the next transfer there. The Queue Folder field updates to match.

Sample transfers write under `UserSamples`. Restore can replace the selected card folders and firmware. The firmware wizard updates only `bento1.bin` and `bento2.bin`, leaving samples, projects and patches in place.

### Backup

**Backup** copies card files into a folder you choose. Bin files at the card root (`bento1.bin` and any other `.bin`) are always included. You then choose:

- **Factory Patches** — the factory `Patches` folder
- **User Patches** — `UserPatches` and `Projects`
- **All User Samples** — every file under `UserSamples`

1. Put the Bento in SD Reader Mode and wait for the Desktop icon.
2. Launch Bento Drop and Grant Access.
3. Choose **Actions → Back Up Card…** in the Card pane or **Card → Back Up Card…** in the menu bar.
4. Turn on Factory Patches, User Patches, and/or All User Samples, then pick a destination. Bento Drop creates `Bento Backup` plus the date and time.
5. A Backup window shows each file as it copies. Cancel stops the copy and removes the incomplete folder.

Keep that folder if you reformat the card or update firmware.

### Restore

**Restore** copies a Bento Backup folder back onto the granted card. Files with the same names are replaced. Bin files are always restored. You then choose Factory Patches, User Patches, and/or All User Samples.

1. Grant Access to the card.
2. Choose Restore, then pick the `Bento Backup` folder from the date you saved.
3. A Restore window shows each file as it copies. Cancel stops remaining files. Files already copied stay.

Turn on Factory Patches only if that backup includes the factory `Patches` folder. Older backups may not.

### Format

1010music Support asks you to format the microSD card with **SD Card Formatter** from the SD Association, not Disk Utility.

**Format** opens that app if it is installed. If it is not, Bento Drop opens the SD Association download page.

Backup first, including Factory Patches. Format erases the card.

1. Backup the card.
2. Choose Format and open SD Card Formatter.
3. In SD Card Formatter, pick the Bento volume and format it. Use the tool’s Quick format.
4. When the card remounts, Grant Access again, then Restore your backup.

### Firmware

Bento Drop reads `bento1.bin` on the card and checks the official Bento version on the 1010music downloads page.

If the card files are older, the update wizard opens when other card operations have finished. Close the wizard to defer the update. Reopen it from **Card → Check for Firmware Updates…**, the Queue wand, or the update status button. HTTP 503 responses are retried up to three times with a two-second pause.

1. **Backup:** choose a folder on your Mac or a different drive. Choose **Full card** to copy and verify regular card files, including custom files and existing firmware, or **Firmware files only** to save just the existing firmware files at the card root. The firmware-only option does not back up samples, projects, or patches. It skips known macOS system folders at the card root, such as the Spotlight index, Trash, and filesystem event logs. This backup is required. Other unreadable files or folders, links, and special files stop the backup with an error. This is a file backup, not a disk image.
2. **Download:** download and validate the official release inside Bento Drop. Failed or cancelled downloads can be retried without changing the card.
3. **Write:** choose **Write Firmware**. Keep the card connected while both firmware files are staged, written and verified. Recovery copies are retained until completion. Other card operations are unavailable while the wizard is open.
4. **Finish:** choose **Eject Card**. With Bento powered off, ensure the card is inserted and connect external power. Hold the power button until the Bootloader appears, press **REC**, and wait for Bento to restart. Do not remove power or the card during installation. Check the installed version with **PROJ**.

**Firmware ready on card** confirms the Mac-side preparation, not installation on Bento. The wizard links to the official instructions and release notes. Factory content updates are separate.

If a completed write leaves an update record, **Verify and Finish** checks the firmware hashes and removes the record without rewriting the firmware. If a write is interrupted, reconnect the same card and use **Recover Previous Update** before using it in Bento. Recovery can restore saved originals or finish cleanup of a verified update. Keep your verified backup; if recovery files are damaged or missing, use that backup to restore the firmware files before proceeding.

**PROJ** on the Bento shows the version installed on the hardware. The files on the card are what you would install next.

Card → Check for Firmware Updates… runs the same check again.

### Eject

Eject is available when nothing is converting or copying. After a successful batch, the app offers to eject.

Wait until the Desktop icon is gone, then press Back (`<`) on the Bento to leave SD Reader Mode.

> Never unplug the cable or leave SD Reader Mode while a row says Converting or Copying.


### Create a Default SD Card

Choose **Card → Create Default SD Card…**. Select the root of your external SD card. If it contains files, choose a folder on another drive for a complete verified backup.

Prepare the downloads before formatting. BentoDrop checks the official downloads page for the latest firmware and factory patches. It retains a verified factory archive in its Application Support folder, reuses it on later runs, and checks for factory updates only when this wizard prepares downloads. A changed revision or a missing/damaged archive triggers a replacement download. An unavailable server stops preparation so you can retry before erasing the card. Allow roughly 6 GB on your Mac for the current factory download and 7 GB on the card for its contents; an update temporarily needs room for both cached revisions.

Confirm that formatting erases the card, then open **SD Card Formatter**. In the official formatter, check the card name and capacity, choose **Quick Format**, and wait for its success message. Return to BentoDrop, confirm success, and select the same formatted card again. BentoDrop checks its device/capacity and requires an empty destination; internal disks and subfolders are rejected.

Choose **Install to SD Card**. Keep the card connected while patches, firmware and user folders are written and verified. If interrupted, retry the installation. You can also reopen this wizard and select the unfinished card; matching setup files are resumed without formatting again. Changed or unrelated files stop the retry so they can be preserved. A different downloaded revision cannot resume an old installation automatically.

After verification, eject the card and follow the wizard's Bento bootloader instructions. The wizard prepares firmware files on the SD card; Bento itself performs the firmware update. SD Formatter runs separately: closing BentoDrop does not cancel a format already running there.


#### Restore safety

Choose a backup outside the destination card. BentoDrop rejects overlapping folders, aliases to the destination, and unsafe links. Each file is copied to a temporary file on the card and verified before replacing the destination. Keep the backup: a cancelled or failed restore can leave a mix of completed and untouched files. The whole restore is not one atomic operation.

<a id="transfer"></a>

## Sample Sync

Open **New Sample Sync…**, give the job a name, select the destination, then add files or folders. Review the destination paths and exclusions. Unsupported, unreadable, empty or over-length samples are excluded when detected during review; files that fail later are reported in the log.

- **Skip existing** leaves matching card files unchanged and transfers new samples.
- **Overwrite existing** replaces matching destination files after the new sample has been converted and verified.

Click **Run Sample Sync**. The progress dialog shows the current filename, a file count and the white music note moving toward the studio. Keep the card connected until the job finishes. Cancelling stops remaining work; files already transferred stay on the card.

BentoDrop validates the converted WAV before copying and verifies the written bytes. Check the job’s log for its outcome and use the Card pane to eject safely.

<a id="naming"></a>

## Names and Folders

Bento rejects some characters and long paths. Bento Drop fixes names on the Queue so Load All still works.

### Forbidden characters

These become `_`:

`" / \ ? * < > : |`

Curly quotes are treated as `"`. Spaces stay. The file on the card always ends in `.wav`.

### Path length

The full path including `UserSamples/` must be under 256 characters. If it would be longer, the file name is shortened. Folder names are not shortened.

### Collisions

If two files would land on the same path, the second becomes `Name-2.wav`, then `Name-3.wav`.

If the name would be empty after cleaning, the file is called `sample.wav`.

### Multisample names

If the file already looks like Bento Load All, that pattern is kept:

- `name-048-066` (note and velocity)
- `name_048_066`
- Four-number velocity range form

### Where files go

Destination is under `UserSamples` on the selected card.

- A queued destination such as `Kits/808s/Kick.wav` becomes `UserSamples/Kits/808s/Kick.wav`.
- The Queue **Folder** field wraps files in a project folder, for example `UserSamples/MyKit/Kick.wav`.
- Selecting a Card folder sets that destination for waiting items.

Create nested folders with **New Folder** or by typing `Project/Sub` in Folder.

<a id="shortcuts"></a>

## Keyboard Shortcuts

| Shortcut | Action |
| --- | --- |
| Command-Return | Open **New Sample Sync…** |
| Return | Open the sync wizard when the main workspace is active and you aren’t editing text |
| Escape | Dismiss the active dialog or cancel when offered |
| Command-? | Open BentoDrop Help |

Use the Queue’s right-click menu to preview, inspect or remove a source file. In the Card pane, right-click a sample to play it from the card, or right-click a file or folder to move, rename or delete it. Folder deletion requires confirmation.

<a id="troubleshooting"></a>

## Troubleshooting

### Transfer is disabled

- Grant Access on the Card and select the Bento volume.
- Add at least one file to the Queue.
- Wait until the current transfer finishes.

### Samples were excluded from a sync

Review **Excluded** in the wizard or in the saved job log. Check the file’s format, duration and access. If a historical job no longer has access, reselect the original files or folders when prompted.

### A file will not add to the Queue

- It may be longer than 30 seconds.
- The format may be Unknown (macOS could not open it). Export WAV or FLAC and add that.
- Add to Queue only includes files that can be queued.

### Files landed in the wrong folder

Select the Card folder, or set Folder on the Queue, **before** Transfer. Waiting items are retargeted when you change the folder. Already transferred files stay where they were written.

### Convert failed

The source may be damaged, or a format macOS cannot decode. Try opening it in QuickTime Player. If QuickTime cannot play it, Bento Drop cannot convert it.

### Preview will not play

The status line shows Couldn't preview and the file name. The source may be missing, or macOS cannot decode it. Try QuickTime Player.

### Card not listed

- Put the Bento in SD Reader Mode first (**PROJ** → Menu → **SD Reader Mode**). Leave that screen up.
- Wait for the card icon on the Desktop **before** you launch Bento Drop. A large card can take a minute or more.
- Use a USB-C data cable on the Device port, not a charge-only cable.
- In Finder → Settings → General, turn on External disks if you expect the icon on the Desktop.
- The card root should have `Patches`, `UserPatches`, `Projects`, `UserSamples`, `bento1.bin`, or `bento2.bin`. The volume name does not matter.
- Use Grant Access and pick the mounted volume even if listing failed.

### Previous queue on launch

The Queue is cleared when Bento Drop starts. Add the samples you want this time.

### Format will not open SD Card Formatter

Install SD Card Formatter from the SD Association. 1010music Support does not recommend Disk Utility. After you install it, choose Format again.

### Restore says that folder is not a Bento Backup

Pick the folder named `Bento Backup` plus the date, not the parent folder and not a random samples folder.

### Firmware check is wrong or missing

Bento Drop reads `bento1.bin` on the card, not the version burned into the hardware. Press **PROJ** on the Bento to see the installed version. If the card has no `bento1.bin`, the check cannot read a card version.

### Couldn't check firmware

BentoDrop reads the official version from the [1010music downloads page](https://1010music.com/downloads). HTTP 503 means the server is unavailable even if your Mac is online. BentoDrop retries three times, waiting two seconds between retries.

### Privacy and files on this Mac

Bookmarks, the Library index, and the saved queue live in:

`~/Library/Application Support/Bento Drop/`

The app only reads folders you add and the card you grant. Temporary convert files are deleted after copy. Firmware check reads the 1010music downloads page.

## Documentation licence

The written Help guide is licensed under [CC BY 4.0](../LICENSE.md).
