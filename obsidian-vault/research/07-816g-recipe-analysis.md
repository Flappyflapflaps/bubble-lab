---
title: "Analysis — User's 816 g-water 'Best So Far' Recipe: Why It Made Huge Bubbles That Failed in Wind"
date: 2026-05-15
tags: [analysis, recipe-comparison, wind-failure-mechanism, coacervate, sovereign-ipn, science-grounded]
status: analysis
related: ["[[00-world-class-recipe-v2]]", "[[The Sovereign Semi-IPN Kinetic Assembly Protocol]]", "[[06-real-raw-surfactant-recipes]]"]
---

# Analysis — Why the 816 g recipe gave huge bubbles but failed in wind

## The recipe under analysis (the user's "best so far")

| Component | Mass per 1 L | Active mass | Active wt % | Role |
|---|---|---|---|---|
| Distilled water | 816.0 g | — | — | Solvent |
| Vegetable glycerin | 100.0 g | — | 10 % | Humectant |
| IPA 99 % | 30.0 g | — | 3 % | Polymer slurry wetting |
| SLES-70 paste | 35.0 g | 24.5 g | 2.45 % | Primary anionic |
| CAPB-35 | 12.0 g | 4.2 g | 0.42 % | Amphoteric synergy partner |
| LDAO-30 | 5.0 g | 1.5 g | 0.15 % | Non-ionic foam booster |
| PEO WSR-301 aged | 0.2 g | 0.2 g | 0.02 % | Extensional "stretch" polymer |
| Anionic PAM HMW | 0.05 g | 0.05 g | 0.005 % | Structural scaffolding |
| Dipotassium phosphate | 1.5 g | — | — | Primary buffer |
| Sorbic acid | 2.0 g | — | — | pH lock to ~5.5–6.0 (titrant + preservative) |
| **Total surfactant actives** | — | **30.2 g** | **~3.02 %** |  |

Field result reported: **big bubbles in calm conditions, poor wind survival.**

---

## Verdict — substantially science-based, with three specific addressable wind-failure mechanisms

The recipe gets the most important thing right: **the surfactant architecture matches Fairy.**

- **SLES + CAPB + LDAO in approximately Fairy's INCI ratio.** This is the *working* architecture of commercial dish soap. Frazier 2020 measured Dawn (same SLES+CAPB+LDAO + minor co-surfactants) at ~22 s film life vs raw SDS at ~5 s on a 100 cm² film. The synergy is real and measured.
- **10 % glycerin exactly matches Pasquet 2022's measured optimum** (140× lifetime vs 0 % glycerin).
- **IPA for polymer slurry** is sound technique — prevents fish-eye gel-blocking of UHMW PEO/PAM during hydration.
- **Distilled water** is correct for Ca²⁺-sensitive HPAM.

Three of the four pillars of giant-bubble physics done right. The huge bubbles you observed in calm conditions are the experimental proof.

The wind failure is *not* a problem with the surfactant stack. It's caused by three other choices — each of them identifiable, each fixable.

---

## Mechanism 1 (probably dominant): the sorbic-acid pH lock creates a coacervate that shear-melts

Sorbic acid at 2 g/L is a strong-enough acid to titrate the mix down to roughly **pH 5.5–6.0** even with 1.5 g/L DKP buffering present. At that pH:

- **CAPB is below its isoelectric point** (pI ≈ 6.25, Mitrinova 2013 measured value). The carboxylate group on CAPB is protonated; the quaternary ammonium is the only charged group; **CAPB becomes net-positive.**
- **SLES is fully anionic** across the working pH range (5–10).
- **Net-positive CAPB + net-negative SLES = strong electrostatic attraction.** They co-precipitate at the air-water interface as an *associative coacervate* — a gel-like ionic-crosslinked network.

**Why this gives huge bubbles in calm conditions:**
- Coacervate films are mechanically strong in still air. The ionic crosslinks provide high static yield stress. The film feels thick, drains slowly, can be inflated to enormous diameter before gravity-driven thinning ruptures it.
- This is what makes the "Sovereign Semi-IPN" lock work for indoor / sheltered-garden record attempts.

**Why this fails in wind:**
- The electrostatic crosslinks in a coacervate are **shear-sensitive** — when a gust stretches the film locally, ionic bonds break before the polymer chains can extend to absorb the stress. The gel network unzips, and the film snaps.
- Polymer + surfactant coacervates have a measured *yield-thin* rheology: high static modulus, very low modulus once flowing. That's the exact rheology profile that fails a gust.

