# /ssat-verbal/

This directory is a StatiCrypt 3.5.4 page for Avery's original SSAT verbal practice. `index.html` is the encrypted file. The question bank is not stored in plaintext anywhere in this repository.

The lock runs in the visitor's browser. It is not a server login. A short password can be guessed offline from the public file. Do not add personal progress or real results to this repository.

## Rebuild without putting the password in git

1. Get the private source bundle (logic, app, styles, shell, build and encrypt scripts, salt file, and the original canvas export). It is not in this repository.
2. Get the page password out of band. Export it as `STATICRYPT_PASSWORD` for the encrypt process, or place it alone in a gitignored file outside this repository. Do not commit it, and do not paste it into an issue, pull request, or this file.
3. From the private bundle, run `node build.mjs <canvas.tsx> <traceability.csv>` and then `node encrypt.mjs`. The encrypt script uses StatiCrypt 3.5.4, `--short`, a 30-day remember-me checkbox that starts checked, and these localStorage keys: `ssatv_staticrypt_passphrase`, `ssatv_staticrypt_expiration`.
4. Replace only `ssat-verbal/index.html` with `encrypted/site.html`. Do not add the plaintext `site.html`, the canvas source, the CSV, or a source map.
5. Keep the salt recorded as `staticryptSaltUniqueVariableName` in the current `index.html` (the same value is in the private `.staticrypt.json`). Generating a new salt signs out saved unlocks.
6. Do not edit the other project Pages repositories, and do not add a root `index.html` here.

Saved practice progress never belongs in this repository. It stays in the browser key `averySsatVerbal.v1` until the visitor exports a backup or clears site data. Reloading resumes the same round on that browser and device only. Nothing is sent to SSAT Verbal Bot unless a person pastes or sends an export.

To drop a remembered unlock, open the page with `?staticrypt_logout`.
