# Using Imago

## Opening a Directory

On launch, paste the full path to your photo folder into the input field and click **Open**. Previously opened directories appear under **Recent** for quick access.

If Imago hasn't seen the folder before, it will create a `.imago` database file inside it. If one already exists, it loads your existing tags and people.

Once open, the header shows your current directory path. Use **Library**, **People**, and **Settings** in the top right to navigate between views. Click **×** to close the current directory and return to the start screen.

---

## Library

The Library shows every photo in your directory as a grid. Photos with untagged faces show a small indicator in the corner.

**Filter tabs** at the top let you narrow the view:
- **All** — every photo in the directory
- **Untagged** — photos with at least one face that hasn't been named yet
- **Tagged** — photos where all detected faces have been tagged or ignored
- **Unscanned** — photos that haven't been through face detection yet

**Search by name** in the top right filters the grid to photos containing that person.

**Scan** runs face detection across all unscanned photos. This may take a moment depending on how many photos you have.

---

## Tagging Faces

Click any photo to open it. Detected faces are shown as boxes overlaid on the image.

A panel on the right lists all untagged faces in the current photo. Click a face box on the image or a thumbnail in the panel to select it.

With a face selected:
- Type a name in the **Tag as** field and click **Tag** to assign it. If the name is new, a new person is created. If they already exist in your archive, their record is updated.
- Click **Ignore** to mark the face as a false positive — it won't appear as untagged again.
- Click **Select next** to move to the next untagged face without tagging the current one.
- Click **Ignore remaining** to ignore all remaining untagged faces in the photo at once.

Use the arrow on the right edge of the photo to move to the next photo without returning to the grid.

Hover over any tagged face box to see the person's name.

---

## Drawing Faces Manually

If someone in a photo wasn't picked up by the scanner — common with old, low-quality, or partially obscured photos — click **Draw face** in the top right of the photo view.

Click and drag directly on the photo to draw a bounding box around the face, then tag it as normal. Manually drawn faces are stored and treated the same as detected ones.

---

## People

The **People** tab shows everyone tagged in the current directory, with a representative face thumbnail and their name.

Click any person to see every photo they appear in. From there you can click into individual photos as normal.

---

## Settings

Settings are per-directory and found under the **Settings** tab.

| Setting | Description |
|---|---|
| **Scan subdirectories** | When enabled, Imago includes photos in subfolders when scanning. Off by default. |
| **Min neighbours** | Controls how strict face detection is. Higher values mean fewer false positives but may miss real faces. Range 4–15, default 8. |
| **Min face size (px)** | Faces smaller than this are skipped entirely — useful for ignoring background people. Default 40px. |

Changes take effect on the next scan. Already-scanned photos are not re-processed unless you manually trigger a rescan.

---

## The `.imago` file

Every managed directory contains a single `.imago` file at its root. This is a SQLite database holding all face data, tags, and people for that folder.

- Your photo files are **never modified**
- Deleting `.imago` removes all tags for that directory — the photos themselves are untouched
- Moving a directory to another location with `.imago` intact preserves everything
- Different directories have completely separate databases — tagging someone in one folder has no effect on another

---

## Tips

- If the scanner misses faces on old or dark photos, try lowering **Min neighbours** in Settings and rescanning
- Use **Ignore** freely — it's easy to un-ignore a face from the photo view if you change your mind
- The **Draw face** tool is particularly useful for group photos where someone is partially turned away or at the edge of the frame
- Subdirectory scanning is useful if your archive is organised into subfolders by year or event, but keep it off if you only want to work on the top-level folder
