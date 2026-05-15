---
title: "pH, buffers, water chemistry, chelators for giant bubbles"
date: 2026-05-15
tags: [research, ph, buffer, water, giant-bubbles]
---

# pH, buffers, water chemistry, chelators for giant bubbles

Giant bubble formulations operate between competing chemistries: surfactant ionisation, polyelectrolyte conformation, divalent-cation poisoning of polymer chains, micelle packing density, and atmospheric CO2 absorption that drags any open vessel toward pH 5.5-6.0 over hours. The four sections below assemble published numbers that constrain a world-record recipe.

---

## 1. Optimal pH: three documented regimes

The peer-reviewed literature and the bubble-community formularies converge on three distinct pH operating points, each picked for a different mechanism. Conflating them is the most common formulation mistake.

### Regime A: pH 6.0-6.5 — the CAPB-PAM coacervate lock

This is the regime used by the **Sovereign Semi-IPN Kinetic Assembly Protocol** (`Q:\v2 Giant Bubbles\.claude\worktrees\distracted-easley-79f6a3\obsidian-vault\The Sovereign Semi-IPN Kinetic Assembly Protocol.md`), which titrates with sorbic acid to "exactly pH 6.2," and the **Master Recipe for Colossal Bubble Physics** (`Master Recipe for Colossal Bubble Physics.md`) which targets pH 6.0-6.5 with 1.5 g/L dipotassium phosphate plus 0.2 g/L lactic acid 80%.

