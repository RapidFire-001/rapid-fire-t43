# GM T43 release history

## 0.4.233 - separate public pre-release candidate

This candidate is documented on its own branch and does not replace the published 0.4.216 release on the main branch.

- Adds OBDSync as a supported adapter through its own transport path.
- Adds local structural evaluation for unlisted OS images before enrollment.
- Binds a successful new enrollment to the full image and live VIN/OS identity.
- Keeps calibration writes, recovery and OS changes tied to the evaluated controller image and matching saved original.
- Includes a fresh-start package with no customer enrollments, saved originals, logs or standalone OS BINs.
- Adds a new illustrated PDF supplement and current compatibility/help documentation. The original 0.4.216 booklet is retained in the updated PDF as a clearly labeled historical appendix.

The candidate's new evaluator is scoped to the image layout, integrity checks and boot/helper ABI recognized by the build. It does not claim universal compatibility or vehicle-performance qualification.

## 0.4.216 - published GitHub prerelease

[Download](https://github.com/RapidFire-001/rapid-fire-t43/releases/download/v0.4.216/GM-T43-for-Windows-0.4.216.zip) · [Release notes](https://github.com/RapidFire-001/rapid-fire-t43/releases/tag/v0.4.216)

The published documentation and application remain available on the main branch. Historical claims for 0.4.216 do not describe the added OBDSync support or unlisted-OS evaluation in 0.4.233.

## 0.4.156 - superseded

[Historical release](https://github.com/RapidFire-001/rapid-fire-t43/releases/tag/v0.4.156). Earlier release descriptions are not current recommendations.

Earlier development releases introduced enrollment, calibration writing, independent readback, embedded Help/notices and local release-integrity sealing. Private source, vehicle images, enrollments and development logs are not published in this repository.
