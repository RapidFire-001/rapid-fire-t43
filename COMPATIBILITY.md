# GM T43 compatibility and coverage

Applies to **0.4.216**. Eligibility is based on the T43 controller, firmware and requested operation. The old two-OS and VE/VF-only descriptions do not describe this release.

## Available operations

| Operation | What the app requires |
|---|---|
| Identify controller | A valid response from the connected T43. An unlisted OS can be displayed. |
| Save OS / enroll | An enabled read profile and supported firmware/helper method; the completed image must pass validation. |
| Write calibration | A supported profile, compatible full source image, the connected vehicle's enrollment and matching OS/program/protected data. |
| Restore saved calibration | A unique matching completed original for the connected vehicle, with the live protected firmware checked before writing. Both responding and direct recovery entry are available. |
| Change OS / restore original | A supported full image and programming method. The owner supplies the target BIN; each controller uses its own saved original. Matching bytes or OS numbers alone do not establish hardware interchangeability. |
| Recover OS from BIN, no enrollment | A valid full T43 BIN, an accessible supported resident bootloader, explicit compatibility warning and confirmation. A working normal OS or previous enrollment is not required. |
| Three transmission adapt commands | A responding T43 with a valid OS identity; no catalogue or enrollment gate. The controller must accept the command. |
| Vehicle fault-code reading and clearing | A responding T43; no catalogue-only gate. Clearing also requires a recent complete saved scan, unchanged live vehicle/OS identity and confirmation. |
| VIN programming | A responding T43; no single-OS/catalogue gate. Valid current identity, a valid different new VIN, stable supply, confirmation and matching readback are required. |

Unknown OSs do not automatically gain full reading or calibration-write support merely because an adapt, diagnostic or VIN command succeeds. OS changes retain file, layout, boot-method and checksum checks.

## Included OS profile numbers

The app includes these 25 catalogue profiles. This list describes implemented profiles and reviewed files, **not 25 universally interchangeable or hardware-qualified OSs**. Some attempted swaps did not start normally on the tested controllers and were recovered to their originals. A failed swap does not prove that an OS cannot run on the hardware it was designed for.

| OS | OS | OS | OS | OS |
|---|---|---|---|---|
| 24237276 | 24237685 | 24239353 | 24240291 | 24243170 |
| 24244551 | 24249042 | 24249179 | 24251030 | 24252573 |
| 24253414 | 24254909 | 24256025 | 24256125 | 24257135 |
| 24261871 | 24264142 | 24264923 | 24265260 | 24267571 |
| 24267577 | 24268005 | 24270599 | 24276638 | 24294926 |

The public Tested OSs screen lists OS numbers. It does not require users to choose an early/later controller category or a reference boot group. Connect the controller and use its reported identity and the app's operation checks.

## Adapters and Windows

- **OBDX Pro GT / GT Pro and original GM MDI:** shared application workflows and eligibility rules. Recorded tests include successful reads, writes, matching readbacks and recovery on the tested controllers. These results are separate from target-OS compatibility.
- **Original GM MDI:** install its compatible 32-bit J2534 provider. The app uses its adapter-managed transfer path; a registered provider alone does not prove the physical unit is connected. Current recorded qualification is over USB; Wi-Fi and other providers are not newly qualified by this release.
- **MDI 2 and other devices:** not claimed as verified by these results.
- **Windows:** one x86 application, .NET Framework 4.8 and a suitable driver. Windows 11 has recorded host tests. Windows 10 is expected to work but is not separately qualified here. Windows 7 SP1 with .NET Framework 4.8 has owner-reported testing of an earlier build, not a fresh qualification of this release. XP, Linux and macOS are unsupported.

## What the evidence establishes

Archive analysis covered 652 files and 25 OS numbers. The native read/write implementations cover four reviewed boot-code variants. Software checks exercise all 25 profiles, helper behaviour, transfer plans, enrollment/source matching, recovery and readback. They do not establish that every OS will run on every T43.

Recorded hardware work includes full reads, calibration writes, OS changes, matching readbacks and restores, plus a successful full OS recovery without enrollment through the MDI. The owner's observed return to normal startup is recorded separately from readback. Current draw is an observation, not a universal diagnostic threshold or road/shift validation.

The final build passed regression, release-integrity, MDI cleanup, recovery-menu, progress, catalogue, adapt, diagnostic and VIN checks. The new unlisted-OS paths were exercised with software fixtures for acceptance, rejection, timeout, invalid identity and verification failures. This does not claim a live trial on every unlisted OS. The MDI interruption-cleanup correction passed fault simulations; a fresh physical cable-loss retest of that exact correction remains separate evidence.

## Remaining limits

Boot and EEPROM are preserved during OS/calibration programming. Recovery requires a working, accessible supported bootloader and a compatible BIN; damaged boot code is outside this app's repair scope. Readback verifies bytes, not tuning suitability, normal startup or transmission behaviour.

Diagnostics cover participating standard OBD responders and TCM current/history, not every vehicle module. Public clearing is a confirmed network operation; physical TCM-only clearing remains unavailable. Permanent codes may remain until their underlying conditions and required drive cycles are satisfied.

## Planned for the next build

These three functions are planned and **remain disabled in this release**:

1. **Guided Transmission Fast Learn** - the monitored learning procedure.
2. **Trans Clean** - the transmission cleaning procedure.
3. **Security linking** - controller security/linking support.

Trans Fast Adapt Reset is already available. It is a separate command and is not the guided Fast Learn procedure.

