# Rapid Fire GM Holden T43

**Prerelease software by Rapidfire.** Reads and enrolls compatible GM T43 controllers, writes calibration-only edits, and verifies the result by readback. Free personal and business use and free sharing of the complete, unmodified app with notices intact are permitted under the [application licence](LICENSE.txt). Application source is private; this repository contains public documentation and notices only.

## Recommended prerelease

[Download the 32-bit app — 0.4.106](https://github.com/RapidFire-001/rapid-fire-t43/releases/download/v0.4.106-x86/Rapid-Fire-T43-Protected-0.4.106-x86.zip) · [Release notes](https://github.com/RapidFire-001/rapid-fire-t43/releases/tag/v0.4.106-x86)

Download the versioned app ZIP above, rather than GitHub's automatically generated “Source code” archives. Those contain this documentation, not the application.

Extract the single executable to a writable folder and keep its supplied filename. First launch creates **Logs** and **VehicleEnrollments** beside it. Help, licences and the offline fault-code guide are embedded. Updates are manual downloads; the app has no automatic updater.

## Single 32-bit app and GM MDI drivers

The current download choice is **one 32-bit/x86 app**, for supported 32-bit and 64-bit Windows. Older x64 releases are superseded and are not supported for current MDI testing; they remain historical archives.

**The public 0.4.106 app retains its GT workflow. MDI/MDI 2 support is a local, hardware-unverified candidate and is not added to the old public binary by choosing x86.** In the local 32-bit candidate, MDI and MDI 2 require an installed compatible **32-bit J2534 provider**. Match the provider to the app, not to Windows: the original Bosch MDI provider checked on our test PC is 32-bit, so a 64-bit app cannot load it. Other vendor/provider configurations may differ. Driver registration does not confirm a connected unit or qualify vehicle reading/writing.

## Compatibility

- Installed OS **24256125** and **24267577**, with compatible boot/program code, layout and checksums. Each vehicle requires its own read and enrollment. Matching an OS number alone is insufficient.
- Windows 11 has recorded test evidence. Windows 10 is expected with .NET Framework 4.8 and a compatible OBDX Pro GT USB driver, but has not been separately qualified. Windows 7 has user-reported testing with complete environment/operation details. Windows XP is incompatible with this build. macOS and Linux are not supported.
- Use the supplied 32-bit app on supported 32-bit or 64-bit Windows. There is no separate current x64 choice. Historical x86-on-x64 host tests do not qualify every Windows installation.

## Limits

Only calibration data is programmed; this is not an OS, boot, program or EEPROM flasher. Independent verification follows the guided ignition cycle. Recovery and Security linking are disabled. The app does not establish whether tuning values are suitable for driving.

Vehicle fault-code coverage is participating OBD responders plus TCM current/history, not every module. Whole-network clearing requires a fresh report and separate confirmation; permanent codes may remain. Request/acknowledgement/rescan evidence does not prove every stored fault can be removed. The offline guide defines 15 selected transmission codes; other codes are still shown without guessed descriptions.

Read Help before connecting. Use stable vehicle power and follow the in-app prompts. Keep preserved originals and enrollment records. Do not intentionally interrupt programming.

[Quick start](QUICKSTART.md) · [Testing and compatibility](COMPATIBILITY.md) · [Release history](CHANGELOG.md) · [Licence](LICENSE.txt) · [Third-party notices](THIRD-PARTY-NOTICES.txt)

Copyright (c) 2026 Rapidfire. All rights reserved, subject to applicable third-party terms.

The approved whole-app distribution terms are provided in this repository and apply to the exact releases identified in their notes. Version 0.4.106 embeds the approved whole-app terms alongside the Boot Block and third-party notices.
