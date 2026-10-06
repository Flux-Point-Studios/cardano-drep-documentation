# Cleanup verification · 2026-10-06

Base: `dbc5a4aebf36a2881af0d112bc514508ea2cb28c`. PRs #4, #5 and #6 were merged at inspection. Repository visibility: PUBLIC.

- 17 organized metadata views compared byte-for-byte with Git blobs at the base commit; no original metadata edited.
- 313 historical commit/path references inventoried; 313 immutable hosted references downloaded, JSON-parsed and independently matched against BLAKE2b-256. This includes every current anchor, full rationale, profile version and metadata path reachable from the base.
- All three current anchor URLs measured at 128 UTF-8 bytes; their hashes match the corrected unsigned signing manifest.
- README local navigation links resolve. Both manifests parse as JSON; metadata contexts, body fields and declared hash algorithms were inspected. Profiles declare CIP-119, historical comments CIP-100, proposal CIP-108, and current full rationales CIP-136.

These are exact-byte, JSON structure and reference checks, not full JSON-LD expansion or certified CIP schema validation. External proposal links, IPFS source availability and the truth of quoted evidence were not re-audited; those references and bytes were preserved. Historical action IDs and cast dates remain unknown where the source does not record them. No ledger submission or confirmation check was performed. The corrected bundle establishes prepared unsigned choices only. No transaction was regenerated, signed or submitted.

The one-off packaging and verification script ran outside the repository under the explicit scratch-script TDD exception; no production code was added. Git history is the source of historical byte inventory. Primary convention research used `site.cips.cardano.org CIP 100 governance metadata CIP 119 CIP 136 vote rationale`, followed by the official CIP-100, CIP-119 and CIP-136 specifications. Their existing metadata structures fit this documentation task; no new metadata framework was needed.

## Talos account correction · 2026-10-06

Both X Account references in the root and organized Talos profiles now use `https://x.com/agentic_t`. A failing assertion established the old references before editing; the updated references, identical profile bytes, JSON parsing and refreshed manifest hash were checked afterward. The manifest retains the previous immutable profile reference. Historical commit-pinned bytes and all vote anchors remain unchanged. This metadata edit adds no production verification code.

## Root cleanup · 2026-10-06

Removed the 14 redundant loose root JSON-LD files after comparing each with its organized document. Profiles remain under `profiles/`, earlier votes and the Lace proposal under `history/`, and current rationales under per-action `votes/` directories. The three compact root anchor aliases remain. All 17 manifest source URLs were fetched again and matched the organized bytes and manifest hashes. Historical commit-pinned URLs survive removal from the current tree. The account correction was carried forward because PR #7 merged before those commits were included. A failing root-layout assertion preceded the change; the final layout, JSON and hash checks passed. No production verification code was added.

## Ledger reconciliation · 2026-10-06

This later reconciliation supersedes earlier statements that historical identities/cast dates and October submission status were unverified. Eleven distinct cast votes were identified: eight historical document anchors and three October actions. Koios vote_list was cross-checked with tx_info using `_governance: true`: voter, choice, action transaction/index, block height and UTC timestamp agree. Proposal identities and status were retrieved from proposal_list. These are two views of one indexer, not independent node consensus; transaction and block references are retained for reproduction.

Seven historical reading documents match the ledger anchor hashes exactly. The eighth, treasury-cut, has identical JSON content but a trailing newline absent from the historical anchored blob. Its original blob hash matches the ledger and its hosted immutable recovery bytes. All eight mutable historical GitHub anchor URLs returned 404 before repair; restore those root files with exact ledger-hashed bytes. Organized documents, quotations and vote choices are unchanged. Current October anchors and full rationale hashes remain unchanged. A failing ledger-evidence assertion preceded the update; final manifest, ledger mapping, JSON, and byte/hash checks passed. The one-off scratch verification uses the explicit scratch-script exception; no production code was added.
