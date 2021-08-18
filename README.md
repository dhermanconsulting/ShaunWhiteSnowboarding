# ShaunWhiteSnowboarding
A patch to enable playing Shaun White Snowboarding on computers with >7 Cores (Including Hyperthreading).

When I attempted to play Shaun White Snowboarding I came accross a bug where it failed to launch. I eventually tracked this down to an issue with systems that have more than 7 logical cores - it appears that 8 and more cause some kind of buffer overflow due to how the game manages its thread memory. This is a patched version of the game executable which limits Shaun White to 7 Threads.

To use it:

1. Install Shaun White Snowboarding as normal
2. Update to version 1.01 (If you don't have this update, you can find it in this repo under "Releases": https://github.com/dhermanconsulting/ShaunWhiteSnowboarding/releases)
3. Overwrite the executable with the one from this repository
