<div align="center">

# GBCXY

### 8-Bit Colors. Next-Gen CoverFlow.

**v2.1.0 by Kastroe Ã‚Â· PPSA99210**
Originally developed by YAHBALLON

[![Native PS5 Build](https://github.com/kastroe/PS5GBCX/actions/workflows/build-gbcxy.yml/badge.svg)](https://github.com/kastroe/PS5GBCX/actions/workflows/build-gbcxy.yml)
[![GitHub releases](https://img.shields.io/github/v/release/kastroe/PS5GBCX?style=flat-square)](https://github.com/kastroe/PS5GBCX/releases)

</div>

**GBCXY** is a PlayStation 5 homebrew emulator for **Game Boy, Game Boy Color and Game Boy Advance**, powered by the mGBA 0.10.5 GB/GBC/GBA core and a 3D Vulkan CoverFlow frontend. It builds on the same modern frontend foundation as GBAXY, with five original themes and its own animated loading sequence.

> **Compatibility:** the repository remains `PS5GBCX`, Title ID remains **`PPSA99210`**, and existing games, settings, cached box art and saves remain in **`/data/PS5GBC/`**. This is an in-place upgrade, not a new app title.

## Highlights

| Feature | Description |
| --- | --- |
| **3D CoverFlow** | Animated glass cartridge cases, neon edges, cover reflections and wraparound browsing |
| **Artwork lookup/cache** | GB and GBC use their **separate** Libretro Named_Boxarts libraries, with region/name fallbacks and a local disk cache |
| **Five new themes** | Chromatic Shift, Pocket Forest, Berry Soda, Polar LCD and Retro Amber |
| **Chromatic Pocket** | Original animated 8-bit boot: rotating color-pixel mosaic, LCD scanlines, cartridge emblem and genuine ROM scan counts |
| **Native GB/GBC/GBA emulation** | mGBA 0.10.5 with GB/GBC/GBA cores enabled; preserves ROM scanning, audio, saves and controller mappings |
| **SGB enhanced borders** | Supports GB/GBC `160x144`, Super Game Boy border-inclusive `256x224`, and GBA `240x160` output paths |
| **Flexible scaling** | Stretch to full screen, original GB/GBC aspect ratio or integer scaling |
| **Three-row library** | Independent Game Boy, Game Boy Color and Favourites rows with persistent favourites |
| **Cover Size** | Small, Medium and Large display sizes, persisted in the existing settings |
| **Safe PS5 exit** | In the library, Circle opens the close confirmation, Cross confirms, Circle cancels. Shutdown uses `sceSystemServiceLoadExec("exit", nullptr)` rather than unsupported libc `exit(0)`. |

### Choose your theme

- **Chromatic Shift** Ã¢â‚¬â€ multicolor turquoise and purple; default
- **Pocket Forest** Ã¢â‚¬â€ LCD greens and spring-leaf highlights
- **Berry Soda** Ã¢â‚¬â€ pink, raspberry and sunset orange
- **Polar LCD** Ã¢â‚¬â€ icy blue and white glass
- **Retro Amber** Ã¢â‚¬â€ dark gold inspired by vintage handheld screens

Select a theme under **Settings Ã¢â€ â€™ Appearance Ã¢â€ â€™ Theme**. The selection is stored in the existing global configuration.

## Box art sources

GBCXY uses the existing local cover folder and cache first. For missing covers it looks up No-Intro names and common USA, Europe and Japan region variants in the correct system-specific directories:

- **Game Boy (.gb):** [Libretro GB Named_Boxarts](https://thumbnails.libretro.com/Nintendo%20-%20Game%20Boy/Named_Boxarts/)
- **Game Boy Color (.gbc):** [Libretro GBC Named_Boxarts](https://thumbnails.libretro.com/Nintendo%20-%20Game%20Boy%20Color/Named_Boxarts/)
- **Game Boy Advance (.gba):** GBA recognition is supported; artwork remains on-demand and policy-controlled without changing the existing GB/GBC artwork providers.

Game Boy artwork will not be incorrectly selected from the Game Boy Color library (or the reverse). Portrait art stays portrait, landscape artwork keeps its complete source image, and reflections follow the same geometry. Cover downloads happen on demand and are cached for the next boot.

## Installation / updating

1. The production workflow assembles **`GBCXY-v2.1.0-by-Kastroe.zip`** with the complete `PPSA99210` payload and required notices. The user-confirmed tested fix package is the basis for these v2.1.0 notes; the production ZIP SHA-256 is 10eccb33fbf171192f9a2ed7daaa9690905b4debce86c4d429df1f86809901fd. A GitHub source-code ZIP is **not** an installable PS5 build.
2. Extract the **complete `PPSA99210` folder**, retaining `eboot.bin`, `sce_sys`, `sce_module` and the packaged helper.
3. Copy it to a supported PS5 homebrew install folder, commonly `/data/homebrew/PPSA99210/`, and start **GBCXY** from your jailbroken PS5.

### Game folders and saved data

```text
/data/PS5GBC/games/
/data/PS5GBC/roms/
/data/PS5GBC/saves/
/data/PS5GBC/states/
/data/PS5GBC/covers/
/data/PS5GBC/cache/
/data/PS5GBC/logs/
```

You can also scan USB game directories such as `/mnt/usb0/homebrew/PS5GBC/games/` and configured NFS shares. Use your own legally acquired GB/GBC/GBA game files; the repository includes **no ROMs**.

## Controller controls

### Library

| Input | Action |
| --- | --- |
| D-pad Left/Right | Browse the current row |
| L1/R1 | Jump through the row |
| Up | Cycle the library collection |
| Down | Open library search |
| Triangle | Toggle the selected game's favourite state |
| Square | Open settings |
| R2 | Refresh the selected game's artwork |
| Cross/Options | Launch the selected game |
| Circle | Open the exit confirmation |

### In-game

Cross and Circle map to A and B. The D-pad maps to directions, Options maps to Start,
Create maps to Select, and holding L1+R1+Touchpad for two seconds returns to the shelf.
Holding L2 enables fast forward. L3+R3+Up saves a state; L3+R3+Down loads one. Button mappings and shortcuts
can be changed globally or per game.

## Saves, states and resume

Battery-backed cartridge saves, RTC data where supported, and save states are stored
under `/data/PS5GBC/saves/` and `/data/PS5GBC/states/`. Save-state slots can be
written and loaded from the in-game shortcuts above, and the frontend preserves the
selected game and resume state across a normal relaunch. Existing save data remains
in place when updating the app.

## NFS game libraries

NFS support is configurable and does not require a repository-local server address.
Open **Settings Ã¢â€ â€™ Network Ã¢â€ â€™ NFS URL** and enter a share such as:

```text
nfs://your-server/export/gbcxy
```

Alternatively, place one configured share per line in `/data/PS5GBC/nfs.txt`.
Use a hostname or the address of your own server; do not commit private NAS addresses
or credentials. The library cache preserves discovered games between launches, while
manual rescan and the configured refresh policy remain available.

## Artwork and favourites

GBCXY checks local artwork and its persistent cache before using the system-specific
Libretro Named_Boxarts sources listed above. **Settings Ã¢â€ â€™ Artwork Ã¢â€ â€™ Scrape Missing
Artwork** performs a manual full-library scrape; automatic cover downloads remain off
by default. Downloaded, validated artwork is stored in the runtime data directory,
not in this repository. Existing cached covers are never required for a source build.

## Source layout and builds

The [**GBCXY Native Build & Release**](.github/workflows/build-gbcxy.yml) workflow performs automated source/box-art/controller regression tests and assembles a native signed PS5 package from source. Package hashes are published only with the corresponding final artifact; version metadata is maintained in `app.json` and `gbc/src/gbcxy_build_version.h`.

```text
gbc/src/                   GB/GBC/GBA core wrapper, emulator and Chromatic Pocket animation
gbc/third_party/mgba/      Original open-source mGBA source
gbc/tools/                 Native PS5 build scripts and regression checks
ps5/frontend/              Game library, cover worker, settings, native Vulkan bridge
ps5/porpoise_original/     Licensed Porpoise 3D UI code
ps5/frontend/assets/       GBCXY icon and embedded UI assets
tests/                     GBCXY visual, cover-provider and exit regression tests
.github/workflows/         Automated signed build and release
```

GBCXY builds require the PS5 payload toolchain, native Vulkan dependencies and compatible Linux SDK tools. Host-only builds cannot produce an installable PS5 binary.

### Windows development with WSL

The Windows checkout is the authoritative source tree. Use WSL for Linux-based
host checks and PS5 cross-build tools:

```bash
cd /mnt/c/path/to/PS5GBCX
python3 gbc/tools/test.py
```

For a native PS5 build, prepare the pinned dependencies described in
[`BUILDING.md`](BUILDING.md), then provide the dependency locations and run:

```bash
export PS5GBC_DEPS=/path/to/prepared/ps5-build
export PS5_PAYLOAD_SDK=/path/to/ps5-payload-sdk
export LIBNFS_PREFIX=/path/to/libnfs-install
export LIBZ_PREFIX=/path/to/pacbrew/sysroot/user/homebrew
bash gbc/tools/build.sh
```

The scripts use Clang/LLVM 18, LLD, CMake/Ninja, Python, PS5/Vulkan SDK
components, libnfs and PacBrew curl/OpenSSL/zlib dependencies. SDKs and generated
dependency trees are intentionally not stored in Git. Native Windows builds are
not supported by these entry points.

See [`BUILDING.md`](BUILDING.md), [`INSTALL.md`](INSTALL.md), [`CONTROLS.md`](CONTROLS.md)
and [`TESTING.md`](TESTING.md) for operational details and known PS5 validation limits.

## Credits and licensing

**GBCXY v2.1.0 by Kastroe. Originally developed by YAHBALLON.** GB/GBC/GBA emulation is provided by [mGBA](https://github.com/mgba-emu/mgba)
(MPL-2.0), with frontend code adapted from [Porpoise](https://github.com/elripalda/Porpoise-Dolphin-Emulator-for-PS5)
and other open-source PS5 development projects. The repository also contains vendored
dependencies including Vulkan tooling, libnfs, curl/OpenSSL/zlib components, fonts,
stb libraries and other upstream code with their own licenses.

The project is distributed under GPL-3.0-or-later where applicable. See
[`LICENSE`](LICENSE), [`COPYING.GPLv3`](COPYING.GPLv3), [`THIRD_PARTY_NOTICES.md`](THIRD_PARTY_NOTICES.md),
the `gbc/licenses/` directory and bundled third-party license files before
redistributing modified or packaged builds. The GBCXY logo and project-specific
assets remain subject to their stated provenance and permissions.

There is no dedicated in-app About screen. Credits are shown in the loading frame and boot/report header; this README and the notices are the authoritative attribution locations. This independent community homebrew project is not affiliated with Sony or Nintendo. It does not distribute commercial ROMs, copyrighted BIOS files or pirated games. The exact FINAL-RC production artifact was tested on PS5 hardware before publication.
