# AGENTS.md — vasilisnasopoulos-stack organization rules

**Every Cursor / cloud agent must read this file first** when the task touches:

- This profile repo or any public repo under `vasilisnasopoulos-stack`
- Public visibility, READMEs, slice messaging, or GitHub outreach
- What is already published vs what stays private

For private engine work (`active/full2/`, full `formal/share/`), also read
`vortex/AGENTS.md` after this file. **Public claims** follow this file; **engine truth**
follows private `vortex/AGENTS.md`.

---

## Mandatory start (every new task)

| Step | File | Why |
|------|------|-----|
| 1 | **[READ_THIS_FIRST.md](READ_THIS_FIRST.md)** | One-page orientation |
| 2 | **This file (`AGENTS.md`)** | Public-surface rules |
| 3 | **[ORGANIZATION.md](ORGANIZATION.md)** | Full repo map |
| 4 | **[SLICES.md](SLICES.md)** | How parts connect |
| 5 | **[repos/README.md](repos/README.md)** | Per-repo entry points |

Stop here for public-only tasks. Add private `vortex/READ_THIS_FIRST.md` + `vortex/AGENTS.md`
only when editing C code or private formal staging.

---

## What this organization publishes

| Live public repo | Role |
|------------------|------|
| `vasilisnasopoulos-stack/vasilisnasopoulos-stack` | Profile + org index (this repo) |
| `vortex-dse-cslot-proofs` | Default late-tolerant C-slot + **TLAPS** |
| `vortex-dse-cslot-spec` | **Strict** admission variant + TLC + JS ref |
| `vortex-merkle-agreement` | Baseline per-slot Merkle agreement (AE) |

**Not public:** production C (`active/full2/`), Lossy/ExactlyOnce AE modules, full
`formal/share/` bulk export, `vortex-loss-recoverability` (does not exist).

---

## Truth hierarchy (public tasks)

| Priority | Source | Use for |
|----------|--------|---------|
| 1 | Live GitHub tree + README/STATUS in each public repo | What is actually published |
| 2 | This repo: `ORGANIZATION.md`, `SLICES.md`, `repos/*` | Scope and reading order |
| 3 | Private `vortex/formal/share/` + `PUBLIC_REPO_ALIGNMENT.md` | Pre-push alignment (private only) |
| 4 | `replit.md`, `.agents/memory/` | Historical leads — **never** sole source |

If two sources disagree on what is public: **trust the live GitHub repo**.

---

## Never cite as sole truth

| Path | Why |
|------|-----|
| `replit.md` (private vortex) | Stale session import |
| `.agents/memory/` | Prior agent notes, not verified |
| Draft files under `vortex/docs/research/drafts/` | Not published until owner approves |
| Strict spec repo | **Not** the default running admission rule |

---

## Variant rule (memorize)

| Model | Admission rule | Repo |
|-------|----------------|------|
| Default late-tolerant | `m.cslot ≤ current_slot` | proofs |
| Strict | `m.cslot = current_slot` | spec |

Never imply the strict spec equals default C without stating the variant.

---

## Safe claims

- TLAPS: `[]TypeInvariant`, `[]NoFutureAdmission` on default model (proofs repo).
- TLC/Apalache bounded checks on strict admission, skew, baseline AE (per repo STATUS).
- Public repos are **parts of one machine**, checked in isolation.
- Production C is intentionally private.

## Avoid claiming

- Full end-to-end composed proof across all public repos.
- Lossy recovery or exactly-once is on GitHub (it is not, unless explicitly published).
- Strict spec repo matches default C admission.
- Patented / production-ready without owner + document support.

---

## Before any public GitHub change

1. Read private `vortex/docs/research/PUBLIC_REPO_ALIGNMENT.md` if you have workspace access.
2. Get **explicit owner approval** in the current conversation.
3. Do not bulk-copy `formal/share/github_cslot_ae/` — public merkle keeps abstract envelope wording.
4. Commit and push each logical phase; open/update PR.

---

## Absolute safety rules

- Do not publish `active/full2/`, tradingbot, or private IP bundles.
- Do not change repo visibility without explicit Vasilis approval.
- Do not create new public repos without explicit approval.
- GitHub branches are durable memory — commit and push after each phase.

---

## Handoff to other agents

When passing work to another agent (Replit, Cursor cloud, etc.), send:

1. https://github.com/vasilisnasopoulos-stack — profile
2. Link to **READ_THIS_FIRST.md** and **AGENTS.md** in this repo
3. Task scope: public formal surface only unless private `vortex/` is explicitly in scope

Copy-paste block for quick handoff: `vortex/docs/research/COPY_PASTE_FOR_OTHER_AGENT.md`
(private — use for Phase 1 banners/topics, not as truth over this file).

---

*Authoritative for public organization work. Private engine rules: `vortex/AGENTS.md`.*
