# Organization map — vasilisnasopoulos-stack

**Front door:** https://github.com/vasilisnasopoulos-stack

This file is the canonical index for the public GitHub organization. Every agent
and every external reviewer should start here before opening a slice repo.

---

## What this organization is

| | |
|---|---|
| **Public** | Three formal-methods repos (TLA+, TLAPS, TLC, Apalache) — verified **parts** of one Vortex DSE machine |
| **Private** | Production C engine (`active/full2/`), benchmarks, trading, full formal staging — **not** on GitHub |
| **Profile repo** | `vasilisnasopoulos-stack/vasilisnasopoulos-stack` — orientation, slice map, agent rules |

Read **[SLICES.md](SLICES.md)** for how the parts connect. Read **[repos/README.md](repos/README.md)**
for per-repo entry points.

---

## Repository inventory

| Repo | Visibility | Layer | Verification | Start when… |
|------|------------|-------|--------------|-------------|
| [vasilisnasopoulos-stack](https://github.com/vasilisnasopoulos-stack/vasilisnasopoulos-stack) | Public (profile) | Index + agent onboarding | — | **Always start here** |
| [vortex-dse-cslot-proofs](https://github.com/vasilisnasopoulos-stack/vortex-dse-cslot-proofs) | Public | Default C-slot admission | **TLAPS** (deductive) | Reviewer asks what is proved on the default model |
| [vortex-dse-cslot-spec](https://github.com/vasilisnasopoulos-stack/vortex-dse-cslot-spec) | Public | Strict admission variant + adversary | TLC + JS ref (bounded) | Reviewer asks about strict same-slot admission or skew |
| [vortex-merkle-agreement](https://github.com/vasilisnasopoulos-stack/vortex-merkle-agreement) | Public | Per-slot Merkle agreement (baseline AE) | TLC + Apalache (bounded) | Reviewer asks about input-set agreement per slot |
| `vortex` (main portfolio) | **Private** | Full engine + all formal staging | C smoke + full formal tree | Owner-approved internal work only |
| `vortex-loss-recoverability` | **Does not exist** (404) | Lossy AE slice | — | Do not link until published |

---

## Folder layout (this profile repo)

```text
vasilisnasopoulos-stack/
├── README.md              ← GitHub profile front page (human-facing)
├── READ_THIS_FIRST.md     ← One-page orientation (agents + owner)
├── AGENTS.md              ← Authoritative rules for cloud/Cursor agents
├── ORGANIZATION.md        ← This file — full org map
├── SLICES.md              ← How public parts connect (design vs proof)
└── repos/
    ├── README.md          ← Per-repo index with links
    ├── vortex-dse-cslot-proofs.md
    ├── vortex-dse-cslot-spec.md
    └── vortex-merkle-agreement.md
```

Slice repos keep their own `README.md`, `ARCHITECTURE.md`, specs, and logs.
Do not duplicate TLA+ sources here — only pointers and scope notes.

---

## Private source of truth (for agents with workspace access)

When working from the private `vortex` workspace, align public changes to:

| Public repo | Private working copy |
|-------------|----------------------|
| proofs | `formal/share/Vortex_DSE_CSlot.tla`, `Vortex_DSE_CSlot_Proofs.tla` |
| spec | `formal/share/Vortex_DSE_CSlot.tla` (strict variant), `Vortex_DSE_CSlot_Skew.tla`, `ref_impl/` |
| merkle | `formal/share/github_cslot_ae/` (baseline only; Lossy/ExactlyOnce stay private) |

Private alignment audit: `vortex/docs/research/PUBLIC_REPO_ALIGNMENT.md` (not public).

---

## Suggested reading order

1. [README.md](README.md) or [READ_THIS_FIRST.md](READ_THIS_FIRST.md)
2. [SLICES.md](SLICES.md)
3. [vortex-dse-cslot-proofs](https://github.com/vasilisnasopoulos-stack/vortex-dse-cslot-proofs)
4. [vortex-merkle-agreement](https://github.com/vasilisnasopoulos-stack/vortex-merkle-agreement)
5. [vortex-dse-cslot-spec](https://github.com/vasilisnasopoulos-stack/vortex-dse-cslot-spec) (strict variant — read after proofs)

---

## Agent handoff (mandatory)

**Every new Cursor / cloud agent** working on Vortex DSE or this organization:

1. Read **`READ_THIS_FIRST.md`** in this repo (or clone and open it).
2. Read **`AGENTS.md`** in this repo for public-surface rules.
3. If the task touches private code: also read `vortex/READ_THIS_FIRST.md` and
   `vortex/AGENTS.md` — private rules override for engine truth; this org map
   overrides for what is already public.

Do **not** start from `replit.md`, `.agents/memory/`, or repo-wide grep alone.

---

*Last updated: 2026-06-17*
