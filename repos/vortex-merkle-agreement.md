# vortex-merkle-agreement

**Live repo:** https://github.com/vasilisnasopoulos-stack/vortex-merkle-agreement

## Role

Baseline **per-slot Merkle agreement** (anti-entropy slice): Freeze → Reconcile → Commit
on the admitted input set (`MerkleAgreement`).

## Question it answers

After admission, do nodes commit the **same input set** per cslot? (ideal network baseline)

## Verification

| Property | Tool | Scope |
|----------|------|-------|
| `MerkleAgreement` and related | TLC + Apalache | Bounded instances |
| TLAPS scaffold | `Vortex_DSE_CSlot_AE_Proofs.tla` | In progress — see `TLAPS_NEXT.md` |

## Design link (not composed proof)

Intended stack: **proofs** (admission) → **merkle** (agreement). Connected in design;
no published refinement theorem imports one `Spec` into the next yet.

## Private staging (not public)

| Module | Status |
|--------|--------|
| `Vortex_DSE_CSlot_AE_Lossy.tla` | Private |
| `Vortex_DSE_CSlot_AE_ExactlyOnce.tla` | Private |

## Private source (workspace)

`vortex/formal/share/github_cslot_ae/` — public copy is partial, abstract envelope wording.

## Start here when

Reviewer asks about per-slot input-set agreement or baseline AE — not lossy recovery.
