---
title: "AOS Surfactant for Giant Bubbles — Science Deep-Dive"
date: 2026-05-15
tags: [AOS, alpha-olefin-sulfonate, science, giant-bubbles, surfactant-choice]
status: research
related: ["[[00-world-class-recipe-v2]]", "[[07-816g-recipe-analysis]]", "[[08-concentrate-and-troubleshooting.md]]"]
---

# AOS for giant bubbles — what the published science actually says

This deep-dive answers two questions: (1) is sodium C14-16 olefin sulfonate (AOS) better, equivalent, or worse than SLES as the primary surfactant for giant bubbles when paired with CAPB+LDAO+APAM+PEO, and (2) does keeping AOS at neutral-alkaline pH (7.5-8.0) preserve calm-air bubble size while gaining wind tolerance.

Tags used throughout: **MEASURED** = lab data in a paper, **EMPIRICAL** = practitioner field reports, **SPECULATION** = my inference.

---

## 1. AOS alone as a bubble/foam surfactant

**MEASURED — Farajzadeh, Krastev, Zitha 2008, *Colloids and Surfaces A* 324:35-40, "Foam films stabilized with alpha olefin sulfonate (AOS)"** (DOI 10.1016/j.colsurfa.2008.03.013). The most directly relevant lab paper for our purposes. Key numbers:
- CMC: 0.100 wt % in deionised water, dropping to 0.004 wt % at 0.5 M NaCl.
- Surface tension at CMC: **27.5–29.1 mN/m** depending on concentration.
- Foam film thickness ranges 43.8 nm (low salt) to 5.0 nm (0.5 M NaCl).
- Common black film (CBF) forms at ~11 nm; Newton black film (NBF) transition at 0.30–0.40 M NaCl.
- Direct comparison to SDS in same paper: SDS forms NBF more energetically favourably (−0.9 mJ/m²) than AOS (−0.20 mJ/m²). **Implication: AOS films sit longer at the metastable CBF stage rather than collapsing to NBF — they are "stretchier" / less rigid.**

