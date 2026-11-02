# Compatibility and test coverage

| Area | Evidence and limits |
|---|---|
| Controller support | Installed OS 24256125 and 24267577 with compatible code and per-vehicle enrollment. Other OS versions and unknown code/hardware variants remain unsupported. No blanket support for every T43 or transmission model is claimed. |
| Recorded vehicle workflows | Full reading/enrollment, original and selected modified calibration writes, independent full readback, protected boot/program comparisons, monitored upload suppression and GT release were checked on the tested controllers. |
| General calibration acceptance | Alternate valid edits across all three calibration segments and incompatible-source rejection passed software models. This is not road/shift validation or proof of every possible calibration. |
| Configuration differences | Both profiles accept compatible per-vehicle configurations against their own original and reject cross-vehicle protected data in model checks. These checks do not qualify every car or firmware variant. |
| Fault clearing | Whole-network request/acknowledgement and automatic rescan workflows have evidence on the tested controllers. Some pre-clear lists were empty; actual stored-fault removal and every-module coverage are not established. TCM-only clearing remains unavailable. |
| Recovery and Security linking | Disabled; interrupted-write recovery needs bench validation, and security linking needs a known-good capture and testing. |
| Current packaging | Both exact architectures passed software regression and calibration-policy checks, isolated single-EXE startup/preservation, embedded Help/notices, resource auditing and 32 executable integrity cases. The packaging revision did not change vehicle protocol code or native helpers. |
| Windows 11 | Recorded host tests exercised x86 and x64 executables on 64-bit Windows. |
| Windows 10 | Expected compatibility with .NET Framework 4.8 and a compatible GT driver; not separately qualified. |
| Windows 7 | User reported testing. Exact service pack/build, architecture, framework/driver versions and read/write/verification coverage have not been supplied for independent reproduction. |
| Windows XP | Incompatible with the current framework API requirements. |

The app uses a local signed integrity seal. It is not a Windows publisher certificate, activation system or guarantee against reverse engineering. Integrity checks run before new operations, not as an integrity-triggered abort during active transfers. Keep the supplied executable filename.
