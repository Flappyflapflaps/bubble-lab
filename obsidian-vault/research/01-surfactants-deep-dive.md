---
title: "Surfactants deep dive — AOS, SLES, CAPB, LDAO, sulfobetaines, APGs"
date: 2026-05-15
tags: [research, surfactants, giant-bubbles]
---

# Surfactants deep dive — AOS, SLES, CAPB, LDAO, sulfobetaines, APGs

A working-level chemistry brief on which surfactant system to build a world-record giant-bubble film on. Sources cited inline. Concentrations are quoted from datasheets where possible.

---

## 1. SLES-70 vs AOS-40 for giant bubbles

The two workhorse anionics on the giant-bubble shortlist are **sodium laureth sulfate, 2EO** (SLES, "Texapon N70" at 70% active) and **sodium C14–16 alpha-olefin sulfonate** (AOS, "Calsoft AOS-40" / "Bio-Terge AS-40" at 40% active). They look interchangeable in a SDS but they behave very differently in a 3-metre soap film.

### Active matter and the mass-swap factor

SLES-70 is sold at **70% ± 2% active matter, with molecular weight 376.48 g/mol and pH 6.5–9.5 in 1% aqueous solution** ([SLES 70% technical datasheet, Ronas / Yeser](https://www.specialchem.com/cosmetics/product/ronas-chemicals-sodium-lauryl-ether-sulfate-sles-70)). BASF Texapon N70 is the canonical reference grade ([BASF Texapon N 70 TDS](https://promo.basf.com/campaign/Projetos/CaringForYou/Documentos/Geral/Texapon%C2%AE%20N%2070.pdf)).

AOS-40 is sold at **~40% active**, with viscosity 151 cP at 25 °C and pH 7–9 in 1% solution ([Chemistry Connection AOS-40 TDS](https://chemistryconnection.com/sds/data/pdf/AOS_40_TDS.pdf)).

**Mass-swap factor: to deliver the same active surfactant matter you must dose AOS-40 at 70/40 = ×1.75 the mass of SLES-70.** That is, 50 g of SLES-70 carries 35 g of active anionic; you need 87.5 g of AOS-40 to match. Note this is a *mass* swap of raw materials, not a like-for-like performance swap — see foam profile below.

### Critical micelle concentration

| Surfactant | CMC (water, 25 °C) | Source |
|------------|--------------------|--------|
| SLES (2EO) | ~0.8 mM (~0.3 g/L) | [Aoudia & Al-Maamari, J. Surf. Det. 2010](https://link.springer.com/article/10.1007/s11743-009-1131-9) |
| AOS C14–16 | ~8 mM (~2.5 g/L) | [α-Olefin sulfonate review, Cosmetics & Toiletries](https://www.cosmeticsandtoiletries.com/cosmetic-ingredients/cleansing/article/21837056/examining-tomorrows-surfactant-personalities-alpha-olefin-sulfonate-in-personal-care) |
| SDS (no EO) | ~8 mM | reference baseline |

SLES has an order-of-magnitude lower CMC than AOS. The ethoxy groups give ion-dipole stabilisation of the micelle, dropping the CMC by roughly 10× versus SDS ([Aoudia 2010](https://link.springer.com/article/10.1007/s11743-009-1131-9)). For a giant-bubble film at 2–3% active, both surfactants are far above CMC, so the bulk fluid is fully micellised in either case. The difference matters at the interface: SLES reaches a saturated monolayer at lower bulk concentration, which protects you against late-dilution losses inside the film.

### Hard-water tolerance: sulfate vs sulfonate

This is the single biggest chemistry difference.

**SLES** is an **alkyl sulfate ester** — `R-O-SO3⁻Na⁺`. The C–O–S bond is hydrolysable. Below pH 4 it cleaves to lauryl alcohol + sodium sulfate. Strongly recommended pH window: **5–9** ([Camachem SLES FAQ](https://camachem.com/en/blog/frequently-asked-question-about-sodium-laureth-sulfate-sles); [Yeser SLES MSDS rev 3](https://yeserchem.com/wp-content/uploads/2023/02/MSDS-Yeser%C2%AE-SLES-70-Rev..pdf)). SLES self-hydrolyses slowly even at neutral pH, releasing acidity over weeks.

**AOS** is an **alkene sulfonate** — `R-CH=CH-SO3⁻Na⁺` (plus ~25% hydroxyalkane sulfonate isomer). The C–S bond is covalent and non-hydrolysable. AOS is rated stable from **pH 2 to 12** ([α-Olefin sulfonate Wikipedia](https://en.wikipedia.org/wiki/%CE%91-Olefin_sulfonate); [Cosmetics & Toiletries](https://www.cosmeticsandtoiletries.com/cosmetic-ingredients/cleansing/article/21837056/examining-tomorrows-surfactant-personalities-alpha-olefin-sulfonate-in-personal-care)).

In **hard water (Ca²⁺, Mg²⁺)**, both anionics can in principle form insoluble divalent salts, but SLES is far more tolerant than non-ethoxylated SDS because the ethylene oxide groups solubilise the calcium salt: *"the alkylpoly(oxyethylene) sulfates (such as SLES) are shown to be the best surfactant for their practical uses in hard water, since their sodium and calcium salts as well as their mixtures are readily soluble at room temperature"* ([Hardness tolerance review, ResearchGate](https://www.researchgate.net/publication/279554860_Hardness_tolerance_of_anionic_surfactants_in_the_presence_of_nonionic_surfactants)). AOS handles hard water even better. AOS has "great hard-water resilience and good dispersion of calcium soap" and is preferred over LAS in hard-water zones ([Calsoft AOS-40 / Harcros](https://www.harcros.store/products/calsoft-aos-40-mysrkl89)).

In quantitative foam work at 32 mM AOS, foam half-life reached **~345 minutes with 99.6% quality** in salt brine ([Pal et al., enhanced oil recovery foam study via search summary](https://www.sciencedirect.com/science/article/abs/pii/S016773221830953X)).

### pH stability window summary

| Property | SLES-70 | AOS-40 |
|----------|---------|--------|
| Active matter | 70 ± 2% | ~40% |
| Stable pH | 5–9 (sulfate ester hydrolyses below 4) | 2–12 |
| Hard-water tolerance | good (2EO solubilises Ca salt) | excellent |
| Self-hydrolysis in water | yes, slow drift acidic | none |
| CMC | 0.8 mM | 8 mM |
| Foam character | high flash, lower stability solo | denser, creamier, longer-lived |

### Foam profile

SLES alone gives a **high-flash, low-stability** foam — copious initial bubbles, fast drainage. *"SLES produces relatively unstable foam"* alone ([Foam Making, Steven Abbott](https://www.stevenabbott.co.uk/practical-surfactants/foam-making.php)). AOS gives a *"denser, more creamy texture"* with longer-lived foam ([AOS vs SLS/SLES, NBInno](https://www.nbinno.com/article/detergents/aos-vs-sls-sles-milder-sustainable-surfactants-ym)). For a giant-bubble film, the goal is not flash but a film that survives 60+ seconds of drainage at 3-m radius — which favours AOS's intrinsic film robustness.

The published foam-film work on AOS (Farajzadeh et al.) measured equilibrium AOS foam films with controlled gas permeability and salt-dependent thickness ([Foam films stabilized with AOS, ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S092777570800191X); [Gas Permeability of AOS Films, ResearchGate](https://www.researchgate.net/publication/24423096_Gas_Permeability_of_Foam_Films_Stabilized_by_an_a-Olefin_Sulfonate_Surfactant)). Critically, AOS shows decreasing gas permeability with decreasing film thickness above a critical salt concentration — meaning the AOS film *resists* gas exchange even when thin, which is exactly what you want for a multi-cubic-metre bubble.

### Behaviour with anionic PAM (polyacrylamide)

Both SLES and APAM (anionic polyacrylamide) carry a negative charge. They do **not** strongly co-adsorb — anionic PAM stays in the bulk as a rheology modifier and adds extensional viscosity through entangled chains. Anionic PAM works **better as a drag reducer in fresh water** and is degraded by salinity, electrolytes and shear ([Polyacrylamide degradation, npj Clean Water 2018](https://www.nature.com/articles/s41545-018-0016-8)). The big risk: Ca²⁺ collapses anionic PAM by charge-screening and cross-linking — *"the formation of calcium soap complexes is so efficient that the concentration of free surfactant available for cleaning is reduced to effectively zero until all the calcium has been removed from solution"* ([Chelant Science overview](https://www.aboutcleaningproducts.com/science/chelant-science/)). The same collapse applies to APAM coils. **Hard water + APAM + SLES is a triple-vulnerability.** Use AOS + chelator, or move PAM to nonionic.

### Behaviour with PEO

PEO is non-ionic and high-MW (PolyOx WSR-301 is ~4 × 10⁶ g/mol, [Industrial Cellulosics / Roquette](https://www.industrialcellulosics.com/products/polyox/polyox-wsr-301); J-Lube is **25% PEO of MW up to 8 × 10⁶, 75% sucrose** ([sciencemadness discussion confirms J-Lube composition](http://www.sciencemadness.org/talk/viewthread.php?tid=18786) and the Burton group's working note).

PEO **suppresses initial foaming** of both SLES and ALES (ammonium laureth sulfate) by competing with surfactant for the air–water interface: at 0.1 wt% SDS + 0.15 wt% PEO, foam volume drops 57% (538 → 234 mL); at the same PEO dose with ALES (a sulfate close to SLES), foam volume drops only 16% ([Effects of PEO on Foam Properties of Anionic Surfactants, PMC12431101](https://pmc.ncbi.nlm.nih.gov/articles/PMC12431101/)). However PEO **extends drainage half-life** — ALES + 0.15% PEO gives the longest drainage time of any tested system (117 s at 0.5 wt% ALES). The picture: PEO trades flash for film life. That trade is exactly what a giant bubble needs.

Both SLES and AOS work with PEO, but the polydispersity of PEO matters more than the surfactant identity — *"polydispersity in molecular weight of the solvated polymers leads to better performance at lower concentrations"* ([Frazier, Jiang & Burton, "How to make a giant bubble", Phys. Rev. Fluids 2020 / arXiv:1908.00537](https://arxiv.org/abs/1908.00537)).

### Behaviour with CAPB

This is where SLES is famous and AOS is weaker.

**SLES + CAPB** is the canonical worm-like micelle pair — at pH 5.5 CAPB carries a slight positive charge, neutralises the SLES head group repulsion, raises the surfactant packing parameter, and converts spherical micelles into giant entangled worms ([Cocamidopropyl betaine overview, ScienceDirect](https://www.sciencedirect.com/topics/chemistry/cocamidopropyl-betaine)). The pair is *"two excellent fast foamers"* with strong synergy ([Steven Abbott foam-making](https://www.stevenabbott.co.uk/practical-surfactants/foam-making.php)). For SLES + CAPB at 2:1 molar ratio, the mixed CMC drops to **~0.5 mM** ([Mitrinova, Tcholakova et al. via search summary](https://www.researchgate.net/publication/259872743_Surface_and_foam_properties_of_SLES_CAPB_fatty_acid_mixtures_Effect_of_pH_for_C12-C16_acids)). Optimal interaction ratio is around **3:1 SLES:CAPB by molar / active matter** ([Chemists Corner discussion citing formulators' practice](https://chemistscorner.com/cosmeticsciencetalk/discussion/best-ratio-for-sles-c-dea-capb/)).

**AOS + CAPB** also works but synergises less strongly than SLES + CAPB. Industry experience: *"AOS neither foams nor synergistically interacts with CAPB as well as SLES does, and formulators have had to use a bit more AOS (as active matter) to cope with these differences"* ([Chemists Corner discussion](https://chemistscorner.com/cosmeticsciencetalk/discussion/why-this-shampoo-formula-doesnt-foam-when-i-replace-sles-with-aos/)).

### Verdict on SLES vs AOS for giant bubbles

For a **world-record-attempt giant bubble (>3 m diameter)** in **UK water (10–15 °fH, ~250–300 ppm CaCO₃)**, the professional choice is **AOS-40 as primary anionic**, for four reasons:

1. **No hydrolysis drift.** A bubble juice that ferments overnight in a jar at pH 5 because of SLES self-hydrolysis is a daily real-world failure mode. AOS doesn't do this.
2. **Better hard-water film behaviour** with reduced calcium-soap precipitation risk, especially in southern English tap water.
3. **Tougher, lower-permeability film** — AOS film gas permeability decreases as film thins (above a critical salt level), which is what a 100 m³ bubble needs in its final seconds.
4. **Stable across pH 2–12**, removing one variable from polymer + glycerol + chelator interactions.

You give up some CAPB synergy and some flash foam, but neither matters for a single huge film — and you compensate by keeping CAPB at 0.3–0.5% active (see Section 2).

If cost or supply is constraining, **SLES-70 is still acceptable** if you keep the recipe at pH 7–8, dose chelator (Section 4), and use it within 4–6 weeks of mixing.

---

## 2. CAPB-35 vs LDAO-30 (Lauramine Oxide / Ammonyx LO)

Both are zwitterionic / nonionic-at-neutral-pH co-surfactants. They're not the same thing.

### Cocamidopropyl betaine (CAPB)

CAPB is **amphoteric**: it has a permanent quaternary ammonium head and a pH-dependent carboxylate tail. Its **isoelectric point is 6.25** ([CAPB charge analysis, ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0927775722018787)). Below pH 6 it is slightly cationic; above pH 7 it is anionic.

Datasheet specs:
- **CAPB-30 / CAB-35** is sold at **30% ± 2% active matter** (standard grade), or 38% active for the 45% grade ([CAPB grades & specifications, Elchemy](https://elchemy.com/blogs/capb-reports/capb-grades-specifications)).
- Use rate in personal care: **3–10% raw product**, i.e. 1–3% active, in shampoos and body washes ([Formulating with CAPB, NBInno](https://www.nbinno.com/article/surfactants/formulating-cocamidopropyl-betaine-optimal-performance-dy)).

What CAPB **actually does** in a SLES-anionic system at pH 5–6:

1. **Charge neutralisation:** the cationic ammonium head shields anionic sulfate repulsion in the mixed micelle.
2. **Packing density up:** mixed micelles re-pack from spheres to cylinders, then to wormlike threads. Cryo-TEM has imaged wormlike micelles → disklike aggregates in SLES/CAPB/fatty-acid systems ([Mitrinova et al., Langmuir 2018](https://pubs.acs.org/doi/10.1021/acs.langmuir.8b00421)).
3. **Wormlike micelle network in bulk** → bulk viscoelasticity, drag reduction, slower film drainage.
4. **Mildness via reducing free monomeric anionic** — important for skin, less critical for bubbles.

The wormlike-micelle synergy peaks around **SLES:CAPB ≈ 3:1 active mass** ([Mitrinova, Tcholakova et al.](https://www.researchgate.net/publication/263575359_Rheology_of_Aqueous_Solutions_Containing_SLES_CAPB_and_Microemulsion_Influence_of_Cosurfactant_and_Salt)).

### Lauramine oxide (LDAO / DDAO, "Ammonyx LO")

LDAO is a true **amine oxide**: N-oxide of dodecyldimethylamine, MW 229.4 g/mol ([Lauryldimethylamine oxide, Wikipedia](https://en.wikipedia.org/wiki/Lauryldimethylamine_oxide)). Its behaviour is sharply pH-dependent in a different way from CAPB:

- **Above pH ~7**: nonionic, the N→O dipole carries no net charge.
- **Below pH ~5**: protonated, behaves cationic.

Datasheet specs:
- **Ammonyx LO (Stepan):** **30% amine oxide active**, MW 251 (counter-ion-corrected), viscosity 18 cP at 25 °C, "long-lasting foam" ([Stepan Ammonyx LO datasheet, Knowde](https://www.knowde.com/stores/stepan-company/products/ammonyx-lo); [Stepan product page](https://www.stepan.com/content/stepan-dot-com/en/products-markets/product/AMMONYXLO.html)).
- **CMC ~1–2 mM (0.023–0.046% w/v)** — lower than CAPB and much lower than AOS ([LDAO Grokipedia / Cayman](https://grokipedia.com/page/Lauryldimethylamine_oxide)).

What LDAO does that CAPB doesn't:

1. **CMC reduction is stronger.** Adding LDAO to SLES/AOS/CAB lowers both surface tension and CMC further, with synergistic effects on viscosity ([Bhardwaj et al., RJPC-A 2017 — Synergism of anionic/amphoteric mixtures with amine oxide](https://link.springer.com/article/10.1134/S0036024417130064)).
2. **Surface viscosity / dilatational modulus boost.** The N-oxide dipole hydrogen-bonds across the monolayer, giving an unusually rigid surface film. *"2–3% lauryl amine oxide added to a mild surfactant transforms weak, short-lived foam into rich, stable lather"* ([Lauryl amine oxide in personal care, Elchemy](https://elchemy.com/blogs/chemical-market/lauryl-amine-oxide-in-personal-care-foaming-cleansing-and-mildness-benefits)).
3. **Compatible with both anionic and cationic surfactants** simultaneously, because of the swing-charge.

The Stepan Cocamide-DEA Replacements deck explicitly shows lauramine oxide outperforming alternatives on foam volume in hand-dish formulations ([Stepan technical bulletin](https://www.stepan.com/content/dam/stepan-dot-com/webdam/website-product-documents/literature/household-institutional-industrial-cleaning/StepanCocamideDEAReplacementsHardSurfaceCare.pdf)).

### CAPB vs LDAO comparison

| Property | CAPB-35 | LDAO-30 (Ammonyx LO) |
|----------|---------|---------------------|
| Active matter | 30–38% | 30% |
| Class | amphoteric (zwitterion) | nonionic at pH > 7, cationic at pH < 5 |
| Isoelectric / pivot pH | 6.25 | ~5.0 |
| CMC | ~0.1 mM (mixed with SLES) | 1–2 mM solo, lower mixed |
| Best at | wormlike micelles, bulk viscosity, low-foam thickening | surface viscosity, monolayer rigidity, foam stability |
| With SLES | strong wormlike synergy (3:1) | additive, less wormy |
| With AOS | moderate synergy | strong synergy |
| Thermal stability | moderate | better |

### Use both or just one?

**Both — for a giant-bubble film.** They occupy different physical roles:

- **CAPB does the bulk job**: builds wormlike micelles with the anionic, raises bulk extensional viscosity, slows drainage at the Plateau borders. CAPB's wormlike-micelle physics requires an anionic partner with low CMC (SLES) or a salt; AOS-only systems still benefit because at 2–3% active you are far above CMC and CAPB will still pair with AOS to lengthen rod-like micelles ([Synergistic Growth of Giant Wormlike Micelles, Langmuir 2017](https://pubs.acs.org/doi/abs/10.1021/acs.langmuir.6b03955)).
- **LDAO does the *surface* job**: builds rigid monolayer at the gas/water interface, raises Gibbs–Marangoni elasticity, slows pinch-off and Ostwald ripening on the actual bubble wall.

For an AOS-based 2–3% active recipe at pH 7:
- **AOS active 2.0%** (primary).
- **CAPB active 0.4–0.6%** (anionic-amphoteric pairing — ~5:1 AOS:CAPB by active).
- **LDAO active 0.2–0.4%** (surface stiffness — ~10:1 AOS:LDAO by active).

This is the same logical structure as the Sovereign IPN protocol you've been working with: anionic + amphoteric for bulk micelle structure, amine oxide for monolayer rigidity. The peer-reviewed Mitrinova group work shows that a third "co-foamer" component (CAPB or amine oxide) added to a SLES base reliably raises surface elasticity and slows drainage ([Mitrinova et al., Colloids and Surfaces A 2014](https://www.sciencedirect.com/science/article/abs/pii/S092777571200862X)).

### Worm-like micelle physics with SLES + CAPB

The mixed-surfactant packing parameter `P = v / (a₀ × l)` (Israelachvili) rises from ~0.33 (sphere, SLES alone) to ~0.5 (worm) once CAPB neutralises the head charge. In experimental SLES (10 mM) + CAPB (5 mM) systems, adding a fatty acid (myristic, lauric) gives a *"very high surface modulus"* that "modifies dynamic foam properties — inside-foam friction, foam-wall friction and bubble breakup"; foam stability is maximum near the fatty-acid pKa ([Mitrinova, Tcholakova, Denkov 2014](https://www.sciencedirect.com/science/article/abs/pii/S092777571200862X)). This is what's behind the "trace stearic acid / cetyl alcohol" boost in some street-performer recipes.

The Frazier–Burton paper measured extensional rheology in soap-with-polymer films and concluded that **the extensional viscosity of the polymer solution, not the bulk shear viscosity, governs film stretch**; surfactant + worm-like micelle physics handles the surface; polymer handles the bulk extension ([Frazier, Jiang, Burton, Phys. Rev. Fluids 5, 013304 (2020)](https://journals.aps.org/prfluids/abstract/10.1103/PhysRevFluids.5.013304)).

---

## 3. Sulfobetaines and APGs — can they replace CAPB?

### Cocamidopropyl hydroxysultaine (CAPHS)

CAPHS is a sulfobetaine: a permanent quaternary ammonium paired with a sulfonate (not a carboxylate, as in CAPB). The sulfonate stays ionised at *all* pH values, so unlike CAPB the molecule is **permanent zwitterion across the entire pH range** ([Cocamidopropyl hydroxysultaine, Wikipedia](https://en.wikipedia.org/wiki/Cocamidopropyl_hydroxysultaine); [Hydroxysultaine class, Wikipedia](https://en.wikipedia.org/wiki/Hydroxysultaine)).

Properties:
- "Compatible with cationic surfactants and stable over a wide pH range in soft or hard water" ([New Directions Aromatics CAPHS spec](https://www.newdirectionsaromatics.com/cosmetic-ingredients/raw-materials/cocamidopropyl-hydroxysultaine)).
- Excellent foaming and viscosity-building "even in hard water or high pH systems" ([Therapy Clean CAPHS overview](https://therapyclean.com/blogs/cleaning/cocamidopropyl-hydroxysultaine-gentle-foaming-surfactant-for-natural-cleaning-products)).
- In the peer-reviewed CO₂-foam study, **CAPHS:SDS 2:1 ratio gave a foam half-life 4× longer than either component alone** at the same total surfactant concentration ([Viscosity-driven stabilization of CO2-in-brine foams, ScienceDirect 2021](https://www.sciencedirect.com/science/article/abs/pii/S0167732221003391)).

The sulfobetaine class generally **enhances foam half-life and lamella strength**: *"the increase of the carbon chain and sulfonyl substitution of betaine significantly enhanced the stability of CO2 foam, and strengthened the foam lamella strength by improving the interfacial adsorption and increasing the viscosity of the interfacial film"* ([betaine foam review via search summary](https://www.sciencedirect.com/science/article/abs/pii/S0016236122019858)).

**CAPHS vs CAPB pros and cons for giant bubbles:**

- **Pro CAPHS:** charge stable at any pH (no isoelectric weak point at pH 6.25), more salt-tolerant, demonstrably stronger CO₂-foam stabilisation.
- **Pro CAPHS:** longer half-life lamellae are *exactly* the giant-bubble use case.
- **Con CAPHS:** less ubiquitous in UK supply, costs ~2–3× CAPB, the wormlike-micelle literature with SLES is much thinner (most rheology data is on SLES + CAPB).
- **Con CAPHS:** the sulfonate group competes with the anionic, so the SLES/CAPHS synergy is *weaker* than SLES/CAPB at the same molar ratio (sulfonate is still negative; CAPB at pH 5.5 is positive).

**Lauryl betaine** is a simpler amphoteric without the amido linker. It produces *"foam characterized by larger bubble sizes that create impressive initial volume, often described as 'flashy' foam, though the larger bubbles dissipate somewhat faster than those produced by CAPB"* ([Elchemy: Lauryl betaine vs CAPB](https://elchemy.com/blogs/chemical-market/understanding-lauryl-betaine-and-capb-which-surfactant-works-best-in-personal-care-products)). It is *thermally more stable* than CAPB but **worse for film longevity**. Not recommended for giant bubbles.

### Alkyl polyglucosides (APGs)

APGs are pure nonionics built from a fatty alcohol + glucose Fischer glycosylation. They are sold at 50–70% active and are pH-stable across pH 2–14.

Datasheet numbers:
- **Coco-glucoside: CMC 67.2 ppm, surface tension 29 mN/m at 0.1% active, 25 °C** ([Cosmetics & Toiletries APG foam article](https://www.cosmeticsandtoiletries.com/research/literature-data/article/21835913/foaming-for-formulators-cocoglucoside)).
- **Decyl glucoside (C10): CMC 50.1 ppm, surface tension 29 mN/m at 0.1% active, 25 °C** ([same source](https://www.cosmeticsandtoiletries.com/research/literature-data/article/21835913/foaming-for-formulators-cocoglucoside)).

Foam ranking: lauryl glucoside > coco-glucoside > decyl glucoside for **stability**, but decyl glucoside foams up *faster* ([VRP guide](https://vermontruff.com/blogs/news/surfactants-glucosides-decyl-coco-caprylyl-lauryl-explained); [Branch Basics coco vs decyl](https://branchbasics.com/blogs/cleaning/coco-glucoside-vs-decyl-glucoside)).

**APGs in a giant-bubble formulation:**

- **Pro:** nonionic, fully calcium-tolerant, will not precipitate in hard water, immune to chelator scarcity.
- **Pro:** mixed micelles of APG + anionic improve hard-water tolerance (the classic "nonionic rescue" effect — *"the addition of nonionic surfactants greatly enhances the solubility of Ca-salts of anionic surfactants"* — [Hardness Tolerance review](https://www.researchgate.net/publication/279554860_Hardness_tolerance_of_anionic_surfactants_in_the_presence_of_nonionic_surfactants)).
- **Pro:** very low CMC at the air-water interface.
- **Con:** glucoside foam is *thin and short-lived* on its own.
- **Con:** APGs do not build wormlike micelles with anionics — CAPB still wins on bulk viscoelasticity.

**APG as a partial CAPB replacement** (e.g. 0.2% active decyl glucoside + 0.4% active CAPB) **for hard-water robustness** is a defensible move and is used in some "sulphate-free / SLES-free" naturals systems ([Stepan sulphate-free brochure](https://www.stepan.com/content/dam/stepan-dot-com/webdam/website-product-documents/literature/personal-care/Sulfate-Free-Brochure.pdf)).

### Has any record-setter used these?

No published world-record giant-bubble recipe (Pearlman 2015, the Megan Colby Parker record, Graeme Denton / Marty McBubble Adelaide records) appears to use CAPHS or APG ([Gary Pearlman record at RecordSetter, 96.27 m³](https://recordsetter.com/world-record/free-floating-soap-bubble/39035); [Adelaide bubble record, ACEMS](https://acems.org.au/Adelaide-bubble-record)). The published research recipes (Burton group, "Optimized Recipe for Giant Bubbles" Salkin 2022) and the popular bubble-wiki recipes still favour Dawn Pro + guar / J-Lube / PolyOx WSR-301 — i.e. a commercial sulfate dish detergent + a high-MW polymer ([Emory News, Burton lab](https://news.emory.edu/features/2020/01/physics-of-bubbles/); [Salkin et al., EPJ E 2022](https://link.springer.com/article/10.1140/epje/s10189-022-00255-6) and [arXiv:2209.04435](https://arxiv.org/abs/2209.04435)). There is no published peer-reviewed giant-bubble record using a sulfobetaine or APG as the headline surfactant. That makes it open ground for experimentation — but not the place to bet a single world-record attempt.

---

## 4. Hard water and chelators

UK tap water averages **70–286 mg/L CaCO₃**, with the South East (London, Southampton) at the upper end — **~285 mg/L CaCO₃ equivalent** ([Variation in Tap Water Mineral Content in the UK, PMC 2022](https://pmc.ncbi.nlm.nih.gov/articles/PMC9457372/)). London is **~320 mg/L CaCO₃** (very hard) ([UK Water Hardness Map, Filter Flair](https://filterflair.co.uk/pages/uk-water-hardness-map)). 10–15 °fH is roughly **100–150 mg/L CaCO₃**, i.e. moderate.

### Why chelation matters here

Free Ca²⁺ does three bad things to a giant-bubble juice:

1. **Precipitates calcium dodecyl sulfate / calcium soap** at the surfactant head ([Calcium dodecyl sulfate precipitation, J. Colloid Interface Sci. 1983](https://www.sciencedirect.com/science/article/abs/pii/002197978390440X)). SDS solubility is governed by the Ca²⁺–dodecyl-sulfate solubility product below CMC. SLES is much more tolerant because the 2EO sterically solubilises the calcium salt.
2. **Charge-screens anionic PAM** and folds the polymer coils, eliminating extensional viscosity.
3. **Bridges PEO + APAM** in unfortunate ways: high MW polymers can flocculate around Ca²⁺ centres, dropping the effective active polymer in the film.

The chemistry: *"the formation of calcium soap complexes is so efficient that the concentration of free surfactant available for cleaning is reduced to effectively zero until all the calcium has been removed from solution, either by chelation or by forming the insoluble soap adduct"* ([Chelant Science](https://www.aboutcleaningproducts.com/science/chelant-science/)).

### EDTA disodium vs tetrasodium vs citrate vs gluconate

| Chelator | log K_Ca (25 °C, μ = 0.1 M) | Working pH | Typical use level |
|----------|----------------------------|------------|--------------------|
| **Disodium EDTA** (Na₂H₂EDTA) | 10.69 (EDTA⁴⁻ form) | 4.5–12 (works above 6) | 0.1–0.3% (CIR up to 0.85%) |
| **Tetrasodium EDTA** (Na₄EDTA) | 10.69 (same anion, pre-neutralised) | 7–14 | 0.1–0.3% |
| **Sodium citrate** | 3.5 | 3–9 | 0.5–2% |
| **Sodium gluconate** | 1.2 (single) → ~6 with high pH chelate | 3–10, best at high pH | 0.1–0.5% |

Sources: [Ethylenediaminetetraacetic acid, Wikipedia](https://en.wikipedia.org/wiki/Ethylenediaminetetraacetic_acid); [Chempendix EDTA formation constants](https://sites.google.com/site/chempendix/formation-constants/formation-constants-for-metal-edta-complexes); [Disodium EDTA cosmetic use, Specialchem](https://www.specialchem.com/cosmetics/inci-ingredients/disodium-edta); [Sodium gluconate as chelator, Jungbunzlauer 2024 comparative study](https://www.jungbunzlauer.com/wp-content/uploads/2025/06/JBL-AR-Green-and-effective-complexation-%E2%80%93-a-comparative-study-2024-112-1.pdf); [Sodium gluconate / Juventude](https://www.juventudeskincare.com/blogs/founders-journal/sodium-gluconate-in-skincare-the-gentle-chelating-agent-with-a-clean-origin).

**Log K is logarithmic.** EDTA at log K ≈ 10.7 binds Ca²⁺ roughly **10⁷ times more strongly than citrate** (log K ≈ 3.5) and **10⁹ times more strongly than gluconate** at neutral pH. To bind the same amount of Ca²⁺ with citrate as with EDTA, you need disproportionately more citrate because the equilibrium leaves more free Ca²⁺ in solution.

### Disodium vs tetrasodium EDTA — the practical difference

The two are the *same chelator molecule*. The difference is the **starting pH** when you dissolve them:

- **Disodium EDTA (Na₂H₂EDTA):** 1% solution pH ~4.5–5.0. It will drop the pH of your bubble juice; you must buffer back up with NaOH or sodium carbonate. **Risk: drives SLES toward hydrolysis pH window.**
- **Tetrasodium EDTA (Na₄EDTA):** 1% solution pH ~11. It raises pH; you may need citric acid to buffer down. **Risk: drives glycerol + sugar into Maillard-like discoloration over time.**

For an **AOS-based recipe (pH-tolerant 2–12)**, **tetrasodium EDTA is the better choice** — it doesn't risk dropping you into the SLES-hydrolysis zone, and AOS doesn't care about pH 8–9. For a **SLES-based recipe**, **disodium EDTA is safer** because keeping pH at 6.5–7.5 is critical and tetrasodium EDTA will push you past 9.

### Dose calculation for UK hard water (10–15 °fH ≈ 150 mg/L CaCO₃)

Molecular weights: CaCO₃ = 100 g/mol; Ca²⁺ = 40 g/mol; EDTA·2Na·2H₂O = 372.24 g/mol; EDTA·4Na = 380.17 g/mol; sodium citrate dihydrate = 294 g/mol.

For 1 L of 150 mg/L CaCO₃ water: 150 mg / 100 g·mol⁻¹ = 1.5 mmol Ca²⁺.

1:1 stoichiometry → **1.5 mmol EDTA = 558 mg disodium EDTA dihydrate per litre = 0.056% w/v.**

To be on the safe side (Mg²⁺, Fe³⁺ also present, plus a margin), dose **0.10–0.15% w/w disodium EDTA** in any SLES recipe in UK tap water — well within the cosmetic CIR-cleared safety range ([CIR safety assessment, EDTA & salts](https://www.cir-safety.org/sites/default/files/EDTA.pdf)). For very hard water (London, 320 mg/L), go to **0.20%**.

Sodium citrate equivalent: at log K ~3.5, you need substantial molar excess. Practical citrate dose is **0.5–1.0% w/w sodium citrate dihydrate** to do what EDTA does at 0.1%. Citrate also buffers pH (which can be good or bad depending on the recipe).

Sodium gluconate equivalent: **0.3–0.5% w/w**, but expect noticeably weaker Ca²⁺ control vs EDTA.

### Does AOS need chelator?

Less than SLES needs it — but **yes, still useful**. AOS is more hard-water tolerant than SLES, but:
- Any anionic PAM polymer in the recipe still collapses with free Ca²⁺.
- High-MW PEO is less affected but still benefits from clean water.
- The lubricin / film mechanics improve consistently with chelated water.

For an **AOS + PEO + CAPB + LDAO recipe**, **0.05–0.10% tetrasodium EDTA** is sufficient. For an **AOS + APAM + PEO** semi-IPN recipe, hold to **0.10–0.15% tetrasodium EDTA** because the APAM is the vulnerable component.

For a pure **glucoside + PEO** nonionic recipe, chelator is optional — but adding 0.05% prevents trace metal-catalysed PEO oxidative chain scission over the working life of the juice.

---

## Synthesis: which surfactant system to use

For a **world-record-attempt giant-bubble recipe at metric scale (1 L mix)** in UK tap water at 10–15 °fH:

### Recommended blend — active matter targets

| Component | Active % w/w | Why |
|-----------|-------------|-----|
| **AOS-40 (Calsoft AOS-40 / Bio-Terge AS-40)** | 2.0% active (= 5.0 g/L raw at 40% active) | Primary anionic; non-hydrolysing, hard-water tolerant, low-permeability film |
| **CAPB-30/35** | 0.4–0.5% active (= 1.3–1.7 g/L raw at 30% active) | Wormlike-micelle partner; bulk extensional viscosity; charge-shields AOS heads |
| **Lauramine oxide (Ammonyx LO, 30%)** | 0.2–0.3% active (= 0.7–1.0 g/L raw at 30% active) | Surface dilatational modulus; Marangoni rigidity at the bubble wall |
| **PEO (PolyOx WSR-301 OR J-Lube)** | 0.05–0.10% PEO (i.e. 0.5–1.0 g/L PolyOx, or 2.0–4.0 g/L J-Lube to deliver 25% PEO) | Extensional viscosity for film stretch; polydisperse MW for low-concentration performance |
| **Glycerol (humectant)** | 3–5% | Vapour-pressure reduction, slows evaporation thinning |
| **Tetrasodium EDTA** | 0.08–0.10% | Ca²⁺/Mg²⁺ sequestration without dropping pH into SLES-hydrolysis zone (AOS-tolerant pH 8–9) |
| **Sodium benzoate or potassium sorbate** | 0.1–0.2% | Preservative (sorbate works best below pH 6.5; benzoate works to pH 5; switch to phenoxyethanol if pH > 7) |

### Total active surfactant: ~2.7%

This sits comfortably in the published "not too high" surfactant zone identified by Salkin et al. for an optimised giant bubble — too much surfactant lowers initial film thickness too far and breaks pinch-off ([Salkin et al., EPJ E 2022 / arXiv:2209.04435](https://arxiv.org/abs/2209.04435)).

### pH target: 7.0–8.0

- AOS is fully stable.
- LDAO is nonionic (cleanest behaviour).
- CAPB is slightly anionic (mildly destabilises wormlike micelles, but the LDAO surface stiffness compensates).
- Tetrasodium EDTA buffers without spiking the pH past 9.
- Bonus: sorbate/benzoate preservatives still active.

### Why this beats the SLES/CAPB classic

1. **No pH drift over 4 weeks** — SLES hydrolysis is gone.
2. **Hard-water immune** — AOS + EDTA handle the worst UK tap water.
3. **Two complementary stiffness mechanisms** — bulk worms (CAPB) + surface rigidity (LDAO).
4. **PEO is the polymer choice over APAM** because PEO is nonionic, hard-water indifferent, and the literature is unambiguous that polydisperse high-MW PEO produces the largest published bubbles (Burton group).
5. **The trade-off** is some flash foam (SLES's strength) — irrelevant for a single 100 m³ bubble.

### Why we keep CAPB instead of going CAPHS

The peer-reviewed wormlike-micelle and dilatational-rheology data with SLES/AOS exists predominantly for **CAPB**, not for CAPHS. CAPHS is an interesting upgrade path — its permanent zwitterion charge profile and 4× foam half-life with SDS at 2:1 ratio is compelling ([Viscosity-driven CO2-foam stabilization, 2021](https://www.sciencedirect.com/science/article/abs/pii/S0167732221003391)) — but use it as an **adjunct** at first (e.g. replace half the CAPB with CAPHS) before swapping out the whole CAPB position. For the record attempt itself, stay with the well-characterised CAPB.

### If the budget allows one experimental upgrade

Add **0.05% myristic acid + sodium hydroxide (saponified in situ)** — the Mitrinova/Tcholakova/Denkov line shows this gives a *"very high surface modulus"* on SLES/CAPB foams, dramatically slowing Ostwald ripening on the actual bubble surface ([Mitrinova et al. 2014, Colloids Surf. A](https://www.sciencedirect.com/science/article/abs/pii/S092777571200862X)). At our pH 7–8, sodium myristate sits near its working window. This is the same chemistry behind shaving-foam stability — proven, just rarely used in giant bubbles.

---

## Sources

Primary peer-reviewed:
- Frazier, Jiang & Burton, "How to make a giant bubble", *Phys. Rev. Fluids* 5, 013304 (2020). [arXiv 1908.00537](https://arxiv.org/abs/1908.00537), [APS](https://journals.aps.org/prfluids/abstract/10.1103/PhysRevFluids.5.013304).
- Salkin et al., "An optimized recipe for making giant bubbles", *EPJ E* (2022). [arXiv 2209.04435](https://arxiv.org/abs/2209.04435), [Springer](https://link.springer.com/article/10.1140/epje/s10189-022-00255-6).
- Mitrinova, Tcholakova, Denkov et al., "Surface and foam properties of SLES + CAPB + fatty acid mixtures", *Colloids Surf. A* (2014). [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S092777571200862X).
- Mitrinova et al., "Viscosity Peak due to Shape Transition from Wormlike to Disklike Micelles", *Langmuir* (2018). [ACS](https://pubs.acs.org/doi/10.1021/acs.langmuir.8b00421).
- Aoudia & Al-Maamari, "SLES Micellization and Water Solubility Enhancement", *J. Surf. Det.* (2010). [Springer](https://link.springer.com/article/10.1007/s11743-009-1131-9).
- Bhardwaj et al., "Synergism and Physicochemical Properties of Anionic/Amphoteric Surfactant Mixtures with Amine Oxide", *Russ. J. Phys. Chem. A* (2017). [Springer](https://link.springer.com/article/10.1134/S0036024417130064).
- Farajzadeh et al., "Foam films stabilized with α-olefin sulfonate", *Colloids Surf. A* (2008). [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S092777570800191X); "Gas Permeability of AOS Films" [ResearchGate](https://www.researchgate.net/publication/24423096_Gas_Permeability_of_Foam_Films_Stabilized_by_an_a-Olefin_Sulfonate_Surfactant).
- "Effects of PEO on Foam Properties of Anionic Surfactants", *PMC* (2025). [PMC12431101](https://pmc.ncbi.nlm.nih.gov/articles/PMC12431101/).
- "Viscosity-driven stabilization of CO2-in-brine foams using CAPHS + SDS", *J. Mol. Liq.* (2021). [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0167732221003391).
- "Variation in UK Tap Water Mineral Content", *PMC* (2022). [PMC9457372](https://pmc.ncbi.nlm.nih.gov/articles/PMC9457372/).
- Polyacrylamide degradation review, *npj Clean Water* (2018). [Nature](https://www.nature.com/articles/s41545-018-0016-8).

Supplier datasheets:
- [BASF Texapon N 70 TDS](https://promo.basf.com/campaign/Projetos/CaringForYou/Documentos/Geral/Texapon%C2%AE%20N%2070.pdf) (SLES-70).
- [Ronas SLES-70 TDS](https://www.specialchem.com/cosmetics/product/ronas-chemicals-sodium-lauryl-ether-sulfate-sles-70); [Yeser SLES MSDS Rev 3](https://yeserchem.com/wp-content/uploads/2023/02/MSDS-Yeser%C2%AE-SLES-70-Rev..pdf).
- [Chemistry Connection AOS-40 TDS](https://chemistryconnection.com/sds/data/pdf/AOS_40_TDS.pdf); [Calsoft AOS-40 / Harcros](https://www.harcros.store/products/calsoft-aos-40-mysrkl89).
- [Stepan Ammonyx LO datasheet](https://www.stepan.com/content/stepan-dot-com/en/products-markets/product/AMMONYXLO.html); [Stepan PDF bulletin](https://www.stepan.com/content/dam/stepan-dot-com/webdam/website-product-documents/product-bulletins/surfactants/AMMONYXLO.pdf).
- [Industrial Cellulosics / Roquette PolyOx WSR-301 spec](https://www.industrialcellulosics.com/products/polyox/polyox-wsr-301).
- [Stepan sulfate-free brochure](https://www.stepan.com/content/dam/stepan-dot-com/webdam/website-product-documents/literature/personal-care/Sulfate-Free-Brochure.pdf).
- [Stepan Cocamide DEA replacements bulletin](https://www.stepan.com/content/dam/stepan-dot-com/webdam/website-product-documents/literature/household-institutional-industrial-cleaning/StepanCocamideDEAReplacementsHardSurfaceCare.pdf).

Reference / educational:
- Steven Abbott, "Foam Making" and "Foam Elasticity", [Practical Surfactants Science](https://www.stevenabbott.co.uk/practical-surfactants/foam-making.php).
- [α-Olefin sulfonate, Wikipedia](https://en.wikipedia.org/wiki/%CE%91-Olefin_sulfonate); [Lauryldimethylamine oxide, Wikipedia](https://en.wikipedia.org/wiki/Lauryldimethylamine_oxide); [Cocamidopropyl hydroxysultaine, Wikipedia](https://en.wikipedia.org/wiki/Cocamidopropyl_hydroxysultaine); [EDTA, Wikipedia](https://en.wikipedia.org/wiki/Ethylenediaminetetraacetic_acid).
- [Chempendix EDTA formation constants table](https://sites.google.com/site/chempendix/formation-constants/formation-constants-for-metal-edta-complexes).
- [Cosmetics & Toiletries — Foaming with Coco-glucoside](https://www.cosmeticsandtoiletries.com/research/literature-data/article/21835913/foaming-for-formulators-cocoglucoside).
- [Cosmetics & Toiletries — Examining AOS in Personal Care](https://www.cosmeticsandtoiletries.com/cosmetic-ingredients/cleansing/article/21837056/examining-tomorrows-surfactant-personalities-alpha-olefin-sulfonate-in-personal-care).
- [CIR Safety Assessment of EDTA & salts](https://www.cir-safety.org/sites/default/files/EDTA.pdf).
- [Disodium EDTA cosmetic INCI, Specialchem](https://www.specialchem.com/cosmetics/inci-ingredients/disodium-edta).
- [Jungbunzlauer green chelation comparative study 2024](https://www.jungbunzlauer.com/wp-content/uploads/2025/06/JBL-AR-Green-and-effective-complexation-%E2%80%93-a-comparative-study-2024-112-1.pdf).
- [UK Water Hardness Map, Filter Flair](https://filterflair.co.uk/pages/uk-water-hardness-map).
- [Emory News on Burton lab bubble work](https://news.emory.edu/features/2020/01/physics-of-bubbles/); [MIT Tech Review on giant bubble chemistry](https://www.technologyreview.com/2019/08/24/102697/the-chemistry-behind-how-you-make-a-record-breaking-giant-soap-bubble/).
- [Gary Pearlman free-floating record, RecordSetter](https://recordsetter.com/world-record/free-floating-soap-bubble/39035); [Adelaide tallest-bubble record, ACEMS](https://acems.org.au/Adelaide-bubble-record).
