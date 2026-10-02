# interlock-forensics

Public witness repo for the AEGIS Day-30 gate (2026-10-27 23:59 America/Edmonton).

Scope at the gate: this SDK, the pre-registered benchmark, and the smallest AEGIS slice that benchmark can score. Not the full agent OS.

## Witness rule

Hash input is `prereg/day30.md` at tag `aegis-day30`.
SHA-256 of the raw file bytes: UTF-8, LF, no BOM, exactly one trailing newline.
The hash line is absent from that file.
Stranger command after clone: `sha256sum prereg/day30.md`.

Clone path, once the tag exists:

```
git clone --depth 1 --branch aegis-day30 https://github.com/marsojuji-cmyk/interlock-forensics.git
```

## Not frozen

`prereg/day30.md` on `main` is the approved draft. Tag `aegis-day30` is not cut.
No hash until the schema, verify key, signature algorithm, invoke command, and the recorded-bit URL are in the file that gets tagged.
No graded SDK diff merges before that tag.

## Still UNKNOWN

Attestation schema. Verify key. Signature algorithm. Verify invocation. Where the gate records M_fc.
