# Pokebook — Version History

All notable changes to Pokebook are documented here. Each entry lists what changed, when it was released, and what it does for the user.

---

## Version 1.0.0 — 09/30/2026

**First public release.**

Pokebook is a Windows desktop application for designing, organizing, and documenting custom Pokémon for personal projects — fan games, tabletop campaigns, fakemon dexes, roleplay sessions, illustration references, and anything else you need a personal Pokédex for. It runs as a standalone program, stores all your data locally on your own machine, and works completely offline after installation. No account, no login, no internet required.

Below is a complete breakdown of everything Pokebook can do.

---

### Create Pokémon Pokédex Entries

Press the **Create New Entry** button to register a new Pokémon. A form opens where you fill in any of the following fields:

| Field | Description | Example |
|---|---|---|
| **Name** | The Pokémon's species name. Required. | `Volcarona` |
| **Typing** | One or more types. Separate multiple types with a slash or comma. Required. | `Fire / Bug` |
| **Pokédex Number** | Your custom index number for this entry. | `#001` |
| **Classification** | The "X Pokémon" category title used in the official games. | `Sun Pokémon` |
| **Height** | Free-form text — use whatever units you like. | `1.6m` |
| **Weight** | Free-form text — use whatever units you like. | `46.0kg` |
| **Total Stages** | How many stages this Pokémon's evolutionary line has: 1, 2, or 3. | `2` |
| **Current Stage** | Which stage *this specific entry* represents: Basic, Stage 1, or Stage 2. | `Stage 1` |
| **Pokédex Entry** | A short flavor-text description, like the text in the official games. | `A sun-like Pokémon...` |
| **Image** | An optional sprite, artwork, or photo. | (any image file) |

Every field except Name and Typing is optional. The moment you press **Save Pokémon**, the entry is written to disk — there's no separate "save" step or file menu to worry about.

---

### Edit Existing Entries

Every card in the grid has an **Edit** button. Clicking it opens the same form, pre-filled with that entry's current data. Change anything you want and save — the entry is updated in place, without creating a duplicate or losing its ID. If you don't upload a new image during an edit, the existing image is preserved automatically.

---

### Delete Entries

Every card also has a **Delete** button. A confirmation prompt appears before anything is removed, so you can't wipe an entry by accident. Deleting an entry also deletes its associated image file from disk, keeping your data folder clean.

---

### Pokédex Detail View

Click any card (the card itself, not the buttons) to open a full-screen Pokédex view. This shows:

- The Pokémon's sprite or artwork
- Its name and Pokédex number
- All of its types as colored badges
- Classification, height, weight, and current evolution stage
- The full Pokédex flavor text

The layout is inspired by the Pokédex screens from the games, with the sprite and name on the left and the details on the right. Long flavor text automatically shrinks to fit the entry box without overflowing.

---

### Search

The search bar in the action bar filters the grid live as you type. It matches against every text field on an entry:

- Name
- Typing
- Classification
- Pokédex Number
- Pokédex flavor text

Type any fragment — like `fire` or `#001` or `sun` — and the grid updates instantly.

---

### Sort Options

Choose from five sort modes via the dropdown menu next to the search bar:

- **# Ascending** — by Pokédex number, low to high
- **# Descending** — by Pokédex number, high to low
- **A–Z** — alphabetical by name
- **Z–A** — reverse alphabetical
- **Stages** — grouped by evolutionary stage count (1-stage first, then 2-stage, then 3-stage), with alphabetical order within each group

---

### Filter by Evolution Stage

Four filter buttons in the action bar narrow the grid to a specific type of evolutionary line:

- **All** — every entry
- **3-Stage** — three-stage evolution lines only
- **2-Stage** — two-stage lines only
- **1-Stage** — single-stage Pokémon only

Filters stack on top of search and sort. So you can, for example, filter to 3-stage Pokémon, search for "fire", and sort by name — all at once. The header stats (Total / 3-Stage / 2-Stage / 1-Stage) update live to reflect what's currently visible.

---

### Image Uploads

Each entry can have one image attached to it. Supported formats:

- PNG
- JPG / JPEG
- GIF
- WEBP
- SVG
- BMP

