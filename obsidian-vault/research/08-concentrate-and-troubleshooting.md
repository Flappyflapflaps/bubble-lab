---
title: "Surfactant Concentrate Manufacture + Troubleshooting (Glittering, Fallout, Storage)"
date: 2026-05-15
tags: [concentrate, manufacturing, troubleshooting, glittering, storage, coacervate]
status: practical-guide
related: ["[[00-world-class-recipe-v2]]", "[[07-816g-recipe-analysis]]"]
---

# Surfactant concentrate + troubleshooting guide

## Part 1 — Making a surfactant-only concentrate

### Why concentrate?

Pro-grade approach. Commercial bubble juice makers (Bubble Inc Supapop, Dr Zigs, Bubblelab, Bubblebabez) all sell concentrates rather than mixing fresh each session. Advantages:

1. **Buy raw surfactants once, mix juice on demand.** No need to weigh tiny doses each batch.
2. **Stable storage.** Surfactant-only concentrates keep 6–12 months at room temperature; finished bubble juice with polymer and glycerin keeps 2–6 weeks.
3. **Consistency.** Same surfactant ratio every batch; only water + glycerin + polymer + EDTA varies.
4. **Polymer bake-off becomes trivial.** Same surfactant base + different polymer = isolate the variable.

### Concentrate recipe (10× — makes 10 L of finished v2 grounded juice)

| Ingredient | Mass per 1 L concentrate | Active mass | Notes |
|---|---|---|---|
| Distilled water | 600 g | — | Carrier — keeps it pourable. SLES-70 paste is too thick alone. |
| SLES-70 paste | 200 g | 140 g | Primary anionic — matches Fairy's primary. |
| CAPB-30 | 150 g | 45 g | Amphoteric synergy partner. |
| LDAO-30 (Ammonyx LO) | 50 g | 15 g | Non-ionic foam booster. |
| **Optional preservative:** | | | |
| Potassium sorbate | 1.0 g | — | Works at pH < 6.5. Most concentrates land below this naturally. |
| OR Sodium benzoate | 1.0 g | — | Works at pH > 4.5. Either works for this recipe. |

**Total: ~1001 g per 1 L concentrate.**

### Why these ratios

Matches the grounded v2 mainline 1:1 when diluted 10×:
- 14 g SLES active per 1 L finished = 1.4 % active ✓
- 4.5 g CAPB active per 1 L finished = 0.45 % active ✓
- 1.5 g LDAO active per 1 L finished = 0.15 % active ✓

### Mixing protocol — concentrate

1. **Warm the SLES-70 paste** in its container to 25–30 °C (sit in a warm-water bath for 10 min). Cold SLES is thick and hard to dissolve.
2. **In a clean 2 L jug:** weigh 600 g distilled water.
3. **Add SLES-70 paste 200 g** in a thin stream while stirring slowly with a spatula. Don't whip — surfactants foam easily. Stir until optically clear (~5 min).
4. **Add CAPB-30 150 g** slowly while stirring. Mixture stays clear.
5. **Add LDAO-30 50 g** slowly while stirring. Should remain clear, very faintly straw-coloured.
6. **(Optional) Add 1 g preservative** and stir to dissolve.
7. **Pour into clean 1 L HDPE bottles** with tight caps. Label clearly: "v2 grounded surfactant concentrate — 10× — 1 part concentrate + 9 parts diluent."

### Dilution — making 1 L of finished juice from concentrate

1. In a clean 2 L bucket: **770 g distilled water + 0.5 g disodium EDTA**. Dissolve.
2. **Polymer slurry:** in a 250 mL beaker, **100 g glycerin + your polymer dose** (1.5 g guar OR 2.2 g HEC OR 0.4 g J-Lube). Stir until dispersed.
3. Slow paddle the water-EDTA into a vortex. Pour the glycerin/polymer slurry into the vortex centre. Stir gently 5 min. Cover. **Rest 12–24 hr.**
4. After rest, slow paddle. **Pour in 100 g of concentrate** in a thin stream over 30 s. Fold gently 5 min until optically clear.
5. Rest another 24–48 hr cool dark. Use within 2 weeks.