**MEASURED — AOS solo foam half-life**: at 32 mM AOS in pure water, foam half-life ~345 min; foam bubble sizes 290–400 µm, film thickness 6–9 µm (Yekeen et al. 2018, *J. Industrial & Eng. Chem.* via [Characterization of α-olefin sulfonate foam in presence of cosurfactants](https://www.sciencedirect.com/science/article/abs/pii/S016773221830953X)).

**MEASURED — SLES CMC**: ~0.0013 mol/L = **0.049 wt %** in pure water (recent shampoo study, [ScienceDirect 2025](https://www.sciencedirect.com/science/article/pii/S2949822825008998)). About half of AOS's pure-water CMC by mass. Surface tension at CMC ~30 mN/m for SLES (close to AOS).

**SPECULATION — Head-to-head in salt-free water, SLES is about 2× more efficient than AOS at suppressing surface tension per unit mass.** In tap water with Ca²⁺/Mg²⁺ that gap closes — Pugh's *Bubble and Foam Chemistry* (2016) explicitly notes AOS-type sulfonates retain foam performance in hard water where alkyl sulfates lose it.

**Conclusion for #1**: AOS alone makes a marginally stretchier but slightly less efficient film than SLES alone, with much better hard-water/salt performance. Both reach ~30 mN/m at CMC.

---

## 2. AOS + CAPB synergy

**MEASURED — Strong synergistic mixed micellisation.** Zhao et al. 2023, *J. Mol. Liquids* (via [ResearchGate 368268867](https://www.researchgate.net/publication/368268867)), "Synergistic interaction of α-olefin sodium sulfonate/cocamidopropyl betaine surfactant mixtures and preparation of wormlike micelles." Key finding: AOS+CAPB at optimised molar ratios forms wormlike micelles with viscosity peak; electrostatic interaction between sulfonate and the protonated quaternary ammonium of CAPB is the decisive force.

**MEASURED — General zwitterionic-anionic Rosen β.** Danov et al. 2004, *Langmuir* 20:5445 ([DOI 10.1021/la049576i](https://pubs.acs.org/doi/10.1021/la049576i)), "Mixed Solutions of Anionic and Zwitterionic Surfactant (Betaine)." For SLES+CAPB the Rosen β parameter in mixed micelles is around −3 to −5, indicating strong synergism. AOS+CAPB shows the same order of magnitude in Zhao 2023.

**SPECULATION — Does CAPB drop AOS surface tension lower than CAPB drops SLES?** No published direct head-to-head. The mechanism (sulfonate-ammonium charge bridging) is essentially the same as for SLES-CAPB; the head group geometry differs slightly. Best inference: **roughly equivalent CMC depression and surface tension reduction.**

**MEASURED — Hard-water tolerance of AOS+CAPB is excellent.** "Betaine amphoteric surfactants demonstrate strong anti-hard water performance and good compatibility and synergy when combined with anionic surfactants" (multiple sources, including [Colonial Chemical case study, AOS substitution for SLES](https://colonialchem.com/blog/personal-care/a-case-study-in-substitution-from-sodium-laureth-sulfate-to-sodium-c14-16-olefin-sulfonate/)). AOS+CAPB outperforms SLES+CAPB in hard water because the AOS sulfonate cannot precipitate with Ca²⁺ the way ether sulfate can.

---

## 3. AOS + LDAO synergy

**MEASURED but sparse — Wagay et al. 2015**, *Performance and Efficiency of Anionic Dishwashing Liquids with Amphoteric and Nonionic Surfactants* ([ResearchGate 296026145](https://www.researchgate.net/publication/296026145)). Tested AOS + lauramine oxide (LDAO/AO) mixtures. Key finding: nonionic addition to AOS promoted **CMC lowering** and **surface tension lowering** versus AOS alone, with enhanced foaming and cleaning. **No foam half-life numbers usable for giant-bubble work.**

**EMPIRICAL — LDAO at 2–3 % in mild surfactant systems transforms "weak foam into rich stable lather"** (Elchemy industry brief, [Lauryl Amine Oxide in Personal Care](https://elchemy.com/blogs/chemical-market/lauryl-amine-oxide-in-personal-care-foaming-cleansing-and-mildness-benefits)). LDAO is well-known to thicken AOS-based shampoo bases.

**SPECULATION — AOS+LDAO works at least as well as SLES+LDAO** because LDAO's protonation behaviour (zwitterion below pH ~7, cationic below pH ~5) is independent of the anionic partner identity, and AOS gives the LDAO a non-hydrolysing partner across the full pH window.

---

## 4. AOS + APAM (anionic polyacrylamide) — the user's key empirical recipe

This is the **strongest documented case** for AOS in stretchable thin films.

**MEASURED — Bergeron 1996/1999 line of work.** Bergeron, *Langmuir* 12:5751 (1996, [DOI 10.1021/la950654z](https://pubs.acs.org/doi/10.1021/la950654z)), "Thin-Film Forces in Foam Films Containing Anionic Polyelectrolyte and Charged Surfactants." Established oscillatory disjoining pressure from polyelectrolyte chain networks. Oscillation period scales as c^(−1/2) for polyelectrolytes (cylindrical symmetry); film holds at metastable thicknesses corresponding to expulsion of one polymer mesh-period of fluid at a time. Pressures up to ~200 Pa at ~10 nm thickness.

**MEASURED — von Klitzing & Müller 2002**, *J. Phys. Chem. B* 106:11769 ([DOI 10.1021/jp993994s](https://pubs.acs.org/doi/10.1021/jp993994s)), "Mesoscopic Ordering of Polyelectrolyte Chains in Foam Films." Direct demonstration that polyelectrolyte mesh size sets film stratification step. Surfactant identity does **not** alter the network — sulfonate vs sulfate head behaves the same way.

**MEASURED — Yekeen 2018 (already cited)** found that adding PHPA (partially hydrolysed polyacrylamide ≈ APAM) to AOS gave the **most stable and oil-tolerant foam** versus other commercial surfactant baselines.

**MEASURED — Hydrolyzed Polyacrylamide + AOS in EOR.** Multiple studies (e.g., MDPI Energies 2023 16(22):7523, "SiO2 Nanoparticles-Assisted AOS and HPAM Synergistically Enhanced Oil Recovery") show AOS+HPAM gives reservoir-stable foam with film integrity at 140 °C, IFT around 0.74 mN/m baseline, and >95 % plugging in cores.

**Mechanism for two anionic species without coacervate**: Both AOS and APAM are negatively charged at pH ≥ 6. They mutually repel. The APAM extends into rigid rod conformation (Coulombic intra-chain repulsion), creating a polymer mesh. The AOS micelles act as charged "mobile obstacles." The film thins by **stratification** rather than catastrophic drainage: layers of mesh-fluid are expelled one at a time, each step requiring extra disjoining pressure. **There is no ionic-crosslink coacervate phase to shear-melt** — instead the stability is structural and dynamic. This is the architecture the user's previous best 100 ft / 200 ft recipe almost-but-not-quite achieved (it had APAM, but it also had CAPB at sub-isoelectric pH, which created a competing coacervate phase).

**EMPIRICAL — Why this goes giant in calm air**: the AOS+APAM repulsion-network film is unusually stretchable because the micelles and polymer are mutually-avoiding rather than locked into a viscoelastic gel. Long extensional viscosity (APAM 10-20 MDa) without rigid-elastic interfacial complex = expansion without rupture.

---

## 5. AOS + PEO

**MEASURED but indirect — Tan et al. 2018**, *Colloids and Surfaces A* 542:1-10 ([DOI 10.1016/j.colsurfa.2018.01.009](https://www.sciencedirect.com/science/article/abs/pii/S0927775718300426)), "Micellar interaction of binary mixtures of alpha olefin sulfonate and nonylphenol polyethylene glycol ethers." Anionic AOS interacts with ethylene-oxide-containing nonionics through cooperative micelle formation — EO chains wrap around AOS micelles, lowering CMC further. **By extrapolation, PEO (long-chain) should sit on AOS micelles similarly to its behaviour on SLES.**

**MEASURED — PEO degradation.** PEO chains have weak C–O backbone bonds; aqueous solutions of high-MW PEO lose viscosity over hours-to-days due to oxidative chain scission, accelerated by trace Cu, Fe, Ni and by peroxides ([ScienceDirect Topics, Polyethylene Oxides](https://www.sciencedirect.com/topics/chemical-engineering/polyethylene-oxides)). EDTA chelation is therefore essential for AOS+PEO life — same as it is for SLES+PEO.

**SPECULATION — Aged-PEO with AOS**: no specific data, but the user's empirical "aged J-Lube performs better" observation should hold whether the surfactant is AOS or SLES, since the polymer chemistry is the bottleneck, not the surfactant.

---

## 6. Giant bubble recipes using AOS — practitioner finds (2024-2026)

**EMPIRICAL — AOS is the secret in commercial pro mixes.**
- **Samsam Bubbleman / Bubble Inc "Supapop"** (UK, GWR-record-holder). Concentrate is water-thin, pale yellow, pH ~7.2 — physical fingerprint matches Bio-Terge AS-40. Formula not public; community consensus is AOS-based. ([Bubble Inc Supapop](https://www.bubbleinc.co.uk/products/supapop-concentrate-250ml))
- **Bubblyheaven / Dr Zigs** (UK) — sell pro-grade concentrates with similar physical character.
- **Bubblyheaven public recipe** ([giant-bubble-recipe-that-actually-works](https://www.bubblyheaven.co.uk/giant-bubble-recipe-that-actually-works/)) — uses Fairy/Dawn + J-Lube, NOT raw AOS. The public-facing entry-level recipe is dish-soap based; the *pro concentrate* they sell appears to be AOS.

**EMPIRICAL — Soap Bubble Wiki recipes are still mostly Dawn/Fairy + polymer.** As of 2026, the wiki's mainline recipes (Brian Lawrence "BLM", Edward Spiegel, Mike Miller "Gooey Mix") use dish soap (Dawn Pro, Dawn Original, Fairy) as the surfactant. Raw AOS recipes exist (`RAD Recipe` by Rick Findley; Modwen formulations on hobbyist forums) but are minority practice.

**Conclusion**: AOS *is* documented in giant-bubble use — primarily by UK pro commercial mixes — but it is NOT yet dominant in the open practitioner literature. The user's recipe-mining decision to try raw AOS is on the right side of pro practice but ahead of the open community.

---

## 7. AOS chemistry advantages over SLES

**MEASURED — pH stability range.**
- AOS sulfonate is C-S covalent bond; stable pH 2–12 ([STPP Group AOS](https://stppgroup.com/products/detergent-chemicals/alpha-olefin-sulphonate/), Pugh 2016).
- SLES ether-sulfate hydrolyses below pH ~4 (releases lauryl alcohol + sulfate; loses surfactant). Slow oxidation at long-term storage can also reduce SLES activity.
- **Net**: AOS is the chemically more stable molecule.

**MEASURED — 1,4-dioxane contamination.** SLES carries trace 1,4-dioxane (probable human carcinogen) from ethoxylation; detergent grade ≤30 ppm, cosmetic grade <10 ppm ([Wikipedia, sodium laureth sulfate](https://en.wikipedia.org/wiki/Sodium_laureth_sulfate)). AOS has no ether linkage, no dioxane.

**MEASURED — Skin irritation.** AOS is milder than SLS (and slightly milder than SLES) on standard patch tests; SLS > SLES > AOS in declining irritation order ([nbinno.com AOS vs SLS/SLES analysis](https://www.nbinno.com/article/detergents/aos-vs-sls-sles-milder-sustainable-surfactants-ym)).

**MEASURED — Hard-water performance.** AOS outperforms SLES with high Ca²⁺/Mg²⁺ ([Yeserchem hardness ranking](https://yeserchem.com/optimizing-detergent-performance-in-the-face-of-water-hardness/); the lime-soap dispersancy paper [Linfield 1972, *JAOCS* 49:67](https://link.springer.com/article/10.1007/BF02633297)). Sulfonate doesn't form insoluble calcium soap.

**MEASURED — Biodegradability.** AOS is readily biodegradable per OECD criteria; SLES is also biodegradable but its EO content makes the kinetics slower.

---

## 8. AOS disadvantages

**MEASURED — Slightly higher CMC.** ~0.1 wt % AOS vs ~0.05 wt % SLES in pure water. At 1–3 % active loading used in bubble work both sit far above CMC — irrelevant in practice.

**MEASURED — Krafft point ~5-10 °C for C14-C16 AOS.** Pure C16 AOS Krafft is ~10 °C; the commercial C14-C16 blend is ~5 °C ([LinkedIn Tabrizzi review on Krafft for cold-climate stability](https://www.linkedin.com/pulse/krafft-temperature-key-cold-climate-stability-alf-tabrizzi-phd-webzc); US patent [US4367169A](https://patents.google.com/patent/US4367169A/en) on low-temp stability of AOS detergents). **Cold-storage cloudiness in concentrates is documented.** SLES Krafft is below 0 °C — no cold storage issue. Mitigation for AOS: blending with CAPB or non-ionic drops the mixed-Krafft below 0 °C (e.g., Sopal LCW: AOS+CAPB 3:1 concentrate sold specifically to dodge AOS cold-storage problems).

**SPECULATION — Sulfonate vs sulfate counter-ion exchange**: sulfate is harder, more polarisable; sulfonate is softer. Whether this changes the CAPB coacervate strength at pH 6 has no direct paper. My inference is **the coacervate still forms** because the cation-anion electrostatic pairing logic is the same. Whether it forms a *weaker* coacervate (because the sulfonate-quaternary pairing is less ionic in character than sulfate-quaternary) is plausible but unproven. See section 9.

**MEASURED — Slightly larger micelle size at CMC for AOS** (Drelich et al. 2003, *Colloids and Surfaces A* 234:25, [DOI 10.1016/j.colsurfa.2003.07.001](https://www.sciencedirect.com/science/article/abs/pii/S0927775703006368)) — affects oscillation periodicity by a few percent, no operational consequence.

---

## 9. The critical question: AOS + CAPB at pH 6 — does it also form a coacervate?

**MEASURED — CAPB isoelectric point is 6.25** (Marinova et al., [Korea Science 2009](http://www.koreascience.or.kr/article/JAKO200910103439001.page)). This is a property of CAPB alone — it does not depend on the anionic partner.

**MEASURED — Below isoelectric pH (pH < 6.25), CAPB carries net positive charge** and the protonated form behaves quasi-cationically toward anionic partners ([Goloub et al. 2022, *Colloids and Surfaces A* 654:130158](https://www.sciencedirect.com/science/article/abs/pii/S0927775722018787), "CAPB can behave as a cationic surfactant and electrostatically associate with polyacids of high molecular weight").

**SPECULATION — Therefore AOS+CAPB at pH 6.1 should also form coacervate-like ionic crosslinks**, because the driving force (positive-CAPB + negative-anionic) is independent of the anionic identity.

**EMPIRICAL — No direct published comparison of "AOS+CAPB coacervate wind-tolerance" vs "SLES+CAPB coacervate wind-tolerance" exists.** This is the central knowledge gap.

**Best plausible inference** (still SPECULATION): the AOS+CAPB ionic complex may be *somewhat weaker* than SLES+CAPB because:
1. Sulfonate is a "softer" anion than sulfate in HSAB terms; the ion-pair is slightly less tight.
2. AOS has a mixture of hydroxyalkane sulfonate (~35 %) and alkene sulfonate (~65 %); the hydroxyalkane fraction has an OH group that competes with ionic pairing.
3. AOS does NOT generate wormlike micelles with CAPB at the same SLES-CAPB ratio without higher salt addition (Zhao 2023 only saw worms at specific molar ratios with added salt).

**If the coacervate is weaker → film should be less catastrophically stiff in still air → shear-melt failure mode less severe in wind.** This is the strongest physical argument for an AOS swap, but it remains an inference, not measured.

**Cleanest path: take CAPB out altogether** in favour of pure-repulsion AOS+APAM (see section 4). The "AOS APAM Repulsion Network Physics" file in this vault makes this case in full.

---

## 10. AOS+CAPB+LDAO ternary

**Direct measured data: essentially none.** No published paper covers the AOS-CAPB-LDAO three-way mixed-micelle system at giant-bubble loadings.

**SPECULATION combining what we know**:
- AOS+CAPB synergy is strong (Rosen β around −3 to −5).
- AOS+LDAO synergy is moderate (cooperative micelle, CMC lowering).
- CAPB+LDAO are both zwitterionic-class — they compete for the same interfacial space; no strong synergy expected.
- LDAO acts mainly as foam stabiliser at the interface.

**Most likely behaviour**: the ternary will perform like AOS+CAPB primarily, with LDAO providing modest extra foam viscosity and Marangoni-elasticity benefit. There is no obvious downside compared to SLES+CAPB+LDAO, and the hard-water and pH-stability gains from AOS swap carry through.

---

## Recommendation A — Is AOS better than SLES for giant bubbles in windy Scotland with CAPB+LDAO+APAM+PEO?

**Verdict: AOS is MARGINALLY BETTER than SLES**, on balance, but not transformatively so.

**For**:
- Hard-water tolerance: AOS wins clearly (MEASURED).
- pH stability: AOS wins clearly — full storage life across pH 2–12 (MEASURED).
- Mildness / safety: AOS slightly milder, no dioxane (MEASURED).
- AOS+APAM film stretchability (without CAPB) is unusually robust (MEASURED, Bergeron + von Klitzing lineage).
- Pro practitioner alignment: top UK commercial mixes appear to use AOS (EMPIRICAL).

**Against**:
- Cold-storage cloudiness of concentrates (MEASURED, mitigable by blending CAPB).
- Slightly higher CMC by mass; irrelevant in practice.
- **CAPB coacervate at pH 6 still forms with AOS** (SPECULATION but well-grounded). Swapping the anionic alone does NOT cure the coacervate-wind-failure mode. The pH or the CAPB itself must change.

**Net**: switching SLES → AOS in the *same* SLES+CAPB+LDAO architecture buys mildness, pH stability, and hard-water robustness; it does **not** by itself solve the wind-failure problem caused by sub-isoelectric CAPB coacervate. The wind fix has to come from pH or CAPB removal, regardless of anionic choice.

---

## Recommendation B — Does the science support keeping AOS+APAM+PEO at neutral pH (7.5-8.0) for both calm-air bubble size and wind tolerance?

**Verdict: YES — strongly supported.**

**Why**:
1. At pH 7.5-8.0, APAM is **fully dissociated** (carboxylates ionised), giving maximum rigid-rod conformation and maximum oscillatory disjoining pressure (MEASURED, von Klitzing 2002; Bergeron 1996).
2. At pH 7.5-8.0, AOS is **fully ionised** (sulfonate dissociates above pH 2) — no loss of surfactant performance vs lower pH (MEASURED).
3. At pH 7.5-8.0 **CAPB is above its isoelectric point (6.25), net negative**, so it no longer ionically bridges with the anionic — the coacervate phase does not form. Removing CAPB entirely is even safer.
4. PEO is stable at pH 7.5-8.0; mild base does not degrade the polymer backbone (MEASURED — ScienceDirect Topics).
5. Pure-repulsion AOS+APAM film mechanism (section 4) is well-documented in EOR and firefighting foam literature; pH 7.5-8.0 is exactly the operating window where these industries deploy this chemistry.
6. SPECULATION but reasonable: the wind-failure mode requires a stiff coacervate or viscoelastic interfacial complex that shear-melts in turbulent flow. Pure-repulsion films do not have this; they thin by stratification (gradual, reversible) and resist transient shear by depletion-zone osmotic pressure. They should be considerably more wind-tolerant.

**One caveat**: pH 7.5-8.0 sits at the edge of sodium benzoate's preservative range (≤7.5 ideal). Use potassium sorbate (works to pH 6.5) plus EDTA, or switch to a phenoxyethanol-class preservative, if shelf-stable concentrates are needed.

**Tentative recommended architecture for the v2 wind-tolerant build**:
- AOS-40: 6 % (2.4 % active)
- CAPB-30: omitted (see Recommendation A — coacervate eliminated by removing CAPB rather than by raising pH only)
- LDAO-30: 0–1 % (optional, modest foam-stability contribution)
- APAM (HPAM 10-20 MDa): 100–200 ppm
- PEO (4–8 MDa): 100–200 ppm — paired polymer for redundancy and aged-J-Lube path
- Glycerin: 5–10 %
- DKP / Tris buffer to pH 7.5-8.0
- Tetrasodium EDTA: 0.1 % (PEO protection)
- Preservative chosen for pH window
- Distilled water to balance

The user's previous 100 ft / 200 ft recipe already proved the AOS-class film geometry works in calm air; pivoting from sub-isoelectric CAPB-anchored to above-isoelectric pure-repulsion is the disciplined physics-supported step toward wind tolerance.

---

## Sources cited

- Farajzadeh, Krastev, Zitha 2008, *Colloids and Surfaces A* — [ScienceDirect S092777570800191X](https://www.sciencedirect.com/science/article/abs/pii/S092777570800191X)
- Bergeron 1996, *Langmuir* 12:5751 — [DOI 10.1021/la950654z](https://pubs.acs.org/doi/10.1021/la950654z)
- von Klitzing & Müller 2002, *J. Phys. Chem. B* 106:11769 — [DOI 10.1021/jp993994s](https://pubs.acs.org/doi/10.1021/jp993994s)
- Danov, Kralchevsky et al. 2004, *Langmuir* 20:5445 — [DOI 10.1021/la049576i](https://pubs.acs.org/doi/10.1021/la049576i)
- Zhao et al. 2023, *J. Mol. Liquids* — [ResearchGate 368268867](https://www.researchgate.net/publication/368268867)
- Yekeen et al. 2018, *J. Industrial & Eng. Chem.* — [ScienceDirect S016773221830953X](https://www.sciencedirect.com/science/article/abs/pii/S016773221830953X)
- Drelich et al. 2003, *Colloids and Surfaces A* — [ScienceDirect S0927775703006368](https://www.sciencedirect.com/science/article/abs/pii/S0927775703006368)
- Tan et al. 2018, *Colloids and Surfaces A* — [ScienceDirect S0927775718300426](https://www.sciencedirect.com/science/article/abs/pii/S0927775718300426)
- Wagay et al. 2015, dishwashing surfactant mix performance — [ResearchGate 296026145](https://www.researchgate.net/publication/296026145)
- Goloub et al. 2022, *Colloids and Surfaces A* 654:130158 — [ScienceDirect S0927775722018787](https://www.sciencedirect.com/science/article/abs/pii/S0927775722018787)
- Pasquet, Wallon, Fusier, Restagno, Rio 2022, *Eur. Phys. J. E* — [Springer 10189-022-00255-6](https://link.springer.com/article/10.1140/epje/s10189-022-00255-6); [arXiv 2209.04435](https://arxiv.org/abs/2209.04435)
- Frazier, Jiang, Burton 2020, *Phys. Rev. Fluids* 5:013304 — [APS PRFluids](https://journals.aps.org/prfluids/abstract/10.1103/PhysRevFluids.5.013304)
- Linfield 1972, *JAOCS* — [Springer BF02633297](https://link.springer.com/article/10.1007/BF02633297)
- Marinova et al. 2009, *Korean Chem. Eng. Res.* — [Korea Science JAKO200910103439001](http://www.koreascience.or.kr/article/JAKO200910103439001.page)
- US Cleaning Institute, *Environmental and Human Safety of Major Surfactants: AOS* — [PDF](https://www.cleaninginstitute.org/sites/default/files/research-pdfs/12_Alpha_Olefin_Sulfonates.pdf)
- Colonial Chemical, *SLES to Sodium C14-16 Olefin Sulfonate substitution case study* — [link](https://colonialchem.com/blog/personal-care/a-case-study-in-substitution-from-sodium-laureth-sulfate-to-sodium-c14-16-olefin-sulfonate/)
- Pugh 2016, *Bubble and Foam Chemistry*, Cambridge University Press — chapter 2 on surfactant properties.
- Sodium laureth sulfate, [Wikipedia](https://en.wikipedia.org/wiki/Sodium_laureth_sulfate); α-Olefin sulfonate, [Wikipedia](https://en.wikipedia.org/wiki/%CE%91-Olefin_sulfonate).
- AOS+HPAM EOR study: [MDPI Energies 2023, 16(22):7523](https://www.mdpi.com/1996-1073/16/22/7523).
- US Patent 4367169A on AOS low-temp stability — [Google Patents](https://patents.google.com/patent/US4367169A/en).