Images are saved as individual files inside the app's `images/` folder — not embedded in the database file — so they stay manageable in size and easy to back up or replace. Image previews appear in the entry form as soon as you select a file, and on the card grid and detail view.

---

### Bulk Import from PDF, TXT, DOCX, and XLSX

The **Upload Bulk Entries** button accepts four file formats:

- **PDF** — text is extracted and parsed (works with Pokebook's own PDF exports, and with any document that follows the same field format)
- **TXT** — plain text files in the same field format
- **DOCX** — Microsoft Word documents
- **XLSX / XLS** — Excel spreadsheets (the first sheet is read)

The parser looks for fields in this format:

```
Pokedex Number: #001
Pokemon Name: Volcarona
Type: Fire / Bug
Classification: Sun Pokémon
Height: 1.6m
Weight: 46.0kg
Total Stages: 2
Current Stage: Stage 1
Pokedex Entry: A sun-like Pokémon that scatters burning scales...
```

A fallback parser also handles looser formats (label-on-its-own-line styles), so you don't need to be perfectly consistent with the layout.

After parsing, the app shows how many entries were found and asks for confirmation before importing. All imported entries are saved to disk immediately, with fresh IDs and blank images.

---

### Export to PDF

The **Export PDF** button generates a formatted PDF containing every entry currently in your collection. Each entry is laid out with its number, name, type, classification, height, weight, stage information, and flavor text. Entries are separated by horizontal rules, and pages break automatically when needed.

The exported PDF uses the same field format the bulk importer expects — so you can export your collection, edit it in a text editor, and re-import it on another machine without losing anything.

```
The app auto-saves on every action:

- Creating an entry
- Editing an entry
- Deleting an entry
- Bulk importing from a file

There is no "Save" button to remember and no way to lose unsaved work — every change is written to disk immediately.

---

### Floating Action Button

A circular **+** button floats at the bottom-right of the screen. Press it any time to open the "New Pokémon" form without scrolling back to the top of the page. A **↑** button appears above it once you've scrolled down, which jumps you back to the top of the grid.

---

### Toast Notifications

Every action — creating, updating, deleting, importing, exporting — shows a brief notification in the bottom-right corner of the screen confirming success or reporting an error. Notifications disappear automatically after a few seconds.

---

### Keyboard Support

- Press **Escape** to close any open modal (entry form, Pokédex view)
- Press **Tab** to navigate through form fields
- The Name field is focused automatically when the entry form opens, so you can start typing immediately

---

### Auto-Update System

Pokebook checks for updates automatically a few seconds after launch. If a newer version is available, a teal banner slides down from the top of the window with the version number and a **Download** button. Click it to fetch the update in the background — a progress bar shows the download speed and percentage. When the download finishes, the button changes to **Restart & Install**. Click it once and Pokebook restarts with the new version, keeping all your data intact.

If you're already on the latest version, nothing happens — no popups, no nagging. If you're offline or the update check fails, the app just runs normally.

---

### Windows Installer

Pokebook is distributed as a single file, `PokebookSetup.exe`. Running it launches a standard Windows install wizard:

- Per-user install — no admin password needed
- Custom install location supported (default is `%LOCALAPPDATA%\Programs\Pokebook`)
- Desktop shortcut created automatically
- Start Menu shortcut created automatically
- Add/Remove Programs entry for easy uninstallation
- Uninstaller included
- Uninstalling does **not** delete your Pokémon collection

---

### Known Limitations

- **Windows only.** Built and tested on Windows 10. Mac and Linux builds are possible in the future but not currently produced.
- **No cloud sync.** Data is stored locally on the machine where Pokebook is installed. To move your collection to another machine, copy the `Documents\Pokebook\` folder manually, or use the PDF export / bulk import feature.
- **Installer is not code-signed.** Windows Defender will show a "Windows protected your PC" warning the first time you run the installer. This is normal for unsigned software and does not indicate a problem. Click **More info → Run anyway** to proceed.
- **One image per entry.** Multiple images per Pokémon are not currently supported.

---

<!--
Future versions go below this comment, newest first. Copy this template:

## Version X.Y.Z — MM/DD/YYYY

**Short summary line.**

### New Features
- ...

### Improvements
- ...

### Bug Fixes
- ...

### Breaking Changes
- ...
-->
