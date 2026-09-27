# Organizing Digital Photos Safely

Use this guide to turn photos scattered across phones, computers, memory cards,
cloud accounts, messaging apps, and old drives into one understandable,
protected collection. Work in stages; a large library does not need to be
finished in one weekend.

> [!IMPORTANT]
> Never reorganize the only copy of a photo collection. Before moving,
> renaming, deduplicating, or deleting anything, make a separate backup and
> verify that sample files open. Keep originals unchanged until the organized
> collection and its backups have been checked.

## The simple system

The finished collection uses four ideas:

1. **One primary library** is the collection you organize and browse.
2. **Verified backups** protect the library from device failure, mistakes,
   theft, and disasters.
3. **Date-based folders and filenames** remain understandable without a
   particular app.
4. **A small intake routine** prevents new photos from becoming another
   backlog.

Software may add search, face recognition, albums, ratings, or editing, but the
underlying files should remain portable and recoverable.

## Before you begin

### Choose safe storage roles

Write down which storage serves each role:

| Role | Purpose | Example choice | Requirement |
| --- | --- | --- | --- |
| Primary library | The organized working collection | Computer or external SSD | Enough free space for the consolidated library plus working room |
| Local backup | Fast recovery from mistakes or drive failure | Separate external drive | Not the same physical device as the primary library |
| Off-site backup | Recovery from theft, fire, or local damage | Encrypted cloud backup or a drive stored elsewhere | Independent of the primary and local backup |

Aim for at least three copies, on two different storage types or systems, with
one copy off-site. Synchronization is useful, but it is not automatically a
backup: a sync service may copy deletions or corruption to every device.
Confirm that it keeps version history or use a separate backup system.

### Estimate capacity

- [ ] Record the used space reported by each source.
- [ ] Allow for overlap: the same files may appear on several devices.
- [ ] Ensure the primary location can hold the estimated total with at least
      20% free space afterward.
- [ ] Ensure each backup destination can hold the complete library.
- [ ] Connect devices to power during long copies.
- [ ] Use a stable wired connection for large transfers when practical.

### Protect privacy

- [ ] Decide who may access the primary library and each backup.
- [ ] Enable device encryption and strong account authentication where
      available.
- [ ] Keep passwords and recovery codes in a password manager, not in photo
      folders or this repository.
- [ ] Do not upload private images to a service until its storage, sharing,
      retention, deletion, and machine-learning settings are understood.
- [ ] Treat location, face, school, home, medical, and identity-document
      images as sensitive.

## 1. Inventory every source

Do not start copying until the likely sources are listed. Include sources that
are currently unavailable so they are not silently forgotten.

| Source ID | Device, account, or media | Owner | Approximate years | Approximate size or count | Includes videos or RAW? | Existing backup? | Access confirmed? | Imported? | Notes |
| --- | --- | --- | --- | ---: | --- | --- | --- | --- | --- |
| S01 |  |  |  |  |  |  |  |  |  |

Check:

- Phones, tablets, current and old computers.
- Camera memory cards and internal camera storage.
- External drives, USB drives, optical discs, and network storage.
- Cloud photo libraries, file-storage accounts, and old online galleries.
- Messaging apps, social-network downloads, and email attachments.
- Shared family albums and folders owned by someone else.
- Scanned prints, slides, negatives, and photo CDs.
- Photographer deliveries, school photos, and event download links.
- Editing applications and export folders.
- Old backups, device migrations, and folders named `Pictures`, `DCIM`,
  `Camera Uploads`, `Downloads`, or `Desktop`.

For an unavailable device or account, record the blocker instead of marking it
complete.

## 2. Create a protected staging area

Create these top-level folders on the primary storage:

```text
Photo-Library/
├── 00-Inbox/
├── 01-Photos/
├── 02-Scans/
├── 03-Exports/
├── 90-Review/
└── 99-Quarantine/
```

- `00-Inbox/` receives untouched copies from each source.
- `01-Photos/` holds organized camera and phone originals.
- `02-Scans/` holds digitized prints, slides, and negatives.
- `03-Exports/` holds edited or resized files intended for viewing or sharing.
- `90-Review/` holds files that need a decision, such as unknown dates.
- `99-Quarantine/` temporarily holds suspected duplicates or rejected files.

