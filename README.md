# OpenGL C++ Template

A clean, scalable starter template for OpenGL projects using **C++**, **CMake**, and **vcpkg**. 

## Features

- **Modern CMake** setup with `CMakePresets.json` for seamless cross-platform configuration.
- **vcpkg Integration** for effortless dependency management (pre-configured with `glfw3`, `glad`, and `glm`).
- **Scalable Structure** using a dedicated `src/CMakeLists.txt` to keep your project organized as it grows.
- **Include Directory** pre-configured for your custom header files.
- **Strict Compiler Warnings** enabled by default to encourage best practices.

## Prerequisites

1. **C++ Compiler** (Visual Studio MSVC, GCC, or Clang).
2. **CMake** (3.21 or newer).
3. **vcpkg** installed on your system.
4. **Ninja** build system (optional, but recommended and used by the default presets).

## Setup

### 1. Set Environment Variable

Ensure you have an environment variable named `VCPKG_ROOT` pointing to your vcpkg installation folder. CMake will use this to find the vcpkg toolchain.
- *Windows Example:* `C:/dev/vcpkg`
- *Linux/Mac Example:* `~/vcpkg`

### 2. Create a New Project

Click the green **"Use this template"** button on GitHub to create a new repository from this starter code, or clone it directly.

### 3. Build & Run

**Using Visual Studio / VS Code (Recommended):**
Open the folder in your IDE. CMake should automatically detect the CMakePresets.json file. Select the x64-debug (or x64-release) preset, configure, and build.

**Using Command Line:**

```bash
# Configure the project using the preset
cmake --preset x64-debug

# Build the project
cmake --build --preset x64-debug

# Run the executable (Windows)
./out/build/x64-debug/opengl-cpp-template.exe

# Run the executable (Linux/Mac - if presets are added)
./out/build/linux-debug/opengl-cpp-template
```

## Adding New Source Files

This template uses the recommended "subdirectory" approach for CMake.

When you want to add a new `.cpp` file (e.g., `camera.cpp`), simply:

1. Place the new file inside the `src/` folder.
2. Open src/CMakeLists.txt.
3. Add the filename to the `add_executable` list, right below `main.cpp`:

```cmake
add_executable(${PROJECT_NAME} 
    main.cpp
    camera.cpp
)
```
