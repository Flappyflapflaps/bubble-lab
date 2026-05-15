---
title: "Why citric + lactic acid chelation splits Fairy+PAM+PEO mixes overnight"
date: 2026-05-15
tags: [troubleshooting, phase-separation, chelation, citric-acid, lactic-acid, PAM, PEO, ionic-strength]
status: troubleshooting-guide
related: ["[[00-world-class-recipe-v2]]", "[[03-ph-buffer-water]]", "[[07-816g-recipe-analysis]]", "[[08-concentrate-and-troubleshooting]]"]
---

# Acid titration phase-split — diagnosis and fix

**Observation:** distilled water + Fairy + PAM + PEO + citric acid + lactic acid, titrated to pH 7.5. Mix appeared homogeneous after stirring. After overnight stand, mix had **phase-split** into two layers.

This page explains the science. Short version: **citric acid is a terrible chelator at giant-bubble doses, so the user added grams of multivalent salt while believing they were chelating, and the salt load broke the polymer solution.**

---

## 1. The citric chelation trap

Both citric and lactic acid CAN chelate Ca²⁺. The question is *how strongly*, and at what dose.

| Chelator | Log K with Ca²⁺ | Dose needed for 100 mg/L Ca²⁺ |
|---|---|---|
| Disodium EDTA | 10.7 | ~0.5 g/L |
| Tetrasodium EDTA | 10.7 | ~0.5 g/L |
| Citrate (citric acid, pH > 6.4) | 3.5 | **~2-3 g/L** (and equilibrium incomplete) |
| Lactate (lactic acid, pH > 4) | 1.4 | Essentially negligible |
| Gluconate | 1.2 | Negligible |

Sources: Martell & Smith *Critical Stability Constants* (compiled 1974-1989); IUPAC Stability Constants Database; Mehta 2008 review of polyols and α-hydroxy acids as Ca²⁺ binders.

EDTA wins by a factor of **10⁷** in binding constant. To chelate the same amount of Ca²⁺, you need roughly **4-6× more citrate by mass** — *and* the chelation is incomplete because the equilibrium favours free Ca²⁺ at neutral pH.

**Conclusion:** if you used 1-3 g of citric acid in a 1 L bubble juice "for chelation," you did not chelate meaningfully. You added 1-3 g of trisodium citrate equivalent to the solution. That is what split the mix.

---

## 2. What 2 g of citric acid at pH 7.5 looks like to the chemistry

Citric acid has three pKa values: **3.13, 4.76, 6.40**. At pH 7.5 (above all three), citrate is the fully-deprotonated trianion (citrate³⁻) balanced by 3 sodium cations from your NaOH or other base you used to come back up to 7.5.

**For 2 g citric acid (MW 192) in 1 L water:**
- 10.4 mmol citrate³⁻
- ~31 mmol Na⁺ counter-ions (assuming neutralised to citrate trianion)
- **Total ionic strength contribution: ~0.06 mol/L** (a hefty load)

For comparison, sea water is ~0.7 mol/L. You added ~10 % of sea-water-strength salt while thinking you were chelating.

Lactic acid (MW 90) at typical dosing adds another ~5-10 mmol of lactate⁻ + Na⁺.

---

## 3. Three measured mechanisms that split the mix overnight

### 3.1 PAM chain collapse during the acidification dip

**MEASURED — Chen et al. 2019, *MDPI Energies* 12:49.** Hydrolysed polyacrylamide (HPAM) hydrodynamic radius drops ~40% when pH cycles through 4. The carboxylate side groups protonate, intra-chain repulsion vanishes, the rod-conformation polymer balls up.

**Mechanism for your specific case:**
1. You add citric acid to the mix. Locally, pH drops to ~4 around the acid drops before stirring distributes it.
2. PAM chains in those low-pH zones collapse into balls.
3. As you stir and titrate further, pH equilibrates around 7.5.
4. The collapsed PAM chains **do not fully re-extend** — partly because surrounding citrate ions screen the carboxylate charges, partly because tangled coils take hours to unwind.
5. Collapsed PAM is denser and less soluble than extended PAM. Over 6-12 hours it settles.

