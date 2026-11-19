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

## OS profiles grouped by recorded results

All **25 included OS profiles** are accounted for below. These groups show what was demonstrated on the actual test controllers; they are not a list of interchangeable OSs. The headings identify each controller by its saved-original OS, not a universal hardware family.

The app preserved each controller's existing boot area and EEPROM during these OS changes. A result applies to the tested target image on that controller. It does not approve every BIN bearing that OS number or every possible swap between the listed OSs.

### Working results: controller with saved original 24254909

| OS | Recorded result on this controller |
|---|---|
| **24254909** | Saved original; successful restoration and matching full readback recorded. |
| 24252573 | Candidate write followed by matching full readback. |
| 24256025 | Candidate write followed by matching full readback. |
| 24257135 | Candidate write followed by matching full readback. |
| 24264142 | Candidate write followed by matching full readback. |
| 24264923 | Candidate write followed by matching full readback. |
| 24265260 | Candidate write followed by matching full readback. |
| 24270599 | Candidate write followed by matching full readback. |
| 24276638 | Candidate write followed by matching full readback after interrupted attempts. |
| **24294926** | Candidate write followed by matching full readback on the completed retest. |

This is the saved original plus **nine verified candidate OSs**. These nine successes do not establish their compatibility with the controller whose saved original is 24267577.

### Working results: controller with saved original 24267577

| OS | Recorded result on this controller |
|---|---|
| **24267577** | Saved original; successful restoration, recovery and matching full readback recorded. |
| **24256125** | OS change from 24267577 followed by matching full readback in the public-app test. |

For example, **24256125 was verified on the 24267577 controller**, while **24294926 was verified on the 24254909 controller**. Those results do not establish a 24256125-to-24294926 swap or that every controller reporting one of those OS numbers has interchangeable hardware.

### Earlier prepared-image successes

| OS | Scope of the earlier record |
|---|---|
| 24239353 | A prepared image was recorded as verified on the earlier validation controller. |
| 24243170 | A prepared image was recorded as verified on the earlier validation controller. |
| 24251030 | A prepared image was recorded as verified on the earlier validation controller. |
| 24261871 | A prepared image was recorded as verified on the earlier validation controller. |

These earlier release records are separate from the later stock-image trial batch. They do not establish that every archive variant can be substituted on either of the controllers above.

### Unsuccessful combinations

| Target OS | Controller with original 24254909 | Controller with original 24267577 |
|---|---|---|
| 24237276 | Identification rejected after write; failed startup reported. | Identification rejected after write; failed startup reported. |
| 24237685 | Identification rejected after write; failed startup reported. | No attempt recorded in this batch. |
| 24240291 | Completed retest write, then identification rejected. | Identification rejected after write. |
| 24244551 | Identification rejected after write. | Transfer accepted; no matching readback result saved. **Not a verified success.** |
| 24249042 | Identification rejected after write. | Identification rejected after write. |
| 24249179 | Completed retest write, then identification rejected. | Identification rejected after write. |
| 24253414 | Completed retest write, then identification rejected. | Identification rejected after write. |
| 24267571 | Failed normal startup reported in the earlier trial; original recovered. | Failed normal startup reported in the earlier trial; original recovered. |
| 24268005 | Identification rejected after write. | Identification rejected after write. |

The owner also reported failed normal startup during the unsuccessful trials. An accepted transfer alone is not a working result. A failed combination on these controllers does not prove that the OS cannot work on its intended hardware.

**Unrecorded pairings remain unverified.** In particular, do not infer that 24254909 can be exchanged with 24268005, or that 24256125 and 24294926 are interchangeable, merely because all appear in the app.

The public Tested OSs screen lists included OS numbers; this page supplies the recorded outcome and controller context. Connect the controller, save its own original where possible, and use the app's operation checks. A shared boot-code fingerprint or successful software-model check is not a substitute for a demonstrated working combination.

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

