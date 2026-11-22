# GM T43 help - 0.4.233 public pre-release

[Illustrated guide](GM-T43-User-Guide-0.4.233.pdf) · [Quick start](QUICKSTART.md) · [Compatibility and scope](COMPATIBILITY.md)

This guide describes the 0.4.233 candidate. The published 0.4.216 release remains separate. The 0.4.233 package starts without customer enrollment records, saved originals, logs or standalone OS BINs; built-in catalogue profiles remain inside the executable.

## Connect and identify

The supported adapter choices in this candidate are **OBDSync**, **OBDX Pro GT / GT Pro**, and the **original GM MDI**. Each has a separate transport path. A driver for one device does not establish compatibility with another. The original GM MDI requires a compatible 32-bit J2534 provider.

Confirm stable power, ignition on, engine off and other diagnostic software closed. Select the connected adapter and choose **Identify controller**. This reads the live T43 identity and determines which operation paths are eligible.

## Save OS and enroll

Choose **Save OS** and complete a full read. A catalogue OS follows its reviewed profile. An unlisted OS can go through local structural evaluation if its boot/helper ABI is recognized by the build.

The evaluation checks the full image, expected T43 layout and headers, calibration checksums and program integrity. It does not run the image. If evaluation and live identity checks pass, enrollment binds the complete original to the controller's VIN, OS, program, boot and segment identities. Keep an independent copy of the original BIN.

A failed evaluation or incomplete read does not create a usable enrollment. A fresh package has no saved original until this process completes.

## Write calibration

Edit a copy of the complete enrolled original. Load the complete edited BIN, choose **Write calibration**, and follow setup, preparation and confirmation prompts. The source must match the enrolled controller's OS, program, boot and segment identities. The write plan contains calibration segments only.

Complete the independent readback and wait for the app to report a match. A passed file check does not establish tuning suitability or vehicle performance.

## Calibration recovery

Choose **Calibration recovery** and select the controller state. For a responding controller, the app uses its supported authorization route. For a nonresponsive controller, select direct recovery. That path does not send a diagnostic preflight before the calibration transfer.

The app requires a matching saved original for that controller and stops before writing if the identity or source cannot be confirmed. After recovery, complete readback verification.

## Change OS and recover OS

For an OS swap, choose **Change OS**, select the recovery original belonging to this controller, then select a complete target BIN. Review the target image and checks before confirmation. The existing boot area and EEPROM are preserved; the selected BIN does not replace them.

When no enrollment is available, use the no-enrollment OS recovery path with a complete supplied BIN and supported loader. File checks and explicit confirmation still apply. Verify the completed write and confirm normal startup separately. A compatible-looking OS number is not proof that the target fits every T43.

## VIN and transmission functions

VIN programming checks the live T43 identity, requires a valid intended VIN, sends the selected request once, and verifies readback. Transmission adapt functions are issued one at a time to a responding T43 and report acceptance, rejection or timeout. A command acknowledgement is not proof of a completed learning procedure.

## Fault codes

The report includes available standard OBD replies and TCM current/history. It is not a scan of every vehicle module. Missing replies are not a clean result. Clearing requires a fresh complete report, matching live identity and separate confirmation; it can erase fault/freeze-frame evidence and reset readiness monitors.

## Fresh start, updates and scope

The clean package contains no customer BINs, enrollment receipts, session logs or prior recovery originals. New customers must save and enroll their own controller. Built-in reference profiles remain embedded for the catalogue paths.

For an existing installation, back up the full app data folder before replacing files. Keep saved originals, enrollments and Logs. The local release seal is an integrity check, not a Windows publisher certificate.

This pre-release has not been qualified for every OS, boot variant or T43 hardware revision. Structural evaluation, transfer acceptance and matching readback are separate from normal startup and vehicle performance. Keep evidence private; do not post VINs, BINs, enrollment records or unredacted logs publicly.

## Historical 0.4.216 booklet

The 0.4.233 PDF begins with a new supplement and retains the 0.4.216 illustrated booklet as an unchanged historical appendix. Where the appendix differs on adapter support or unlisted-OS eligibility, follow the 0.4.233 supplement and this guide.
