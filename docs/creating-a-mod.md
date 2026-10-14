# Creating a Simple Mod

A high-level overview of making a basic Subnautica mod with Nautilus.

## Minimal Plugin

```csharp
using BepInEx;
using HarmonyLib;

namespace MyMod
{
    [BepInPlugin("com.example.mymod", "My Mod", "1.0.0")]
    [BepInDependency("com.snmodding.nautilus")]
    public class Plugin : BaseUnityPlugin
    {
        private void Awake()
        {
            var harmony = new Harmony("com.example.mymod");
            harmony.PatchAll();
            Logger.LogInfo("My Mod loaded!");
        }
    }
}
```

## Using Nautilus Features

Nautilus provides helpers for common tasks:

- **Custom items / prefabs** — Register new TechTypes, craftables, equipment.
- **Crafting recipes** — Add or modify recipes.
- **Console commands** — `ConsoleCommandsHandler.RegisterConsoleCommand`.
- **Options menu** — ConfigFile or ModOptions for in-game settings.
- **Localization** — Multi-language support.
- **Asset loading** — Asset bundles for models, textures, audio.

### Example: Register a Console Command

```csharp
using Nautilus.Handlers;

// Inside your plugin Start/Awake
ConsoleCommandsHandler.RegisterConsoleCommand<string>("mymod_hello", (name) =>
{
    return $"Hello, {name}!";
});
```

## Asset Bundles

For custom 3D models:
1. Use Unity 2019.4.36 (matching Subnautica).
2. Create an AssetBundle.
3. Load it at runtime with Nautilus utilities.

See the official [Asset Bundles Guide](https://subnauticamodding.github.io/Nautilus/guides/assetbundles.html).

## Best Practices

- Use unique plugin GUIDs (e.g. `com.yourname.modname`).
- Log useful messages with `Logger.LogInfo` / `LogWarning` / `LogError`.
- Declare dependencies properly.
- Handle missing optional dependencies gracefully.
- Test thoroughly; many crashes come from incorrect Harmony patches or null references.

## Publishing

Common places:
- [Nexus Mods](https://www.nexusmods.com/subnautica)
- Thunderstore
- GitHub Releases

Include a clear README, version, dependencies, and installation instructions.
