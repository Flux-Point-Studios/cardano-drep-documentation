# Talos · Cardano governance record

Talos is the DRep described in [the Talos profile](profiles/talos.jsonld), backed by Flux Point Studios. This repository publishes profiles, governance proposals and the reasoning behind Talos's voting choices so delegators and public readers can inspect the evidence. It is a documentation record, not a wallet or a transaction submission service.

## Start here

- [Talos profile](profiles/talos.jsonld) and [Flux Point Studios profile](profiles/flux-point-studios.jsonld): preserved DRep metadata and self-descriptions. These are historical statements, not independently verified identity claims. The Studios profile includes `doNotList`; publication here does not override that preference.
- [Agent T voting policy v1.0](policy/voting-policy-v1.0.md): the rules Talos votes under. Its closing note lists what this public edition removes from the in-force file the rationales cite.
- [Current vote rationales](votes/): each action has a full `rationale.jsonld` and a shorter `vote-context.jsonld` linking to the full rationale and its hash.
- [Earlier vote documents](history/votes/) and [the Lace assistant proposal](history/proposals/talos-assistant-lace.jsonld): preserved historical documents.
- [Document manifest](manifest.json): original paths, organized views, immutable source URLs, byte hashes, action identities and evidence limits.
- [Historical reference inventory](history/manifest.json): every metadata path at every commit reachable from the cleanup's recorded base commit, including earlier versions and renamed paths.

## Voting policy

Talos votes under the Agent T voting policy. Version 1.0 has been in force since 2026-10-01, and Talos's rationales cite it by name and by the sha256 of the in-force file.

| File | sha256 | blake2b-256 |
| --- | --- | --- |
| [policy/voting-policy-v1.0.md](policy/voting-policy-v1.0.md), the public edition | `79c0cc1d5462da1e04907b3ecd2b2b9f1d1862ab7da94ba3d9ceb659a6c03cee` | `4ee835af66a5a1aba11036d95583fc4f23478321fe8532602ed47671538bfaab` |
| The in-force file the rationales cite, not published (see the public edition note) | `ffe021d3847f3bb67176272cfa892de217d3fb1ae4509e3302cbf9d1ecf89c44` | `bd76e4f00241b91f61b2f9ef9b2a5ec50017018ff4785a0653d2854a126bee69` |

The public edition keeps the rules that decide votes (sections 2 to 9) as in the in-force file, with one addition directed on 2026-10-07: every rationale is written in Talos's first-person voice (section 8, fixture TC-11). Section 7 names Flux Point Studios's interests explicitly, and the edition's closing note lists the other changes. To check a vote against the policy, verify its rationale as in [Verify a reference](#verify-a-reference), then compare the rationale's rule trace with sections 3 to 5 of the policy and its conflict-of-interest disclosure with section 7. The policy is not governance metadata, so it is not listed in `manifest.json`.

## Votes and evidence

These votes are **cast on mainnet**, verified from Koios ledger records and transaction voting procedures. Dates below are UTC block dates, distinct from document commit dates. [Ledger evidence](history/ledger-evidence.json) records transaction hashes, block heights, epochs, original anchors and hash comparisons.

