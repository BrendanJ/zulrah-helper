# Zulrah Helper

A standalone RuneLite plugin that provides overlays for the Zulrah boss fight. Extracted from [kotori-plugins](https://github.com/OreoCupcakes/kotori-plugins) and stripped of all automation — this plugin only reads game state and draws overlays.

## Features

- **Rotation detection** — identifies which of the four Zulrah rotations you're in
- **Phase tiles** — highlights where Zulrah will appear (current and next phase)
- **Stand/stall locations** — shows where to stand for each phase
- **Prayer helper** — displays which protection prayer to use, colored green/red based on whether you're praying correctly
- **Prayer marker** — highlights the correct prayer in your prayer book
- **Tick counters** — phase ticks, attack ticks, and total kill timer
- **Toxic cloud & projectile overlays** — highlights clouds and incoming projectiles
- **Prayer conservation** — reminds you when it's safe to turn off overheads

## What this plugin does NOT do

- No input automation (no auto-clicking, no auto-prayer switching)
- No packet sending
- No reflection-based game manipulation
- No dependency on KotoriUtils or any external plugin framework

All functionality is strictly read-only game state observation + overlay rendering.

## Requirements

- JDK 11 or higher
- IntelliJ IDEA (recommended) or any Java IDE

## Running

### From IntelliJ

1. Open the project as a Gradle project
2. Open `src/test/java/com/zulrahhelper/ZulrahPluginTest.java`
3. Run the `main` method

### From command line

```bash
./gradlew run
```

This launches RuneLite in developer mode with the plugin loaded. Enable "Zulrah Helper" in the RuneLite plugin panel.

## Origin

Extracted from the `zulrahoverlay` module of [OreoCupcakes/kotori-plugins](https://github.com/OreoCupcakes/kotori-plugins). The following changes were made during extraction:

- Removed `@PluginDependency` on KotoriUtils
- Removed snakeling entity hider (used reflection)
- Removed snakeling menu entry swapper (modified game menus beyond overlays)
- Replaced all KotoriUtils method calls with inline RuneLite API equivalents
- Fixed a config group name mismatch bug from the original code
- Repackaged to `com.zulrahhelper`
