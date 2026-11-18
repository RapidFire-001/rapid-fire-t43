# GM T43 release history

## 0.4.216 - current Windows prerelease

[Download](https://github.com/RapidFire-001/rapid-fire-t43/releases/download/v0.4.216/GM-T43-for-Windows-0.4.216.zip) · [Release notes](https://github.com/RapidFire-001/rapid-fire-t43/releases/tag/v0.4.216)

This release replaces the older two-OS/vehicle-series description with controller and firmware-profile based support, and consolidates the following work since the previously published build:

- 25 native OS profiles integrated with the full reader and calibration writer, with supported boot/layout/helper and checksum checks.
- GT and original GM MDI read/write, readback and recovery workflows; automatic fast transfer paths retained.
- Reusable OS BIN selection, file-check details, recorded-operation verification and one Restore original button naming the saved OS, with responding/direct modes inside.
- Full OS/program and calibration recovery from a user-supplied BIN without enrollment; boot area and EEPROM preserved, compatibility warning and explicit confirmation retained.
- Single-action calibration recovery: one live protected-firmware read, automatic original matching and restoration on the same connection. Wrong OS/program/vehicle and missing/ambiguous originals stop before writing.
- Progress through preparation, countdown, write, restore and verification; live updates appear once beside the bar, with bytes, percentage and speed where available. Adapter-specific completion text.
- MDI interrupted-connection cleanup corrected to run once, retain the driver and original error, and reject sends after unconfirmed release. Interrupted attempts remain incomplete.
- Three adapt commands, fault-code reading/public network clearing and VIN programming available for responding T43s with unlisted OSs. Existing identity, confirmation, acknowledgement and verification requirements remain.
- Green public interface, searchable OS list, updated help and no preset owner or recovery image in a fresh package.

The exact build passed software regression and integrity checks. Recorded controller work supports the documented tested workflows; the expanded profiles and unlisted-OS cases include software-model evidence, not a live qualification of every hardware/OS combination. See [coverage](COMPATIBILITY.md).

## Planned for the next build

These three functions are planned and **remain disabled in this release**:

1. **Guided Transmission Fast Learn** - the monitored learning procedure.
2. **Trans Clean** - the transmission cleaning procedure.
3. **Security linking** - controller security/linking support.

Trans Fast Adapt Reset is already available. It is a separate command and is not the guided Fast Learn procedure.

## 0.4.156 - superseded

[Historical release](https://github.com/RapidFire-001/rapid-fire-t43/releases/tag/v0.4.156). Added the automatic faster original-MDI calibration transfer for the then-supported profiles and simplified transport controls. Use the current release above for OS changes, recovery and expanded support. Historical release notes describe that older binary only.

## Earlier development releases

Earlier releases introduced enrollment, calibration writing, independent readback, embedded Help/notices and local release-integrity sealing. Old architecture choices and capability statements are historical, not current recommendations. Private source, vehicle images, enrollments and development logs are not published in this repository.