Inside `00-Inbox/`, create one folder for each inventory source and import
date, for example:

```text
00-Inbox/2026-09-27_S01_Alex-Phone/
00-Inbox/2026-09-27_S02_Old-Laptop/
```

Copy files into the inbox; do not move them. Preserve the source device or
cloud copy until the full workflow is complete and backed up.

### Verify each copy

- [ ] Compare source and destination file counts and total sizes.
- [ ] Investigate differences caused by hidden files, cloud-only placeholders,
      unsupported formats, or interrupted transfers.
- [ ] Open photos and videos from the beginning, middle, and end of each copy.
- [ ] Include several large videos and uncommon formats in the sample.
- [ ] Use checksum or file-verification features when available, especially
      for memory cards, old drives, and irreplaceable files.
- [ ] Record the import and verification result in the progress log.

Do not erase a memory card or retire a device based only on a successful copy.
First verify the organized library and at least two backups.

## 3. Back up the untouched inbox

Before cleanup:

1. Back up the entire `Photo-Library/`, including `00-Inbox/`, to the local
   backup destination.
2. Create or update the off-site backup.
3. Confirm both jobs report success.
4. Restore several files from each backup to a temporary location.
5. Open the restored files, then remove only the temporary restore copies.

Record the date, backup destinations, restore sample, and result. A completed
backup job without a successful sample restore is not fully verified.

## 4. Separate files by type and purpose

Keep related media without mixing originals and disposable exports.

| Material | Destination | Handling |
| --- | --- | --- |
| Camera and phone originals | `01-Photos/` | Preserve original file and metadata |
| RAW plus camera JPEG | Same event folder | Keep both until the RAW workflow is understood |
| Videos and Live Photo companions | Same date/event folder as related photos | Keep companion files together |
| Scans | `02-Scans/` | Record known subject and approximate date |
| Edited master | Near the original or in an app-managed non-destructive catalog | Never overwrite the original |
| Share-ready resized export | `03-Exports/` | Regenerable; include purpose in the name |
| Screenshots, receipts, and reference images | `90-Review/` or a non-photo records system | Keep only when they have lasting value |
| Messaging and social-media downloads | `90-Review/` first | Expect stripped dates, reduced quality, and duplicates |

If editing software stores adjustments in a catalog, database, or sidecar
files, include those items in backups. Export important edited results to a
widely readable format as well.

## 5. Normalize dates before filing

Capture date is the best default for camera and phone images. Before relying
on it:

- [ ] Correct a camera clock only when the offset is known and can be applied
      consistently.
- [ ] Keep the original metadata or record the correction method.
- [ ] Use file modification date only with caution; downloads, copies, edits,
      and scans often change it.
- [ ] For scans, use the date the image depicts, not the scan date, when known.
- [ ] Represent uncertain dates honestly rather than inventing precision.

Use these date forms:

| Knowledge | Date form | Example |
| --- | --- | --- |
| Exact date | `YYYY-MM-DD` | `2019-08-17` |
| Known month | `YYYY-MM` | `1987-06` |
| Known year | `YYYY` | `1974` |
| Approximate year | `circa-YYYY` | `circa-1965` |
| Unknown | `date-unknown` | `date-unknown` |

Store uncertain files in a matching year/month folder when useful, or in
`90-Review/Unknown-Date/` until someone can identify them.

## 6. Use a portable folder structure

Organize originals primarily by date, with a short event or subject label:

```text
01-Photos/
├── 2024/
│   ├── 2024-01/
│   │   └── 2024-01-06_Winter-Walk/
│   └── 2024-07/
│       ├── 2024-07-03_to_2024-07-10_Lake-Holiday/
│       └── 2024-07-21_Family-Lunch/
└── date-unknown/
    └── date-unknown_Childhood-Photos/
```

Rules:

- Use four-digit years and two-digit months and days.
- Use one event folder for a multi-day event; include a date range when useful.
- Keep labels short, factual, and consistent.
- Use broad, non-sensitive labels when folder names might be visible in
  backups or shared locations.
- Do not create a folder for every person, place, and topic. One photo can
  involve several; albums and metadata handle those relationships better.
- Avoid very deep folder trees and operating-system-reserved characters such
  as `< > : " / \ | ? *`.

## 7. Rename files deterministically