### Concentrate shelf life and storage

- **Sealed, room temperature:** 6–12 months. Surfactants don't degrade in solution; preservative extends viability against bacterial growth.
- **Don't refrigerate.** SLES-70 starts to gel below ~10 °C; once gelled it doesn't fully re-dissolve cleanly.
- **Don't expose to direct sunlight.** UV can slowly oxidise the ether linkage in SLES (very slow at room light).
- **Glass or HDPE only.** PET bottles slowly leach trace antimony — not a bubble-juice problem but bad practice.
- **If concentrate goes cloudy over time:** filter through a coffee filter to remove suspended particles. Most likely cause is trace tap-water contamination during manufacture; small amounts are cosmetic, not functional.

### Cost breakdown (UK 2026 prices)

| Item | Cost per 1 L concentrate | Cost per 1 L finished juice |
|---|---|---|
| SLES-70 paste 200 g | £4 | £0.40 |
| CAPB-30 150 g | £2.40 | £0.24 |
| LDAO-30 50 g | £1.50 | £0.15 |
| Preservative + water | £0.20 | £0.02 |
| Glycerin 100 g | — | £0.60 |
| Polymer (HEC) 2.2 g | — | £0.20 |
| EDTA 0.5 g | — | £0.02 |
| **Per 1 L** | **~£8** concentrate | **~£1.63** finished juice |

---

## Part 2 — Troubleshooting glittering, fallout, and storage problems

### Symptom: glittery flecks appear after 12–48 hours

#### Most likely cause if the recipe used a pH lock below 7 (e.g., the 816 g recipe with sorbic acid):

**CAPB-SLES coacervate particle aggregation.**

Mechanism:
- At pH ~6, CAPB sits below its isoelectric point (pI = 6.25, Mitrinova 2013) → net-positive
- SLES is net-negative across pH 5–11
- Electrostatic pairing → associative coacervate (gel-like ionic-crosslinked network)
- At low concentration: invisible nano-domains
- Over 24+ hours: domains aggregate into visible micron-scale particles → "glittering"

**This is the "electrostatic lock" working at the macroscopic level.** It's the same mechanism that gives huge bubbles in calm air *and* shear-melts in wind.

**Fix:** raise pH above 6.5 (CAPB returns to net-negative, no coacervate). Or — better — formulate without a pH lock from the start. The grounded v2 mainline at free-running pH 7.5–8.0 doesn't do this.

#### Other possible causes (if pH is above 7):

**(a) Lime-soap precipitate** (SLES + Ca²⁺ → insoluble fatty-acid calcium salts)
- Symptom: white waxy specks; more in hard-water regions
- Fix: use distilled water + 0.5 g/L EDTA (chelates Ca²⁺ to non-precipitating complex)

**(b) NaCl recrystallisation** (only if Fairy/Dawn was the surfactant source)
- Symptom: clear sparkling crystals; happens after cold storage and re-warm
- Fix: not an issue with raw SLES + CAPB + LDAO (no added salt)

**(c) HPAM aggregation** (anionic polyacrylamide cross-linking with trace Ca²⁺)
- Symptom: stringy sparkles or filamentous "fish-eyes"
- Fix: distilled water + EDTA; mix polymer with low-shear paddle only (high shear scissions chains, then the broken ends cross-link more easily); use within 4 weeks

**(d) Cold-crystallised LDAO**
- Symptom: needle-like crystals; appears after cold storage
- Fix: warm gently to 25 °C and stir; don't refrigerate the finished juice

**(e) Cetyl alcohol precipitation** (only relevant for v2-Plus / Appendix A2 recipes)
- Symptom: white waxy clumps
- Fix: pre-melt cetyl alcohol into glycerin at 60 °C before combining; don't refrigerate

**(f) Polymer fallout from insufficient hydration**
- Symptom: gel-like clumps or fish-eyes near the surface
- Fix: the 12–24 hr polymer hydration rest at low shear is non-negotiable; skipping it is the most common cause

