# GM T43

[Download the illustrated PDF booklet](GM-T43-User-Guide-0.4.216.pdf)

Windows software by Rapidfire for GM T43 transmission controllers: save and enroll an original, write calibration changes, change or restore the OS, recover from a supplied BIN, and verify by readback.

Support is determined by the connected T43 and its firmware profile, rather than a VE/VF vehicle label. The current app includes **25 OS profiles**, supports **OBDX Pro GT / GT Pro and the original GM MDI**, and offers adapts, fault-code reading/clearing and VIN programming without requiring the OS to appear in the catalogue. See [compatibility](COMPATIBILITY.md) for the requirements of each operation.

## Current Windows prerelease: 0.4.216

[Download GM T43 for Windows](https://github.com/RapidFire-001/rapid-fire-t43/releases/download/v0.4.216/GM-T43-for-Windows-0.4.216.zip) · [Release notes](https://github.com/RapidFire-001/rapid-fire-t43/releases/tag/v0.4.216) · [Quick start](QUICKSTART.md) · [Full user guide](HELP.md)

One **32-bit/x86 app** runs on compatible 32-bit or 64-bit Windows with .NET Framework 4.8 and the correct diagnostic-device driver. The original GM MDI requires a matching **32-bit J2534 provider**. MDI 2 and other adapters are not included in this release's verified adapter scope.

Extract the ZIP to a writable folder and keep the supplied executable filename. Download the named application ZIP, not GitHub's automatically generated source archives, which contain documentation only. The package starts with **no enrollment, saved vehicle, preset OS or recovery BIN**. Updates are manual.

## What is included

- **Save OS and enrollment:** a complete image from the connected controller, with its own preserved original.
- **Write calibration:** compatible calibration edits matched to the connected vehicle, enrolled original and installed OS/program, followed by readback verification.
- **Change OS:** select a full BIN without rebuilding the app. File checks and calibration differences are shown before confirmation.
- **Restore original:** one button names the saved OS; choose the responding-controller or direct-recovery path inside the confirmation.
- **Recover OS from BIN without enrollment:** supply a compatible full BIN when there is no usable enrollment or the normal OS cannot identify itself.
- **Calibration recovery:** one restore action checks the installed protected firmware once, finds the matching saved original and restores on the same connection. A mismatch stops before erase or write.
- **Transmission adapts:** Trans Adapt Reset, Trans Adapt Preset and Trans Fast Adapt Reset, including responding controllers with unlisted OSs.
- **Vehicle fault codes and VIN:** read/save a report, clear participating vehicle codes with confirmation, and program/verify a VIN; no single-OS or catalogue-only gate.
- **Clear progress and records:** preparation, acknowledged transfer and readback progress appear once beside the bar, with bytes, percentage and speed where applicable. Interrupted operations, accepted transfers and verified readbacks remain distinct.

## Before driving after a calibration change

The GM T43 workflow requires this checkpoint after the calibration write and its readback verification have passed. Open **Transmission Functions** and run the top three buttons in their displayed order:

1. **Trans Adapt Reset**
2. **Trans Adapt Preset**
3. **Trans Fast Adapt Reset**

Run one at a time, follow the displayed conditions and wait for each acceptance before continuing. **Complete all three before driving.** A rejection or timeout leaves the checkpoint incomplete; resolve it before proceeding. Also follow the vehicle-specific service procedure for operating conditions and any further relearn. These command acknowledgements do not establish a completed guided Fast Learn or road/shift validation.

## Recovery preserves the boot area

Calibration writes, OS changes and OS recovery **do not erase or program the existing boot area**. OS changes and recovery write the main program and calibration while preserving the controller's boot area and EEPROM, even when the chosen full BIN contains those regions.

A controller whose normal software will not start but whose supported bootloader still responds may be recoverable from a **soft-bricked / semi-bricked** state using a compatible BIN. This app does not repair damaged boot code. A passed file check or readback does not by itself prove that a different OS will start or operate correctly on that hardware.

## Planned for the next build

These three functions are planned and **remain disabled in this release**:

1. **Guided Transmission Fast Learn** - the monitored learning procedure.
2. **Trans Clean** - the transmission cleaning procedure.
3. **Security linking** - controller security/linking support.

Trans Fast Adapt Reset is already available. It is a separate command and is not the guided Fast Learn procedure.

## Use and support

Read the [user guide](HELP.md) before use. Keep stable power and connections during programming, follow the ignition prompts and preserve the entire application data folder when updating. The app reports the controller's actual acceptance, rejection or timeout; an available command is not a promise that every controller implements it.

Free personal/business use and sharing of the complete, unmodified application are permitted under the [application licence](LICENSE.txt). Source remains private; this repository contains documentation and notices. [Third-party notices](THIRD-PARTY-NOTICES.txt) remain applicable.

For help, email [Rapid Fire Software Support](mailto:support@rapidfiresoftware.net) with the application version, adapter, operation and error message. Keep raw BINs, VINs, enrollment files and unredacted logs out of public issues.

[Compatibility and coverage](COMPATIBILITY.md) · [Release history](CHANGELOG.md) · [Update policy](RELEASE-POLICY.md)

Copyright (c) 2026 Rapidfire. All rights reserved, subject to applicable third-party terms.
