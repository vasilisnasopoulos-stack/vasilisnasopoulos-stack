# vortex-dse-cslot-spec

**Live repo:** https://github.com/vasilisnasopoulos-stack/vortex-dse-cslot-spec

## Role

**Strict** same-slot admission variant (`m.cslot = current_slot`) + clock skew / adversary
extensions + JavaScript reference implementation.

## Question it answers

How does strict single-slot admission behave under skew and spoofing scenarios?

## Verification

| Artifact | Tool | Scope |
|----------|------|-------|
| `Vortex_DSE_CSlot.tla` (strict) | TLC | Bounded |
| `Vortex_DSE_CSlot_Skew.tla` | TLC | Bounded |
| `ref_impl/cslot_ref.mjs` | Node.js scenarios | Executable reference |

## Critical warning

This is **not** the default running admission rule in private C. Default model → **proofs** repo.

## Private source (workspace)

Strict variant of `formal/share/Vortex_DSE_CSlot.tla`; `Vortex_DSE_CSlot_Skew.tla` identical when in sync.

## Start here when

Reviewer asks about **strict** admission or TLC-friendly pedagogical variant — not default TLAPS path.
