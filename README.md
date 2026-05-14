# Surge AdvertisingLite Safe Fork

Privacy-scoped Surge module forked from blackmatrix7 `AdvertisingLite.sgmodule`.

## Files

- `AdvertisingLite-SelectiveMITM.sgmodule`
  - Keeps all reject rules.
  - Keeps a scoped MITM whitelist for ad SDK, ad exchange, tracking / delivery, media ad, and content-platform ad hosts.
  - Excludes account, asset / netdisk, identity, payment, private-content, order, finance, banking, medical, government, and real-name-service hosts.
- `AdvertisingLite-FullMITM.sgmodule`
  - Keeps the upstream MITM list and `force-http-engine-hosts`.
  - Best for temporary compatibility / blocking-effect testing.
  - Broadest HTTPS decryption scope; not recommended as the long-term default.
- `AdvertisingLite-NoMITM.sgmodule`
  - Keeps all reject rules.
  - Removes MITM completely.
  - Safest privacy posture, lower HTTPS path-level blocking coverage.

## Tradeoff

`SelectiveMITM` is the recommended default: it preserves more HTTPS ad blocking
than `NoMITM`, while avoiding the original module's very broad HTTPS decryption
scope. Its MITM list is intentionally category-scoped rather than fully removed.

Both files are pinned to upstream source:
`blackmatrix7/ios_rule_script@c6623e2040a2192855e378c2106b1b7eaf968cec`

Use a raw URL pinned to this repository's commit SHA instead of `main`.
