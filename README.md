# Lulzyverse

**User-owned apps, one universe — browser shell, social identity, chain playground.**

[Planning (living notes) →](docs/planning.md) · [Repository](https://github.com/lulzypher/lulzyverse)

---

## What this is

**Lulzyverse** is the **browser-facing hub** for a small constellation of projects: one place to land, sign in, message, and jump into **Shadowbox** work (jobs, modules, credits, contracts). You can use **one piece** or the **full mesh**; nothing forces you to run every module.

| Domain (intent) | Role |
|-----------------|------|
| **lulzyverse.dao** | Public home: **this repo** grows into the **UI shell** — navigation, chrome, ecosystem story. |
| **gHosted.u** | **Login and messaging** — DID-first, local-first social layer the hub embeds or deep-links to. Code: **[gHosted](https://github.com/lulzypher/gHosted)**. |
| **ArchiveBox.nft** | Preservation / archiving as a **named surface**; implementation evolves from **[DecentralizedArchiveBox](https://github.com/lulzypher/DecentralizedArchiveBox)** as the **ArchiveBox** module inside Shadowbox. |

---

## Three layers (mental model)

| Layer | Responsibility |
|--------|----------------|
| **Lulzyverse** (this repo) | **Browser interface** — where people live day-to-day: apps, layout, and glue into the other systems. |
| **[gHosted](https://github.com/lulzypher/gHosted)** | **Identity + chat** — profiles, DIDs, messaging; the hub treats this as the social substrate. |
| **Shadowbox** | **Chain playground** — modules (ArchiveBox, static hosts, webhooks, sandboxes, tunnels, capture jobs, …), **schedulers** (who may run work), **settlement** (gifts, **credits**, optional escrow). On-chain coordination and **MPC-style coalitions** attach here, not to “replace” off-chain compute. |

---

## Shadowbox in one paragraph

**Shadowbox** is modular **personal infrastructure**: short-lived or on-demand runtimes (sites, APIs, previews, glue endpoints, dev sandboxes, VPN/tunnel **where policy allows**), plus scheduled **capture / mirror** jobs (the ArchiveBox lineage). **ArchiveBox** is a **component module** of Shadowbox — not a competing top-level brand.

Each module declares **inputs, outputs, resource class**, and **receipts** so work can be attested and settled.

---

## Per-job contracts (and agents)

There is **no single global boilerplate** for all work. **Terms are written per job**: acceptance criteria, bounty or split, deadlines, receipts, dispute hooks — whether the poster is a **person** or an **agent** integrated with the system. That keeps **effort and risk** honest without one fixed “ratio” for every job type.

*(Ingress APIs, auth, and rate limits for agent-posted jobs are part of Shadowbox design; see [planning](docs/planning.md).)*

---

## Economics (culture + mechanics)

- **Default:** **sharing-first** — capacity, pipelines, pinning, mutual aid; reputation and reciprocity.  
- **Shadowbox:** **credits** for fulfilled, attested work on the playground.  
- **Optional later:** **prepaid crypto** on the same **per-job contract** graph when completion must be guaranteed and outputs are **verifiable** (hashes, bundles, signed attestations — not hand-wavy “run a service forever”).

---

## LARP-forward, not lore-washed

The product **reads like a LARP** when you want it to: guilds, quests, diegetic names for real systems. **Money, keys, and legal obligations** stay **explicit** (plain language, ToS, OOC docs) so story never obscures stakes.

---

## On-chain vs MPC (short version)

- **On-chain:** coordination — registries, stakes, escrow, reputation anchors.  
- **MPC / threshold coalitions (“MPC servers” in lore):** **t-of-n** operators so **no single party holds the full secret** — signing, gated release, attestations. Good for **custody and policy**; not a substitute for abuse review on heavy always-on services.

More detail: [docs/planning.md](docs/planning.md) (tables, open decisions, draft pitch).

---

## Repositories

| Repo | What to open for |
|------|------------------|
| **[lulzyverse](https://github.com/lulzypher/lulzyverse)** (here) | Hub UI + ecosystem docs. |
| **[gHosted](https://github.com/lulzypher/gHosted)** | Decentralized social / DID / mesh app. |
| **[DecentralizedArchiveBox](https://github.com/lulzypher/DecentralizedArchiveBox)** | Archiving stack → **ArchiveBox** module. |

---

## Layout of this repo

```
docs/
  planning.md    # Architecture, LARP/MPC notes, economics, open questions
README.md        # You are here — public overview
```

Application code for **gHosted** and **DecentralizedArchiveBox** lives in those repositories; **Lulzyverse** is the shell and map **until** (and while) hub code accumulates here.

---

## Contributing

Issues and PRs welcome for **docs and canon**. For **gHosted** or **ArchiveBox** behavior and code, contribute in **[gHosted](https://github.com/lulzypher/gHosted)** and **[DecentralizedArchiveBox](https://github.com/lulzypher/DecentralizedArchiveBox)**.

---

## License

*To be determined.*
