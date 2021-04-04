# GS+, modded to provide access to emulated memory
stacksmith: Memory is available as an 8.25MB shared block at $100000000.  It is also backed by a file 'RAM.bin' stored in the current (startup) directory.  Added benefit: upon crash, RAM.bin is a memory dump.

An Apple IIgs emulator based on KEGS

# Build instructions

## OS X dependencies
    brew install cmake pkg-config re2c sdl2 sdl2_image freetype

## Linux dependencies
    apt-get install re2c libsdl2-dev libsdl2-image-dev libfreetype6-dev libpcap0.8-dev

## WIN32 dependencies
Install MSYS2 (not MSYS, not cygwin)

32-bit build:

    pacman  -S re2c mingw-w64-i686-cmake mingw-w64-i686-SDL2 mingw-w64-i686-SDL2_image mingw-w64-i686-freetype

64-bit build:

    pacman  -S re2c mingw-w64-x86_64-cmake mingw-w64-x86_64-SDL2 mingw-w64-x86_64-SDL2_image mingw-w64-x86_64-freetype


## Linux, OS X, build
    mkdir build
    cd build
    cmake ..
    (optionally: ccmake .. to configure stuff)
    make


## Windows Build

### mingw SDL build
    mkdir build
    cd build
    cmake ../ -DDRIVER=SDL2 -DWITH_DEBUGGER=OFF -G "MSYS Makefiles"
    make GSplus.exe
### mingw GDI build

    mkdir build
    cd build
    cmake ../ -DDRIVER=WIN32 -DWITH_DEBUGGER=OFF -G "MSYS Makefiles"
    make GSplus.exe
