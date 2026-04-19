# Lulzyverse — planning

This document captures product and architecture intent for the ecosystem. It is living notes, not a spec.

---

## Domains and roles

| Surface | Role |
|--------|------|
| **lulzyverse.dao** | Hub: collection of apps in the ecosystem, identity, navigation, and narrative. |
| **gHosted.u** | Messaging and social — identity-first, local-first, mesh-oriented ([gHosted](https://github.com/lulzypher/gHosted)). |
| **ArchiveBox.nft** | Preservation / archiving — historically the archive product; see Shadowbox below. |

**Ecosystem principles**

- One umbrella story on the hub: identity + social + durable memory, user-owned where it matters.
- Shared visual language and cross-linking between surfaces so it reads as one ecosystem, not unrelated repos.
- Optional depth: visitors do not need every product to understand the hub.

---

## Experience: LARP-centered service

**Intent.** The ecosystem should **read and feel like a LARP** (live-action role-play): factions, guilds, quests, in-world titles, and diegetic UI — not cold enterprise SaaS. Serious cryptography and infra still sit underneath; the **presentation layer** is playful, consensual, and invitation-based.

**What that can mean in product**

- **Diegetic naming** — Pipelines become “quests” or “contracts”; capacity providers join a “guild” or “order”; ArchiveBox work is “sealing” or “binding” memory to the vault. Shadowbox runtimes are “ciphers,” “wardens,” or similar in-world labels (exact lexicon TBD).
- **Opt-in depth** — A plain-language / “out of character” (OOC) toggle or doc for anyone who wants specs without lore.
- **Social glue** — Sharing-first economics map naturally to **in-character gift culture** (favors, oaths, reputation) while real limits (quotas, abuse, legal) stay in clear OOC policy.
- **Boundaries** — LARP framing is not a substitute for consent, safety tooling, or terms of service. Anything that affects money, keys, or third parties stays **explicitly signposted** so players are never confused about what is “real.”

---

## On-chain coordination and MPC “servers”

**Intent.** Use **on-chain** layers mainly for **coordination, commitments, and settlement** (who offered what, escrow, reputation anchors, registry of coalitions) — not as a replacement for off-chain compute. Use **MPC** (multi-party computation) where **no single party should hold a full secret** or where **private inputs** must be combined without revealing them to each other.

**“MPC servers” as a product metaphor**

- Technically: a **threshold coalition** (t-of-n operators) runs protocols for things like **distributed key generation / signing**, **private aggregation**, or **gated release** of artifacts — so “the server” is **the protocol + quorum**, not one admin’s machine.
- In LARP terms: an **order**, **circle**, or **shard-host** that only acts when enough wardens agree — aligns with trust story and with auditability on-chain (membership commitments, stakes, rotation).
- **Services offered through coalitions** — Examples that fit MPC + registry well: threshold-backed signing for releases; coordinated decryption of a time-locked bundle; attested “pipeline completed” without revealing intermediate secrets. Heavier always-on services (generic VPN, arbitrary APIs) still need **clear trust and abuse models**; MPC helps **key and policy custody**, not magic scaling.

**Rough split**

| Concern | On-chain (typical) | MPC / off-chain (typical) |
|--------|-------------------|---------------------------|
| Identity of coalition, stakes, rotation | Registries, deposits, slashing rules | Key shares, protocol rounds |
| Bounty / escrow for a verifiable deliverable | Lock funds, payout on attested receipt | Optional: threshold attestation |
| Private inputs | Commitments, nullifiers where needed | Actual MPC math, execution |

---

## Shadowbox (platform)

**Purpose.** Shadowbox is broader than a web archive: modular **personal infrastructure** — orchestration and runtime for things that may be **short-lived** or **on demand**, for example:

- Ephemeral websites, previews, file drops with expiry
- Temporary API endpoints, webhooks, glue between services
- Personal VPN / tunneling (framed as legitimate personal use; clear policies)
- Sandboxed dev or preview environments
- Scheduled capture and mirror jobs (ArchiveBox DNA)

**Positioning.** “Shadowbox” suggests isolation, sandboxes, and **time-bounded** capability — distinct from “ArchiveBox” as a wordmark for long-term preservation.

---

## ArchiveBox (module)

**Relationship.** ArchiveBox is a **subsidiary / component of Shadowbox**, not a competing top-level brand. It is one **module** in a modular catalog.

**Modular ecosystem**

- Users and operators **do not** need every part — install or enable only the modules they want.
- Shadowbox describes the **platform** (policies, scheduling, settlement, orchestration). Modules declare **inputs, outputs, resource class**, and receipts.

---

## Economics: sharing first, optional markets later

**Default culture.** Sharing-based: capacity, pipelines, pinning, and mutual aid within groups or the public mesh — reputation and reciprocity, not every interaction priced.

**Future: paid pipelines (crypto)**

- Optional path when someone needs **guaranteed** completion (deadline, SLA, rare skill): **prepay** into escrow; **fulfillers** who complete the pipeline receive the bounty.
- Works best when work is **verifiable**: e.g. WARC or bundle hash, replayable artifact on IPFS, signed attestation, CI artifact — not open-ended “run a good VPN.”
- Design needs: clear acceptance criteria, dispute window, abuse controls (rate limits, reputation, staking/slash if anonymous).

**Conceptual layering**

| Layer | Role |
|--------|------|
| **Modules** | ArchiveBox, static host, webhook sink, etc. |
| **Schedulers** | Who may run it: self, friends, public mesh. |
| **Settlement** | None (gift), reciprocal credits, or crypto escrow. |

“Paid pipeline” is a **scheduler + settlement policy** on the same module graph, not a separate product.

---

## One-line pitch (draft)

**Lulzyverse** is the hub for user-owned apps. **Shadowbox** is modular personal infrastructure — run what you need, share what you can. **ArchiveBox** is the preservation module: optional, composable, compatible with gift economies or escrowed work later.

**LARP + infra (draft).** *Enter the verse: guilds run shadow-work through threshold circles — real cryptography, played for keeps, consensual as a game and serious as a tool.*

---

## Open decisions

- Self-hosted only vs hosted multi-tenant vs peer/crypto-aligned deployment for Shadowbox modules.
- Which **killer loop** ships first (e.g. “URL → archive + shareable replay for N days”) to tie runtime to preservation cleanly.
- Chain, token, and dispute mechanics for bounties — defer until receipts and module APIs are concrete.
- **LARP canon** — Factions, lexicon, and art direction vs minimal “lore skin” only; how much is required for v1.
- **MPC scope** — Which user journeys are threshold-first (signing, release, attestation) vs traditional single-operator modules for v1.
