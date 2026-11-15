🎮 GBCXY — Game Boy & Game Boy Color Emulator for PS5

GBCXY v2.0.1 — Kastroe Edition

An optimised Game Boy and Game Boy Color emulator for homebrew-enabled PlayStation 5 consoles.

Originally developed by YAHBALLON, GBCXY has been enhanced with a redesigned game library, NAS/NFS support improvements, integrated cover artwork scraping, persistent favourites, performance optimisations and a completely redesigned PS5 home-screen icon.

This repository hosts the public releases and downloads of GBCXY — Kastroe Edition.

📥 Download GBCXY

Download the latest stable release

Download the installation ZIP from the release's Assets section.

Requirements:

A PlayStation 5 capable of running compatible homebrew applications

A supported PS5 homebrew environment

Game Boy (.gb) or Game Boy Color (.gbc) ROM files

Optional: A NAS or network server for loading games over NFS

No commercial game ROMs are included.

✨ Features

🎮 Redesigned Game Library

GBCXY features a console-friendly interface with three dedicated game rows:

Library

Description

GAME BOY

Your original Game Boy collection

GAME BOY COLOR

Your Game Boy Color collection

FAVOURITES

Quick access to games you've marked as favourites

Additional improvements include:

Larger game cover artwork

Small, Medium and Large cover-size options

Smooth horizontal browsing

Clear game titles and selection highlighting

Improved spacing and library presentation

Faster library startup through caching

🌐 NAS / NFS Network Support

GBCXY supports loading games from compatible NFS network shares.

This is particularly useful for large ROM collections, allowing you to keep your games on a NAS rather than transferring every ROM onto your PS5.

Example NFS locations:

nfs://192.168.1.100/volume2/Roms/roms/gb
nfs://192.168.1.100/volume2/Roms/roms/gbc

These are examples only. Replace the IP address and paths with your own server configuration.

For NAS users:

Enable NFS sharing on your NAS or network server.

Create or select folders containing your GB and GBC games.

Grant your PS5 permission to access the relevant exports.

Enter the appropriate NFS locations in GBCXY's configuration.

Refresh or rescan the library.

Your NAS must be reachable from the PS5 over the local network. NFS permissions and export paths depend on your NAS model and configuration.

🖼️ Cover Artwork

GBCXY includes artwork functionality to make your game library look more like a modern console frontend.

Features include:

Automatic game cover matching

Downloading missing cover artwork

Scrape Missing Artwork for the entire library

Manual artwork refresh

Local artwork caching

Controls for automatic cover downloading

Not every ROM will have a matching cover available. Artwork results can depend on ROM naming and available artwork sources.

⭐ Favourites

Create your own collection of frequently played games.

Press Triangle on a selected game to add or remove it from Favourites.

GB and GBC games can appear together in the Favourites row.

Favourites are retained across application restarts and library refreshes.

⚡ Performance Improvements

This edition includes improvements focused on large game libraries and network-based collections.

Reduced unnecessary library file operations

Improved startup caching

More efficient artwork loading

Additional texture and memory safeguards

Improved handling of library refreshes

Reduced unnecessary background processing

🛠️ Installation

Visit the Releases page.

Open the latest release.

Download the PS5 installation ZIP under Assets.

Extract the archive as required by your preferred installation method.

Install the packaged application using your compatible PS5 homebrew environment.

Launch GBCXY from your PS5 home screen.

The application will appear with the redesigned neon GBCXY icon.

Note: GBCXY is a homebrew application. It is not intended for a standard retail PS5 without a compatible homebrew environment.

📚 Adding Games

GBCXY supports Game Boy and Game Boy Color game libraries.

System

File extension

Game Boy

.gb

Game Boy Color

.gbc

You can organise games into separate directories, for example:

Roms/
├── gb/
│   ├── Game 1.gb
│   └── Game 2.gb
└── gbc/
    ├── Game 1.gbc
    └── Game 2.gbc

Configure the corresponding locations in GBCXY, then refresh the library.

For NFS collections, make sure the configured path points to the correct exported location and that the PS5 has permission to read it.

🎮 Controls

Button

Function

Directional controls

Navigate games and menus

Triangle

Add/remove selected game from Favourites

R2

Manual artwork refresh where supported

Additional controls and options are available through the application's on-screen menus and controller prompts.

⚙️ Settings

GBCXY provides options for customising your game library, including:

Cover size: Choose Small, Medium or Large artwork.

Artwork scraping: Download missing artwork manually or configure automatic downloading.

Game directories: Configure local or network-based game locations.

Library refresh: Rescan configured collections when games are added or removed.

🧪 Testing and Compatibility

GBCXY — Kastroe Edition has been tested on actual PS5 hardware.

Testing has included:

A combined GB/GBC library of approximately 1,979 games

NFS ROM library access from an Asustor NAS

Cover artwork scraping across a large library

Game library navigation

Persistent Favourites

Adjustable game cover sizes

Installation of compiled PS5 builds

Verification of the redesigned PS5 home-screen icon

The project has also passed GitHub Actions source regression tests and PS5 package compilation checks.

Please note: Testing with a large library does not mean every individual game has been tested for compatibility. Some games, artwork matches and network configurations may behave differently.

❓ Troubleshooting

My games aren't appearing

Check that your ROM directory is correct, the files have supported extensions and the library has been refreshed.

For NAS users, verify your NFS export path, permissions and network connectivity.

Covers are missing

Try the Scrape Missing Artwork option or manually refresh artwork.

Some ROM names may not match available artwork databases.

NFS isn't connecting

Check the following:

Your NAS has NFS enabled.

The exported path is correct.

Your PS5's IP address is permitted to access the export.

The NAS and PS5 can communicate over the local network.

The export allows the required file access.

A game doesn't run correctly

Confirm the ROM file is valid and try another known-working game.

Not all compatibility issues are necessarily caused by the frontend.

📝 Reporting Issues

Found a bug or encountered a problem?

Use the GitHub Issues page and include:

Your GBCXY version

Your PS5 homebrew environment

Whether the game is loaded locally or over NFS

A description of the problem

Any relevant error messages or screenshots

Please don't upload copyrighted game ROMs when reporting issues.

🙏 Credits

YAHBALLON — Original GBCXY project and foundation.

Kastroe — Optimised frontend, library improvements, NAS/NFS refinements, artwork workflow, Favourites and PS5 presentation.

mGBA contributors — Game Boy and Game Boy Color emulation core.

Original upstream and homebrew contributors — Supporting libraries, resources and development work.

All applicable upstream licence and attribution requirements remain in effect.

⚠️ Disclaimer

GBCXY is an unofficial homebrew application.

It is not affiliated with, endorsed by or sponsored by Sony Interactive Entertainment or Nintendo.

Game Boy, Game Boy Color and PlayStation are trademarks of their respective owners.

No commercial game ROMs are distributed with this project. Users are responsible for ensuring they have the rights to any game files they use.

GBCXY — Kastroe Edition

Bringing classic Game Boy gaming to the PlayStation 5.
