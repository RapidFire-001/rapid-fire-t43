# GM T43 quick start - 0.4.233 public pre-release

[Illustrated 0.4.233 guide and historical booklet](GM-T43-User-Guide-0.4.233.pdf) · [Full help](HELP.md) · [Compatibility](COMPATIBILITY.md)

## Clean first use

1. Extract the separate 0.4.233 package to a writable folder. It contains no customer enrollment, original BIN, logs or standalone OS image. Do not copy another controller's enrollment into it.
2. Connect one supported adapter: **OBDSync**, **OBDX Pro GT / GT Pro**, or **original GM MDI**. Each uses its own transport. The MDI needs its compatible 32-bit J2534 provider.
3. Confirm stable power, ignition ON, engine OFF, then select the exact adapter and run **Identify controller**.
4. Choose **Save OS** and complete the full read. For an unlisted OS, the app performs a local image evaluation before it will offer enrollment. The read must pass the T43 layout, checksum, program-integrity and recognized boot/helper checks.
5. Complete the live VIN and OS confirmation to create the enrollment for this controller. Keep an independent copy of its complete original BIN.
6. For calibration changes, edit a copy of that complete original, load it and choose **Write calibration**. The app matches the live controller to the enrollment, checks the source image, requires confirmation and verifies by readback.
7. For calibration recovery, use the saved original for the same enrolled controller. For an OS change, choose a complete supplied BIN, review the checks and complete readback. The existing boot area and EEPROM are preserved.

An unlisted OS is not automatically approved for every operation. If evaluation or identity matching fails, stop and keep the report. Image checks do not establish vehicle performance.

## Notes for existing installations

The 0.4.233 clean package starts fresh. Before replacing an existing installation, preserve its complete data folder, including VehicleEnrollments, saved originals and Logs. Keep the supplied executable name. The release-integrity seal is not a Windows publisher certificate.

For command details, recovery routes and evidence limits, use the [full help](HELP.md).
