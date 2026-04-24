# alt.dream — planning

This document captures product and architecture intent for the ecosystem. It is living notes, not a spec. It extends the [README](../README.md) with deeper narrative and Shadowbox-related planning where those pieces touch the hub.

---

## Surfaces and roles

| Surface | Role |
|--------|------|
| **alt.dream (this hub)** | Browser shell: cross-app views, personas, per-app buckets, pin health, CID graph ingestion — see README. |
| **gHosted.u** | Messenger / slimmer client — auth and messaging; pairs with the full social build ([gHosted](https://github.com/lulzypher/gHosted)). |
| **Shadowbox** | Modular personal infrastructure (runtimes, jobs, scheduling, settlement) — one **ecosystem bucket** the hub can summarize alongside gHosted. |

**Ecosystem principles**

- **Local-first** aggregation: the hub explains what the user exports or syncs; no pretend single-database truth for all bytes.
- Shared visual language across surfaces so companion apps read as one ecosystem.
- Optional depth: visitors do not need every product to understand the hub.

---

## Experience: optional LARP-centered presentation

**Intent.** Some surfaces may **read and feel like a LARP** (live-action role-play): factions, guilds, quests, diegetic UI — while cryptography and infra stay explicit in OOC docs.

**What that can mean in product**

- **Diegetic naming** — optional in-world labels for pipelines, coalitions, or modules; exact lexicon TBD.
- **Opt-in depth** — Plain-language / “out of character” (OOC) paths for specs without lore.
- **Boundaries** — LARP framing is not a substitute for consent, safety tooling, or terms of service. Anything that affects money, keys, or third parties stays **explicitly signposted**.

---

## On-chain coordination and MPC “servers”

**Intent.** Use **on-chain** layers mainly for **coordination, commitments, and settlement** — not as a replacement for off-chain compute. Use **MPC** (multi-party computation) where **no single party should hold a full secret** or where **private inputs** must be combined without revealing them to each other.

**“MPC servers” as a product metaphor**

- Technically: a **threshold coalition** (t-of-n operators) for DKG/signing, private aggregation, or gated release.
- Heavier always-on services still need **clear trust and abuse models**; MPC helps **key and policy custody**, not magic scaling.

**Rough split**

| Concern | On-chain (typical) | MPC / off-chain (typical) |
|--------|-------------------|---------------------------|
| Identity of coalition, stakes, rotation | Registries, deposits, slashing rules | Key shares, protocol rounds |
| Bounty / escrow for a verifiable deliverable | Lock funds, payout on attested receipt | Optional: threshold attestation |
| Private inputs | Commitments, nullifiers where needed | Actual MPC math, execution |

---

## Shadowbox (platform)

**Purpose.** Modular **personal infrastructure** — orchestration and runtime for short-lived or on-demand workloads (previews, webhooks, sandboxes, scheduled capture jobs, etc.), aligned with **ecosystemBucket** reporting in the hub.

**Positioning.** Distinct from day-to-day **gHosted** social surfaces; summarized as its own bucket in cross-app dashboards.

---

## ArchiveBox (module)

**Relationship.** ArchiveBox is a **component module** of Shadowbox when that stack ships — preservation-oriented jobs and receipts inside the broader Shadowbox catalog.

---

## Economics: sharing first, optional markets later

**Default culture.** Sharing-based: capacity, pipelines, pinning, mutual aid — reputation and reciprocity.

**Future: paid pipelines (crypto)** — optional when completion must be guaranteed and outputs are **verifiable** (hashes, bundles, attestations).

---

## One-line pitch (draft)

**alt.dream** is the hub that makes **pins, personas, and bandwidth** legible across apps. **gHosted** is the social layer; **Shadowbox** (when enabled) is modular personal infra — run what you need, share what you can.

---

## Open decisions

- Hub stack, export formats, and first-party ingestion paths vs gHosted CID map JSON.
- Self-hosted vs hosted deployment for companion apps and hub.
- How much optional LARP presentation ships in v1 vs plain “infra dashboard” mode.
- MPC scope for first user journeys (signing, release, attestation) vs traditional single-operator modules.
