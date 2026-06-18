# vortex-dse-cslot-proofs

**Live repo:** https://github.com/vasilisnasopoulos-stack/vortex-dse-cslot-proofs

## Role

Default **late-tolerant** C-slot admission model + **TLAPS** deductive proofs.

## Question it answers

Can a node admit a message from the future? (default model: `m.cslot ≤ current_slot`)

## Verification

| Property | Tool | Scope |
|----------|------|-------|
| `[]TypeInvariant` | TLAPS | Unbounded over parameters |
| `[]NoFutureAdmission` | TLAPS | Unbounded over parameters |
| Other invariants | TLC | Bounded instances (see repo) |

## Private source (workspace)

`vortex/formal/share/Vortex_DSE_CSlot.tla`, `Vortex_DSE_CSlot_Proofs.tla` — byte-identical when in sync.

## Not this repo

- Strict admission (`m.cslot = current_slot`) → **spec** repo
- Merkle agreement → **merkle** repo
- Lossy / exactly-once → private, not published

## Start here when

Reviewer asks what is **machine-proved** on the default admission model.
