README
======

This is the source code of the game [Enemy Nations](http://enemynations.com)
without the [content](http://timeoutd.net/EnemyNationsSource.rar).

There is also a [very old binary package](http://timeoutd.net/enemy_nations.iso.gz) available that I actually got working
in windows 7 and probably also in wine, but it requires some fiddling. 
Message me if you need help.

See license.txt for the license.

Goals
=====

Well, ultimately to port it to linux and update the graphics and udpade the
weird userinterface to something more usable. 
But step by step:

1. Update to compile with Visual C++ 2010 and remove CD check 
2. Port to Linux
3. Enhance rendering engine and graphics 
4. Enhance userinterface

--Marenz


Related
=======

There is also the [Enemy Nations Revival Project](http://groups.google.com/forum) which seems pretty dead though.


Building on modern Windows
==========================

The repository now ships with a CMake build that targets Visual Studio 2022
and replaces the original proprietary dependencies with source builds and
open stubs.  To build the game on Windows 10/11:

1. Install [Visual Studio 2022](https://visualstudio.microsoft.com/vs/) with
   the **Desktop development with C++** workload.  Make sure the optional MFC
   component is selected.
2. Install [CMake 3.20+](https://cmake.org/download/).  CMake is also bundled
   with recent Visual Studio installations.
3. Open a "x86 Native Tools Command Prompt for VS 2022" (the project still
   targets Win32) and configure the build:

   ```cmd
   cmake -S src -B build -A Win32
   ```

4. Build the solution from the command line or from the generated Visual
   Studio solution:

   ```cmd
   cmake --build build --config Release
   ```

The configuration stage builds the `windward` support library directly from
the sources under `windward/src` and links in stub implementations for the
Miles Sound System and VDMPlay networking APIs.  The game executable is
produced in the `build/Release` directory when building the Release
configuration.