This matches the field observation precisely: huge bubbles when calm, sudden rupture under any gust.

**Pasquet 2022 measured the consequence directly:** neutralising her Fairy + guar recipe from free-running pH 7.5 down to pH 7.0 reduced lifetime. She didn't titrate further down, but the trend strongly suggests pH 6 would be worse for film durability under mechanical stress — exactly what we see in the field.

**Source vault notes:** [[The Sovereign Semi-IPN Kinetic Assembly Protocol]] documents the coacervate mechanism; the "electrostatic lock" terminology originates there. [[03-ph-buffer-water]] tabulates CAPB pI = 6.25 and gives the three pH-regime mechanism map.

---

## Mechanism 2: total surfactant ~3 % is above Pasquet's measured ceiling

Pasquet 2022 ran a controlled experiment varying total surfactant from 20 % Fairy down to 1 % Fairy. **Lifetime increased by 50× as she went from 20 % to 1 %.** Counterintuitively, *less* surfactant = *longer* bubbles. Her measured peak was **1.0–1.5 % total active surfactant**.

The 816 g recipe sits at ~3.0 % active total — about double the measured optimum.

**Mechanism:** excess surfactant in the bulk creates "reservoir" micelles that buffer the interfacial layer. When a perturbed interface (a stretched film) re-equilibrates, the rapid micelle-to-interface exchange *reduces* Marangoni elasticity (the surface-tension gradient that re-stiffens a stretched film). Marangoni elasticity is what saves a film from breaking when it gets stretched. Too much surfactant kills it.

Below the CMC there's no micellar reservoir; well above the CMC the reservoir is so big that interfacial perturbations equilibrate too fast. There's a sweet spot ~3–10× CMC where the interfacial response is fastest but the reservoir is small enough to preserve Marangoni gradients. That sweet spot lands at ~1.0–1.5 % total active for SLES-based systems.

(Source: Pasquet 2022 EPJ E 45:96, Section "Influence of surfactant concentration".)

---

## Mechanism 3: 250 ppm dual-polymer load creates a brittle viscoelastic network

The PEO 200 ppm + HPAM 50 ppm = 250 ppm total polymer is high enough that the two polymers' entanglement networks overlap and reinforce each other. That's good for *static* extension (= big bubbles in still air). It's bad for *transient* extension under gust shock for two reasons:

1. **Relaxation time mismatch.** PEO WSR-301 (4 MDa) has a relaxation time around 1–10 ms. HPAM HMW (12–18 MDa) has a relaxation time around 100 ms – 1 s. A gust shock has a strain rate around 10–100 s⁻¹ — fast enough that HPAM's slow chains can't relax and end up *snapping* under tension rather than extending.

2. **Polydispersity bias toward HPAM.** The Frazier 2020 polydispersity finding favours a *broad* molecular weight distribution. The 4:1 PEO:PAM mass ratio in the 816 g recipe lands a relaxation-time spectrum that's mass-dominated by the *long* end (HPAM). For calm conditions that's fine — long-relaxation chains hold a big static film. For gusts, short-relaxation chains absorb the shock without snapping. The 816 g blend has too few short-relaxation chains by mass.

The vault note [[Polymer Degradation Dynamics in Giant Bubble Formulations]] makes the actionable rule: in gusts, drop PAM (the long-relaxation component) and bias toward aged-PEO (broader, shorter distribution).

---

## How the grounded v2 fixes each failure

| Failure in 816 g recipe | Fix in grounded v2 mainline |
|---|---|
| Sorbic acid pH lock → coacervate → shear-melts in wind | **No pH adjuster, no buffer, no sorbic acid.** Free-running pH 7.5–8.0. CAPB stays net-negative; no electrostatic coacervate forms. (Pasquet measured.) |
| ~3 % total active surfactant — above Pasquet's measured ceiling | **2.0 % total active** (1.4 % SLES + 0.45 % CAPB + 0.15 % LDAO). Slight margin above the 1.5 % measured peak for wand-fluid-uptake headroom. |
| 250 ppm dual-polymer brittle network | **One polymer at documented working range.** Three candidates for bake-off — guar 0.15 % (Pasquet measured optimum), HEC 0.22 % (Flavour Blaster commercial level), J-Lube 0.04 % (polydisperse PEO practitioner). |
| DKP buffer to pH 7.4 contradicts Pasquet's measured finding | **No DKP, no buffer.** Free-running. |
| IPA needed for dry-PEO/PAM slurry | **No IPA needed** — guar/HEC/J-Lube slurry directly into glycerin. One fewer variable. |

