# Rapid Fire GM Holden T43

**Prerelease software by Rapidfire.** Reads and enrolls compatible GM T43 controllers, writes calibration-only edits, and verifies the result by readback. Free personal and business use and free sharing of the complete, unmodified app with notices intact are permitted under the [application licence](LICENSE.txt). Application source is private; this repository contains public documentation and notices only.

## Recommended prerelease

[Download 0.4.105 for Windows x64](https://github.com/RapidFire-001/rapid-fire-t43/releases/download/v0.4.105/Rapid-Fire-T43-Protected-0.4.105.zip) · [Release notes](https://github.com/RapidFire-001/rapid-fire-t43/releases/tag/v0.4.105)

Download the versioned app ZIP above, rather than GitHub's automatically generated “Source code” archives. Those contain this documentation, not the application.

Extract the single executable to a writable folder and keep its supplied filename. First launch creates **Logs** and **VehicleEnrollments** beside it. Help, licences and the offline fault-code guide are embedded. Updates are manual downloads; the app has no automatic updater.

## Compatibility

- Installed OS **24256125** and **24267577**, with compatible boot/program code, layout and checksums. Each vehicle requires its own read and enrollment. Matching an OS number alone is insufficient.
- Windows 11 has recorded test evidence. Windows 10 is expected with .NET Framework 4.8 and a compatible OBDX Pro GT USB driver, but has not been separately qualified. Windows 7 has user-reported testing with incomplete environment/operation details. Windows XP is incompatible with this build. macOS and Linux are not supported.
- The download above is x64. [Download the x86 prerelease](https://github.com/RapidFire-001/rapid-fire-t43/releases/download/v0.4.105-x86/Rapid-Fire-T43-Protected-0.4.105-x86.zip) for the separately tested 32-bit executable. Testing an x86 executable on 64-bit Windows does not establish qualification of every 32-bit Windows installation.

## Limits

Only calibration data is programmed; this is not an OS, boot, program or EEPROM flasher. Independent verification follows the guided ignition cycle. Recovery and Security linking are disabled. The app does not establish whether tuning values are suitable for driving.

Vehicle fault-code coverage is participating OBD responders plus TCM current/history, not every module. Whole-network clearing requires a fresh report and separate confirmation; permanent codes may remain. Request/acknowledgement/rescan evidence does not prove every stored fault can be removed. The offline guide defines 15 selected transmission codes; other codes are still shown without guessed descriptions.

Read Help before connecting. Use stable vehicle power and follow the in-app prompts. Keep preserved originals and enrollment records. Do not intentionally interrupt programming.

[Quick start](QUICKSTART.md) · [Testing and compatibility](COMPATIBILITY.md) · [Release history](CHANGELOG.md) · [Licence](LICENSE.txt) · [Third-party notices](THIRD-PARTY-NOTICES.txt)

Copyright (c) 2026 Rapidfire. All rights reserved, subject to applicable third-party terms.

The approved whole-app distribution terms are provided in this repository and apply to the exact releases identified in their notes. The 0.4.105 binary is unchanged; its embedded Help still carries the existing Boot Block and third-party notices.
