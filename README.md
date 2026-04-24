# alt.dream

**alt.dream** is a browser hub for a small digital ecosystem: an **alternative dream** to corporate centralization — one where **IPFS**, **DIDs**, and **your** nodes carry identity, media, and sync instead of a single company’s servers.

The name is intentional: not escapism, but a **different shape of infrastructure** — legible pinning, personas, bandwidth, and “who holds what” across the apps you choose to run.

## What lives here

This repository is the **shell / dashboard** for that story:

- **Cross-app views** — pin health, storage, and usage narratives that span more than one app.
- **Personas** — DID-backed identities; one human may run several public faces with clear data boundaries.
- **Per-app buckets** — data grouped under an ecosystem app for each persona (for example **gHosted** for social, **Shadowbox** for other workloads) so the hub can show clean, per-bucket breakdowns.

Companion apps (like [**gHosted**](https://github.com/lulzypher/gHosted)) emit structured **reference events** and export data the hub can ingest to build **CID graphs**, **pin maps**, and future mesh metrics.

## Relationship to gHosted

[**gHosted**](https://github.com/lulzypher/gHosted) is the decentralized social / media experience in this ecosystem. alt.dream is not a clone of gHosted; it **orchestrates and explains** what multiple apps do to your pins, keys, and bandwidth.

Rough split you can mirror in deploys:

| Surface | Role |
|--------|------|
| **alt.dream (full client)** | Social graph, posts, groups, IPFS-backed profiles, pin map, ecosystem tooling. |
| **gHosted.u (messenger)** | Dedicated inbox: auth + encrypted-style messaging; slimmer API and client bundle. |

From the full app, “open messages” should land on your messenger URL (for example **gHosted.u**), not inside the heavy social shell.

## Shared protocol (ecosystem)

Until there is a published npm package, ecosystem types and Zod schemas are maintained alongside gHosted in `shared/ecosystemProtocol.ts` (or copied into a `packages/protocol` workspace here). They define shapes such as:

- **`EcosystemReferenceEvent`** — links a CID (or content digest) to a stable place id, surface, optional `personaDid`, optional `ecosystemBucket`.
- **`PinIntent`** — optional declaration that a user intends to pin a CID (for dashboards).
- **`ConversationPolicy` / `ParticipantMediaPolicy`** — local-first chat retention and media preferences.

**Ingestion:** the hub should accept the same JSON the gHosted **CID map** export uses, merge events (see gHosted’s `ingestReferenceEventsJson` / `ecosystemReferenceStore` concepts), and partition the graph by **`personaDid` + `ecosystemBucket`**.

## Goals (non-exhaustive)

- Make **pin support, space, and bandwidth** understandable across personas and apps.
- Stay **local-first** where possible; aggregate only what the user explicitly syncs or exports.
- Grow toward **mesh** visibility (libp2p / pinning metrics) without pretending every byte lives in one database.

## Development

*(Fill in once this repo’s stack and scripts are finalized — e.g. `pnpm dev`, env vars, and how to point at a local gHosted instance for event export.)*

Suggested environment ideas for a split deploy:

| Variable | Where | Purpose |
|----------|--------|---------|
| `VITE_APP_MODE` | gHosted **client build** | `altdream` vs `messenger` — two Vite bundles. |
| `APP_MODE` | gHosted **server** | `full` vs `messenger` — gates social APIs vs messaging-only. |
| `VITE_MESSENGER_URL` | gHosted **alt.dream build** | Where the header “messages” link should open (e.g. `https://gHosted.u`). |

## License

*(Add your license here — e.g. MIT — and a short contributing note if you want outside PRs.)*

---

**alt.dream** — *an alternative dream: freedom, legibility, and your mesh.*
