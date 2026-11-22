# GM T43 compatibility and scope - 0.4.233 public pre-release

This candidate documents OBDSync as a supported adapter and adds a local structural evaluation path for unlisted OS images. It remains separate from the published 0.4.216 main release. Eligibility is determined by the T43 identity, requested operation, image checks and adapter-specific transport.

## Adapter support

| Adapter | Transport in this app | Notes |
|---|---|---|
| OBDSync | OBDSync's own USB/DVI transport path | Added as a selectable supported adapter in 0.4.233. Do not substitute OBDX drivers or infer support from shared ownership. |
| OBDX Pro GT / GT Pro | Existing OBDX transport | Its driver and connection setup are specific to the OBDX device. |
| Original GM MDI | Adapter-managed 32-bit J2534 provider | Provider registration alone does not prove that a physical MDI is connected. |

Adapter availability does not make every operation suitable for every controller. The app checks the live identity and chosen operation before proceeding.

## Operation requirements

| Operation | Requirements |
|---|---|
| Identify T43 | Valid live T43 response and adapter session. An unlisted OS may be reported. |
| Save OS | Complete supported read. A catalogue OS uses its reviewed profile. An unlisted OS uses local evaluation and must pass all image and boot/helper checks. |
| Enroll | Completed read, verified full image, and matching live VIN and OS from the same controller. The original is preserved for that enrollment. |
| Calibration write | Source must match the enrolled controller's OS, program, boot and segment identities. Only calibration segments are written. Confirmation and independent readback are required. |
| Calibration recovery | Matching saved original for the installed controller. Nonresponsive recovery uses the direct recovery transaction; it does not send a diagnostic preflight before calibration transfer. |
| Change OS / OS recovery | Complete supplied T43 BIN, supported layout and loader checks, explicit confirmation, preservation of the existing boot area and EEPROM, and readback verification. |
| Adapt functions | A responding T43 with valid identity. The selected controller must accept the command. |
| VIN programming | Live T43 identity, valid new VIN, confirmation and readback verification. |
| Vehicle fault codes | A responding controller. Coverage is limited to participating standard responders and the TCM. Clearing needs a fresh complete report, matching live identity and confirmation. |

## Local evaluation for unlisted OSs

The evaluator does not run an unknown image. It checks the completed 2 MiB read for a valid T43 OS value, the expected calibration-segment layout and headers, calibration checksums, program CRC and word-sum integrity, and a boot/helper ABI already recognized by this build.

If any required check fails, enrollment or programming does not proceed. If checks pass, the app can enroll the exact image against the live controller identity. A structural pass does not mean that the OS is a vehicle-compatible calibration or that it will operate correctly on every T43.

## Built-in catalogue

The app retains 25 reviewed profile entries for catalogued read/program paths. These are profile identifiers, not a universal interchangeability list.

| OS | OS | OS | OS | OS |
|---|---|---|---|---|
| 24237276 | 24237685 | 24239353 | 24240291 | 24243170 |
| 24244551 | 24249042 | 24249179 | 24251030 | 24252573 |
| 24253414 | 24254909 | 24256025 | 24256125 | 24257135 |
| 24261871 | 24264142 | 24264923 | 24265260 | 24267571 |
| 24267577 | 24268005 | 24270599 | 24276638 | 24294926 |

## Scope

The 0.4.233 app is a public pre-release. The new evaluator is limited to the image layout, integrity checks and boot/helper ABI recognized by this build. It does not guarantee support for every OS, boot variant, T43 hardware revision, vehicle or calibration. A passed readback does not prove normal startup or vehicle performance.

The earlier 0.4.216 guide remains appended to the 0.4.233 PDF for historical workflow reference. Its older adapter and OS-eligibility statements are superseded by this file and the 0.4.233 supplement.

Do not post VINs, raw BINs, enrollment files or unredacted logs in public issues.
