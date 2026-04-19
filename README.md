# Lulzyverse

**User-owned apps, one universe.**

[Lulzyverse planning →](docs/planning.md)

---

## How it fits together

**Yes — this is the shape:** one **browser-facing** home for the ecosystem, **identity and chat** on gHosted, and **Shadowbox** as the place where chain rules, jobs, and **credits** play out.

| Layer | What it is |
|--------|------------|
| **Lulzyverse** (`lulzyverse.dao`, this repo) | The **browser interface** for the whole project: navigation, chrome, and the shell that ties modules together. It is where people **live in the UI** day to day. |
| **[gHosted](https://github.com/lulzypher/gHosted)** (`gHosted.u`) | **Login** and **messaging** — DID-first, social, mesh-oriented identity and chat that the Lulzyverse UI plugs into. |
| **Shadowbox** | The **chain playground**: modules (ArchiveBox, hosts, hooks, …), schedulers, settlement, and **credits earned** for fulfilled work. On-chain coordination, escrow, and MPC-style coalitions attach **here**. |

You can still adopt **one piece** or the **full mesh**; the README above describes the **integrated** story.

---

## Per-job contracts

Work is not one boilerplate agreement for everything. **Terms are written per job**: each request (including bounties posted by people **or** agents plugged into the system) carries its own **contract** — acceptance criteria, splits or bounties, deadlines, receipts, and dispute hooks — so **effort and risk** can vary job by job without a single global ratio pretending to fit all.

---

## What lives in which repo

| Piece | Role |
|--------|------|
| **Lulzyverse (this repo)** | Browser UI / hub app + ecosystem docs until the app code fully lands here. |
| **[gHosted](https://github.com/lulzypher/gHosted)** | Auth, profiles, messaging — the social and identity layer the hub uses. |
| **[DecentralizedArchiveBox](https://github.com/lulzypher/DecentralizedArchiveBox)** | Archiving stack, evolving as the **ArchiveBox** module under Shadowbox. |

---

## Shadowbox (platform)

**Shadowbox** is the **platform layer** behind the playground: modular **personal infrastructure** — orchestration and runtime for workloads that may be **short-lived** or **on demand** (sites, APIs, sandboxes, tunnels, capture jobs, and more). It is **broader** than a single archive product.

### ArchiveBox inside Shadowbox

**ArchiveBox** is a **component of Shadowbox**, not a separate top-level brand. It is one **module** in a catalog.

- **Modules** — e.g. ArchiveBox (preservation), static hosts, webhook sinks, …  
- **Schedulers** — who may run a job: you, friends, a guild, public mesh.  
- **Settlement** — gift / reciprocity by default; **credits** and on-chain **escrow** where policies say so; **per-job contracts** define the economics and acceptance for that run.

Details: [docs/planning.md](docs/planning.md).

---

## How it *feels*: LARP-forward

The ecosystem is meant to **read like a LARP**: guilds, quests, in-world names for real systems — **not** gray corporate SaaS. Underneath, cryptography and policy stay explicit: **money, keys, and obligations stay signposted** so nobody confuses story with stakes.

There will always be an **out-of-character** path (plain specs, ToS, abuse limits) for operators and auditors.

---

## On-chain coordination and MPC

**On-chain** is for **coordination and settlement** where useful: registries, stakes, escrow, reputation anchors — not “put the whole internet on-chain.”

**MPC (multi-party computation)** supports **threshold coalitions** — t-of-n operators so **no single party holds a full secret**. In product language, these are **“MPC servers”**: orders or circles that act only when enough members agree, useful for signing, gated release, and attestations. Heavy always-on services still need clear trust and abuse models; MPC addresses **custody and policy**, not infinite scale.

---

## Economics (intent)

- **Default:** sharing-first — capacity, pipelines, pinning, mutual aid; reputation and reciprocity.  
- **Shadowbox / chain:** **credits** for fulfilled, attested work; optional **prepaid crypto** on **per-job contracts** when someone needs guaranteed completion and verifiable receipts.

---

## Repository layout

```
docs/
  planning.md   # Living architecture + product notes
```

Implementation for **gHosted** and **ArchiveBox / DecentralizedArchiveBox** lives in their **own repositories**. This repo is the **Lulzyverse shell** and **constellation map** as the UI grows here.

---

## Contributing

Ideas, canon, and planning edits welcome via issues and PRs. For **gHosted** or **ArchiveBox / DecentralizedArchiveBox** code changes, use the linked repositories.

---

## License

*To be determined.*