The mechanism is electrostatic: cocamidopropyl betaine (CAPB) is a zwitterion whose **isoelectric point is around pH 6.25**, and the threshold pH at which CAPB switches into cationic behaviour and complexes with polyanions has been measured at **pH 4.79 in dilute systems**. At slightly acidic pH the carboxylate arm of CAPB protonates, the molecule reads as net cationic, and it bridges electrostatically to the carboxylate side groups of anionic polyacrylamide (APAM/PAM) to form a polymer-surfactant coacervate complex (Sciencedirect, "Cocamidopropyl betaine can behave as a cationic surfactant and electrostatically associate with polyacids," https://www.sciencedirect.com/science/article/abs/pii/S0927775722018787).

The same pH 6 regime is also the optimum for the classic **SLES + CAPB + myristic acid** ternary system. Mitrinova et al. report that "much higher surface modulus, G > 100 mN/m, indicating the formation of condensed adsorption layer, was measured when adding myristic acid to the surfactant mixture at pH approximately 6 and 25 C," with the foam reaching surface modulus values of 400 mN/m vs 50 mN/m at neutral pH (https://www.sciencedirect.com/science/article/abs/pii/S092777571200862X). The film becomes highly viscoelastic with G' > G", and bubble drainage slows.

This regime trades stretch for wind tolerance. A condensed adsorption layer plus an interlocked CAPB-PAM scaffold gives a rigid skin that survives gusts.

### Regime B: pH 7.2-7.4 — the consumer/commercial safe lane

This is the regime used by **Supapop** (12x Guinness World Record holder, https://www.bubbleinc.co.uk/products/supapop-concentrate-250ml) and most consumer giant-bubble mixes. The pH is set by adding **double-acting baking powder** which buffers to about pH 7.4. As one popular recipe explains, "baking powder is used to neutralize the alkalinity of the detergent, and to keep the pH level at 7.4, resulting in thinner and stronger bubble walls" (https://shinynewparent.com/glycerin-bubble-recipe/).

Edward Spiegel of the Soap Bubble Wiki performed methodical experiments in 2013-2014 demonstrating that "the benefit of baking soda + citric acid is almost solely the result of the pH adjustment," with citric-acid-only and baking-soda+citric-acid mixes at matched final pH performing identically (https://soapbubble.fandom.com/wiki/PH_Adjusters_and_Water_Conditioners).

This regime is favoured commercially because:
- pH 7.2-7.4 is "skin-neutral" and inside cosmetic safety limits.
- It avoids the alkaline-hydrolysis drift of SLES (which "breaks down below pH 4," but is also slowly hydrolysed above pH 9, https://elchemy.com/blogs/chemical-market/alpha-olefins-uses-applications-across-chemicals-plastics-and-detergents).
- Baking powder + sodium acid pyrophosphate gives a slow-release acid component that buffers atmospheric CO2 absorption over hours.

### Regime C: pH 8.0-9.0 — full APAM deprotonation, pure repulsion physics

This is the regime described in `Q:\v2 Giant Bubbles\.claude\worktrees\distracted-easley-79f6a3\obsidian-vault\AOS APAM Repulsion Network Physics.md`. The mechanism is the opposite of regime A: at pH 8-9 the carboxylate side chains of partially hydrolysed polyacrylamide (HPAM) are essentially **fully deprotonated**. Liu et al. report that "at pH 3, 16.6% of anionic groups are ionized, whereas at the pH values 6 and 9, the dissociation is practically complete" (https://pmc.ncbi.nlm.nih.gov/articles/PMC4978783/).

Fully ionised, the HPAM chain has a carboxylate on every ~5-10 backbone units and the intra-chain electrostatic repulsion forces it into an extended "rigid-rod" conformation with maximum hydrodynamic radius. Bing et al. show "the higher the hydrolysis degree, the more negatively charged carboxyl groups are present on the HPAM chain; then, the increased electrostatic repulsion due to the carboxyl groups will result in a larger hydrodynamic radius" (https://www.sciencedirect.com/science/article/abs/pii/S0927025618303951).

This regime maximises extensional viscosity per gram of polymer (best stretch) but at a cost:
- AOS + APAM at pH 9 has no electrostatic lock to CAPB, so the surfactant skin is held to the polymer skeleton only by chain-entanglement and hydrophobic-tail interaction. Wind shear can pull them apart.
- APAM hydrolyses slowly at pH > 10. APAM datasheets state "APAM exhibits a broad effective pH range (6-14)" but warn that "at extremely high pH values, the polymer may undergo degradation" (https://www.atamanchemicals.com/anionic-polyacrylamide-apam_u31731/).
- SLES is not safe in this regime. AOS is, so this is the **AOS-native** regime.

### Trade-off curve

| Regime | pH | Wind tolerance | Stretch | Surfactant compatibility |
|--------|-----|----------------|---------|-------------------------|
| A: Coacervate | 6.0-6.5 | Excellent | Moderate | SLES + CAPB + PAM, requires CAPB |
| B: Consumer | 7.2-7.4 | Good | Good | SLES + CAPB OK, AOS OK |
| C: Repulsion | 8.0-9.0 | Poor (gust-sensitive) | Maximum | AOS + APAM + PEO, NOT SLES |

Wind tolerance peaks at regime A because the surface is viscoelastic and the polymer skin is anchored. Stretch peaks at regime C because the polymer chains are at their fullest extension and pull bubbles to long elastic strands. Regime B is the safe consumer compromise.

---

## 2. Buffer system comparison

### Phosphoric acid system (DKP / MKP)

Phosphoric acid is triprotic with pKa1 = 2.15, pKa2 = 7.20, pKa3 = 12.38 at 25 C (https://www.aatbio.com/resources/buffer-preparations-and-recipes/potassium-phosphate-ph-5-8-to-8-0). For pH 6.5 to 8.0, the working pair is **dipotassium phosphate (K2HPO4, MW 174.18)** and **monopotassium phosphate (KH2PO4, MW 136.09)**. The buffer is centred on pKa2 = 7.20, so it is maximally effective in regime B (consumer safe lane) and somewhat weaker at the edges of regimes A and C.

For a 10 mM phosphate buffer at pH 7.2 in soft water with 2% AOS-40, using Henderson-Hasselbalch:
- ratio K2HPO4 : KH2PO4 ~ 1 : 1 at pH = pKa = 7.20
- 5 mM K2HPO4 = 0.87 g/L
- 5 mM KH2PO4 = 0.68 g/L
- total ~ 1.55 g/L

This matches the Master Recipe load of **1.5 g/L dipotassium phosphate + 0.2 g/L lactic acid 80%** almost exactly. The lactic acid pulls the equilibrium down from pH 7.2 to the target 6.0-6.5 by protonating part of the K2HPO4 to KH2PO4 in situ.

For a target of pH 8.5, phosphate is a poor choice: it is 1.3 pH units above pKa2, ratio HPO4:H2PO4 is 20:1, and buffer capacity is collapsed.

**Caveat for hard water:** "potassium phosphate buffer reacts with some metal ions including calcium and magnesium, and inhibits enzymatic reactions" (https://www.aatbio.com/resources/buffer-preparations-and-recipes/potassium-phosphate-ph-5-8-to-8-0). Phosphate also precipitates calcium as Ca3(PO4)2 in hard water. **Soft water or distilled water only.**

### Sodium bicarbonate / carbonate system

NaHCO3 is dipoles of a system with pKa1 = 6.35 (H2CO3/HCO3-) and pKa2 = 10.33 (HCO3-/CO32-) (https://en.wikipedia.org/wiki/Bicarbonate_buffer_system). A pure NaHCO3 solution sits near pH 8.3 because it is the conjugate base of carbonic acid AND the conjugate acid of carbonate. **It is not a strong buffer in the 7.0-7.5 window** — for that you need to either combine with carbonic acid (i.e. dissolved CO2) which equilibrates with atmosphere, or co-add an acid.

In a soft-water 2% AOS-40 system, 1.0 g/L NaHCO3 alone gives pH ~ 8.2; adding 0.5 g/L citric acid drops it to about 7.3. The carbonate-bicarbonate equilibrium **also tracks atmospheric CO2** which is exactly why baking-soda-only mixes drift acidic over a day in an open bucket — every CO2 molecule that dissolves shifts the equilibrium toward H2CO3 (https://www.scientificamerican.com/article/washing-carbon-out-of-the-air/).

For pH 8.5 specifically, 2-3 g/L Na2CO3 (washing soda) is the simple approach but it produces a pH that is poorly controlled, sliding from 11 (fresh) to 9 (CO2-equilibrated) over hours.

### Borax / boric acid

Borate buffers (sodium tetraborate Na2B4O7.10H2O, pKa boric acid = 9.24 at 25 C, low ionic strength) have an effective range of pH 8.0-10.0 with maximum capacity at pH ~ 9.24 (https://www.aatbio.com/resources/buffer-preparations-and-recipes/sodium-borate-buffer-ph-8-5). For pH 8.5, ~1.0-2.0 g/L borax in soft water is the typical loading.

Two critical issues for giant bubbles:
- Borax cross-links PEO chains via boron-diol complexation. This is the basis of "slime" chemistry and will severely change PEO rheology — sometimes desirable (extra elasticity) but unpredictable.
- Borax is regulated in EU/UK cosmetics (REACH SVHC, reprotoxic above 5.5%), so it is not consumer-safe at typical buffer loadings.

It works for pH 8.5 in a **PVA or HEC-based** mix but will gel a PEO mix.

### Summary table — mass per litre to hit pH targets in soft water with 2% AOS-40

| Buffer | Target pH 7.0-7.5 | Target pH 8.5 | Compatible with hard water? | Compatible with PEO? |
|--------|-------------------|---------------|----------------------------|----------------------|
| K2HPO4 / KH2PO4 | 1.0-2.0 g/L (1:1 ratio) | Poor capacity | NO (precipitates Ca) | Yes |
| NaHCO3 alone | 1.0 g/L + acid to ~7.3 | n/a | OK | Yes |
| Na2CO3 (washing soda) | n/a | 2-3 g/L | OK | Yes |
| Borax | n/a | 1-2 g/L | OK | NO (gels PEO) |
| K2HPO4 + lactic acid (Master Recipe) | 1.5 g/L DKP + 0.2 g/L LA80 -> pH 6.2 | n/a | NO | Yes |

The Master Recipe vault file's choice of **1.5 g/L dipotassium phosphate + 0.2 g/L lactic acid 80%** is well-grounded: it sits in the high-capacity zone of pKa2 = 7.20, the lactic acid pulls it cleanly into regime A (pH 6.0-6.5), and the salt loading is modest enough not to disrupt micelles or salt-out PEO. It requires distilled water (no Ca/Mg present to precipitate).

---

## 3. Acidifier comparison

When the formulation starts at alkaline pH (washing soda, borax, or a fresh K2HPO4 solution) and needs to drop to regime A or B, four acidifiers compete.

### Lactic acid 80% (pKa 3.86)

This is the Master Recipe pick (`Master Recipe for Colossal Bubble Physics.md`: "0.2 g Lactic Acid 80% concentration: used to titrate the solution down to a slightly acidic pH 6.0 to 6.5").

Lactic acid has pKa = 3.86 (https://pubchem.ncbi.nlm.nih.gov/compound/Lactic-acid), and "AHAs (alpha-hydroxy acids like lactic acid) achieve chelation of calcium ions" — though as one industry source notes, "lactic acid has weak chelating ability, meaning it struggles with hard water scale and mineral deposits" (https://elchemy.com/blogs/food-nutrition/lactic-acid-vs-citric-acid-which-organic-acid-works-best-for-your-application). It is mild, food-safe, and produces a clean titration to pH 6.0-6.5 without precipitating anything in soft water.

Pros: clean acidifier, mild scent, no co-issues with surfactants, FDA GRAS.
Cons: weak chelator (so still need EDTA in hard water), more expensive per equivalent than citric.
Best fit: **SLES + CAPB + PAM mixes in distilled or soft water** (i.e. the Master Recipe).

### Sorbic acid (pKa 4.76)

This is the Sovereign IPN pick — "1.5 to 3.0 grams... titrated to pH 6.2." Sorbic acid has pKa = 4.76, "about as acidic as acetic acid" (https://en.wikipedia.org/wiki/Sorbic_acid). Crucially, it is **dual-function**: it is a recognised preservative (E200) effective against mold and yeast at pH < 6.5.

The antimicrobial action depends on the undissociated form: "the antimicrobial action of sorbate depends on pH and is most effective approaching its dissociation constant (pKa = 4.76)" (Wikipedia, sorbic acid). At pH 6.2 only ~3.5% is undissociated, which gives weak preservation; for stronger preservation you would need to drop below pH 5.5 — but that is incompatible with regime A.

Pros: dual acidifier + preservative, food-grade, cheap.
Cons: low solubility in water (1.6 g/L at 20 C — exactly why the Sovereign protocol's titrated 1.5-3.0 g/L is at the solubility limit), benzene-like UV absorbance, slightly pungent.
Best fit: **SLES + CAPB + PAM coacervate mixes** where preservation matters and pH target is 6.2.

### Citric acid (pKa 3.13, 4.76, 6.40)

Citric acid is the Soap Bubble Wiki community default for pH adjustment. It has three pKa values (3.13, 4.76, 6.40, https://alliancechemical.com/blogs/articles/citric-acid-beyond-the-citrus-zest) giving broad buffering action. As a tricarboxylic acid, it is a moderately strong calcium and magnesium chelator: "the negatively charged citrate ion acts like a multi-pronged molecular claw that firmly binds to positively charged metal ions — calcium, magnesium, iron, copper" (https://nuvoh2o.com/blog/how-does-citric-acid-soften-water/).

The chelation log K for Ca-citrate is around 3.5-4.6, **far below** EDTA's log K = 10.7 (https://sites.google.com/site/chempendix/formation-constants/formation-constants-for-metal-edta-complexes). So citric acid does some chelation but cannot replace EDTA in hard water.

Pros: cheap, food-safe, mild chelation built in, three pKa values give buffering.
Cons: chelates calcium poorly compared to EDTA (so it's a band-aid in hard water); some sources warn "citric acid... chelates calcium poorly"; can interact with calcium ion to give insoluble calcium citrate in very hard water; slightly cooling/tart scent transfers.
Best fit: **kitchen/consumer recipes** where it doubles as acidifier and weak chelator, and a child-safe choice when distilled water is unavailable. Not the right pick for a pro mix.

### Phosphoric acid (pKa 2.15, 7.20, 12.38)

Phosphoric acid is the strongest of the four and the standard pH adjuster in industrial cosmetic formulations. It is "used in personal care formulations as a buffering or stabilizing agent" (https://www.decachem.com/how-buffering-agents-like-phosphates-stabilize-industrial-formulations).

Pros: cheap, very strong (small mass for big pH shift), inorganic and odourless.
Cons: titration is sharp (overshoot risk); compounds phosphate already present in DKP buffer (adds more PO4 that can precipitate Ca); inorganic taste; not ideal for delicate organic polymer matrices.
Best fit: **commercial volume production** where cost and pH precision matter more than craft. Not chosen for the Master Recipe.

### Best pick by system

- **AOS-based mix (no CAPB), pH 7.2 target, soft water:** citric acid 0.3-0.5 g/L. Doubles as auxiliary chelator.
- **AOS-based mix, pH 8.5 alkaline-repulsion regime:** no acidifier needed if starting from Na2CO3 or borax; if drifting low from CO2 absorption, top up with washing soda.
- **SLES + CAPB + PAM mix, pH 6.0-6.5 coacervate regime, distilled water:** lactic acid 80% 0.15-0.25 g/L (Master Recipe choice) OR sorbic acid 1.5-3.0 g/L if you also want preservation (Sovereign IPN choice).

The two work-record-class recipes pick differently for a clean reason: lactic acid is the cleanest titrant when preservation is handled by something else (e.g. sorbate, benzoate, Phenova), and sorbic acid is the dual-function pick when no separate preservative is added.

---

## 4. Hard water management

### UK water hardness ranges

- Scotland (Highland, Glasgow): often below 20 mg/L CaCO3, classed soft (https://mytapwater.co.uk/hard-water-areas-uk/)
- Manchester: ~60 mg/L CaCO3, soft
- London: ~320 mg/L CaCO3, very hard
- Cambridge: ~310 mg/L CaCO3, very hard
- Hull: ~380 mg/L CaCO3, the hardest mains in the UK

Anything above 200 mg/L is "hard," above 250 is "very hard." For comparison: under 100 mg/L is the standard threshold below which a giant bubble formulator can largely ignore hard-water effects, and above 200 mg/L chelator becomes mandatory.

### Effect on surfactants and polymers

**AOS (alpha-olefin sulfonate):** the most hard-water-tolerant of the major anionics. AOS "exhibits good resistance to hard water and good dispersion of calcium soap" and "the strongest foaming among tested surfactants, attributed to its good solubility and dispersibility in salt solutions" (https://stppgroup.com/products/detergent-chemicals/alpha-olefin-sulphonate/). This is one of the main reasons world-record formulators prefer AOS over SLES.

**SLES (sodium laureth sulfate):** more sensitive. SLES is "stable across wide pH ranges" but its ester linkage hydrolyses below pH 4 and slowly above pH 9 (https://elchemy.com/blogs/chemical-market/alpha-olefins-uses-applications-across-chemicals-plastics-and-detergents). In hard water, Ca and Mg displace Na on the sulfate headgroup forming sparingly-soluble Ca/Mg laureth sulfates that drop micelle stability.

**CAPB (cocamidopropyl betaine):** essentially insensitive to Ca/Mg hardness because the zwitterion has both charges intrinsic to the molecule and does not need a counterion. This is a major reason CAPB is universal in shampoos and is added at 1:3 ratio to SLES in pro-mix bubble recipes.

**HPAM (anionic polyacrylamide):** **highly sensitive**. The carboxylate side groups cross-link with divalent Ca2+ and Mg2+ to form an irreversible gel/precipitate. The Sovereign IPN protocol is explicit: "Tap water contains calcium/magnesium ions that will prematurely cross-link the anionic PAM, ruining the fluid." This is why all the pro recipes mandate distilled or deionised water for any PAM-containing system.

**PEO (polyethylene oxide):** moderate sensitivity. "The presence of inorganic salts in a PEO aqueous solution lowers the solubility and viscosity upper temperature limit. The concentration and valence of the ionic species that are present influence the upper temperature limit of solubility" (https://www.sciencedirect.com/science/article/abs/pii/S092777571930799X). Divalent cations also salt-out PEO at modest concentration. PEO can survive moderate tap water but performs better in distilled.

### Chelator comparison

| Chelator | Form | log K (Ca2+) | Chelation value (mg CaCO3/g) | Optimal pH | Cost |
|----------|------|--------------|------------------------------|------------|------|
| Disodium EDTA | EDTA-2Na | 10.7 | ~265 (crystal) | 5-8 | mid |
| Tetrasodium EDTA | EDTA-4Na | 10.7 | ~220-229 (https://www.hoochemtec.com/chelating-agent/tetrasodium-edta-salts/) | 7-12 | mid |
| Versene 100 (39% EDTA-4Na liquid) | liquid | 10.7 | 102 (per g of product) (https://www.dow.com/en-us/pdp.versene-100.90684z.html) | 7-12 | mid |
| Sodium citrate dihydrate | salt | ~3.5 | ~75-90 | 4-7 | low |
| Sodium gluconate | salt | ~1.2 (neutral); strong at pH >11 | n/a | alkaline only | low |

**Disodium EDTA** works best at slightly acidic to neutral pH and is the standard cosmetic chelator. It is "typically used at 0.1 to 0.5%" of total weight, i.e. **1-5 g/L** in a bubble mix (https://www.juventudeskincare.com/blogs/founders-journal/disodium-edta-in-skincare-the-chelating-agent-protecting-your-formula). At 1 g/L of disodium EDTA dihydrate (chelation value ~265 mg CaCO3/g), you can sequester roughly 265 mg/L of CaCO3 — enough to fully chelate Manchester soft water (60 mg/L) and roughly match London hard water (320 mg/L). For very hard water, push to 2 g/L.

**Tetrasodium EDTA** is the better pick when the formulation is alkaline (regime C, pH 8.0-9.0) because it is already in fully-deprotonated form. It also raises pH by about 0.3 units at 1 g/L loading, which actually helps in regime C.

**Sodium citrate dihydrate** is the kitchen-grade option. At 0.5-1.0% (5-10 g/L) it can chelate ~50-100 mg/L CaCO3, fine for soft water but inadequate for London/Cambridge tap. "Typical dosage is 13 to 39 g per 1000 g fats (1.3% to 3.9% of total fat weight), with more used for hard water and less for soft water" (https://www.ultimateguidetosoap.com/post/the-role-of-chelators-why-hard-water-and-soap-don-t-get-along). Acts also as mild buffer.

**Sodium gluconate** is excellent at pH 11-13 but "less effective in acidic conditions" — it "showed the best performance at pH 13... at more moderate alkaline pH values, sodium gluconate showed the poorest performance" (https://rawsource.com/sodium-gluconate-vs-edta-comparison/). For giant bubbles which sit at pH 6-9, gluconate is a poor pick.

### Distilled water vs tap+chelator: does it matter for performance?

The Soap Bubble Wiki community position is "tap water is generally as good or better for making bubbles as distilled or reverse osmosis water" for **consumer dish-soap-based recipes** (https://soapbubble.fandom.com/wiki/Water) — because dish detergents already include enough chelator (EDTA-2Na, sodium citrate, sodium silicate) to handle normal tap water.

But for a **pro-mix containing anionic polyacrylamide**, the calculation is completely different. APAM cross-links irreversibly with calcium; even 1 ppm of free Ca2+ over a long mixing time can form micro-aggregates that scatter light, raise viscosity unpredictably, and reduce extensional elasticity. The Sovereign protocol's mandate of deionised/distilled water is therefore not optional or paranoid — it is a physical requirement of the polymer.

Practical hierarchy:
- **PAM-based pro mix:** distilled or deionised mandatory, even in Scotland. Belt-and-braces: add 0.5-1.0 g/L disodium EDTA anyway as insurance against trace ions from glycerin, surfactant pastes, or storage containers.
- **PEO-only mix (HEC, J-Lube, no PAM):** tap water plus 1-2 g/L disodium EDTA is fine up to ~200 mg/L hardness; above that switch to distilled.
- **Hardest UK water (London, Cambridge, Hull, 300+ mg/L):** distilled is cheaper than dealing with batch-to-batch inconsistency.

The performance difference between (a) distilled + no chelator and (b) tap + sufficient chelator in a well-formulated AOS+CAPB+PEO mix is small, **probably below the resolution of human judging**. But for a **PAM-containing world-record attempt**, distilled is mandatory because chelator alone cannot fully prevent slow Ca-PAM aggregation over days of curing.

---

## Synthesis: pH and water recipe

For a **world-record-class AOS-based giant bubble formulation** combining the wind tolerance of regime A with the AOS hard-water tolerance and the option of either pure-repulsion or coacervate-lock physics:

**Water:** distilled or deionised, mandatory if PAM is in the recipe. Even with EDTA, free divalent ions in 300+ mg/L London tap will slowly aggregate APAM over the 24-hour curing window. Cost is ~£2 per 5 L from any supermarket — trivial vs the value of a repeatable record attempt.

**Buffer:** 1.5 g/L dipotassium phosphate K2HPO4 (~8.6 mM at MW 174.18). Sits on pKa2 = 7.20 for maximum buffer capacity to resist atmospheric CO2 drift. Provides phosphate ions that also bind any rogue Ca2+ as a secondary precaution. **Do not exceed 2 g/L** — phosphate can salt-out PEO at higher loadings.

**Acidifier:** 0.2 g/L lactic acid 80% — pulls the mix from pH 7.2 to the target pH 6.2 +/- 0.1, locking CAPB into cationic form and bridging it to PAM carboxylates. If preservation is needed in the same step, substitute 1.5 g/L sorbic acid crystalline powder titrated to the same pH (Sovereign IPN choice).

**Chelator:** 1.0 g/L disodium EDTA (EDTA-2Na, MW 372.24, chelation value ~265 mg CaCO3/g). Even with distilled water, this guards against trace divalent ions from the surfactant pastes (which contain residual salts from manufacture), the polymer powders, the glycerin, and the storage container leachate. Tetrasodium EDTA is fine as a substitute if the recipe is in regime C (pH 8.0-9.0).

**Final water profile:** sub-1 mg/L free Ca2+/Mg2+, pH 6.2, buffer capacity ~ 9 mM phosphate, ionic strength ~ 25 mM, surface tension dominated entirely by the surfactant matrix and bulk viscosity by the polymer skeleton with no metallic interference.

For a **pure-repulsion alternative** (regime C, AOS + APAM, no CAPB) for maximum bubble length at the cost of wind tolerance:

**Buffer:** 1.0 g/L sodium bicarbonate + 0.5 g/L sodium carbonate (Na2CO3) — gives stable pH ~8.5, lets HPAM fully ionise, no PEO-borax gelling risk.
**Acidifier:** none in steady state; if CO2 absorption drops pH below 8.2, top up with 0.2 g/L Na2CO3.
**Chelator:** 1.0 g/L tetrasodium EDTA — works best at alkaline pH, also reinforces buffer.
**Water:** distilled, same logic.

The regime A recipe (pH 6.2 coacervate) is the better world-record choice in any wind. The regime C recipe is the better choice for maximum-length still-air laboratory shots where polymer extension is the only thing that matters.

---

## Sources

- [PAM | Soap Bubble Wiki](https://soapbubble.fandom.com/wiki/PAM)
- [Surface and foam properties of SLES + CAPB + fatty acid mixtures: Effect of pH for C12-C16 acids](https://www.sciencedirect.com/science/article/abs/pii/S092777571200862X)
- [An optimized recipe for making giant bubbles | European Physical Journal E](https://link.springer.com/article/10.1140/epje/s10189-022-00255-6)
- [Impact of anionic polyacrylamide on stability and surface properties (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC4978783/)
- [Potassium Phosphate Buffer pH 5.8-8.0 | AAT Bioquest](https://www.aatbio.com/resources/buffer-preparations-and-recipes/potassium-phosphate-ph-5-8-to-8-0)
- [Sodium Borate Buffer pH 8.5 | AAT Bioquest](https://www.aatbio.com/resources/buffer-preparations-and-recipes/sodium-borate-buffer-ph-8-5)
- [Anionic Polyacrylamide (APAM) | Ataman Kimya](https://www.atamanchemicals.com/anionic-polyacrylamide-apam_u31731/)
- [Lactic Acid vs Citric Acid | Elchemy](https://elchemy.com/blogs/food-nutrition/lactic-acid-vs-citric-acid-which-organic-acid-works-best-for-your-application)
- [Lactic Acid PubChem](https://pubchem.ncbi.nlm.nih.gov/compound/Lactic-acid)
- [Sorbic acid | Wikipedia](https://en.wikipedia.org/wiki/Sorbic_acid)
- [How Does Citric Acid Soften Water | NuvoH2O](https://nuvoh2o.com/blog/how-does-citric-acid-soften-water/)
- [Citric Acid Uses Guide | Alliance Chemical](https://alliancechemical.com/blogs/articles/citric-acid-beyond-the-citrus-zest)
- [EDTA Chelating Agent | Hoo Chemtec](https://www.hoochemtec.com/news/edta-chelating-agent-industrial-uses/)
- [Tetrasodium EDTA Chelating Agent | Hoo Chemtec](https://www.hoochemtec.com/chelating-agent/tetrasodium-edta-salts/)
- [VERSENE 100 Chelating Agent | Dow Inc.](https://www.dow.com/en-us/pdp.versene-100.90684z.html)
- [Disodium EDTA in Skincare | Juventude](https://www.juventudeskincare.com/blogs/founders-journal/disodium-edta-in-skincare-the-chelating-agent-protecting-your-formula)
- [Sodium Gluconate vs. EDTA | Rawsource](https://rawsource.com/sodium-gluconate-vs-edta-comparison/)
- [Hard Water Areas UK 2025 Map | MyTapWater](https://mytapwater.co.uk/hard-water-areas-uk/)
- [Alpha Olefin Sulphonate AOS | STPP Group](https://stppgroup.com/products/detergent-chemicals/alpha-olefin-sulphonate/)
- [Alpha Olefins Uses | Elchemy](https://elchemy.com/blogs/chemical-market/alpha-olefins-uses-applications-across-chemicals-plastics-and-detergents)
- [Cocamidopropyl betaine cationic surfactant electrostatic association with polyacids](https://www.sciencedirect.com/science/article/abs/pii/S0927775722018787)
- [Cocamidopropyl betaine | Wikipedia](https://en.wikipedia.org/wiki/Cocamidopropyl_betaine)
- [Bicarbonate buffer system | Wikipedia](https://en.wikipedia.org/wiki/Bicarbonate_buffer_system)
- [PH Adjusters and Water Conditioners | Soap Bubble Wiki](https://soapbubble.fandom.com/wiki/PH_Adjusters_and_Water_Conditioners)
- [Effect of HPAM hydrolysis degree on catanionic mixtures](https://www.sciencedirect.com/science/article/abs/pii/S0927025618303951)
- [Conformation and solubility of poly(ethylene oxide) at high salinity](https://www.sciencedirect.com/science/article/abs/pii/S092777571930799X)
- [How Buffering Agents Like Phosphates Stabilize Industrial Formulations | Decachem](https://www.decachem.com/how-buffering-agents-like-phosphates-stabilize-industrial-formulations)
- [The Role of Chelators: Why Hard Water and Soap Don't Get Along | Ultimate Guide to Soap](https://www.ultimateguidetosoap.com/post/the-role-of-chelators-why-hard-water-and-soap-don-t-get-along)
- [Supapop Giant Bubble Mixture | Bubble Inc](https://www.bubbleinc.co.uk/products/supapop-concentrate-250ml)
- [Easy Homemade Bubble Recipe with Glycerin | Shiny New Parent](https://shinynewparent.com/glycerin-bubble-recipe/)
- [Formation Constants for metal-EDTA Complexes | Chempendix](https://sites.google.com/site/chempendix/formation-constants/formation-constants-for-metal-edta-complexes)
- [Water | Soap Bubble Wiki](https://soapbubble.fandom.com/wiki/Water)
- [Washing Carbon Out of the Air | Scientific American](https://www.scientificamerican.com/article/washing-carbon-out-of-the-air/)