Renaming is optional if an app manages a reliable catalog, but meaningful,
unique filenames make exported and restored files easier to understand.

Recommended pattern:

```text
YYYYMMDD-HHMMSS_source-sequence[_description].ext
```

Examples:

```text
20240721-132405_phoneA-0001.jpg
20240721-132405_phoneA-0002.jpg
20240721-132405_cameraB-0001.nef
19870600-000000_scan-001_grandparents-house.tif
date-unknown_scan-014_school-group.tif
```

Use these rules:

- Preserve the original extension and do not convert files merely to rename
  them.
- Use the capture timestamp where trustworthy.
- Add a stable source code and sequence number to prevent collisions when two
  devices create files at the same second.
- For a known year or month but unknown day, use the folder date form in
  preference to pretending the exact date is known. If a tool requires digits,
  document a placeholder such as `00` and never treat it as a real date.
- Keep a mapping from original name to new name until the project is complete.
- Test a rename rule on copied sample files before applying it to a batch.
- Confirm RAW/JPEG pairs, Live Photos, sidecars, subtitles, and video companion
  files remain associated.
- Never allow a batch tool to overwrite an existing file. Stop and resolve
  collisions explicitly.

## 8. Review duplicates safely

There are three different problems:

- **Exact duplicates** contain identical file data even if their names or
  folders differ. A checksum can identify them reliably.
- **Near-duplicates** may be resized, recompressed, edited, or metadata-altered
  versions of the same image.
- **Similar images** are separate captures of the same moment, such as a burst.
  They are not duplicates.

Use this sequence:

1. Back up and verify the untouched inbox.
2. Find exact duplicates by file content, not filename alone.
3. Select a keeper using provenance, completeness, location, and metadata.
   Identical bytes have identical image quality; prefer the copy in the
   intended source folder with the clearest history.
4. Move extra copies to a dated folder under `99-Quarantine/`; do not delete.
5. Review near-duplicates side by side at full size. Prefer the highest useful
   resolution, least compression, correct color, best metadata, and wanted
   edit, but keep the original plus an important edit.
6. Treat similar images as a creative selection task. Check focus, expression,
   composition, and whether each frame records something distinct.
7. Back up the organized result and wait through a review period before
   deleting quarantined files.

Automatic duplicate tools should produce a report or preview and must never
delete unattended. Similar filenames, file sizes, or thumbnails alone are not
safe proof of duplication.

## 9. Add useful, portable description

Folders answer **when**. Metadata and albums can answer **who, where, what, and
why**.

Prioritize:

- Correct capture date and time zone when known.
- Broad location, avoiding exact private addresses unless truly needed.
- Names or relationship labels for people, with their consent where
  appropriate.
- Event, activity, and subject keywords.
- A short caption for context that a future viewer would not know.
- Rating, favorite, reject, and color labels used consistently.
- Copyright or creator information for original work.

Prefer tools that write standard metadata into supported files or portable
sidecar files and can export albums and captions. Some cloud-only face labels,
albums, edits, and descriptions do not survive export. Test an export of a
small album and confirm filenames, dates, captions, keywords, edits, and video
companions survive before committing to a catalog.

Do not change embedded metadata across the whole library without a current
backup. Some formats are safer with sidecar metadata than in-place writes.

## 10. Curate without losing history

Use a simple rating system:

| Mark | Meaning | Action |
| --- | --- | --- |
| Reject | Accidental, unusable, or confirmed redundant | Move to quarantine after review |
| Unrated | Valid record not yet selected | Keep |
| 1 star | Worth retaining | Keep |
| 2 stars | Good representative image | Add to an event album |
| 3 stars | Favorite or print candidate | Include in highlights and backup checks |

Delete conservatively. A technically imperfect photo may be the only record of
a person, place, object, or event. Remove obvious accidents first: pocket
shots, black frames, unintended screenshots, and unusable test captures.

For edited photos:

- Preserve the untouched original.
- Prefer non-destructive editing where available.
- Keep an editable master when substantial work cannot be reproduced.
- Export a high-quality, widely readable final version for important images.
- Include an edit or purpose suffix such as `_edit`, `_print`, or `_web`;
  never present an export as the camera original.

## 11. Handle special sources

### Screenshots and reference images

Review separately from personal photography. Move lasting records to the
appropriate household, project, or reference system. Delete temporary
screenshots only after confirming they are no longer needed.

