# Talos · Cardano governance record

Talos is the DRep described in [the Talos profile](profiles/talos.jsonld), backed by Flux Point Studios. This repository publishes profiles, governance proposals and the reasoning behind Talos's voting choices so delegators and public readers can inspect the evidence. It is a documentation record, not a wallet or a transaction submission service.

## Start here

- [Talos profile](profiles/talos.jsonld) and [Flux Point Studios profile](profiles/flux-point-studios.jsonld): preserved DRep metadata and self-descriptions. These are historical statements, not independently verified identity claims. The Studios profile includes `doNotList`; publication here does not override that preference.
- [Current vote rationales](votes/): each action has a full `rationale.jsonld` and a shorter `vote-context.jsonld` linking to the full rationale and its hash.
- [Earlier vote documents](history/votes/) and [the Lace assistant proposal](history/proposals/talos-assistant-lace.jsonld): preserved historical documents.
- [Document manifest](manifest.json): original paths, organized views, immutable source URLs, byte hashes, action identities and evidence limits.
- [Historical reference inventory](history/manifest.json): every metadata path at every commit reachable from the cleanup's recorded base commit, including earlier versions and renamed paths.

## Votes and evidence

The October 2026 choices below are **prepared votes**. The corrected unsigned signing bundle was verified on October 6, 2026; this repository does not establish that those transactions were signed, submitted or confirmed. “I vote” expresses Talos's decision. The phrase “cast by my DRep key holder” describes responsibility for casting; it is not a transaction receipt. Earlier documents sometimes say “I cast”; their ledger status and action identities have not been independently established by this cleanup. Commit dates below are document dates, never inferred vote dates. No date is inferred from a filename.

| Document | Choice in text | Action ID | Document commit date |
| --- | --- | --- | --- |
| [cardano-constitution](history/votes/cardano-constitution.jsonld) | Yes (document text; ledger not verified) | Not recorded; unverified | 2025-01-31 |
| [treasury-cut-10-percent](history/votes/treasury-cut-10-percent.jsonld) | Yes (document text; ledger not verified) | Not recorded; unverified | 2025-02-14 |
| [2025-ncl-350-million](history/votes/2025-ncl-350-million.jsonld) | Yes (document text; ledger not verified) | Not recorded; unverified | 2025-04-07 |
| [2025-ncl-competing-proposals](history/votes/2025-ncl-competing-proposals.jsonld) | Yes (document text; ledger not verified) | Not recorded; unverified | 2025-04-07 |
| [2025-ncl-200-million](history/votes/2025-ncl-200-million.jsonld) | Yes (document text; ledger not verified) | Not recorded; unverified | 2025-04-28 |
| [2025-intersect-ecosystem-budget](history/votes/2025-intersect-ecosystem-budget.jsonld) | Yes (document text; ledger not verified) | Not recorded; unverified | 2025-05-16 |
| [amaru-treasury-withdrawal](history/votes/amaru-treasury-withdrawal.jsonld) | Yes (document text; ledger not verified) | Not recorded; unverified | 2025-07-11 |
| [cardano-builder-dao-withdrawal](history/votes/cardano-builder-dao-withdrawal.jsonld) | Yes (document text; ledger not verified) | Not recorded; unverified | 2025-07-18 |
| [openzeppelin-418df598](votes/openzeppelin-418df598/rationale.jsonld) | No | 418df5986f50547ec4a709f1a5bce6b850753ad6614c873386b7c953fee84a9f#0 | 2026-10-06 |
| [min-pool-cost-75e7882a](votes/min-pool-cost-75e7882a/rationale.jsonld) | Yes | 75e7882a8ef2bc39517bffbfb654e89f525def5a8364d81e11fc5facafc6dd9b#0 | 2026-10-06 |
| [stake-pool-target-f6fd3678](votes/stake-pool-target-f6fd3678/rationale.jsonld) | Abstain | f6fd3678f12edc58dd8739560149fcdb0b8b6fc77a5f303d49c87c74d1fccb4c#0 | 2026-10-06 |

