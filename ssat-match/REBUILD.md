# /ssat-match/

This directory is a StatiCrypt 3.5.4 page for Avery's SSAT book matching game. `index.html` is the encrypted file. The book items are not stored in plaintext in this repository.

The lock runs in the visitor's browser. It is not a server login. A short password can be guessed offline from the public file. Do not add progress or results to this repository.

## Rebuild without putting secrets in git

1. Get the private source bundle. It is not in this repository.
2. Get the page password out of band. Export it as `STATICRYPT_PASSWORD` for the encrypt step. Do not commit it, and do not paste it into an issue, pull request, or this file.
3. The sync address and the match token are baked into the encrypted page at build time from files outside the repository. They must not appear in plaintext here.
4. Encrypt with StatiCrypt 3.5.4, `--short`, a 30-day remember-me checkbox that starts checked, and these localStorage keys: `ssatm_staticrypt_passphrase`, `ssatm_staticrypt_expiration`. The salt is the `staticryptSaltUniqueVariableName` already in `index.html`. Do not reuse the verbal page's salt.
5. Replace only `ssat-match/index.html`. Do not add a plaintext page, the item bank, or a source map.

Saved matches stay in the browser key `averySsatMatch.v1` and in the match cloud file. They are not part of this repository.

To drop a remembered unlock, open the page with `?staticrypt_logout`.
