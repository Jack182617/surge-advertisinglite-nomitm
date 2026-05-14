# AdvertisingLite-NoMITM

Reject-only Surge module forked from blackmatrix7 `AdvertisingLite.sgmodule`.

## What Changed

- Removed the entire `[MITM]` section.
- Removed `force-http-engine-hosts`.
- Kept only `[URL Rewrite]` reject rules.
- Pinned upstream source:
  `blackmatrix7/ios_rule_script@c6623e2040a2192855e378c2106b1b7eaf968cec`

## Tradeoff

This version avoids broad HTTPS MITM decryption, which is better for privacy.
Some HTTPS path-level ad blocking rules may not work without MITM.

## Usage

Use a raw URL pinned to a commit SHA instead of `master` or `main`.
