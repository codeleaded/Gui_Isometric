# Project README

## Overview
- The project is a C-based application that renders an isometric tile map using graphical tiles. It includes support for different platforms including Linux, Windows (using Wine), and WebAssembly.

## Features
- Renders an isometric tile map.
- Supports mouse interaction to display the coordinates of tiles under the cursor.
- Uses a simple windowing system for rendering.

## Project Structure
- build/              # .exe files produced by Main.c
- src/                # Source code
│   ├── Main.c          # Entry point
│   └── *.h             # Standalone Header-based C-files, without *.c files that implement it
├── Makefile.linux      # Linux Build configuration
├── Makefile.windows    # Windows Build configuration
├── Makefile.wine       # Wine Build configuration
├── Makefile.web        # Emscripten Build configuration
└── README.md           # This file

### Prerequisites
- C/C++ Compiler and Debugger (GCC, Clang)
- Make utility
- Standard development tools
- Libraries needed in specific projects:
  - Linux: X11 for windowing
  - Windows: WINAPI
  - WebAssembly: Emscripten

## Build & Run
### Linux
To build and run the project on Linux:

```sh
cd /path/to/Gui_Isometric
make -f Makefile.linux all
make -f Makefile.linux exe
```

### Windows (using Wine)
To build and run the project on Windows using Wine:

```sh
cd /path/to/Gui_Isometric
make -f Makefile.wine all
WINEPREFIX=~/wine64 WINEARCH=win64 wine ./build/Main.exe
```

### WebAssembly
To build and run the project in the browser using Emscripten:

```sh
cd /path/to/Gui_Isometric
make -f Makefile.web all
emrun --no_browser --port 8080 ./build/index.html
```

### Build Options
- `make -f Makefile.(os) all`: Builds the output executable.
- `make -f Makefile.(os) do`: Builds and executes the output executable.
- `make -f Makefile.(os) clean`: Removes build artifacts.

Replace `(os)` with either `linux`, `windows`, `wine`, or `web` depending on your target platform.