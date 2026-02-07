# Admissibility-Physics-Engine-V-3.5

**Deriving the Standard Model from 5 axioms — 48 theorems, 0 free parameters, 0 contradictions.**

```
$ python3 Admissibility_Physics_Engine_V3_5.py

  Total theorems:  48
  Passed:          48/48
  All pass:        YES
```

## What This Is

Starting from five information-theoretic axioms (finite capacity, non-closure, locality, irreversibility, genericity), this framework derives quantum mechanics, gauge theory, general relativity, and the dark sector — with zero free parameters.

| Prediction | FCF Value | Experiment | Error |
|---|---|---|---|
| sin²θ_W | 3/13 ≈ 0.23077 | 0.23122 (PDG 2024) | **0.19%** |
| Gauge group | SU(3)×SU(2)×U(1) | SU(3)×SU(2)×U(1) | exact |
| Generations | 3 | 3 | exact |
| Spacetime d | 4 | 4 | exact |
| Dark matter | required | Ω_DM = 0.261 | exact |

## Quick Start

```bash
# Full 48-theorem verification (no dependencies beyond Python 3.8+)
python3 Admissibility_Physics_Engine_V3_5.py

# Machine-readable JSON
python3 Admissibility_Physics_Engine_V3_5.py --json

# Full epistemic gap audit
python3 Admissibility_Physics_Engine_V3_5.py --audit-gaps

# Individual modules (standalone)
python3 Admissibility_Physics_Theorems_V3_5.py    # 34/34
python3 Admissibility_Physics_Gravity_V3_5.py     # 6/6
```

## Files

| File | Description |
|------|-------------|
| `Admissibility_Physics_Engine_V3_5.py` | Master engine — runs everything (48 theorems) |
| `Admissibility_Physics_Theorems_V3_5.py` | Theorem bank: Tiers 0-3 (34 theorems) |
| `Admissibility_Physics_Gravity_V3_5.py` | Gravity closure: Tier 5 (6 Γ_geo theorems) |
| `Admissibility_Physics_DarkMatter_V3_5.py` | T12: Dark matter standalone derivation |
| `Admissibility_Physics_BaryonFraction_V3_5.py` | T12E: Baryon fraction standalone |
| `Admissibility_Physics_Dashboard_V3_5.jsx` | Interactive dashboard (React) |
| `Admissibility_Physics_Energy_Budget_V3_5.jsx` | Cosmic energy budget visualization |
| `VERSION_3_5.md` | Release notes + red-team audit response |

## The Five Axioms

| Axiom | Name | Statement |
|---|---|---|
| **A1** | Finite capacity | Total enforcement resources C are finite |
| **A2** | Non-closure | The algebra of observables is not closed under limits |
| **A3** | Locality | Spatially separated systems have independent enforcement |
| **A4** | Irreversibility | Records, once created, cannot be un-created |
| **A5** | Genericity | No fine-tuned cancellations in the enforcement budget |

## Epistemic Honesty

| Tag | Count | Meaning |
|---|---|---|
| **[P]** | 4 | Proved from A1–A5, no structural gaps |
| **[P_structural]** | 41 | Structurally derived, may import external math |
| **[C_structural]** | 2 | Import-gated (Lovelock, HKM) — new in v3.5 |
| **[C]** | 1 | Convention / explicit regime input |

## v3.5 Red-Team Fixes

All 5 findings from an independent red-team audit have been addressed:
1. **Runtime output** — engine now prints verification results on every run
2. **Structural checks** — schema validation + DAG cycle detection
3. **Epistemic labels** — import-gated results correctly labeled C_structural
4. **ASCII compliance** — no hidden Unicode/bidi characters
5. **R11 regime gate** — T11 explicitly depends on Lambda capacity regime

## License

MIT — see LICENSE file.
Constraint-first physics codebase implementing Admissibility Physics: finite enforceability, correlation capacity, and the emergence of quantum mechanics, gravity, entropy, and spacetime as admissible bookkeeping structures
