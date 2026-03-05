# Building Minecraft Ultimate Edition

This guide provides instructions for compiling the Minecraft Ultimate Edition project.

## Prerequisites

- Visual Studio 2022 (for .sln builds)
- CMake 3.24 or later (for CMake builds)
- Windows 10 or later (64-bit)

Note: Building is currently only supported on Windows. Contributors using macOS or Linux will need access to a Windows machine or virtual machine.

## Method 1: Visual Studio Solution

1. Launch Visual Studio 2022.
2. Open the solution file: `MinecraftConsoles.sln`.
3. In the Solution Explorer, right-click `Minecraft.Client` and select "Set as Startup Project".
4. Choose the build configuration:
   - Debug (recommended for development)
   - Release (for optimized builds)
5. Set the platform to `x64`.
6. Build the solution: `Build > Build Solution` (or press `Ctrl+Shift+B`).
7. Run the project: Press `F5` to start debugging.

## Method 2: CMake Build System

### Configuration

Run the following command in PowerShell to configure the build:

```powershell
cmake -S . -B build -G "Visual Studio 17 2022" -A x64 -DCMAKE_GENERATOR_INSTANCE="C:/Program Files/Microsoft Visual Studio/2022/Community"
```

### Building

For Debug build:

```powershell
cmake --build build --config Debug --target MinecraftClient
```

For Release build:

```powershell
cmake --build build --config Release --target MinecraftClient
```

### Running

Navigate to the build directory and execute the binary:

```powershell
cd build\Debug
.\MinecraftClient.exe
```

## Important Notes

- The CMake build system is restricted to Windows x64 platforms.
- Asset files are automatically copied post-build for the `MinecraftClient` target in both Debug and Release configurations.
- The application uses relative paths for assets (e.g., `Common\Media\...`), so it must be launched from the output directory.
- For running on non-Windows systems, consider using Wine, though build support is not available.