### Scans

- Scan the back when it contains writing.
- Preserve the highest-quality master; make smaller viewing copies separately.
- Use an approximate date when necessary and caption the uncertainty.
- Record the physical album, box, or owner as provenance.
- Do not discard physical originals merely because they were scanned.

### Photos received from others

Keep the known creator and source. Do not claim another person's image as an
original. Ask permission before publishing, and expect messaging apps to have
reduced quality or removed metadata.

### Shared and cloud albums

Confirm whether shared items are actually downloaded into the primary library
or are only links to another owner's account. Export important albums with
their originals and captions where possible. Removing an item from a shared
album may affect other people, so verify ownership and behavior first.

### Videos and companion files

Include video formats, motion-photo components, Live Photo pairs, subtitles,
and sidecars in inventory, transfers, renaming, backup, and restore tests. A
still thumbnail does not prove the video plays correctly.

## 12. Validate the organized library

Before clearing an inbox or source:

- [ ] Every inventory source is imported or has a documented blocker.
- [ ] Source and imported file counts and sizes were reconciled.
- [ ] A sample from every source, year, and important format opens.
- [ ] Videos play with sound and expected duration.
- [ ] RAW files and sidecars open in the intended software.
- [ ] Folder names and filenames follow the documented conventions.
- [ ] No rename collision overwrote a file.
- [ ] Exact duplicates and rejects remain in quarantine, not deleted.
- [ ] Important dates, captions, keywords, albums, and edits survive a test
      export.
- [ ] Local and off-site backups completed after organization.
- [ ] Sample files were restored from both backups and opened.

Only after these checks and a personal review period should source devices or
quarantine folders be cleared. Follow device recycling and secure-erasure
guidance appropriate to the storage type.

## Progress log

Update one row after each work session:

| Date | Source or date range | Copied and verified | Organized | Duplicate review | Metadata or albums | Backups updated and restore-tested | Next action |
| --- | --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |  |

## Maintenance routine

### After an event or device import

- [ ] Copy new photos into a dated source folder under `00-Inbox/`.
- [ ] Verify the copy and update backups before erasing a card.
- [ ] Remove obvious accidents and quarantine suspected duplicates.
- [ ] File by date and event; add a short caption or keywords.
- [ ] Mark favorites and export share-ready copies separately.

### Monthly

- [ ] Empty the inbox into the organized library.
- [ ] Review screenshots, downloads, messaging images, and exports.
- [ ] Confirm automatic backup jobs are succeeding.
- [ ] Restore and open at least one recently backed-up photo.

### Annually

- [ ] Review the source inventory for forgotten devices or accounts.
- [ ] Restore a representative sample from local and off-site backups.
- [ ] Check older file formats, drives, discs, and cloud export options for
      continued readability.
- [ ] Replace failing or obsolete storage and migrate data before it becomes
      unreadable.
- [ ] Export important albums, metadata, and edited favorites in portable
      forms.
- [ ] Review sharing permissions and remove access that is no longer needed.
- [ ] Record the test date and next planned review.

## Recovery and rollback

If a batch rename, metadata edit, move, or deduplication produces unexpected
results:

1. Stop the operation; do not run another cleanup tool.
2. Record what was changed and preserve logs or rename mappings.
3. Keep the affected library unchanged for diagnosis.
4. Restore to a separate temporary location, not over the damaged collection.
5. Compare the restore with the affected files.
6. Correct and test the procedure on a small copy before trying again.

This is why the untouched inbox, quarantine period, rename mapping, and tested
backups are part of the workflow rather than optional extras.

## Definition of done

- [ ] Every known source is accounted for.
- [ ] The complete collection exists in one primary library.
- [ ] Important originals, RAW files, videos, scans, edits, and companion files
      are retained and readable.
- [ ] Folder and filename conventions are documented and consistently applied.
- [ ] Exact duplicates and rejects were reviewed by a person before deletion.
- [ ] Important photos have enough date, people, place, event, or caption
      context to be found and understood.
- [ ] The organized library has a verified local backup and a verified off-site
      backup.
- [ ] Sample restores from both backups open successfully.
- [ ] Shared access and sensitive location or identity information were
      reviewed.
- [ ] A monthly intake routine and annual recovery test are scheduled.
