This is MonoKickstart, a standalone Mono "kick" application to run C# programs on GNU/Linux and macOS without depending on a system installation of Mono.

# About MonoKickstart

Originally developed by Edward Rudd for Bastion, MonoKickstart is a reworking of the stock generated kickstart code from Mono to easily run C# applications on *nix platforms. macOS support was added in 2013 for MonoGame-SDL2 titles.

The project has been further maintain by Ethan Lee (flibitijibibo) for the need of FNA, and by Dean Ellis (dellis1972) for MonoGame.

# About this fork

This specific fork is tailored to the need of Flying Oak Games' projects (ScourgeBringer, NeuroVoider, Boo! Greedy Kid) but should fit any FNA or MonoGame project.

What it does differently is:
- It's based on Mono 5.20.1.19
- It uses the native library search paths ```x86``` ```x64``` on Linux, and to ```./``` on macOS
- It no longer support 32bit on macOS (since Mavericks is a requirement and only runs on 64bit CPU, we assumed it was useless to continue to support 32bit)

The requirements are:
- On Linux: _glibc >= 2.19_
- On macOS: _macOS >= 10.9 Mavericks_

# How to use / about the precompiled folder

We have provided a precompiled MonoKickstart application for you to use in your programs. Included are kick binaries and libmono binaries for macOS and Linux (both x86 and x86_64 for Linux, and Universal Binaries for macOS, though limited to 64bit). We have also provided the
C# assemblies needed by MonoGame and FNA as well as a "./Kick" script to automatically choose the right binary for the operating system and architecture.

To use the precompiled MonoKickstart, simply rename the kick.bin.* binaries to the name of your .exe assembly (for instance, MyGame.bin.x86 starts MyGame.exe).
Additionally, modify "Kick" to run those newly named kick binaries rather than the generic "kick" name. The name of "Kick" itself can be whatever you like.

If you wish to use additional shared libraries (for instance, SDL2, OpenAL, or SteamAPI), simply add the library to the architecture's lib folder:

- Linux (32-bit): ```./x86```
- Linux (64-bit): ```./x64```
- macOS (Universal): ```./```

# License

**kick.c** is released under the zlib license. See LICENSE for details.

**binreloc** is released under the WTFPL license. See binreloc.LICENSE for details.

