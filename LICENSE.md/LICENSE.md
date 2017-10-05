Changes since version 3.7.1 (5th October 2017):
- Fixed crashing when injector is run with .NET Framework 4.7
- Added manual map support for Windows 10 Insider Preview Build 17004

Changes since version 3.7 (28th April 2017):
- Fixed manual map and LdrpLoadDll support for Windows 10 Creators Update
- Fixed critical bug relating to imports resolution (issues when the same module is imported multiple times)
- Fixed bug that led to many handles being opened unintentionally
- Migration of Visual C++ resources and version checking to GitHub for more transparency

Changes since version 3.6 (5th September 2015):
- Fixed manual map support for Windows 8.1 (for real this time)
- Updated file host for Visual C++ dependencies
- Added more aggressive dependency resolving of Microsoft DLLs (fixes SystemFunction036 in advapi32.dll)

Changes since version 3.5/3.5.1/3.5.2 (31st July 2015):
- Fixed exception that occurs on DEP enabled processes on Windows 10.
- Fixed bug with GUI under Advanced Options for injection.
- The Disable SEH Validation option now actually does what it says.
- Fixed critical bug relating to code that resolves exports for Windows 10 modules.
- Fixed bug where exception would be thrown when no export function parameters were specified.
- Fixed manual map support for Windows 8.1 (broken in 3.4).

Changes since version 3.4 (29th July 2015):
- General stability fixes (crashes with 64-bit).
- Updated compatbility with Windows 8.1 and 10 (blame Microsoft and their compatibility "fixes").
- Secure Mode now closes previous instance.
- Fixed critical bug that would have prevented hacks using exception handlers (mainly packed/protected DLLs) from working in manual map mode.
- Added DirectX dependency detection.
- Added the ability to call exported functions after injection (use the ... button next to the listed DLL)
- Added a simple update notification.

Changes since version 3.3 (17th June 2014):
- Fixed bug where 1 CPU core was used because the injector was waiting for *itself* to close (no, it wasn't because of a RAT).
- Fixed bug where attempting to unload a module on a 64-bit process resulted in an exception.
- Fixed bug where the injector threw an exception from writing a scrambled DLL that was in use.
- Added support for LdrpLoadDll on Windows 8.1 Update 1 (64-bit).
- Added missing dependency required for ZIP extraction to work correctly (made the injector crash during Visual C++ Debug dependency installation).
- Added a threads list to the process information window.
- Added a new "Strip section characteristics" option to the Extreme preset of scrambling options.
- Added a new "Shift section memory" option to the Extreme preset of scrambling options, should *significantly* improve the ability for hacks to evade anti-cheat detection. This option is much more powerful on 32-bit DLLs, but is still somewhat effective on 64-bit DLLs.

Changes since version 3.2 (9th June 2014):
- Fixed bug where auto-inject did not seem to work
- Addressed possible crashing from messages failing to display during injection

Changes since version 3.1 (3rd June 2014):
- Fixed bug where a message box would appear randomly if a Visual C++ dependency was missing (leftover from testing code)
- Fixed bug where selecting "No" from the prompt under Advanced in Injection Method would untick the wrong box
- Injector now displays a message box saying that injection was successful

Changes since version 3.0 (31st May 2014):
- Complete rewrite from scratch (same and familiar look from previous versions)
- All injection techniques are now 100% compatible with 64-bit DLLs
- Drag-and-drop fixed when run as administrator on newer OSes
- Automatically elevates without asking if it knows you have administrator rights
- Better scaling on displays with a DPI higher than 96
- Added a Visual C++ Dependency Installer
- Manual map now supports DLLs that use SEH to work (better packer support, eg. Themida, Enigma, etc)
- New injection technique: LdrpLoadDll
- Better exception/error reporting
- New scrambling engine, more scrambling methods
- Removed "Append Random Data" as it just wasted disk space and is ineffective
- Improved detection of different OS versions
- Dynamic assembly code generation (powered by AsmJit)
- Seperate process, thread and window manager, does not rely on .NET Process class anymore
- "Start in Secure Mode" creates an even more "secure" instance of Extreme Injector