### Symptom: mix goes cloudy uniformly (not glittering)

- **Cause:** colloidal precipitate from trace metal contamination (iron from tap water, calcium from a not-fully-rinsed bucket)
- **Fix:** filter through coffee filter; add 0.2 g extra EDTA; remix from scratch with cleaner protocol

### Symptom: layer separation (top is clearer than bottom)

- **Cause A — gentle (recoverable):** insufficient mixing during surfactant integration; glycerin denser than water settles
- **Fix A:** stir gently from the bottom up for 5 min; let stand another 24 hr
- **Cause B — chemical (NOT recoverable, recipe-level fault):** **you used citric or lactic acid for chelation or pH adjustment.** Citric acid is ~10⁷× weaker than EDTA; to chelate anything meaningful you have to dose 1-3 g/L which adds ~0.06 mol/L ionic strength to the mix. This causes (1) PAM chain collapse during the pH dip, (2) PAM-PEO Flory-Huggins phase separation at elevated ionic strength, (3) Ca-citrate-PAM salt-bridge aggregation. See [[10-acid-titration-phase-split]] for full mechanism. **Fix:** decant the top layer for one session use; throw the bottom; remake from scratch using only EDTA (0.5-1 g/L) for chelation and free-running pH — no citric, no lactic.

### Symptom: dark yellow / orange tint developing over weeks

- **Cause:** mild oxidation of SLES ether linkage (slow at room temp, faster in sunlight or with metal catalysts)
- **Effect:** mostly cosmetic; mild loss of foam quality (~10%)
- **Fix:** store in opaque HDPE; use within 6 months; add 0.05 g/L sodium metabisulfite as antioxidant if you want extra-long storage

### Symptom: foam-only when stirred, no big bubbles when used

- **Cause:** polymer hasn't fully hydrated
- **Fix:** rest another 24 hr; if still foam-only, polymer may be old / oxidised — start with fresh polymer

### Symptom: huge bubbles but they burst on contact with anything

- **Cause:** too much polymer (extensional viscosity too high; rebound bursts the film) or too little glycerin (no humectant cushion)
- **Fix:** dilute 10% with water; or add 1% more glycerin

---

## Part 3 — Storage best-practices summary

| Storage state | Container | Temperature | Light | Shelf life |
|---|---|---|---|---|
| **Surfactant concentrate (no polymer)** | HDPE 1 L sealed | Room temp (15–25 °C) | Opaque or dark cupboard | 6–12 months |
| **Finished v2 grounded juice** | Glass or HDPE | Room temp (15–25 °C) | Dark cupboard | 2–6 weeks |
| **Polymer-rich concentrate** (e.g. HEC slurry in glycerin) | Glass | Room temp | Dark | 1 month |
| **Working tray** (decanted for session) | Any | Ambient | OK to use in sun | Use within session |

**Universal rules:**
- **No refrigeration** for finished juice or surfactant concentrate.
- **No fridge re-warm** — even a few days at 4 °C can crystallise LDAO and gel SLES.
- **No metal containers** — aluminium and steel both react slowly with anionic surfactants.
- **No direct sunlight** for storage — UV slow-oxidises ether linkages.

---

## Provenance

- Mitrinova, Z. et al. (2013). Colloids Surf A — CAPB isoelectric pH 6.25 measurement.
- Stepan Bio-Terge AS-40 datasheet — SLES storage and stability.
- Lubrizol Cellosize HEC technical bulletin — polymer storage and degradation.
- [[00-world-class-recipe-v2]] — grounded recipe mainline.
- [[07-816g-recipe-analysis]] — coacervate mechanism analysis (the source of the glittering observation).
- Practitioner sources: Brian Lawrence (BLM mixing protocol), Samsam Bubbleman / Bubble Inc (concentrate-and-dilute commercial workflow).

---

*Written 2026-05-15. Concentrate recipe scaled from the grounded v2 mainline at 10×. Troubleshooting symptoms ordered by likelihood for the user's specific situation (transition from 816 g pH-locked recipe to v2 grounded free-running mainline).*
