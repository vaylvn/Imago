# Imago

**Local photo archive with face tagging.**

Imago is a lightweight desktop application for organising personal photo collections through manual face tagging. Open a folder, scan for faces, tag who's in each photo, and search by name. No cloud, no accounts, no internet connection required.

Everything is stored in a single `.imago` database file that lives inside your photo directory — move the folder anywhere and Imago moves with it.

---

## Features

- Scan a directory for faces and tag them by name
- Manually draw face boxes for anyone the scanner misses
- Ignore false positives with a single click
- Search photos by person's name
- View all photos a person appears in via the People tab
- Hover over a face in any photo to see who it is
- Per-directory databases — different folders stay completely separate
- Configurable detection settings including minimum face size and subdirectory scanning

---

## Download

**[→ Download the latest release](https://github.com/vaylvn/imago/releases)**

Imago is a single `.exe` file. No installation required — just download and run.

> Windows only for now.

---

## Quick Start

1. Download `imago.exe` from the releases page
2. Run it — no installation needed
3. Paste a path to your photo folder and click **Open**
4. Click **Scan** to detect faces
5. Click any untagged face to assign a name

That's it. See [USAGE.md](USAGE.md) for a full walkthrough.

---

## How it works

When you open a directory, Imago creates a `.imago` file inside it. This is a SQLite database containing all face detection data, tags, and people records for that folder. Your photo files are never modified.

---

## License

MIT
