# Yubikey scripts

My yubikey scripts. The only integration I currently need is integration for
totp codes from dmenu.

## TOTP codes from dmenu

[yubikey_totp_dmenu.sh](yubikey_totp_dmenu.sh)

Relies mostly on `ykman` for retrieving the codes, `xclip` for copying the
code, and of course `dmenu` because otherwise it's not `dmenu` integration.

See `yubikey_totp_dmenu.sh --help` for more info.

### Known issues

- `ykman` will sometimes fail with `Error: No YubiKey found with the given
  interface(s)`. This is what will lead to the `Could not get a list of
  accounts` error. This is an issue with ~~`ykman`~~ the `pcsc daemon` and
  generally removing and inserting the yubikey will resolve the problem.
- Using the script will always force a re-pin for the openpgp keys. This is an
  issue with `ykman`.
