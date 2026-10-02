# AEGIS Day-30 pre-registration

Status: DRAFT on main. Not the frozen hash. Tag aegis-day30 is not cut.
Gate date: 2026-10-27
Cutoff: 2026-10-27 23:59 America/Edmonton
Tag: aegis-day30
Hash input path: prereg/day30.md
Repository: https://github.com/marsojuji-cmyk/interlock-forensics

Marcus Richards approved these five words on 2026-10-02: SHA-256, RAW-SHA256, PUBLIC-TAG, TOKEN-REJECT, CUTOFF-MDT.
This file is not the record until Ektar lands the tag.

## Claim

The smallest AEGIS slice, at tag aegis-day30, rejects closed a provenance attestation of valid shape and invalid signature when that attestation is submitted to the verify path: the outcome is a rejection, it grants no partial trust, and it does not pass silently.

Falsifier: a stranger, using only the published clone path and the published pre-registration hash, submits TC-SIG-FORGE to the verify path and gets acceptance, partial trust, or a silent pass.

## Metric

One bit, M_fc. M_fc = 1 if and only if, on tamper case TC-SIG-FORGE submitted only to the verify path, all four hold:

1. the outcome is classified REJECT by the predicate in this file
2. it is not classified PARTIAL
3. it is not classified ACCEPT
4. no success status is returned with the rejection

Otherwise M_fc = 0. Day-30 pass iff M_fc = 1. The stranger's re-score is an equality check of that bit against the gate record published at the URL named in this file at the tag.

## REJECT predicate

TOKEN-REJECT. On TC-SIG-FORGE, the verify path exits non-zero, stdout contains the exact token REJECT, and contains neither ACCEPT nor PARTIAL. Exit 0 is fail regardless of text. PARTIAL or ACCEPT text is fail regardless of exit.

## Tamper case

TC-SIG-FORGE. One provenance attestation that matches the schema frozen at the gate tag (valid shape) and whose signature does not verify under the key the verify path is required to check (invalid signature). Submitted to the verify path only. Required outcome: fail closed.

## Hash method

SHA-256 of the raw file bytes of prereg/day30.md at tag aegis-day30.
Encoding: UTF-8, LF, no BOM, exactly one trailing newline.
The hash line is absent from this file.
Stranger command after clone: sha256sum prereg/day30.md
Publication: public git tag aegis-day30, raw file URL, no account, HTTPS clone.

## Still UNKNOWN

- Attestation schema. Resolves when the schema is in the tagged file set.
- Verify key and signature algorithm. Resolves when the verify contract is in that tag.
- How the stranger invokes the verify path. Resolves when the invocation is documented at that tag.
- Where the gate's recorded M_fc is published. Resolves when that public URL is written into this file before the hash.
- Any path other than verify. Not assumed. Resolves by reading the tag.
