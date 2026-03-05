# Minecraft Ultimate Edition

![Minecraft Ultimate Edition](.github/MUE_Image.png)

## Overview

Welcome to **Minecraft Ultimate Edition**! This repository houses an enhanced version of the Minecraft Legacy Console Edition source code (specifically based on v1.6.0560.0/TU19). We have taken the originally archived codebase and integrated a variety of crucial fixes, modern optimizations, and requested features to improve the overall experience.

---

## Supported Platforms

- **Windows:** Fully supported for both building the project from source and running the game natively.
- **macOS / Linux:** Potentially supported in the future though not essential

---

## Key Features & Improvements

We've brought the classic console experience to modern setups with the following enhancements:



---


## Latest Release: v0.1 Beta

### Overview
This is the initial beta release of Minecraft Ultimate Edition, providing a Windows port of the Minecraft Legacy Console Edition (based on v1.6.0560.0/TU19).

### Key Features
- Functional Windows port with core gameplay intact
- Basic mouse input support
- Enhanced build system and modern optimizations
- **Modern Toolchain:** Fully supports compilation and execution in both Debug and Release modes on Windows using Visual Studio 2022.
- **Native PC Controls:** Added full keyboard and mouse input support.
- **Dynamic Display:** - Automatically adapts to your device's native screen resolution, dropping the hardcoded 1920x1080 limit.
  - Fullscreen mode support included (toggle effortlessly via `F11`).
- **Performance Tweaks:** - Integrated a high-resolution timer on Windows to ensure smoother, high-FPS gameplay.
  - Disabled V-Sync to uncap performance (currently Work In Progress).
- **Multiplayer Ready:** Built-in LAN Multiplayer with automatic network discovery.
- **Player Identity:** Persistent username integration via a simple `username.txt` file.

## Multiplayer Guide

Enjoy seamless local multiplayer on the Windows build, powered by infrastructure adapted from [LCEMP](https://github.com/LCEMP/LCEMP/). 

- **Effortless Hosting:** Starting a multiplayer world will automatically broadcast your session across your local network.
- **Easy Joining:** Players on the same LAN will see your game appear dynamically in the in-game "Join Game" menu.
- **Network Details:** Standard game connections are routed through TCP port `25565`, while LAN discovery broadcasts on UDP port `25566`.

### Command Line Arguments

You can customize your launch experience using the following arguments:

| Argument             | Description                                                                                                    |
|----------------------|----------------------------------------------------------------------------------------------------------------|
| `-name <username>`   | Overrides `username.txt` and sets your in-game player name.                                                    |
| `-server`            | Launches the application as a headless dedicated server instead of the standard game client.                   |
| `-ip <address>`      | **Client:** Manually connect to a specific IP.<br>**Server:** Override the bind IP set in `server.properties`. |
| `-port <port>`       | **Client:** Override the target join port.<br>**Server:** Override the listening port set in `server.properties`.|

**Example Usage:**
`MinecraftUltimateEdition.exe -name Steve -ip 192.168.1.50 -port 25565`


### Known Issues
- Multiple bugs present in this early beta version
- Limited feature completeness compared to the original console edition
- Performance optimizations are still in progress

### Installation
- Build from source using the provided [compile instructions](COMPILE.md)
- Requires Windows 10 or later (64-bit)

### Future Plans
- Comprehensive bug fixes and stability improvements
- Additional features and gameplay enhancements
- Changes to the rendering engine from OpenGL to Vulkan to modernize for performance, fancy graphics, and RTX support