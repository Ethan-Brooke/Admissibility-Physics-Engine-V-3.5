# FCF v3.6 — T_field Uniqueness Proven

## Commit message
```
v3.6: T_field [P], T6 [P], 43P/6Ps (88%), charge quantization + neutral atoms derived
```

## Files changed (4)
- `Admissibility_Physics_Engine_V3_5.py` — 13 predictions, T_field/T6 gap closed, audit A24
- `Admissibility_Physics_Theorems_V3_5.py` — T_field uniqueness proof, T6 SU(5) bridge
- `Admissibility_Physics_Dashboard_V3_5.html` — 6 new constants (charges, neutral atoms)
- `dashboard_data.json` — 43 [P], 6 [P_structural]

## The T_field proof (why this matters)

The framework's single remaining assumption was: "why fundamental representations?"

**Answer: Landau pole exclusion from A1.**

| Step | What | Source |
|------|------|--------|
| 1 | SU(3)³ anomaly → 9 allowed (R_Q, R_u, R_d) | Pure algebra |
| 2 | A1 → no Landau pole → b₃ ≤ 0 | A1 + T1+T2+T3 |
| 3 | b₃(6) = +9, b₃(8) = +13 → **EXCLUDED** | Pure rep theory |
| 4 | b₃(3bar) = b₃(3) but CPT equivalent | Pure QFT (T1+T2+T3) |
| 5 | Anomaly Diophantine → unique hypercharges | Exact arithmetic |

**No A5 minimality needed.** Fundamentals are the ONLY UV-safe option.

## Physical structure corollaries (all [P])

From the unique hypercharges:
- **Q_u = 2/3, Q_d = -1/3** — fractional charges derived, not postulated
- **Q_e = -1** — integer electron charge from anomaly equation
- **Q_ν = 0** — neutrino existence and neutrality derived
- **Q_proton + Q_electron = 0** — neutral atoms from SU(2)²×U(1) anomaly
- **|Q_p/Q_e| = 1 exactly** — tested to 10⁻²¹, here it's an algebraic identity
- **Mesons (qq̄) and baryons (qqq) only** — from fundamental rep color singlets

## Session trajectory

| Metric | Start | Now |
|--------|-------|-----|
| [P] | 37 (77%) | **43 (88%)** |
| [P_structural] | 8 | **6** |
| [C_structural] | 2 | **0** |
| [C] | 1 | **0** |
| Predictions | 8 | **13** |
| Regime-dependent | 2 | **0** |
| QFT imports | 2 | **0** |

## What remains (6 [P_structural] — all genuine open physics)

| Theorem | Gap | What's needed |
|---------|-----|--------------|
| T4G | Yukawa hierarchy | Majorana vs Dirac (open physics) |
| T4G_Q31 | Neutrino mass bound | Same Majorana/Dirac question |
| T10 | κ constant | UV completion (C_total) |
| T11 | Λ value | UV completion (C_total) |
| T12E | f_b ratio | UV completion (α_eff = C_dark/C_visible) |
| T6B | RG running | Capacity ↔ momentum scale mapping |

None of these are closable by better math — they need new physics or a new axiom.
