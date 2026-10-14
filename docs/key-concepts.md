# Key Concepts in Subnautica Modding

## Prefabs and TechTypes

- **Prefab**: A GameObject template that can be spawned. Identified by a **Class ID** (string).
- **TechType**: An enum-like identifier for items, tools, creatures, etc. Used for crafting, inventory, scanning, etc.
- Nautilus helps you register custom prefabs and assign TechTypes.

## Harmony Patching

Most mods modify game behavior by patching methods with [Harmony](https://harmony.pardeike.net/).

Common targets:
- Player movement / oxygen
- Crafting systems
- Creature AI
- UI
- Save/load systems

## BepInEx Plugin Lifecycle

- `Awake()` / `Start()`: Early initialization.
- Harmony patches are typically applied in `Awake`.
- Nautilus handlers are usually called during initialization.

## Configuration

- BepInEx has its own config system.
- Nautilus provides a nicer in-game options menu integration.

## Asset Bundles

Unity AssetBundles are the standard way to ship custom models, textures, sounds, and prefabs.

## Compatibility

- Different game versions (legacy vs current) require different framework versions.
- Mods should declare their dependencies.
- Nitrox (multiplayer) has its own compatibility considerations.

## Logging

Always check `BepInEx/LogOutput.log` when debugging.

## Further Reading

Official Nautilus documentation covers:
- Prefab basics
- Adding items / equipment
- Crafting trees
- Biomes
- Story goals
- And much more.
