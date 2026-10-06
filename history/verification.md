# Cleanup verification · 2026-10-06

Base: `dbc5a4aebf36a2881af0d112bc514508ea2cb28c`. PRs #4, #5 and #6 were merged at inspection. Repository visibility: PUBLIC.

- 17 organized metadata views compared byte-for-byte with Git blobs at the base commit; no original metadata edited.
- 313 historical commit/path references inventoried; 313 immutable hosted references downloaded, JSON-parsed and independently matched against BLAKE2b-256. This includes every current anchor, full rationale, profile version and metadata path reachable from the base.
- All three current anchor URLs measured at 128 UTF-8 bytes; their hashes match the corrected unsigned signing manifest.
- README local navigation links resolve. Both manifests parse as JSON; metadata contexts, body fields and declared hash algorithms were inspected. Profiles declare CIP-119, historical comments CIP-100, proposal CIP-108, and current full rationales CIP-136.

These are exact-byte, JSON structure and reference checks, not full JSON-LD expansion or certified CIP schema validation. External proposal links, IPFS source availability and the truth of quoted evidence were not re-audited; those references and bytes were preserved. Historical action IDs and cast dates remain unknown where the source does not record them. No ledger submission or confirmation check was performed. The corrected bundle establishes prepared unsigned choices only. No transaction was regenerated, signed or submitted.

The one-off packaging and verification script ran outside the repository under the explicit scratch-script TDD exception; no production code was added. Git history is the source of historical byte inventory. Primary convention research used `site.cips.cardano.org CIP 100 governance metadata CIP 119 CIP 136 vote rationale`, followed by the official CIP-100, CIP-119 and CIP-136 specifications. Their existing metadata structures fit this documentation task; no new metadata framework was needed.
