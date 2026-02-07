# RED TEAM AUDIT — FCF v3.6
## Post-Upgrade Assessment
## Date: 2026-02-07

---

## EXECUTIVE SUMMARY

After the Batch 1 epistemic upgrade (37/48 [P], 77%), the framework's attack
surface has shrunk considerably. This audit examines:

  A. What a hostile reviewer attacks first
  B. Whether any [P] labels are too generous
  C. Whether any remaining [P_structural] can be upgraded
  D. Structural risks the dashboard doesn't show

---

## A. HOSTILE REVIEWER ATTACK PRIORITY

### ATTACK 1 (CRITICAL): "sin²θ_W = 3/13 depends on T6 which is P_structural"

CLAIM: T24 → T_sin2theta derives sin²θ_W = 3/13. All marked [P].
ATTACK: T_sin2theta depends on T6 (sin²θ_W = 3/8 at unification) which
        is P_structural. Does the crown jewel actually stand without T6?

ANALYSIS: The 3/13 value comes from the FIXED-POINT mechanism:
  T19 (routing sectors) → T22 (competition matrix) → T23 (fixed point r*)
  → T24 (sin²θ_W = 3/13 from x = b₂/b₁)
  
This chain does NOT flow through T6. T6 gives the UNIFICATION boundary
condition (3/8); T24 gives the IR fixed-point (3/13). These are
INDEPENDENT derivations that converge — the framework predicts both.

VERDICT: [P] label on T24/T_sin2theta is CORRECT. The fixed-point chain
  is self-contained. T6's role is as an independent consistency check,
  not a dependency. BUT: the dependency list on T_sin2theta should be
  audited to confirm T6 is not listed as a prerequisite.

ACTION NEEDED: Verify T_sin2theta dependency chain excludes T6.

---

### ATTACK 2 (HIGH): "T12 dark matter is regime-dependent, not a prediction"

CLAIM: DM = gauge-singlet capacity, not a particle species.
ATTACK: This depends on regime assumptions R12.1 (linear cost scaling)
        and R12.2 (efficient allocation). These are modeling choices,
        not derived from axioms. Any regime assumption can produce
        any answer.

DEFENSE: 
  - R12.1 (linear scaling) is the simplest functional form consistent
    with A1 (finite capacity). Nonlinear forms would need justification.
  - R12.2 (efficiency) follows from A5 (minimality of enforcement cost).
  - The framework's DM is qualitative (existence + mechanism), not
    quantitative. The Ω_DM/Ω_b ratio bounds are wide.
  - The key structural claim (DM exists as capacity residual) follows
    from A1 alone: total capacity > gauge-committed capacity → remainder
    must go somewhere.

VERDICT: P_structural is CORRECT. The existence argument is strong;
  the quantitative details (f_b = 0.200 vs observed 0.157) genuinely
  depend on regime assumptions. Could potentially split:
  - DM existence → [P] (follows from A1 + capacity budget)
  - DM quantitative ratio → [P_structural|regime]
  
ACTION NEEDED: Consider splitting T12 into T12_exist [P] and T12_quant [P_structural].

---

### ATTACK 3 (HIGH): "C_structural theorems break the proof chain"

CLAIM: T9_grav (Einstein equations) and Gamma_signature (Lorentzian) are
        C_structural — the entire gravity sector hangs on imported physics.
ATTACK: Two C_structural theorems sit in the critical path for T10, T11,
        T12. If these imports fail, everything above them fails too.

ANALYSIS:
  T9_grav imports Lovelock (1971): "In d=4, the only divergence-free
  second-order symmetric (0,2)-tensor built from metric is a*G_uv + b*g_uv."
  This is actually a PURE MATHEMATICS theorem — a classification result in
  differential geometry. It's no different from importing Kochen-Specker
  or GNS construction. The "physics" is in the BRIDGE (do our axioms
  actually produce the hypotheses Lovelock requires?), and that bridge
  goes through Gamma_geo closure which is now [P].

  Gamma_signature imports HKM (1976) + Malament (1977): These are theorems
  about partial orders and conformal geometry. Again, pure mathematics.
  The bridge from A4 (irreversibility) to HKM's hypotheses is: A4 →
  strict partial order → causal structure. This is a logical implication.
  The "chartability" hypothesis (H2 in HKM) is the genuine bridge gap.

