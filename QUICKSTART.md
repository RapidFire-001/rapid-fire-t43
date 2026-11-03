# Quick start

1. Download the single recommended 32-bit/x86 app ZIP linked in the README; use it on supported 32-bit or 64-bit Windows. Extract its single executable to a short writable folder; retain the filename. It needs the Windows .NET Framework runtime and the correct OBDX Pro GT USB driver.
2. Read the embedded Help before starting. First launch creates Logs and VehicleEnrollments; there is no automatic vehicle operation or internet requirement.
3. Connect and select the GT. Keep ignition on, engine off, stable battery support and other diagnostic apps disconnected. Follow setup and voltage checks.
4. Use Save OS and complete enrollment. Preserve the first original. Edit a separate full BIN in TunerPro with the matching XDF.
5. Load the edited BIN. Write calibration performs compatibility and non-erasing preparation, followed by a guided ignition cycle and a separate erase-and-write confirmation. Keep power and cables steady during an active operation.
6. Complete the guided post-write ignition cycle and automatic readback. Only a matching comparison becomes Verified. Failed or incomplete comparisons retain their evidence; do not assume Accepted means Verified.

To update, close the idle app and back up Logs and VehicleEnrollments. Put the newly downloaded executable into the same writable folder, retaining its supplied filename. Keep records and preserved originals; do not copy another vehicle's enrollment. Consult Help if Windows-user-bound records need moving. There is no automatic updater.

If an operation stops, retain its report and ask for guidance before retrying. Do not post raw BINs, VINs, enrollment files or unredacted logs publicly. A diagnostic code is a reported condition, not proof that a specific part needs replacement.

The public app's current workflow uses GT. Local MDI/MDI 2 candidates require a compatible installed 32-bit J2534 provider and separate hardware validation. Do not use an old x64 release for MDI testing. See [compatibility](COMPATIBILITY.md) for the distinction between public and candidate capabilities.