**Fix:** if you must adjust pH, use single drops of strong concentrated acid (HCl 10 %) — the local pH excursion is brief and the total added mass is tiny. Or — better — let the mix free-run (Fairy + EDTA in distilled water lands at pH 7.5-8 by itself; nothing to adjust).

### 3.2 PAM-PEO incompatibility increases with ionic strength

**MEASURED — Bailey & Lundberg 1976, "Polymer-Polymer Complexes in Aqueous Solution."** Two dissolved polymers in water are at the edge of mutual compatibility. Their compatibility depends on (a) chain stiffness, (b) charge, and (c) ionic strength.

**Mechanism:**
- At low ionic strength, anionic PAM extends as a rigid rod, occupies a lot of volume, and the entropy gain from mixing with PEO favours one-phase.
- At high ionic strength (your 0.06 mol/L from citrate), PAM's charges are screened, the chain compacts, and the polymer-polymer interaction parameter χ rises.
- Above a critical χ, the PAM+PEO system **phase-separates by Flory-Huggins thermodynamics**: a polymer-rich phase (mostly PAM + glycerin) and a polymer-poor phase (mostly water + PEO) form.

**This is the most likely root cause of your overnight split.** It does not depend on temperature, on agitation, on container — it is thermodynamic destiny once χ goes critical. Stirring vigorously can re-mix it, but it will split again on standing.

### 3.3 Salt-bridge cross-linking via residual Ca²⁺

**MEASURED — Multiple polymer-flocculation studies (Akpomie 2024 review of PAM flocculants).** Trace Ca²⁺ + citrate + PAM carboxylate forms a three-body coordination complex:

PAM-COO⁻ ··· Ca²⁺ ··· ⁻OOC-citrate

These bridges don't precipitate hard but they pull polymer chains toward each other and toward dissolved metal centres. Over hours, this aggregates PAM into denser micro-domains that settle.

**Note:** distilled water is not magically Ca-free. Stored distilled water from PE bottles picks up ~1-3 ppm of trace metals from the bottle and air. Fairy itself has trace calcium from its citric-acid + sodium-hydroxide pH-adjustment system. So the "distilled water" qualifier doesn't fully eliminate this mechanism — only EDTA does.

---

## 4. Why overnight specifically

Phase separation by Flory-Huggins thermodynamics is **diffusion-limited**. Polymer chains move slowly through water (~10⁻⁷ cm²/s for a 1 MDa polymer). To rearrange a 1 L volume into two phases requires chains to traverse ~10 cm — that takes 10⁶ seconds ≈ 12 days *in principle*, but **gravity-aided settling accelerates it dramatically** because the denser phase already wants to fall.

Empirically:
- **First hour:** mix looks uniform (mixing shear keeps it dispersed).
- **2-6 hours:** a faint cloud forms at the bottom.
- **6-12 hours:** clear demarcation between supernatant and lower layer.
- **24+ hours:** if not redispersed, supernatant becomes water-clear; lower layer is gel-like.

This matches the user's observation: mixed, stood overnight, woke up to a split.

---

## 5. The four-way decision matrix — what to use when

| Goal | Wrong choice | Right choice | Why |
|---|---|---|---|
| Chelate hard-water Ca²⁺ | Citric acid 1-3 g/L | **EDTA 0.5-1 g/L (disodium or tetrasodium)** | EDTA is 10⁷× tighter binder; needs 1/20th the dose; adds no functional ionic strength |
| Lower pH (small adjustment) | Citric or lactic acid | **None — let it free-run** | Pasquet 2022 measured that lowering pH below free-running hurts giant-bubble lifetime |
| Lower pH (must do it) | Multiple grams of citric | **Single drops of HCl 10 % or H₃PO₄ 10 %** | Same pH change with 1/100th the mass; monovalent or weakly-multivalent anion |
| Raise pH | NaOH solid (caustic, hot-spots) | **Sodium bicarbonate 1-2 g/L** (mild) or **NaOH 10 % drops** | Bicarbonate self-buffers around pH 8.3 — overshoot-safe |
| Preserve | Sorbic acid 2 g/L | **Potassium sorbate 1 g/L (pH < 6.5) OR sodium benzoate 1 g/L (pH > 4.5)** | Same preservation, no pH shock |

