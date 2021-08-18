# Shaun White Snowboarding Processor Fix
A patch to enable playing Shaun White Snowboarding on computers with >7 Logic Cores (i.e. Including Hyperthreading).

When I attempted to play Shaun White Snowboarding again it failed to launch. I eventually tracked this down to an issue with systems that have more than 7 logical cores - it appears that 8 and more cause some kind of buffer overflow due to how the game manages its thread memory. This is a patched version of the game executable which limits Shaun White to 7 Threads.

To use it:

1. Install Shaun White Snowboarding as normal
2. Update to version 1.01 (If you don't have this update, you can find it in this repo under "Releases": https://github.com/dhermanconsulting/ShaunWhiteSnowboarding/releases)
3. Overwrite the executable with the one from this repository: https://github.com/dhermanconsulting/ShaunWhiteSnowboarding/raw/main/ShaunWhiteSnowboardingGame-Patched.exe

NOTE: The **only** change to this executable is a single line of assembly.

# Manual Patch

Using a hex editor, locate the following Hex string:

FF 15 C0 62 5C 01 8B 4C 24 30 8B 54 24 48

Replace with:

FF 15 C0 62 5C 01 B9 07 00 00 00 90 90 90
