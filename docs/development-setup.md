# Development Setup for SN1 Modding

Guide to setting up an environment for creating Subnautica mods with Nautilus.

## Prerequisites

1. **.NET SDK** (latest) — [Download](https://dotnet.microsoft.com/download)
   - Verify with: `dotnet --version`
2. **IDE** (one of):
   - Visual Studio Community (Windows, free)
   - JetBrains Rider (cross-platform)
   - Visual Studio Code + C# Dev Kit / .NET extension pack
3. **Installed game** with BepInEx Pack + Nautilus already set up (see Getting Started).
4. Basic C# knowledge.

## Install Project Templates

The community provides .NET templates that set up the correct references and structure:

```bash
dotnet new install Subnautica.Templates
```

If you get a NuGet source error:
```bash
dotnet nuget add source https://api.nuget.org/v3/index.json -n nuget.org
```

Available templates include:
- `snmod` — Subnautica template with basic Plugin.cs, Harmony, and logging
- `snmod_nautilus` — Includes Nautilus examples
- `snmod_empty` — Minimal
- Equivalent `bzmod*` templates for Below Zero

## Create a New Project

**CLI:**
```bash
dotnet new snmod -n MyAwesomeMod
cd MyAwesomeMod
```

**IDE:** Use "Create new project" and search for "Subnautica" or "Nautilus".

## Project Structure (typical)

```
MyAwesomeMod/
├── Plugin.cs          # Entry point with [BepInPlugin]
├── MyAwesomeMod.csproj
└── ...
```

**Important:** If using Nautilus, add the dependency attribute:

```csharp
[BepInDependency("com.snmodding.nautilus")]
[BepInPlugin(PluginInfo.PLUGIN_GUID, PluginInfo.PLUGIN_NAME, PluginInfo.PLUGIN_VERSION)]
public class Plugin : BaseUnityPlugin
{
    // ...
}
```

## Building and Testing

1. Build the project (`dotnet build` or IDE build).
2. Copy the output `.dll` from `bin/Debug/net.../` into `Subnautica/BepInEx/plugins/`.
3. Launch the game and check the BepInEx log.

## Tips

- Use Harmony for patching game methods.
- Reference the Nautilus XML documentation (included with the library) for IntelliSense.
- For custom assets, see the official Nautilus Asset Bundles guide.
- Always test on a clean save when possible.

See the official [Development Setup Guide](https://subnauticamodding.github.io/Nautilus/guides/dev-setup.html) for the most up-to-date details.
