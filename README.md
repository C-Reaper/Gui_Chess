# Project README

## Overview
The project is a simple chess game interface built using C/C++. The main functionality includes rendering a chessboard, handling user input for piece movement, and displaying the board's state. The project supports multiple build environments: Linux, Windows, Wine, and WebAssembly.

## Features
- Rendering of an 8x8 chessboard.
- Support for piece movement with basic validation (no capture or check/checkmate logic).
- Display of the current scale of the chessboard.
- Audio output through ALSA (Linux), user32 (Windows), and wine (Wine).

## Project Structure
The project consists of several directories and files:

### Prerequisites
- C/C++ Compiler and Debugger (GCC, Clang)
- Make utility
- Standard development tools
- Libraries needed in specific projects:
  - Linux: X11 for display, ALSA for audio.
  - Windows: WINAPI for display, user32 for audio.
  - Wine: wine32 for cross-compilation to Windows.

## Build & Run
To build and run the project, follow these steps:

### Linux
```bash
cd <Project>
make -f Makefile.linux all
./build/Main
```

### Windows
```cmd
cd <Project>
make -f Makefile.windows all
.\build\Main.exe
```

### Wine (Cross-compilation to Windows)
```bash
cd <Project>
make -f Makefile.wine all
WINEPREFIX=~/wine64 WINEARCH=win64 wine ./build/Main.exe
```

### WebAssembly (Emscripten)
```bash
cd <Project>
make -f Makefile.web all
emrun --no_browser --port 8080 build/index.html
```

The project includes four Makefiles for different build environments, ensuring compatibility across various platforms.