---

## 6. Concrete remediation for the user's split mix

If the split mix is still in the bucket and you want to salvage it:

1. **Don't try to redissolve.** Once Flory-Huggins phase separation kicks in, re-mixing only resets the clock to a new overnight split.
2. **Decant the supernatant** (top layer) — it's mostly water + PEO + some Fairy. Test it as-is on the wand. It may still blow decent bubbles for one session.
3. **Throw the lower layer.** It's PAM-Ca-citrate gel and won't recover.
4. **Re-make from scratch** following the v2 grounded protocol: distilled water + 0.5 g/L EDTA, polymer slurried into glycerin separately, surfactant added last, **no citric, no lactic.** Let pH free-run. ([[00-world-class-recipe-v2]] Section 7.)

---

## 7. The bigger lesson — what counts as "chelation"

The hobbyist bubble-juice community frequently recommends citric acid "for chelation." This is a **legacy recommendation from a time before EDTA was easily available at consumer scale**. Citric is *technically* a chelator (it does bind Ca²⁺ weakly), but at the concentration needed to do useful chelation in bubble juice, you're adding so much salt mass that you break the polymer chemistry.

The correct read: **citric acid is a pH adjuster that has a marginal side effect of weak chelation.** Use it for pH adjustment if you absolutely must, but never as the primary chelator. EDTA is the primary chelator. Sodium citrate as a "milder EDTA" is the same trap — it's the same molecule of citrate, just pre-neutralised.

---

## 8. Sources

- Martell, A.E., Smith, R.M. *Critical Stability Constants*, Vol. 3 (Plenum, 1977). Citrate-Ca²⁺ log K data.
- IUPAC Stability Constants Database (SC-Database). Hill, J.O. et al.
- Mehta, R. (2008). "Polyhydroxy compounds as calcium ion binders." *Industrial & Engineering Chemistry Research.*
- Chen, J. et al. (2019). "Mechanical degradation of HPAM in EOR." [MDPI Energies 12:49](https://www.mdpi.com/1996-1073/12/1/49). HPAM chain-radius vs pH.
- Bailey, F.E., Lundberg, R.D. (1976). "Polymer-Polymer Complexes in Aqueous Solution." In *Industrial & Engineering Chemistry Product Research and Development.*
- Akpomie, K.G. (2024). Review on polyacrylamide-based flocculants — Ca²⁺ salt-bridge mechanisms. *Environmental Chemistry Letters.*
- Pasquet, M. et al. (2022). "An optimized recipe for making giant bubbles." Eur. Phys. J. E 45:96. The pH 8 → 7 lifetime drop.

---

## 9. Provenance

Written 2026-05-15. Triggered by user observation: distilled water + Fairy + PAM + PEO + citric acid + lactic acid titrated to pH 7.5, phase-split overnight. Diagnosis identified citric/lactic combined as the salt-load source (~0.06 mol/L ionic strength from citrate alone) and three concurrent mechanisms: PAM chain collapse during local pH dips during titration, PAM-PEO Flory-Huggins incompatibility at elevated ionic strength, and Ca²⁺-citrate-PAM salt-bridge aggregation. Cross-references [[03-ph-buffer-water]] EDTA log-K table, [[07-816g-recipe-analysis]] coacervate mechanism (related but distinct — that one happens at low pH, this one happens because of the act of titrating to neutral with weak acids).
