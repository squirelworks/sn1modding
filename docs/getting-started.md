# Getting Started with Subnautica 1 (SN1) Modding

This guide covers installing the modding framework and your first mods for the original Subnautica.

## Prerequisites

- A legitimate copy of Subnautica (Steam, Epic, Xbox PC, etc.).
- The ability to extract ZIP files.
- (Optional) [Vortex Mod Manager](https://www.nexusmods.com/) for easier management.

## Step 1: Install BepInEx

BepInEx is the underlying mod loader. Use the community-maintained **Subnautica BepInEx Pack** which is preconfigured for the game.

1. Download the latest pack from:
   - [Nexus Mods](https://www.nexusmods.com/subnautica/mods/1108)
   - Or [GitHub](https://github.com/toebeann/BepInEx.Subnautica/releases)
2. Extract the contents of the ZIP **directly into your Subnautica game folder** (the folder containing `Subnautica.exe`).
   - Typical Steam path: `C:\Program Files (x86)\Steam\steamapps\common\Subnautica`
3. Launch the game once through Steam (or your platform launcher). You should see a BepInEx splash/loading screen.
4. Exit the game.

**Linux / Steam Deck notes:** You may need to set launch options:
```
WINEDLLOVERRIDES="winhttp=n,b" %command%
```

**macOS:** Use the `gib` tool or follow the detailed instructions on the BepInEx.Subnautica repository.

## Step 2: Install Nautilus

Nautilus is the primary modding API/library that most modern SN1 mods depend on.

1. Download the latest Nautilus release from:
   - [Nexus Mods](https://www.nexusmods.com/subnautica/mods/1262)
   - [GitHub Releases](https://github.com/SubnauticaModding/Nautilus/releases)
2. Extract the `plugins` folder (or the Nautilus folder) into `Subnautica/BepInEx/plugins/`.

Your plugins folder should contain a Nautilus folder or DLLs.

## Step 3: Install Mods

Most mods are distributed as ZIP files containing one or more `.dll` files (and sometimes config or asset files).

1. Download a mod from [Nexus Mods](https://www.nexusmods.com/subnautica), Thunderstore, or the mod's GitHub.
2. Extract the mod files into `Subnautica/BepInEx/plugins/`.
   - Some mods want their own subfolder; follow the mod's specific instructions.
3. Launch the game.

### Verifying Installation

- Check the BepInEx log (usually in `BepInEx/LogOutput.log` or the console) for errors.
- Many mods add options in the in-game Mods menu (provided by Nautilus).

## Important Compatibility Notes

- Use the **latest** Nautilus for the current Subnautica version.
- Older branches (legacy / march_2023) require older versions of the frameworks (SMLHelper / specific Nautilus pre-releases).
- QModManager is obsolete for the current game and only worked on the legacy branch.

## Next Steps

- See [Development Setup](development-setup.md) if you want to create your own mods.
- Browse popular mods on Nexus to understand common features.
- Join the Subnautica Modding Discord for help.