**The surfactant stack stays.** The architecture you had was right. The grounded v2 keeps SLES + CAPB + LDAO at Fairy-matched ratio, keeps 10 % glycerin, keeps distilled water + EDTA chelation. It only changes the three things that caused the wind failure:

1. Drops the sorbic-acid pH lock → no coacervate, no shear-melt.
2. Drops surfactant total to 2 % → matches Pasquet's measured ceiling.
3. Drops dual polymer for single polymer at working range → no brittle network.

---

## Practical advice: what to do with a remaining batch of the 816 g recipe

If you still have a bottle of the 816 g recipe mixed:

- **It's still useful as a still-air-only brew.** Indoor demos, sheltered-garden sessions, calm-dawn record attempts. The coacervate mechanism that fails in wind is *strong* in still air — the recipe will still throw the big bubbles you saw.
- **Don't take it out in wind.** The coacervate will keep failing in gusts. No amount of mixing-protocol refinement fixes the mechanism.
- **Don't try to "save" it by adding bicarb to push the pH up.** Once sorbic acid is in solution, partial neutralisation just makes the buffering capacity bigger without resolving the underlying coacervate-prone composition. Brew fresh.

---

## The experiment that proves the diagnosis

The cleanest validation: brew a **direct comparator** to the 816 g recipe. Same SLES + CAPB + LDAO at the *same* concentrations, same 10 % glycerin, same IPA + dual polymer — but **no sorbic acid, no DKP buffer**. Free-running pH lands ~7.5–8.0.

If the diagnosis is right:
- **Bubble size in still air** ≈ 816 g recipe (architecture is the same).
- **Wind survival** is dramatically better (no coacervate to shear-melt).

If the diagnosis is wrong:
- Bubble size drops in still air too (suggests the coacervate was load-bearing, not just shear-fragile).
- Wind survival doesn't change (suggests the surfactant or polymer composition was the wind issue, not pH).

Either way, the experiment resolves the question with one batch. (For the cleanest test, also drop the total surfactant from 3 % to 2 % per Mechanism 2; that's the v2 grounded recipe.)

---

## Provenance

**Primary literature:**
- Pasquet, M. et al. (2022). "An optimized recipe for making giant bubbles." Eur. Phys. J. E 45:96. [arXiv:2209.04435](https://arxiv.org/abs/2209.04435). — Surfactant concentration sweep (20 % → 1 % Fairy = 50× lifetime increase); pH neutralisation hurts lifetime; 10 % glycerin = 140× lifetime peak.
- Frazier, S., Jiang, X., Burton, J.C. (2020). "How to make a giant bubble." Phys. Rev. Fluids 5:013304. — Dawn vs raw SDS film lifetime measurement; polydispersity finding.
- Mitrinova, Z. et al. (2013). "Surface and foam properties of SLES + CAPB + fatty acid mixtures: Effect of pH." Colloids Surf A. — CAPB isoelectric pH 6.25 measurement; surface modulus G' boost from amphoteric + non-ionic addition.

**Vault notes:**
- [[The Sovereign Semi-IPN Kinetic Assembly Protocol]] — coacervate mechanism and "electrostatic lock" terminology.
- [[03-ph-buffer-water]] — three pH-regime map; CAPB pI; Mitrinova SLES+CAPB+myristic G' data.
- [[Polymer Degradation Dynamics in Giant Bubble Formulations]] — polymer-in-wind rules; aged-PEO shock-absorption rationale.
- [[00-world-class-recipe-v2]] — the grounded honest mainline that fixes all three failure mechanisms.
- [[06-real-raw-surfactant-recipes]] — verbatim harvest of published raw-surfactant recipes; confirms SLES + CAPB + LDAO is the only architecturally-grounded raw-recreated path.

---

*Analysis written 2026-05-15. The 816 g recipe is the user's most successful self-built formulation to date — substantially correct on architecture (SLES + CAPB + LDAO + 10 % glycerin + distilled water), with three specific, identifiable, individually addressable failure modes for wind survival. The grounded v2 mainline keeps the parts that worked and removes the parts that failed.*