VERDICT: UPGRADE OPPORTUNITY.
  - T9_grav: Lovelock is pure math. If Gamma_closure [P] provides all
    hypotheses, T9_grav should be [P|import], not C_structural.
  - Gamma_signature: HKM+Malament are pure math. The A4→causal bridge
    is logical. The chartability (H2) bridge is the one gap.

ACTION NEEDED: Audit whether Gamma_closure provides Lovelock's hypotheses.
  If yes, upgrade T9_grav → [P|import]. Examine chartability bridge for
  Gamma_signature.

---

### ATTACK 4 (MEDIUM): "T4G Yukawa is circular — enforcement cost IS mass"

CLAIM: y_f ~ exp(-E_f/T) where E_f = enforcement cost of f-type distinction.
ATTACK: "Enforcement cost" ordering is just mass ordering restated.
        You're defining E_f to match the mass hierarchy, then claiming
        you derived the mass hierarchy.

DEFENSE:
  - E_f is defined INDEPENDENTLY of mass: it's the graph-enforcement
    cost of maintaining the identity distinction between generation copies.
  - The ordering (E_top < E_bottom < E_charm ...) comes from the capacity
    partition structure in T4E/T4F, not from mass measurements.
  - However: the EXPONENTIAL form y_f ~ exp(-E_f/T) is assumed, not derived.
    The framework derives the ORDERING but not the FUNCTIONAL FORM.

VERDICT: P_structural is CORRECT but the summary should clarify:
  - DERIVED: ordering of enforcement costs from capacity partition
  - ASSUMED: exponential suppression form
  - OPEN: absolute mass scale (needs T10 UV bridge)

ACTION NEEDED: Strengthen T4G summary to distinguish derived vs assumed.

---

### ATTACK 5 (MEDIUM): "Your β-functions are just Standard Model β-functions"

CLAIM: T21 derives β-function form from capacity saturation.
ATTACK: T6B uses "admissibility β-functions" that are functionally identical
        to the SM one-loop β-functions. You're reimporting QFT under a
        different name.

DEFENSE:
  - T21 derives the FORM β_i = -b_i g_i³/16π² from capacity competition.
  - The b_i COEFFICIENTS depend on field content (from T_field, which
    depends on the [C] convention R_field).
  - The form is derived; the coefficients use field content input.
  - T6B uses these to run sin²θ_W from 3/8 → 0.231. This running
    is not independent of T24's fixed-point result — they must agree.

VERDICT: P_structural on T6/T6B is CORRECT. The β-coefficient values
  are physics inputs (from QFT loop calculations), not derived from
  pure axioms. This is properly flagged.

---

## B. [P] LABELS — ANY TOO GENEROUS?

### B1: T4E (N_gen = 3) — SOLID
Pigeonhole argument from capacity budget. Pure integer arithmetic.
No hidden assumptions. [P] is correct.

### B2: T_Higgs — NEEDS SCRUTINY
Claims Higgs existence from EW pivot. The IVT argument shows V(Φ)
has a minimum with positive curvature → massive scalar. But:
  - V(Φ) is derived from admissibility potential, not from SM Lagrangian
  - The "9/9 models" are computational witnesses for the derived V(Φ)
  - The EXISTENCE is proven; the MASS VALUE (125 GeV) is not derived

VERDICT: [P] is correct for existence claim. The summary should not
  imply mass value prediction.

### B3: T1 (Kochen-Specker import) — SOLID
KS → incompatible observables. Bridge from A2 is logical implication.
[P] is correct.

### B4: T3 (Skolem-Noether + DR import) — CHECK BRIDGE
Claims locality → gauge bundles. Imports Skolem-Noether + Doplicher-Roberts.
The bridge from A3 (locality) to DR's hypotheses requires:
  A3 → separability of observables → DR superselection
This bridge is non-trivial. DR requires:
  (i) Observable algebra net
  (ii) Haag duality condition
  (iii) Positive energy condition

Does A3 alone give all three? (i) yes via T2. (ii) requires argument.
(iii) requires A4 (irreversibility → energy positivity).

VERDICT: [P] is PROBABLY correct but the bridge should document which
  axiom gives each DR hypothesis. Currently the bridge argument is
  compressed into the summary.

