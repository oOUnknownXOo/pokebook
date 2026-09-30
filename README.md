# Pokebook

**A desktop app for designing, organizing, and documenting custom Pokémon.**

Pokebook is a Windows application for creating personal Pokédex entries — for fan games, tabletop campaigns, fakemon projects, roleplay, worldbuilding, illustration references, or just for fun. Everything is stored locally on your machine, works completely offline, and requires no account or login.

![Pokebook Screenshot](build/screenshot.png)

> **Note:** Replace the image above with an actual screenshot of the app once you have one. Drop a `screenshot.png` into the `build/` folder, and it will show up here.

---

## Download

Get the latest version from the [**Releases page**](https://github.com/oOUnknownXOo/pokebook/releases/latest).

| File | What it is |
|---|---|
| `PokebookSetup.exe` | The installer. Download this, run it, and you're done. |

**Installation:**
1. Download `PokebookSetup.exe`
2. Double-click it. Windows may warn you — click **More info → Run anyway**. (The installer isn't code-signed, so Windows shows this warning for new apps.)
3. Follow the setup wizard. A Pokebook shortcut appears on your Desktop and Start Menu.
4. Launch it. Your collection is saved to `Documents\Pokebook\`.

**Auto-updates:** Once installed, Pokebook checks for new versions automatically on launch. When an update is available, a banner appears inside the app — click Download, then Restart & Install. Your data is never touched during updates.

---

## Features

### Create and manage custom Pokémon

Press **Create New Entry** to register a Pokémon with any combination of the following fields:

- **Name** — species name (required)
- **Typing** — one or more types, slash-separated (required)
- **Pokédex Number** — custom index number
- **Classification** — the "X Pokémon" title
- **Height** and **Weight** — free-form text
- **Total Stages** — 1, 2, or 3 evolution stages
- **Current Stage** — Basic, Stage 1, or Stage 2
- **Pokédex Entry** — flavor-text description
- **Image** — optional sprite or artwork (PNG, JPG, GIF, WEBP, SVG, BMP)

### Pokédex detail view

Click any card to open a full-screen Pokédex view with sprite, name, number, types, classification, height, weight, evolution stage, and flavor text.

### Search, sort, and filter

- **Live search** across name, typing, classification, dex number, and flavor text
- **Five sort modes** — dex number ascending/descending, name A–Z / Z–A, and by evolution stage count
- **Four filters** — All, 3-Stage, 2-Stage, 1-Stage

Filters stack with search and sort. Header stats update live.

### Bulk import

Upload **PDF, TXT, DOCX, or XLSX** files and Pokebook parses them into entries automatically. The parser expects a simple field format:

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

A fallback parser handles looser formats.

### Export to PDF

Generate a formatted PDF of your entire collection. Each entry shows all its details, and pages break automatically. The exported PDF uses the same format the importer expects, so it doubles as a backup you can re-import elsewhere.

### Auto-update system

Pokebook checks for new versions automatically on launch and notifies you in-app when one is available. Downloads and installs happen with two clicks.

---

## System Requirements

- **OS:** Windows 10 or Windows 11
- **Disk space:** ~200 MB for the app, plus space for your images
- **Internet:** Only needed for auto-updates. The app works fully offline.

---

## Version History

See [**CHANGELOG.md**](CHANGELOG.md) for the full version history with detailed notes on every release.

---

## Known Limitations

- **Windows only.** Not currently built for Mac or Linux.
- **No cloud sync.** Data lives on the local machine. Copy the `Documents\Pokebook\` folder to move it.
- **Installer is not code-signed.** Windows Defender shows a "Run anyway" warning on first launch. This is normal for unsigned software.
- **One image per entry.**

---

## License

## License

Pokebook is free to download, install, and use for personal purposes. The unmodified installer may be shared with others free of charge. Modification, redistribution for profit, and derivative works are not permitted.

See [LICENSE](LICENSE) for full terms.

© 2026 oOUnknownXOo. All rights reserved.

---

## Credits

Created and maintained by [@oOUnknownXOo](https://github.com/oOUnknownXOo).

Built with [Electron](https://electronjs.org), [electron-builder](https://www.electron.build), and [electron-updater](https://www.electron.build/auto-update).

Pokémon is a trademark of Nintendo, Game Freak, and Creatures Inc. Pokebook is an unofficial fan tool and is not affiliated with, endorsed by, or sponsored by any of these companies.
