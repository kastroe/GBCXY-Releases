# 🎮 GBCXY — Game Boy & Game Boy Color Emulator for PS5

### GBCXY v2.0.2 — Kastroe Edition

**An optimised Game Boy and Game Boy Color emulator for homebrew-enabled PlayStation 5 consoles.**

Originally developed by **YAHBALLON**, GBCXY has been enhanced with a redesigned game library, improved NAS/NFS support, integrated cover artwork scraping, persistent Favourites, performance optimisations and a completely redesigned PS5 home-screen icon.

*This repository hosts the official public releases and downloads of GBCXY — Kastroe Edition.*

---

## 📥 Download GBCXY

### [⬇️ Download the Latest Stable Release](https://github.com/kastroe/GBCXY-Releases/releases/latest)

Download the **PS5 installation ZIP** from the release's **Assets** section.

### System Requirements

- **Console:** PlayStation 5 capable of running compatible homebrew applications.
- **Environment:** A supported PS5 homebrew environment.
- **Games:** Game Boy (`.gb`) and Game Boy Color (`.gbc`) ROM files.
- **Optional:** A NAS or network server for loading games over NFS.

**Important:** No commercial game ROMs are included.

---

## 📸 Screenshots

### GBCXY Game Library — Running on PS5

### Game Library
![GBCXY Game Library](gbcxy-library.png)

### Settings
![GBCXY Settings](gbcxy-settings.png)

### Game Boy Gameplay
![Game Boy Gameplay](gb-tetris.png)

## ✨ Features

### 🎮 Redesigned Game Library

GBCXY features a **console-friendly interface** with three dedicated game rows:

| Library | Description |
|---|---|
| **GAME BOY** | Your original Game Boy collection |
| **GAME BOY COLOR** | Your Game Boy Color collection |
| **FAVOURITES** | Quick access to your favourite games |

**Additional improvements include:**

- Larger game cover artwork.
- **Small, Medium and Large** cover-size options.
- Smooth horizontal game browsing.
- Clear game titles and selection highlighting.
- Improved spacing and library presentation.
- Faster library startup through caching.

### 🌐 NAS / NFS Network Support

GBCXY supports loading games directly from **compatible NFS network shares**.

This is particularly useful for large ROM collections, allowing you to keep your games on a NAS rather than transferring every ROM onto your PS5.

**Example NFS locations:**

```text
nfs://192.168.1.100/volume2/Roms/roms/gb
nfs://192.168.1.100/volume2/Roms/roms/gbc
```

*These are examples only. Replace the IP address and paths with your own server configuration.*

**Setting up your NAS:**

1. Enable **NFS sharing** on your NAS or network server.
2. Create or select folders containing your GB and GBC games.
3. Grant your PS5 permission to access the relevant NFS exports.
4. Enter the appropriate NFS locations in GBCXY's configuration.
5. Refresh or rescan your game library.

**Note:** Your NAS must be reachable from the PS5 over your local network. NFS permissions and export paths depend on your NAS model and configuration.

### 🖼️ Automatic Cover Artwork

GBCXY includes integrated artwork functionality to make your game library look more like a modern console frontend.

**Artwork features:**

- Automatic game cover matching.
- Downloading missing cover artwork.
- **Scrape Missing Artwork** for the entire library.
- Manual cover refresh using **R2**.
- Local artwork caching for faster browsing.
- Options for automatic cover downloading.

*Not every ROM will have matching artwork available. Results depend on ROM filenames and available artwork sources.*

### ⭐ Persistent Favourites

Create a personalised collection of frequently played games.

- Press **Triangle** on a selected game to add or remove it from Favourites.
- Combine **GB and GBC games** in the same Favourites row.
- Favourites persist across application restarts.
- Your selections remain available after library refreshes.

### ⚡ Performance & Stability Improvements

This edition includes optimisations focused on large game libraries and network-based collections.

- Reduced unnecessary library file operations.
- Improved startup caching.
- More efficient artwork loading.
- Additional texture and memory safeguards.
- Improved handling of library refreshes.
- Reduced unnecessary background processing.
- **v2.0.2:** Fixed a crash when using the DualSense touchpad to return from gameplay to the GBCXY library.

---

## 🛠️ Installation Guide

