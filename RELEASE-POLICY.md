# GM T43 prerelease and update policy

The published GitHub release on the main branch remains version 0.4.216. The 0.4.233 public pre-release candidate is kept on a separate documentation branch until reviewed; its branch and draft pull request do not replace or alter the 0.4.216 release.

## What a public package contains

A clean application package contains the compiled app and public documentation/notices. It contains no user enrollment, original recovery image, VIN, controller BIN, private source, signing key or private logs. Built-in reference profiles required by catalogue paths remain embedded in the application. A new installation creates its own records only after a successful live read and identity confirmation.

GitHub's generated source archives contain the documentation repository, not the compiled application. The app is distributed as a separately named package. Preserve the supplied executable name and follow the applicable application and third-party terms.

## Version 0.4.233 candidate

This candidate adds OBDSync through its own transport path and local structural evaluation of unlisted OS images. A passed local evaluation enables enrollment of that specific read after live VIN/OS checks. It is not a universal compatibility approval.

Calibration writes, recovery and OS changes remain operation-specific and require the app's image, identity, confirmation and readback checks. A successful transfer, image evaluation or readback is not proof of normal startup or vehicle behaviour on every hardware revision.

The release records scope and support requirements. The updated PDF begins with a 0.4.233 supplement; its appended 0.4.216 booklet is retained as historical reference. For differences in adapter support or unlisted-OS eligibility, the 0.4.233 documentation controls.

## Updating and support

Updates are manual. Close the app while idle. Preserve the complete data folder, including Logs, VehicleEnrollments, saved originals and recovery/session records. Do not substitute another vehicle's enrollment or overwrite an operation in progress.

Support reports should include app version, Windows version, adapter and driver/provider version, controller OS if available, operation and stage. Keep raw BINs, VINs, enrollment records and unredacted logs out of public issues. Use the support contact in the README.

The embedded release seal is an integrity check, not a Windows publisher certificate or guarantee of universal compatibility. A withdrawn release will state the reason and affected version; do not treat switching versions as proof that an interrupted write completed.
