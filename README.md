# Surge AdvertisingLite Safe Fork

Privacy-scoped Surge module forked from blackmatrix7 `AdvertisingLite.sgmodule`.

## Files

- `AdvertisingLite-SelectiveMITM.sgmodule`
  - Keeps all reject rules.
  - Keeps only a small MITM whitelist for clearly named ad / ad SDK / ad exchange hosts.
  - Removes broad MITM coverage for account, netdisk, finance, banking, social, and generic app API hosts.
- `AdvertisingLite-NoMITM.sgmodule`
  - Keeps all reject rules.
  - Removes MITM completely.
  - Safest privacy posture, lower HTTPS path-level blocking coverage.

## Tradeoff

`SelectiveMITM` is the recommended default: it preserves more HTTPS ad blocking
than `NoMITM`, while avoiding the original module's very broad HTTPS decryption
scope.

Both files are pinned to upstream source:
`blackmatrix7/ios_rule_script@c6623e2040a2192855e378c2106b1b7eaf968cec`

Use a raw URL pinned to this repository's commit SHA instead of `main`.
