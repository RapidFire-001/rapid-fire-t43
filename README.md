# GM T43

[Download the illustrated Windows user guide for the 0.4.233 candidate](GM-T43-User-Guide-0.4.233.pdf)

Windows software by Rapid Fire for GM T43 transmission controllers. This repository contains public documentation and notices; application source, customer data and signing material are not included.

## Published GitHub release

The release on the main branch remains **0.4.216**: [application ZIP](https://github.com/RapidFire-001/rapid-fire-t43/releases/download/v0.4.216/GM-T43-for-Windows-0.4.216.zip) · [release notes](https://github.com/RapidFire-001/rapid-fire-t43/releases/tag/v0.4.216).

## Separate public pre-release candidate: 0.4.233

This documentation branch describes the **0.4.233 public pre-release candidate** separately from the existing 0.4.216 release. The new guide starts with the 0.4.233 update, then retains the earlier illustrated booklet as a clearly labeled historical reference. The published main release and its files are unchanged.

Version 0.4.233 adds **OBDSync as a supported adapter**, using its own transport path. It also adds local structural evaluation for T43 OS images that are not in the built-in profile catalogue. A full read can be enrolled only after the image and live identity checks pass. Later calibration writes, recovery and OS changes remain tied to the connected controller's evaluated image and enrollment.

A clean 0.4.233 package starts without customer enrollments, saved originals, session logs or standalone OS BINs. Built-in reference profiles stay embedded for catalogue paths. A fresh installation must complete its own live read and enrollment.

The binary candidate package is maintained separately from this documentation branch; this branch does not replace the current GitHub release asset.

## Operation and compatibility

Support is determined by the connected T43, the requested operation, and the exact adapter transport. OBDSync, OBDX Pro GT / GT Pro, and original GM MDI are separate adapter choices. The original MDI requires its compatible 32-bit J2534 provider.

- [Compatibility and scope](COMPATIBILITY.md)
- [Quick start](QUICKSTART.md)
- [Full help](HELP.md)
- [Release history](CHANGELOG.md)
- [Pre-release and update policy](RELEASE-POLICY.md)
- [Licence](LICENSE.txt)
- [Third-party notices](THIRD-PARTY-NOTICES.txt)

## Read before use

The unlisted-OS check evaluates file structure, calibration checksums, program integrity and the recognized boot/helper ABI. It does not prove that an OS is suitable for every T43 or vehicle. Preserve the original, use stable power, follow the app's operation confirmations and complete readback verification.

A passed file check or readback establishes image consistency for that operation. It does not establish calibration suitability, vehicle performance or universal compatibility.

Copyright (c) 2026 Rapid Fire. All rights reserved, subject to applicable third-party terms.
