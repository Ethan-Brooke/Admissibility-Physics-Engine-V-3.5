# FCF v3.6 Deployment — T6 Upgrade Push

## Files to Upload (4 changed files)

| File | What changed |
|------|-------------|
| `Admissibility_Physics_Engine_V3_5.py` | T6 closed in gap classifier, T6B reclassified scale_id, audit A22-A23 |
| `Admissibility_Physics_Theorems_V3_5.py` | T6 [P_structural]→[P] with SU(5) bridge, T6B honest gap text |
| `Admissibility_Physics_Dashboard_V3_5.html` | scale_identification reason code + purple tag |
| `dashboard_data.json` | 42 [P], 7 [P_structural] |

## Commit message
```
v3.6: T6 → [P] (SU(5) pure algebra), 42P/7Ps, zero imports gated
```

## What changed

| Metric | Before | After |
|--------|--------|-------|
| [P] | 41 (84%) | **42 (86%)** |
| [P_structural] | 8 | **7** |
| QFT imports | 2 (T6, T6B) | **0** |
| Scale ID gap | 0 | 1 (T6B) |

### T6 upgrade bridge (pure group theory)
1. SU(3)×SU(2)×U(1) from T_gauge [P]
2. SU(5) is minimal simple embedding (Georgi-Glashow 1974 — Lie algebra classification)
3. Canonical normalization: k₁ = 5/3 from Tr(T_Y²)/Tr(T_3²) [trace identity]
4. sin²θ_W = (3/5)/(1+3/5) = 3/8 [arithmetic]

### T6B reclassification
- Old label: "QFT import" (suggested β-formula was physics)
- New label: "scale identification" (β-formula IS derivable from T1+T2+T3; gap is capacity↔momentum scale mapping)
- Result still doesn't converge (0.285 ≠ 0.231) — supplementary check only

### Current P_structural breakdown (all 7)

| Category | Count | Theorems | What's needed |
|----------|-------|----------|---------------|
| Open physics | 5 | T4G, T4G_Q31, T10, T11, T12E | UV completion / Majorana-Dirac |
| Scale ID | 1 | T6B | Capacity ↔ momentum mapping |
| Rep selection | 1 | T_field | A5 → fundamental reps |
| QFT import | **0** | — | — |
| Regime-dependent | **0** | — | — |