1. Visit the **[GBCXY Releases page](https://github.com/kastroe/GBCXY-Releases/releases)**.
2. Open the **latest stable release**.
3. Download the PS5 installation ZIP under **Assets**.
4. Extract the archive if required by your installation method.
5. Install the packaged application using your compatible PS5 homebrew environment.
6. Launch **GBCXY** from the PS5 home screen.

The application features the redesigned **neon cyan-and-purple GBCXY icon**.

**Note:** GBCXY is a homebrew application and requires a compatible PS5 homebrew environment.

---

## 📚 Adding Games

GBCXY supports both Game Boy and Game Boy Color game libraries.

| System | Supported Extension |
|---|---|
| **Nintendo Game Boy** | `.gb` |
| **Nintendo Game Boy Color** | `.gbc` |

### Recommended Folder Structure

You can organise your games into separate directories:

```text
Roms/
├── gb/
│   ├── Game 1.gb
│   └── Game 2.gb
└── gbc/
    ├── Game 1.gbc
    └── Game 2.gbc
```

Configure the corresponding locations in GBCXY, then refresh the game library.

**For NFS collections:** Ensure your configured location points to the correct exported directory and your PS5 has permission to read it.

---

## 🎮 Controller Controls

| Button | Function |
|---|---|
| **Directional controls** | Navigate games and menus |
| **Cross (✕)** | Launch selected game |
| **Triangle (△)** | Add or remove Favourites |
| **R2** | Refresh selected game's cover artwork |
| **Touchpad (during gameplay)** | Return to GBCXY's game library |

*Additional controls and customisation options are available through the application's menus and on-screen prompts.*

---

## ⚙️ Settings & Customisation

GBCXY provides several options for customising your experience.

**🖼️ Cover Size**

Choose between **Small, Medium and Large** artwork sizes.

**🌐 Artwork Scraping**

Download missing artwork manually or configure automatic downloading.

**📂 Game Directories**

Configure local or network-based game locations.

**🔄 Library Refresh**

Rescan configured game collections when ROMs are added or removed.

---

## 🧪 Testing & Compatibility

**GBCXY — Kastroe Edition has been tested on actual PlayStation 5 hardware.**

Testing has included:

- A combined GB/GBC library of approximately **1,979 games**.
- NFS ROM library access from an **Asustor NAS**.
- Cover artwork scraping across a large collection.
- Game library navigation and scrolling.
- Persistent Favourites.
- Adjustable game cover sizes.
- Installation of compiled PS5 builds.
- Verification of the redesigned home-screen icon.
- Gameplay testing with **The Legend of Zelda: Link's Awakening** for Game Boy.
- Returning from gameplay to the library and launching another ROM after the **v2.0.2 stability fix**.

The project has also passed GitHub Actions source regression tests and PS5 package compilation checks.

**Compatibility notice:** Testing with a large library does not mean every individual game has been tested. Game compatibility, artwork matching and network performance may vary.

---

## ❓ Troubleshooting

### My Games Aren't Appearing

Check that:

- Your ROM directory is configured correctly.
- Your games have supported file extensions.
- The game library has been refreshed.
- Your NFS share is accessible if loading from a NAS.

### Covers Are Missing

Try **Scrape Missing Artwork** or manually refresh the selected game's cover.

Some ROM filenames may not match available artwork databases.

### NFS Isn't Connecting

Verify the following:

- NFS sharing is enabled on your NAS.
- The exported directory path is correct.
- Your PS5's IP address has permission to access the share.
- The NAS and PS5 can communicate over the local network.
- The export provides the required read permissions.

### A Game Doesn't Run Correctly

Confirm that the ROM file is valid and try another known-working game.

Not all compatibility problems are necessarily caused by the GBCXY frontend.

---

## 📝 Reporting Bugs & Issues

**Found a bug or encountered a problem?**

Report it through the **[GitHub Issues page](https://github.com/kastroe/GBCXY-Releases/issues)**.

Please include:

- **GBCXY version** being used.
- **PS5 homebrew environment**.
- Whether the ROM is loaded **locally or over NFS**.
- A clear description of the problem.
- Relevant error messages or screenshots.

*Please do not upload copyrighted game ROMs when reporting issues.*

---

## 🙏 Credits & Acknowledgements

**YAHBALLON** — Original GBCXY project and foundation.

**Kastroe** — Optimised frontend, game library improvements, NAS/NFS refinements, artwork management, Favourites, performance improvements and PS5 presentation.

**mGBA Contributors** — Game Boy and Game Boy Color emulation core.

**Original Upstream & Homebrew Contributors** — Supporting libraries, resources and development work.

*All applicable upstream licence and attribution requirements remain in effect.*

---

## ⚠️ Disclaimer

**GBCXY is an unofficial PlayStation 5 homebrew application.**

It is not affiliated with, endorsed by or sponsored by **Sony Interactive Entertainment** or **Nintendo**.

Game Boy, Game Boy Color and PlayStation are trademarks of their respective owners.

**No commercial game ROMs are distributed with this project.** Users are responsible for ensuring they have the necessary rights to any game files they use.

---

### 🎮 GBCXY — Kastroe Edition

*Bringing classic Game Boy gaming to the PlayStation 5.*

**[📥 Download GBCXY](https://github.com/kastroe/GBCXY-Releases/releases/latest)**
