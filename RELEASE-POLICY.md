# GM T43 prerelease and update policy

GM T43 remains a prerelease while development and controller testing continue. The current distribution is one 32-bit/x86 application for compatible 32-bit or 64-bit Windows. The README names the current version and links its application ZIP. Older release pages remain historical and are superseded by that recommendation.

Each release records its changes, requirements, software checks, hardware evidence and outstanding work. An OS being listed, a command being enabled, a write being accepted, a matching readback and normal startup are separate results. Neither software models nor one successful controller trial establishes universal compatibility.

Public packages contain the compiled app and public documentation/notices. They contain no user enrollment, original recovery image, VIN, controller BIN, private source, signing key or private logs. GitHub source archives contain this documentation repository only. Approved application and third-party terms remain in force.

Updates are manual. Close the idle app and preserve the entire data folder, including Logs, VehicleEnrollments and recovery/session records. Keep the executable filename and use the current package. Do not overwrite an operation in progress or substitute another vehicle's enrollment. The embedded release seal is an integrity check, not a Windows publisher certificate or guarantee of universal compatibility.

If a release is withdrawn, its page will state the reason and affected version. A withdrawn binary may be removed while explanatory history remains. Retain local operation evidence and use the appropriate recovery route; do not treat switching app versions as proof that a partial write completed.

Reports should include app version, Windows version, adapter and driver/provider version, controller OS if available, operation and stage. Keep raw BINs, VINs, enrollment records and unredacted logs out of public issues. Use the support contact in the README for guidance.

Guided Fast Learn, Trans Clean and security linking are the three planned next-build items. They remain disabled until their implementation and checks are complete. Availability is announced through the release notes, not inferred from a button name or a related adapt command.
