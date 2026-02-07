# FCF v3.6 Deployment — Full Push

## Files to Upload (7 files → repo root)

| File | What changed |
|------|-------------|
| `Admissibility_Physics_Engine_V3_5.py` | T0 integration, T12 split, regime gates closed, T_field derived, C_structural→P, 21 audit checks |
| `Admissibility_Physics_Theorems_V3_5.py` | T_field [C]→[P_structural], T6B honesty fix, T_channels dep flipped |
| `Admissibility_Physics_Gravity_V3_5.py` | Gamma_signature [C_structural]→[P] with HKM bridge |
| `Admissibility_Physics_Dashboard_V3_5.html` | New Constants tab (12 constants with derivation chains), rep_selection reason code |
| `dashboard_data.json` | 49 theorems, 41 [P], 0 [C], 0 [C_structural] |
| `theorem_0_canonical_v4.py` | Axiom witness module (already in your repo — confirm it's there) |
| `github_workflows_update_dashboard.yml` | Already deployed — no changes needed |

## Steps

### 1. Go to your repo
https://github.com/ethan-brooke/Admissibility-Physics-Engine-V-3.5

### 2. Upload the 6 files (skip workflow if already deployed)

**Option A — GitHub web UI:**
- Click **Add file → Upload files**
- Drag all 6 files in
- Commit message: `v3.6: 41P/8Ps, zero C/Cs, Constants tab, T0 integrated, regime gates closed`
- Commit to `main`

**Option B — Git CLI:**
```bash
cd Admissibility-Physics-Engine-V-3.5
# copy files into repo directory, then:
git add -A
git commit -m "v3.6: 41P/8Ps, zero C/Cs, Constants tab, T0 integrated, regime gates closed"
git push origin main
```

### 3. Verify Actions run
- Go to **Actions** tab
- The `update_dashboard.yml` workflow should trigger (it fires on `.py` file changes)
- It regenerates `dashboard_data.json` and commits it back
- Wait ~30 seconds for it to complete

### 4. Verify dashboard
- Go to: https://ethan-brooke.github.io/Admissibility-Physics-Engine-V-3.5/Admissibility_Physics_Dashboard_V3_5.html
- Check:
  - Hero cards show **49 theorems, 41 [P], 0 cycles**
  - **Constants tab** appears (7th tab)
  - Click `sin²θ_W` card → chain expands with green dots
  - Status tab shows **0 C_structural, 0 C, 0 regime-dependent**

### 5. Confirm `theorem_0_canonical_v4.py` is in repo
The engine imports it at runtime. If it's not in the repo, the Action will skip T0 gracefully (49→48 theorems). Upload it if missing.

## What Changed (Session Summary)

| Metric | v3.5 | v3.6 |
|--------|------|------|
| Theorems | 48 | **49** |
| [P] | 37 (77%) | **41 (84%)** |
| [P_structural] | 8 | 8 |
| [C_structural] | 2 | **0** |
| [C] | 1 | **0** |
| Regime-dependent | 2 | **0** |
| Audit checks | 12 | **21** |
| Dashboard tabs | 6 | **7** |
