# Release history

## 0.4.106 prerelease — recommended

Embeds the approved full-application distribution terms in Help. Deliberately rotates the local release-integrity signing key because the previous Windows-protected key is unavailable after the original computer was formatted. The old encrypted key and existing releases remain unchanged. New builds contain the new verification public key; this is not a Windows Authenticode publisher certificate. Vehicle protocol code, native helpers and compatibility policy are unchanged.

Both architecture regression/calibration-policy suites, 32 executable integrity cases, single-file storage, compiled Help and resource audits passed. Old and new signatures were checked against both public keys; each verifies only with its own key. Archived enrollment receipts were preserved; fresh synthetic model enrollments were used for these offline policy checks. No new vehicle trial or vehicle command occurred.

New public-key fingerprint (SHA-256 of UTF-8 RSAKeyValue XML): `79ba5b8c8f5123a54ee24ae8f68a23adc1e5a44ecd03159b208802555c516853`.

## 0.4.105 prerelease — superseded

Single-executable packaging with an embedded signed release seal. First launch creates only Logs and VehicleEnrollments. Full Help, licence notices, profiles and fault-code guidance remain embedded. Vehicle protocol and native helper behaviour are unchanged from 0.4.104.

## Earlier versions

Older development and prerelease builds remain superseded. Their historical descriptions are not recommendations for current use. Future published releases will be listed here with links and their status; private build archives and firmware/test data will not be imported into this public repository.
