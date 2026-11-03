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

## Single 32-bit app and GM MDI drivers

The current download choice is **one 32-bit/x86 app**, for supported 32-bit and 64-bit Windows. Older x64 releases are superseded and are not supported for current MDI testing; they remain historical archives.

**The public 0.4.106 app retains its GT workflow. MDI/MDI 2 support is a local, hardware-unverified candidate and is not added to the old public binary by choosing x86.** In the local 32-bit candidate, MDI and MDI 2 require an installed compatible **32-bit J2534 provider**. Match the provider to the app, not to Windows: the original Bosch MDI provider checked on our test PC is 32-bit, so a 64-bit app cannot load it. Other vendor/provider configurations may differ. Driver registration does not confirm a connected unit or qualify vehicle reading/writing.

The app uses a local signed integrity seal. It is not a Windows publisher certificate, activation system or guarantee against reverse engineering. Integrity checks run before new operations, not as an integrity-triggered abort during active transfers. Keep the supplied executable filename.
