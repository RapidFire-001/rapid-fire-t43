# Rapid Fire GM Holden T43

**Prerelease software by Rapidfire.** Reads and enrolls compatible GM T43 controllers, writes calibration-only edits, and verifies the result by readback. Free personal and business use and free sharing of the complete, unmodified app with notices intact are permitted under the [application licence](LICENSE.txt). Application source is private; this repository contains public documentation and notices only.

## Recommended prerelease

> **Microsoft Edge download notice:** Edge may show a warning or block a download from this repository. If the page or download is unavailable in Edge, you can also open the official GitHub page in Firefox or Chrome. If your browser or antivirus flags a file as malware, please report the exact warning and the file name or release version so I can investigate.

[Download Rapid Fire T43 for Windows](https://github.com/RapidFire-001/rapid-fire-t43/releases/download/v0.4.156/Rapid-Fire-T43-for-Windows-0.4.156-test.zip) · [Release notes](https://github.com/RapidFire-001/rapid-fire-t43/releases/tag/v0.4.156)

**What changed in 0.4.156**

- Write Calibration automatically uses the faster transport with the original GM MDI on supported VE and VF T43 profiles.
- Removed the transport test button and trial checkbox. The device selector now displays **GM MDI**.
- The standard erase-and-write confirmation and full readback verification are required.

Download the versioned app ZIP above, rather than GitHub's automatically generated “Source code” archives. Those contain this documentation, not the application.

Extract the ZIP to a writable location, then open the executable inside the included Rapid Fire T43 folder. First launch creates **Logs** and **VehicleEnrollments** beside it. Help, licences and the offline fault-code guide are embedded. Updates are manual downloads; the app has no automatic updater.

## Diagnostic devices

Use a compatible diagnostic driver for the GT or original GM MDI (MDI 1). The original GM MDI requires a compatible 32-bit J2534 provider. Write Calibration automatically selects the faster MDI transport on supported VE and VF T43 profiles.

## Compatibility

- Installed OS **24256125** and **24267577**, with compatible boot/program code, layout and checksums. Each vehicle requires its own read and enrollment. Matching an OS number alone is insufficient.
- One download runs on compatible 32-bit and 64-bit Windows. Windows 11 has recorded test evidence. Windows 10 is expected to work with .NET Framework 4.8 and a compatible diagnostic driver. The project owner verified Windows 7 SP1 with .NET Framework 4.8 on an earlier build. Windows XP is unsupported.

## Limits

Only calibration data is programmed; this is not an OS, boot, program or EEPROM flasher. Independent verification follows the guided ignition cycle. Recovery and Security linking are disabled. The app does not establish whether tuning values are suitable for driving.

Vehicle fault-code coverage is participating OBD responders plus TCM current/history, not every module. Whole-network clearing requires a fresh report and separate confirmation; permanent codes may remain. Request/acknowledgement/rescan evidence does not prove every stored fault can be removed. The offline guide defines selected fault codes; other codes are still shown without guessed descriptions.

Read Help before connecting. Use stable vehicle power and follow the in-app prompts. Keep preserved originals and enrollment records. Do not intentionally interrupt programming.

[Quick start](QUICKSTART.md) · [Testing and compatibility](COMPATIBILITY.md) · [Release history](CHANGELOG.md) · [Licence](LICENSE.txt) · [Third-party notices](THIRD-PARTY-NOTICES.txt)

Copyright (c) 2026 Rapidfire. All rights reserved, subject to applicable third-party terms.

The approved whole-app distribution terms are provided in this repository and apply to the exact releases identified in their notes. Version 0.4.106 embeds the approved whole-app terms alongside the Boot Block and third-party notices.