The full action IDs for the three current decisions come from the independently checked unsigned bundle. Older documents do not record an action ID; the manifest uses `null` rather than guessing. A historical document discusses two NCL proposals, so it must not be treated as a uniquely identified individual on-chain vote.

## Which bytes are authoritative?

For a submitted vote, the ledger's anchor URL and hash identify the authoritative vote-context bytes. That context can reference a separate full rationale by immutable URL and hash. Follow that chain, rather than assuming the latest branch version was the version used on-chain. For the prepared October votes, the manifest records the exact URLs and hashes in the corrected unsigned bundle. No unsigned transaction IDs are presented as confirmed transactions.

Profiles, proposals and vote rationales live in their organized directories. The former loose root JSON-LD files have been removed from the current tree; their original paths remain recorded in the manifest. Historical metadata bytes remain available at their original immutable URLs, and Git history is preserved. The current Talos profile updates its X account to `https://x.com/agentic_t`; its new immutable URL and hash are recorded in the manifest alongside the previous reference. The compact root names `418df59`, `75e7882` and `f6fd367` are anchor aliases: their commit-pinned raw URLs already consume Cardano's full 128-byte anchor URL allowance. Longer directory URLs must not replace them in existing transactions. Historical inventory hashes are computed reference checks, not proof that each version was published on-chain. The manifest itself is a navigation aid, not governance metadata or an on-chain anchor.

## Authorship and signing

Current rationales disclose preparation by Agent T, an AI agent operated by Flux Point Studios. Talos speaks in first person: “I vote”, “my earlier votes”, and “what I verified”. Preserve that voice, the evidence, source quotations and AI disclosure. The human DRep key holder controls signing and submission; AI preparation does not supply that authorization. Metadata author witnesses and transaction signatures are distinct. Empty or absent metadata authors do not establish a cryptographic authorship witness.

## Verify a reference

1. Obtain the anchor URL and hash from the unsigned transaction being reviewed, or from the confirmed ledger record when checking a cast vote.
2. Download the URL as raw bytes. Compare its BLAKE2b-256 digest with the recorded hash. Do not parse and serialize, normalize whitespace or line endings, or hash a GitHub HTML page.
3. Follow the full-rationale URL in the vote context and independently compare its digest. Review its action ID, choice, evidence and references.
4. Establish casting separately using a confirmed transaction and the DRep's voting procedure. A valid document hash proves byte integrity, not the truth of a claim or transaction confirmation.

Python's standard library computes the required digest (32-byte BLAKE2b, not truncated BLAKE2b-512):

```python
import hashlib
from urllib.request import urlopen

url = "PASTE_THE_COMMIT_PINNED_RAW_URL"
expected = "PASTE_THE_RECORDED_BLAKE2B_256_HASH"
with urlopen(url, timeout=30) as response:
    data = response.read()
actual = hashlib.blake2b(data, digest_size=32).hexdigest()
assert actual == expected, (actual, expected)
print(actual)
```

## Metadata conventions and updates

[CIP-100](https://cips.cardano.org/cip/CIP-0100) defines the governance metadata foundation; [CIP-119](https://cips.cardano.org/cip/CIP-0119) describes DRep profiles; [CIP-108](https://cips.cardano.org/cip/CIP-0108) describes governance action metadata. Current full rationales reuse the [CIP-136](https://cips.cardano.org/cip/CIP-0136) rationale structure, whose specified subject is Constitutional Committee votes. Its use here does not make Talos a committee member or establish complete schema conformance. Earlier vote contexts use CIP-100 comments. Existing schemas are preserved, not silently migrated.

When changing a rationale, publish its exact bytes at a new commit-pinned URL and update the full-rationale hash in its vote context. When changing the context, review and refresh the unsigned transaction's anchor URL and hash before any signing. Never sign against a superseded rationale. Preserve previous versions, stable compact aliases and immutable references; do not rewrite history. Update organized documents and manifests together, and independently verify hosted bytes. Add a confirmed cast status only with ledger evidence and its source.

Historical source text, quoted sources and authorship remain intact. This cleanup grants no new license and makes no change to voting policy. See [verification evidence](history/verification.md) for the cleanup's checks and limitations.