ACTION NEEDED: Expand T3 bridge documentation.

---

## C. UPGRADE OPPORTUNITIES

### C1: T9_grav (C_structural → P|import)
Lovelock (1971) is pure mathematics. If Gamma_closure provides:
  - Smooth manifold (from Gamma_continuum [P])
  - Metric tensor (from Gamma_ordering [P])  
  - d = 4 (from T8 [P])
  
Then Lovelock's hypotheses are all satisfied and this should be [P|import].
BLOCKER: Does Gamma_closure provide a Levi-Civita connection? Lovelock
needs the Riemann tensor, which requires a connection.

ESTIMATE: Likely upgradeable if connection derivation is explicit.

### C2: Gamma_signature (C_structural → P|import)
HKM (1976) + Malament (1977) are pure mathematics about causal structures.
Bridge: A4 → causal order → HKM hypotheses.
BLOCKER: HKM's chartability hypothesis (H2). Does Gamma_continuum [P]
provide chartability? If manifold structure is already derived, then yes.

ESTIMATE: Likely upgradeable with one paragraph of bridge argument.

### C3: T12 existence (P_structural → P)
DM existence follows from capacity budget argument:
  C_total > C_gauge_committed → residual > 0 → must manifest as
  gauge-singlet correlation (no other channel available by T_gauge).
This is pure logic from A1 + T_gauge. No regime assumptions needed
for EXISTENCE. Only the QUANTITATIVE ratio needs R12.

ESTIMATE: Splittable into T12_exist [P] + T12_quant [P_structural].

---

## D. STRUCTURAL RISKS

### D1: Single [C] theorem (T_field) is load-bearing
T_field (field content template {Q,L,u,d,e}) is the ONLY [C] theorem.
It's a regime INPUT, not a derivation. Everything in Tiers 2-3 that
uses specific field content ultimately traces to this.

RISK: If a reviewer argues this [C] invalidates everything above it.
DEFENSE: The framework is EXPLICIT that field content is input within
  the admissibility filter. The filter CONSTRAINS what content is
  admissible; it doesn't predict it from nothing. This is a feature,
  not a bug — the framework says "IF the field content is {Q,L,u,d,e}
  THEN these consequences follow necessarily."

### D2: The T6→T6B→T_sin2theta consistency check is untested
The dashboard shows sin²θ_W = 3/13 from the fixed-point. But the
running chain (3/8 at unification → 0.231 at M_Z) should ALSO give
≈3/13. If these don't agree, it's a serious inconsistency.

RISK: No computational check that the two paths converge.
ACTION: Add a numerical test that the β-function running from 3/8
  actually lands near 3/13 ≈ 0.2308.

### D3: f_b prediction is 27% off
f_b = 0.200 predicted vs 0.157 observed is a 27% error. This is the
WORST prediction in the framework and a reviewer will highlight it.
DEFENSE: This depends on α_eff = 4.0, which is a structural estimate.
  The framework predicts f_b ∈ (0, 0.5); the specific value depends
  on capacity ratio details. The 27% error is honest.

---

## RECOMMENDED ACTIONS (PRIORITY ORDER)

1. **Verify T_sin2theta deps exclude T6** — protects crown jewel
2. **Audit T9_grav Lovelock bridge** — potential upgrade C_structural → P
3. **Audit Gamma_signature HKM bridge** — potential upgrade C_structural → P
4. **Split T12 into exist/quant** — upgrades DM existence to [P]
5. **Add convergence test** (T6B running vs T24 fixed-point)
6. **Expand T3 bridge documentation** — preemptive reviewer defense
7. **Clarify T4G derived vs assumed** — honest about functional form

If actions 2+3 succeed: 39/48 [P] (81%), 0 C_structural
If action 4 succeeds: 40/48 [P] (83%)

---

## FINAL ASSESSMENT

The framework is in strong shape post-upgrade. The 8 remaining P_structural
are LEGITIMATELY structural — no dishonest labeling. The 4 open physics
theorems are genuinely waiting on UV completion (new physics, not proof
technique). The 2 C_structural theorems are the most promising upgrade
targets.

The biggest reviewer risk is not epistemic labels — it's the CONSISTENCY
of the two sin²θ_W derivation paths (fixed-point vs running). This should
be tested computationally before submission.
