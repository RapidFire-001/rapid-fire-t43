# GM T43 user guide

[Download the illustrated PDF booklet](GM-T43-User-Guide-0.4.216.pdf)

**Version 0.4.216** - Windows application by Rapidfire.

This guide follows the current public interface. Support is determined by the connected T43's firmware and the requested operation, not a vehicle-series label. See [Compatibility](COMPATIBILITY.md) for the included OS profiles and evidence limits.

## Connect and identify

Choose the GT or original GM MDI and the appropriate connection. MDI requires its installed 32-bit J2534 provider. **Refresh adapters** updates the connection list; it does not measure voltage. **Compare voltage** requests a fresh sample. Driver registration does not confirm a connected adapter.

Confirm stable power, ignition on, engine off and other diagnostic software closed. **Identify controller** displays the responding controller's identity and supported operations. An unlisted OS can be identified without being automatically approved for every write method. No vehicle operation starts merely by opening the app.

## Save OS and enrollment

**Save OS** reads a full image using a supported profile and validates the completed file. Enrollment associates the original with that vehicle. A fresh installation has no enrolled vehicle, fixed original OS or preset recovery image. Each owner supplies their own original or recovery BIN.

Preserve the full original and the entire app data folder. Enrollment and recovery records may be tied to the Windows user; do not assume copying those records to another computer makes them usable. Keep the independent original BIN as well.

## Load BIN and write calibration

Load a full BIN containing the intended calibration changes. File information reports the OS, firmware/profile match and applicable program/calibration checksum results. A passed file check establishes file consistency, not that every calibration value is suitable for driving or that another OS fits the controller.

**Write calibration** checks the live controller and enrolled original, including matching OS/program and protected data. It writes calibration only. Follow the preparation, authorization, confirmation and ignition-cycle prompts, then finish the independent readback. The completion messages name the adapter actually used.

## Before driving after a calibration change

The GM T43 workflow requires this checkpoint after the calibration write and its readback verification have passed. Open **Transmission Functions** and run the top three buttons in their displayed order:

1. **Trans Adapt Reset**
2. **Trans Adapt Preset**
3. **Trans Fast Adapt Reset**

Run one at a time, follow the displayed conditions and wait for each acceptance before continuing. **Complete all three before driving.** A rejection or timeout leaves the checkpoint incomplete; resolve it before proceeding. Also follow the vehicle-specific service procedure for operating conditions and any further relearn. These command acknowledgements do not establish a completed guided Fast Learn or road/shift validation.

## Calibration recovery

Use this when the installed OS/program is to remain unchanged and its own saved calibration needs restoring, including after an interrupted calibration write.

1. Open **Calibration recovery** and select the controller state: normal response/authorization or nonresponding/direct recovery.
2. Confirm the displayed connection conditions and choose **Restore saved calibration**.
3. The app checks the connected vehicle and reads protected firmware once. It automatically matches the completed saved original and restores on that same connection.
4. If the installed OS/program does not match, or the original is absent or ambiguous, it stops before erase or write and reports the problem.
5. Follow the ignition prompt and use **Verify last restore** for the full comparison.

The protected-firmware check reads roughly 1.8 MB from the TCM. It is not uploading that much firmware and does not rewrite the bootloader. It prevents restoring calibration from one OS over a different installed program. A previous accepted restore is history, not proof of the controller's present state.

## Change OS and restore the original

Choose **Change OS**, select this controller's recovery backup and choose **Continue to OS selection**. This selects the recovery original, not the target to flash. In the next window use **Choose OS BIN** to select the target. A main-screen loaded BIN does not automatically replace this selection.

Review the target OS, firmware/program/calibration checks and any calibration difference. **Flash selected OS** writes the selected program and calibration after confirmation. The app preserves the controller's existing boot area and EEPROM. It does not make all listed OSs interchangeable.

**Restore original [OS number]** restores the named saved original. Its confirmation offers:

- **TCM responding normally:** uses the normal authorization route into programming.
- **TCM not responding normally:** uses direct recovery through the resident loader.

Both restore the same selected original; the handshake differs. After the prompted ignition cycle, **Verify last operation** compares against the exact recorded write, even if a different file has since been selected. Choosing a file alone does not start programming.

## Recover OS from BIN without enrollment

Use **Change OS > Recover OS from BIN - no enrollment** when there is no usable saved enrollment, including a controller whose normal OS cannot identify itself. Supply a compatible full T43 BIN, choose the controller state, read the warning and explicitly confirm the write.

This replaces the main OS program and calibration. File/layout/checksum and supported-loader checks still apply. The warning states that compatibility with the connected hardware is unverified. The app does not supply a universal recovery OS or an automatic rollback backup in a fresh installation.