| Document | Ledger choice | Action ID | Cast date (UTC) |
| --- | --- | --- | --- |
| [cardano-constitution](history/votes/cardano-constitution.jsonld) | Yes | [8c653ee5c9800e6d31e79b5a7f7d4400c81d44717ad4db633dc18d4c07e4a4fd#0](https://cardanoscan.io/transaction/a744aef2d8d1ae1a8fcfb917716ff3b97aae404203c00114e0f4c5ab2aa2c9d9) | 2025-01-31 |
| [treasury-cut-10-percent](history/votes/treasury-cut-10-percent.jsonld) | Yes | [941502b0aa104c850d197923259444d2b57cab7af18b63143775465aaacc84f5#0](https://cardanoscan.io/transaction/d7a52916fa031a3a69496379fcdf6a55ed1823ae8f85fe699bc7ecd3050d9b48) | 2025-02-14 |
| [2025-ncl-350-million](history/votes/2025-ncl-350-million.jsonld) | Yes | [9b62b3c632f329016a968ac25211825bb4f84b12461121c7da3aa11df92370f9#0](https://cardanoscan.io/transaction/38b2eed377082acba42103cd68219ca72046e576feaf2f5cb52daf4857b88dbf) | 2025-04-07 |
| [2025-ncl-competing-proposals](history/votes/2025-ncl-competing-proposals.jsonld) | Yes | [7f320409d9998712ff3a3cdf0c9439e1543f236a3d746766f78f1fdbe1e06bf8#0](https://cardanoscan.io/transaction/fb761c85d832e5b2d289efbdbe6d69a541a826a260b8a96b0848a0b01f97c329) | 2025-04-07 |
| [2025-ncl-200-million](history/votes/2025-ncl-200-million.jsonld) | Yes | [7d9fc9fe4cee64fb34e57783378ac869a85c78d6fbcd4078ed131ab6fa3c7db6#0](https://cardanoscan.io/transaction/f97ff6ba752fee966bce59de4e4af0c5411906c9be7c027edb75c8b6880cf1e1) | 2025-04-28 |
| [2025-intersect-ecosystem-budget](history/votes/2025-intersect-ecosystem-budget.jsonld) | Yes | [e14de8d9dc4f4ddf3fe9250a8a926e20f10e99b86bd0610b77d7a054981591ee#0](https://cardanoscan.io/transaction/6c6557c1011b56d33c7c86de623ef3e34e3ddca80bfc07ddee105d0e92c1aa2e) | 2025-05-16 |
| [amaru-treasury-withdrawal](history/votes/amaru-treasury-withdrawal.jsonld) | Yes | [60ed6ab43c840ff888a8af30a1ed27b41e9f4a91a89822b2b63d1bfc52aeec45#0](https://cardanoscan.io/transaction/355e73de47647b1f3a2189c9a124f18928e57a9a3d46d7e9b26553eb09b2aba0) | 2025-07-11 |
| [cardano-builder-dao-withdrawal](history/votes/cardano-builder-dao-withdrawal.jsonld) | Yes | [8ad3d454f3496a35cb0d07b0fd32f687f66338b7d60e787fc0a22939e5d8833e#26](https://cardanoscan.io/transaction/e351729062292ed51351d4186996e7ea0390e156eb5ca7a99d3d9096dbb9161c) | 2025-07-18 |
| [openzeppelin-418df598](votes/openzeppelin-418df598/rationale.jsonld) | No | [418df5986f50547ec4a709f1a5bce6b850753ad6614c873386b7c953fee84a9f#0](https://cardanoscan.io/transaction/da80b171f254ce826987c78bfda9be81c0ab2fd8ccb1709ffa3a931fd5106687) | 2026-10-06 |
| [min-pool-cost-75e7882a](votes/min-pool-cost-75e7882a/rationale.jsonld) | Yes | [75e7882a8ef2bc39517bffbfb654e89f525def5a8364d81e11fc5facafc6dd9b#0](https://cardanoscan.io/transaction/c15585f443166a1767b6c60582861da3b97a446d61a4f1b6ce498731f5325fa2) | 2026-10-06 |
| [stake-pool-target-f6fd3678](votes/stake-pool-target-f6fd3678/rationale.jsonld) | Abstain | [f6fd3678f12edc58dd8739560149fcdb0b8b6fc77a5f303d49c87c74d1fccb4c#0](https://cardanoscan.io/transaction/e7c53e775a4f4e69cd702c02f4c539817ce7a3e0857f24f35ca7d93292646915) | 2026-10-06 |

The competing-NCL document discusses two proposals, but only one cast vote is matched to this exact anchor. The separate 350M document anchors the other recorded vote. The treasury-cut reading copy differs from its ledger-anchored version by a trailing newline; the restored root compatibility file preserves the exact anchored bytes.

## Which bytes are authoritative?

For a submitted vote, the ledger's anchor URL and hash identify the authoritative vote-context bytes. That context can reference a separate full rationale by immutable URL and hash. Follow that chain, rather than assuming the latest branch version was the version used on-chain. The October vote anchor URLs and hashes match the corrected signing bundle and the subsequently confirmed ledger records. The manifest records their cast dates and transaction identities.

Profiles, proposals and vote rationales live in their organized directories. Eight legacy root vote-context files remain solely because historical on-chain anchors use mutable `main` URLs at those paths. Removing them breaks verification; changing their bytes breaks their ledger hashes. The compact aliases `418df59`, `75e7882` and `f6fd367` also remain: their current commit-pinned URLs consume the full 128-byte anchor URL allowance. The manifest distinguishes compatibility paths from organized reading views. The current Talos profile uses `https://x.com/agentic_t`; previous immutable profile references remain recorded. Git history is preserved. Historical inventory hashes are computed reference checks, not proof that each version was published on-chain. The manifest itself is a navigation aid, not governance metadata or an on-chain anchor.

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
