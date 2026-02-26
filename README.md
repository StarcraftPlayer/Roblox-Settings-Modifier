# Roblox Settings Editor

![Photo of the app.](Assets/ReadMePhotos/Main.png)

## Description

**THIS WAS ONLY TESTED ON WINDOWS 11**

A _WINDOWS ONLY_ app I made for editing certain Roblox settings OUTSIDE of Roblox, and enforcing those settings.

This is especially useful for games like Rogue Lineage, where most people use a lot of alt accounts. For example, say you want to run a 23/23 full server with one main account that runs at 60fps. Normally, you'd have to go into the Roblox settings file and manually change the FPS to 1 for the alt accounts or join on an alt and set the graphics to 1 and leave then rejoin on all the others to make sure the graphics setting will apply to the other instances.

That's fine and dandy but it gets annoying when you leave on your main account and on an alternate account. What happens is the settings file gets overridden by your main account (60 fps, full screen, full volume, etc.) but re-overridden by your alt account (1 fps, small screen, no volume, etc.) And when you try to join back on your main, it'll inherit those low-performance settings.

What this program does is enforce the settings YOU WANT, not what Roblox last wrote. If Roblox tries to change any settings in the xml file, this will re-apply your settings automatically.

In no way does this program tamper with non-Roblox related files or edit the Roblox binary or runtime. This only edits the settings file without you having to open up Roblox yourself.

## What it edits

- FPS cap
- Graphics quality
- Master volume
- Fullscreen mode
- Window size

## Installation

1. Download `Roblox-Settings-Editor.exe` from Releases
2. Run it (click "More info" → "Run anyway" on the Windows SmartScreen warning)
3. No install needed - fully self-contained

> Windows flags unsigned .exes as unsafe. The source code is fully available above if you want to verify it. The actual meat of the code is in `MainWindow.axaml.cs`.

## How to Build

```bash
dotnet publish -c Release -r win-x64 --self-contained true -p:PublishSingleFile=true -p:IncludeNativeLibrariesForSelfExtract=true
```