If recovery succeeds, follow the ignition prompt, run the recorded readback verification and confirm normal startup. A working controller can then be read and enrolled through Save OS. This does not automatically approve other OS swaps.

### What boot preservation means

Calibration writes, OS changes and OS recovery do **not erase or program the existing boot area**. A full BIN may contain boot data, but these operations skip that portion. OS changes/recovery also preserve EEPROM rather than replacing it with donor data.

A soft-bricked or semi-bricked controller is one whose normal software does not start but whose bootloader remains intact and responsive. The app can recover supported controllers in this condition with a compatible BIN. It cannot repair damaged boot code, create a missing bootloader response or guarantee recovery from every failure.

## Progress, verification and interruptions

Live progress is shown once beside the bar. The message area is for instructions, results and errors. Preparation/countdowns, writing and reading back have distinct stages. Byte-count stages show bytes, percentage and average transfer speed; preparation time is excluded. Verification shows read speed.

- **Transfer accepted:** the controller acknowledged the requested write.
- **Verification passed:** the completed readback matches the expected protected/program/calibration data for the operation, with mutable EEPROM handled separately.
- **Normal startup:** the controller starts its normal software. This is separate from matching stored bytes and from road/shift performance.

Stopped or interrupted attempts retain their logs and result. MDI cleanup has been corrected to avoid repeated cleanup/early driver unload, preserve the original operation error and prevent further sends after an unconfirmed release. Software interruption tests passed; the app does not treat cable loss as a completed transfer or automatically retry it.

## Transmission Functions

The following are available after valid live T43 OS identification, including an OS not listed in the catalogue:

| Control | Purpose |
|---|---|
| Trans Adapt Reset | Requests reset of transmission adaptive learning. |
| Trans Adapt Preset | Requests the transmission adaptive preset. |
| Trans Fast Adapt Reset | Requests fast-adapt reset; this is not the guided Fast Learn procedure. |

Run one function at a time and follow the displayed conditions. The app sends the selected command once and reports acceptance, rejection or timeout. An acknowledgement is not a readback of every learned value or proof that a complete learning procedure has finished. Complete the GM T43 post-calibration checkpoint above, and follow the relevant vehicle-specific service procedure for any further relearn.

## Vehicle fault codes

**Read and save report** collects the available standard OBD replies and TCM current/history. This is not a scan of every vehicle module. Missing replies are not a clean result. The offline **Fault code guide** explains covered codes; other codes remain visible without invented descriptions.

**Clear vehicle codes** is a network operation, not transmission-only clearing. It needs a recent complete saved scan, the same live vehicle and OS, and explicit confirmation. It can clear stored/freeze-frame evidence and reset readiness monitors. The app checks replies and performs a follow-up scan. It does not repair the underlying fault; permanent codes may remain. A timeout or rejection is not retried automatically.

Reading and public network clearing no longer require a listed OS or one of the original two profiles. Physical TCM-only clearing remains unavailable.

## Change VIN number

Select the adapter and confirm setup. **Read T43 VIN** obtains current OS/VIN identity. Enter the intended valid new VIN, review the current/new identity and confirm **Program VIN**. The app rechecks live identity, writes once and compares immediate readback. Then follow the power-cycle instruction and use **Verify after power cycle**.

This feature is no longer limited to one OS or catalogue membership. The controller still has to implement and accept the request. It does not enable security linking or other module programming.

## Tested OSs

The searchable list contains the 25 catalogue OS numbers. It is a reference list, not a universal swap-compatibility chart. Read/write profiles use firmware/layout checks, while adapt, fault-code and VIN operations can be offered to valid responding unlisted OSs. Detailed internal test categories are not something a public user needs to select.

## Planned for the next build

These three functions are planned and **remain disabled in this release**:

1. **Guided Transmission Fast Learn** - the monitored learning procedure.
2. **Trans Clean** - the transmission cleaning procedure.
3. **Security linking** - controller security/linking support.

Trans Fast Adapt Reset is already available. It is a separate command and is not the guided Fast Learn procedure.

## Updating and getting help

Update only when the app is idle. Back up the full application folder, then extract the new files without deleting your saved originals, enrollments, recovery records or logs. Updates are manual. Keep the executable's supplied name so the embedded integrity check can validate the release. The local integrity seal is not a Windows publisher certificate.

Contact [Rapid Fire Software Support](mailto:support@rapidfiresoftware.net) with version, Windows/adapter details, operation and error. Retain unredacted evidence locally; do not post raw BINs, VINs or enrollment files publicly. See [Licence](LICENSE.txt), [Third-party notices](THIRD-PARTY-NOTICES.txt) and [Release policy](RELEASE-POLICY.md).
