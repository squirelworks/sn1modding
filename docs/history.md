# History of Subnautica 1 Modding

## Early Days: QModManager

- **QModManager** (QMM) was the original config-based mod loader.
- Mods were placed in a `QMods/` folder with a `mod.json` manifest.
- It sat on top of BepInEx.
- Paired with **SMLHelper** (later evolved into Nautilus).

## Transition to BepInEx-Native

- The community shifted toward pure BepInEx plugins.
- QModManager was archived; the last versions were only for the legacy game branch.
- As of the 2025 security hotfix / updates, the legacy branch is no longer available on Steam.

## Nautilus

- **Nautilus** is the modern successor to SMLHelper.
- Provides a cleaner, more robust API for items, prefabs, options, localization, etc.
- Actively maintained for the current version of Subnautica and Below Zero.

## Timeline Summary

| Period              | Primary Framework       | Notes                                      |
|---------------------|-------------------------|--------------------------------------------|
| ~2018–2021         | QModManager + SMLHelper | Config-driven, QMods folder                |
| 2021–2023         | QModManager + SMLHelper | Continued support                          |
| 2023–present       | BepInEx + Nautilus      | Current standard for latest game version   |
| Legacy branch only  | QModManager + SMLHelper | Obsolete for most players                  |

## Current Recommendation

For new mods targeting the current Subnautica release: **BepInEx + Nautilus**.
