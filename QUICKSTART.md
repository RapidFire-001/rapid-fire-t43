# GM T43 quick start

[Download the illustrated PDF booklet](GM-T43-User-Guide-0.4.216.pdf)

For version **0.4.216**. See [the full guide](HELP.md) for each menu and recovery route.

1. Download the application ZIP linked in [README](README.md), extract it to a writable folder and keep the executable filename. Install .NET Framework 4.8 and the correct adapter driver. Original GM MDI needs a 32-bit J2534 provider, even on 64-bit Windows.
2. Open the app. Select **OBDX Pro GT / GT Pro** or **GM MDI** and the matching connection. Nothing starts automatically. Confirm the displayed setup only when the adapter is connected, ignition is on, engine is off and stable power is available. Close other diagnostic software using that adapter.
3. For a normally running controller, use **Identify controller** to see its identity and operation support. **Save OS** reads the complete image and guides enrollment. Preserve that controller's original before making changes.
4. To edit calibration, edit a copy of the full saved BIN, load it and choose **Write calibration**. The app checks the connected vehicle, original, OS/program and source data. Confirm the intended write, follow the ignition-cycle prompts and complete readback verification.
5. To change OS, choose **Change OS**, select the recovery backup belonging to this controller and choose **Continue to OS selection**. Then **Choose OS BIN** in the OS window. Loading a BIN on the main screen is a separate action. Review the file checks and target OS, then confirm **Flash selected OS**. Use **Verify last operation** after the prompted ignition cycle.
6. To put the original OS back, use the single **Restore original [OS number]** button. Choose normal authorization if the TCM responds normally, or direct recovery if it does not. Verify the restored image afterward.

## If there is no usable enrollment

Open **Change OS > Recover OS from BIN - no enrollment**. Select a compatible full T43 BIN and the appropriate controller state. Read and confirm the unverified-compatibility warning before starting. This replaces the OS program and calibration, preserving existing boot code and EEPROM. The existing supported bootloader must remain accessible. No recovery BIN is bundled with the app.

## If only calibration needs restoring

Open **Calibration recovery**, choose the controller state and use **Restore saved calibration**. This single action checks the live installed OS/program, finds the correct saved original and continues on the same connection. A mismatch stops before writing. It cannot use another OS's calibration to repair the installed OS. Complete **Verify last restore** afterward.

## Progress and results

The bar shows the current stage, with bytes, percentage and average speed where available. Preparation/countdowns are separate from transfer timing. **Transfer accepted** means the controller acknowledged the write; **Verification passed** requires a complete matching readback. Normal startup and operation are separate checks.

## Updating

Close the idle app and back up the **entire application folder**, including all enrollment, original, recovery and log records. Extract the new application files into that writable location, retain the supplied executable filename and use the new version. Do not replace your data with another vehicle's enrollment. Windows-user-bound records may need special handling when moving computers; keep an independent copy of your original full BIN.

If a transfer is interrupted, keep the saved original and attempt log. Re-establish the connection and choose the appropriate recovery route; a partial write is not a completed result. Keep power and cables steady while an operation is active.

Guided Fast Learn, Trans Clean and security linking remain disabled and are planned for the next build. The three separate adapt commands are already available. GitHub source archives contain documentation, not the application.

## Before driving after a calibration change

The GM T43 workflow requires this checkpoint after the calibration write and its readback verification have passed. Open **Transmission Functions** and run the top three buttons in their displayed order:

1. **Trans Adapt Reset**
2. **Trans Adapt Preset**
3. **Trans Fast Adapt Reset**

Run one at a time, follow the displayed conditions and wait for each acceptance before continuing. **Complete all three before driving.** A rejection or timeout leaves the checkpoint incomplete; resolve it before proceeding. Also follow the vehicle-specific service procedure for operating conditions and any further relearn. These command acknowledgements do not establish a completed guided Fast Learn or road/shift validation.

