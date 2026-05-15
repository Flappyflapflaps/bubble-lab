---
title: "Polymer physics — PEO, HPAM, guar, HEC, xanthan for giant bubble films"
date: 2026-05-15
tags: [research, polymers, giant-bubbles]
---

# Polymer physics for giant bubble films

The polymer scaffold inside a soap film is the single biggest lever between a 3-foot novelty bubble and a 30-foot record attempt. Surface tension sets the spherical curvature; the surfactant monolayer sets the Gibbs–Marangoni elasticity that arrests local thinning; but the bulk extensional viscosity of the entrained polymer is what allows the film to be drawn out over tens of square metres without rupture. Frazier, Jiang and Burton (Phys. Rev. Fluids 5, 013304, 2020) put it precisely: "the extensional rheology is the most important factor in creating the bubble" and "polymers can dramatically increase film lifetime at high molecular weights and high concentrations, although such high concentrations can inhibit the initial film formation" ( https://journals.aps.org/prfluids/abstract/10.1103/PhysRevFluids.5.013304 ; https://arxiv.org/abs/1908.00537 ). A typical giant film has a surface area approaching 100 m² with an average thickness of ~3 µm and total water mass on the order of 300 mL ( https://news.emory.edu/features/2020/01/physics-of-bubbles/index.html ). At those dimensions, the polymer's ability to develop tensile stress under uniaxial extension — not its standing-viscosity at zero shear — is what keeps the film alive between the wand and the bursting point.

Below, I survey four sub-topics with specific peer-reviewed and supplier-datasheet numbers, then propose a unified polymer scaffold for a metric-scale record attempt.

---

## 1. HPAM (anionic polyacrylamide) molecular-weight selection

Hydrolyzed polyacrylamide is the workhorse of enhanced oil recovery (EOR) precisely because no other commodity polymer combines comparable molecular weight, water solubility and extensional viscosity per ppm. The dominant supplier is SNF Floerger; their Flopaam family covers the full giant-bubble-relevant range.

### SNF Floerger Flopaam grades

The SNF Flopaam range spans roughly 8–20 MDa:

- **Flopaam 3330S** — 8 MDa, 25–30% degree of hydrolysis ( https://link.springer.com/article/10.1007/s13202-020-00841-4 ).
- **Flopaam 3430S** — ~13 MDa medium grade.
- **Flopaam 3630S** — the standard EOR reference, "Mw of 18–20 MDa in powder form" with 25–30% hydrolysis, used at 1000 ppm in the Acharya et al. surfactant–polymer extensional rheology study ( https://pmc.ncbi.nlm.nih.gov/articles/PMC7726756/ ; https://www.snf.co.za/wp-content/uploads/2017/08/Flopaam.pdf ).
- **Flopaam 3530S** and higher — ~16 MDa.

For giant-bubble work the question is: which grade maximises extensional viscosity in a 1–5 µm thin film without being so brittle that the wand-pull shear destroys it on the first stroke?

### The MW versus scission trade-off

HPAM extensional viscosity scales steeply with molecular weight, but so does mechanical sensitivity. Chen et al. (PMC review of EOR HPAM injectivity, Energies 12, 49, 2019) state that "extensional flow is crucial for polymer chain scission, dominating degradation mechanisms during initial fracture flow, particularly at shear rates exceeding 10⁵ s⁻¹" and that "mechanical degradation leads to a decrease in polydispersity of PAM suggesting preferred scission at mid-chain compared to random chain scission of chemical degradation" ( https://www.mdpi.com/1996-1073/12/1/49 ; https://pmc.ncbi.nlm.nih.gov/articles/PMC6403817/ ). Crucially "the viscosity loss of a polymer due to shear degradation can reach 50–70% during the injection process," and "chain scissions due to mechanical degradation yield viscosity loss" with rate constants that scale with molecular weight ( https://link.springer.com/article/10.1007/s13202-020-00905-5 ).

Sorbie, Roodhart and others have shown that scission rate is roughly first-order in the polymer's number-average molecular weight, with the highest-MW linear polymers losing the most viscosity per pass through a high-shear region ( https://pubs.acs.org/doi/10.1021/acspolymersau.5c00105 ). This means a 20 MDa Flopaam 3630S blended with a domestic kitchen blender at 8,000 rpm can lose half its extensional viscosity within seconds; the same blender on a 10 MDa grade may keep 80% or more.

For giant bubble formulation, the practical implication is: choose MW for the highest extensional viscosity you can deliver after the worst shear in your mixing chain, not before.

### Optimal concentration in ppm

Two reference numbers from independent literature converge:

1. **Critical overlap concentration C\*** for HPAM in EOR-grade brine is "200 wppm (weight parts per million). At concentrations below 200 wppm, there was no polymer network, while at concentrations above 200 wppm, networks were more entangled and could recover quickly upon deformation" ( https://link.springer.com/article/10.1007/s12182-017-0152-7 ). Below C\* you have isolated coils with extensional response but no semi-dilute coupling.
2. **Soap Bubble Wiki / PAM page** reports for non-toxic anionic/nonionic PAM "as little as 0.01 grams per liter of bubble juice is effective. The molecular weight of the PAM may approach or even exceed 10 million."

So a useful working window for HPAM in a giant-bubble juice is roughly 10–200 ppm (0.01–0.2 g/L), with 50–100 ppm being the sweet-spot for a 15–20 MDa Flopaam-class grade. The Acharya et al. paper used 1000 ppm for benchmark rheometry ( https://pmc.ncbi.nlm.nih.gov/articles/PMC7726756/ ) but that is well above giant-bubble economy: at 1000 ppm the solution becomes visibly stringy, gel-like and resists being pulled into a thin film by a cotton wand.

A second, severe constraint: HPAM is anionic and aggregates in the presence of divalent cations. Acharya measured for 1000 ppm Flopaam 3630S in deionized water a CaBER break-up time of "3.12 seconds … at 1% CaCl₂, the break-up time decreased to 0.51 seconds" — a sixfold collapse from a single percent of calcium ( https://pmc.ncbi.nlm.nih.gov/articles/PMC7726756/ ). For any HPAM giant-bubble juice the water must be deionized or RO; tap water with even moderate hardness will cause premature gelation or scission.

### Surfactant–polymer extensional synergy

For HPAM with anionic surfactant (SDBS) at the CMC, Acharya et al. measured the extensional relaxation time rising from "0.299 seconds (HPAM alone in deionized water)" to "0.64 seconds (HPAM + 0.1% SDBS in deionized water)" and the extensional viscosity climbing "from 75 to 220 Pa·s" — a 3× boost in elongational stress for free, simply by adding surfactant at the right concentration ( https://pmc.ncbi.nlm.nih.gov/articles/PMC7726756/ ). This is one of the cleanest pieces of evidence for why giant-bubble juice needs both polymer and surfactant at well-tuned ratios.

**HPAM recommendation:** for a metric-scale bubble I would pick **Flopaam 3630S (18–20 MDa) at 50–100 ppm** (0.05–0.10 g/L) if water hardness can be controlled, dropping to Flopaam 3430S (~13 MDa) at 100–200 ppm if it cannot.

---

## 2. PEO grade comparison — WSR-301, WSR-303, WSR-Coagulant, J-Lube

PEO (polyethylene oxide) is the polymer of choice for the entire giant-bubble hobby community for one reason: it is enormously elastic per ppm and far less calcium-sensitive than HPAM, because it is nonionic.

### Polyox WSR grades — Dow / IFF / Roquette

The Polyox WSR series, originally Union Carbide / Dow, now Roquette / IFF, runs across roughly 0.1–8 MDa. The high-MW grades relevant to giant bubbles are:

- **Polyox WSR-301** — Mw 4 × 10⁶ g/mol, viscosity 1,650–5,500 cP at 1 wt% ( https://www.industrialcellulosics.com/products/polyox/polyox-wsr-301 ).
- **Polyox WSR-Coagulant** — Mw 5 × 10⁶ g/mol, viscosity 5,500–7,500 cP at 1 wt% ( https://www.industrialcellulosics.com/products/polyox/polyox-wsr-coagulant ).
- **Polyox WSR-303** — Mw 7 × 10⁶ g/mol, viscosity 7,500–10,000 cP at 1 wt% ( https://www.industrialcellulosics.com/products/polyox/polyox-wsr-303 ).

The viscosity numbers scale roughly with the cube of molecular weight in the entangled regime, but the relevant scaling for extensional rheology is different. PNAS work by Dinic, Sharma and others has shown that "extensional relaxation time and the EC span get longer with increase in polymer concentration or molecular weight" and follows a power law over a wide MW range in PEO ( https://www.pnas.org/content/116/18/8766 ; https://pubs.acs.org/doi/10.1021/acsmacrolett.5b00393 ). For PEO Boger fluids relaxation times "as low as 240 μs" can be reliably measured by slow-retraction methods; for high-MW Polyox these climb into milliseconds, and that is the timescale on which a film thinning at 1 m/s draws extensional stress.

### J-Lube — polydisperse 25% PEO + sucrose

J-Lube (Jorgensen Laboratories veterinary lubricant) is "25% polydisperse PEO (up to 8 × 10⁶ g/mole) and 75% sucrose" ( https://soapbubble.fandom.com/wiki/PEO ; Pasquet 2022 referenced in https://link.springer.com/article/10.1140/epje/s10189-022-00255-6 ). The chemist at the manufacturer has stated only that the PEO has Mw greater than 2 × 10⁶, but every published bubble study that has used J-Lube treats it as if it carries the ~8 MDa upper-tail distribution.

The sucrose matrix has two practical advantages over neat PEO powder:
1. It is a far less hygroscopic, less clumpy powder, so it disperses without lumps.
2. The sucrose dilutes the polymer in the bulk, slowing initial hydration and giving the operator a working window before viscosity climbs.

For Pasquet 2022, "J-Lube is often added in concentrations of 0.1–0.4 g/L, with the caveat that 25% of which is actually PEO" — meaning the *effective* PEO concentration is 25–100 ppm (https://link.springer.com/article/10.1140/epje/s10189-022-00255-6).

### Why "aged PEO" is superior — polydispersity buys you robustness

The single most quoted finding from Frazier, Jiang and Burton 2020 is the discovery that PEO that had sat in an opaque bottle at room temperature for ~6 months gave dramatically stronger giant films than freshly opened PEO. They wrote: "a polydisperse solution will certainly contain a broader range of relaxation times in its rheological response, possibly giving rise to a non-monotonic extensional response" and "polydispersity in molecular weight of the solvated polymers leads to better performance at lower concentrations" ( https://arxiv.org/abs/1908.00537 ; https://journals.aps.org/prfluids/abstract/10.1103/PhysRevFluids.5.013304 ).

Burton's verbatim quote in the Emory press release: "Polymers of different sizes become even more entangled than single-sized polymers, strengthening the elasticity of the film" ( https://news.emory.edu/features/2020/01/physics-of-bubbles/index.html ). The mechanism: aged PEO has undergone hydroperoxide-initiated photo-oxidation and free-radical chain scission ( https://en.wikipedia.org/wiki/Photo-oxidation_of_polymers ; https://pubs.acs.org/doi/10.1021/ie3005995 ). The product is a chain population in which the *long* tail of the molecular-weight distribution is partially broken into shorter chains that now act as "links between the longest and largest polymers in solution" ( https://www.technologyreview.com/2019/08/24/102697/the-chemistry-behind-how-you-make-a-record-breaking-giant-soap-bubble/ ). The film therefore has *both* a long-relaxation-time tail that resists fast extensional pulls and a short-relaxation-time component that dissipates fast shocks — effectively a multi-mode elastic spectrum from a single polymer family.

This is why J-Lube punches above its molecular weight: 8 MDa polydisperse PEO from an opaque sucrose-buffered powder is *intrinsically* more polydisperse than a freshly-opened lot of monodisperse-leaning Polyox WSR-303 of the same nominal Mw.

### PEO recommendation per grade

- **WSR-301 (4 MDa)** at ~150–300 ppm (0.15–0.30 g/L): the bubbleologist's classic; "0.125 g of fresh WSR-301 in 1 gallon of bubble juice (~0.03 g/L)" is the published minimum effective concentration ( https://soapbubble.fandom.com/wiki/PEO ) but practical recipes use 5–10× that. Best for medium bubbles in moderate wind.
- **WSR-Coagulant (5 MDa)** at ~100–200 ppm: stiffer film, slower drainage, harder to launch in low wind.
- **WSR-303 (7 MDa)** at ~50–150 ppm: the highest-elasticity solid grade; very sensitive to mixing shear; require slow hand-stir hydration.
- **J-Lube (polydisperse up to 8 MDa, 25% by mass)** at 0.1–0.4 g/L bulk = 25–100 ppm effective PEO: the *easiest* to mix, the most forgiving, and the most genuinely polydisperse out of the box. For artists and field-record attempts where mixing conditions are variable, this is the most robust choice.

For all PEO grades the published mixing guidance is identical: "reduce the speed of the stirring once all the powder has been added as PEO can be damaged by the high-shear stirring" ( https://soapbubble.fandom.com/wiki/Polymers_-_Mixing ). High-shear induction for less than 30 seconds to wet the powder, then exclusively low-shear paddle stirring.

---

## 3. PEO + HPAM together vs alone — is the IPN really stronger?

The Sovereign IPN protocol in this project (Sovereign Semi-IPN Kinetic Assembly Protocol, ~0.40 g/L J-Lube + 0.02 g/L anionic PAM, sequence-mixed dry, low-shear hydrated) is a deliberate semi-interpenetrating polymer network: the flexible nonionic PEO chains thread through the rigid anionic PAM network with no covalent crosslinks. There are three lines of evidence that this is genuinely better than either polymer at higher concentration.

### Line 1 — Polydispersity argument extends to mixed chemistries

Frazier and Burton's 2020 finding was that polydispersity within a single polymer (PEO) made the film more robust because it broadened the relaxation-time spectrum. The same physical argument applies — and is amplified — when the two polymers also differ in *chain stiffness* and *charge*. A flexible nonionic PEO coil at 4–8 MDa has a Kuhn segment of ~1 nm and a relaxation time of a few milliseconds at giant-bubble concentrations; a partially-hydrolysed anionic PAM at 15–20 MDa with its extended polyelectrolyte conformation has a relaxation time roughly an order of magnitude longer. Mixing the two gives a relaxation-time spectrum that spans, in principle, two to three decades from a single fluid — exactly what an extensional film needs to span the wand-stretch frequency band from quasi-static drainage (10⁻¹ Hz) to wind-induced flapping (10² Hz).

### Line 2 — Surfactant–polymer extensional coupling is additive

PEO famously forms cooperative associates with anionic surfactants. The SDS / PEO literature ( https://www.sciencedirect.com/science/article/abs/pii/S0021979701974387 ; https://pubmed.ncbi.nlm.nih.gov/18684464/ ) establishes that "the formation of micellar aggregates of SDS along the PEO chain results in an increase in the strength of the extension thickening of the PEO solutions … the minimum PEO concentration required to form intermolecular entanglements is substantially reduced in the presence of micellar aggregates." HPAM, being anionic itself, does not associate with anionic surfactant in the same way — but it does respond strongly to the presence of *any* ionic strength change in the bulk. Acharya measured a 3× extensional viscosity climb (75 → 220 Pa·s) when SDBS at 0.1% was added to 1000 ppm HPAM in deionized water ( https://pmc.ncbi.nlm.nih.gov/articles/PMC7726756/ ).

The implication: PEO and HPAM each couple to the surfactant by *different mechanisms* (cooperative micellar binding for PEO, electrostatic environment shift for HPAM), so each gets its own extensional boost from the same surfactant pool. They do not compete for surfactant binding sites in the way two identical anionic polymers would.

### Line 3 — Sovereign and bubble-community experience

The Sovereign semi-IPN protocol (4.0 g J-Lube + 0.2 g PAM per 10 L, i.e. 100 ppm effective PEO + 20 ppm PAM) is at concentrations *below* either polymer's nominal solo working point, yet reported to give a fluid that "looks and behaves almost exactly like plain water in the bucket" while still allowing giant films. This is exactly the Frazier–Burton low-concentration polydisperse signature: maximal elastic robustness at minimal viscosity penalty during loading and launching.

The cautionary note from Soap Bubble Wiki Multi-Polymer Mixes is real: "where both polymers are used in large enough quantities to be effective on their own, the result seems to be problematic. The general conclusion is that guar gum won't make a well-tuned PEO mix better" ( https://soapbubble.fandom.com/wiki/Multi-Polymer_Mixes ). This warning is about guar+PEO at *separately* sufficient concentrations. The semi-IPN logic explicitly inverts that: each polymer is held *below* its solo working point and contributes only its complementary relaxation-time mode. For PEO + HPAM at sub-saturation concentrations this is *not* the same regime as two over-loaded thickeners fighting for entanglement sites.

### Optimal PEO:HPAM ratio

From the Sovereign protocol the ratio is 20:1 by mass (PEO:PAM = 0.40 : 0.02 g/L). If we account for J-Lube being 25% PEO that drops the effective PEO:HPAM mass ratio to roughly 5:1. By chain count, however — given PAM is 4× higher MW than the PEO — the ratio is closer to 20:1 PEO:HPAM chains. This means the HPAM is acting as a rare, very-long-relaxation-time scaffold inside a much denser PEO network. It is a true scaffolding role rather than a co-thickening one. A reasonable working window is 5:1 to 20:1 PEO:HPAM by mass, with total polymer 50–300 ppm.

### Does using both at low concentration beat using either at higher concentration?

Direct head-to-head experimental data is sparse. The strongest indirect evidence is Frazier and Burton's central thesis: that "intermediate concentrations and a polydisperse mixture of polymers of various molecular weights" outperform single-polymer high-concentration mixes ( https://www.futurity.org/giant-bubbles-physics-2270532/ ; https://journals.aps.org/prfluids/abstract/10.1103/PhysRevFluids.5.013304 ). Two polymer families at low concentration is the maximal version of "polydisperse mixture" — you get not only width within each MW distribution but also a discontinuous jump between chemistries. The theoretical prediction is yes; the experimental confirmation specifically for PEO+HPAM in a giant film is, to my knowledge, not yet published in a peer-reviewed paper.

---

## 4. Alternatives — guar, HEC, xanthan, sodium polyacrylate, PVA

A fair comparison requires three axes: shear viscosity (defines pumping and wand-loading feel), extensional viscosity (defines film survival), and operational robustness (cost, biocompatibility, calcium tolerance, shear stability, batch reproducibility).

### Guar gum

- **Mw**: Highly variable. "Commercial guar gum has a molecular weight (Mw) of 3.0 × 10⁶ g/mol with a small degree of polydispersity" but ranges from 5,000 to 8 × 10⁶ Da depending on origin and processing ( https://en.wikipedia.org/wiki/Guar_gum ; https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/guar-gum ).
- **Shear viscosity**: Strongly shear-thinning, with a clear low-shear plateau. At 3.0 g/L (3000 ppm) "the thread length increases dramatically" in capillary breakup tests ( https://soapbubble.fandom.com/wiki/Guar_Gum ; https://www.sciencedirect.com/science/article/abs/pii/S0268005X14000605 ).
- **Extensional viscosity**: Trouton ratio ~20 — high but not as high as flexible PEO ( https://pubmed.ncbi.nlm.nih.gov/29254016/ ).
- **Pros**: Cheap; food-grade biocompatible; works well in tap water; very polydisperse out of the bag.
- **Cons**: Shear-degrades under aggressive mixing; viscosity is "rapidly degraded at temperatures > 50°C at acidic pH"; requires careful pre-dispersion in alcohol to avoid lumping ( https://pmc.ncbi.nlm.nih.gov/articles/PMC9056569/ ).
- **Niche**: Cheap, robust beginner formulas. Frazier and Burton's reference recipe uses 2–3 g guar / 1 L for the published giant-bubble recipe ( https://www.futurity.org/giant-bubbles-physics-2270532/ ).

### HEC (hydroxyethylcellulose)

- **Mw / grades**: Dow Cellosize and Ashland Natrosol grades are the standards. "CELLOSIZE™ QP-100MH … high molecular weight … viscosity range of 4,400–6,000 cPs at 1% concentration" — implying Mw on the order of 1–1.5 MDa ( https://www.chempoint.com/products/dow/cellosize-hydroxyethyl-cellulose/cellosize-hydroxyethyl-cellulose/cellosize-qp-100mh ). Natrosol 250 HHR has viscosity 3,400–5,000 cP at 1% — comparable to Cellosize QP-100MH ( https://www.ulprospector.com/en/na/Cleaners/Detail/872/645506/Natrosol-250-HHR-HEC ).
- **Extensional viscosity**: "Trouton ratio at high extension rates to around 10–20" — modest, because cellulose backbones have limited extensibility ( https://pubs.rsc.org/en/content/articlehtml/2015/sm/c4sm01661k ; https://pubs.acs.org/doi/abs/10.1021/acs.macromol.0c00077 ).
- **Pros**: Nonionic, so very calcium-tolerant. Surface-treated grades (Natrosol HHR with R-coating) disperse cleanly into water without lumps. Highly reproducible viscosity from grade to grade. Stable across pH 2–12.
- **Cons**: Lower extensibility than PEO; cellulose chains are stiff. Can be expensive in HHR grades.
- **Niche**: Reliable middle-ground polymer for hard-water recipes; good companion to a flexible PEO for spectrum-broadening; great for indoor / low-wind work where wand-loading reproducibility matters more than maximum extensional reach.

### Xanthan gum

- **Mw**: 2 × 10⁶ to 20 × 10⁶ Da ( https://www.sciencedirect.com/science/article/abs/pii/S0144861725003601 ).
- **Conformation**: Semi-rigid helix, persistence length ~44 nm (vs ~1 nm for PEO) ( https://www.sciencedirect.com/science/article/abs/pii/S0144861799001563 ).
- **Shear viscosity**: Extremely shear-thinning; high zero-shear viscosity at very low concentrations.
- **Extensional viscosity**: Trouton ratio ~40 — actually higher than guar — *but* xanthan has "much smaller finite extensibility compared to flexible polymers like PEO due to the high monomer mass of the xanthan gum repeat unit and the large persistence length of the chain" ( https://arxiv.org/html/2410.15132v1 ; https://pubmed.ncbi.nlm.nih.gov/29254016/ ).
- **Pros**: Extraordinarily shear-stable (no degradation under aggressive stirring); food-grade.
- **Cons**: Limited extensibility — the rigid rod can't draw out into a long thin film like a flexible coil can. Forms weak gels rather than entanglement networks. Strong shear-thinning hides the elastic stress that the film actually needs.
- **Niche**: Useful as a *minor* component (10–50 ppm) for foam-drainage delay, but should not be the primary polymer for a giant bubble. Cocktail recipes that use xanthan typically pair it with PEO ( https://www.sciencedirect.com/science/article/abs/pii/S0144861725006848 ).

### Sodium polyacrylate / Carbopol

- **Mw**: Commercial sodium polyacrylates span 10⁵–10⁷ Da; Carbopol grades are crosslinked acrylic polymers with effective Mw ~10⁶ depending on grade.
- **Shear viscosity**: Strongly shear-thinning, "flow behaviour index under 0.14" ( https://www.researchgate.net/publication/330149125_Rheological_Characterization_of_Carbopol_Dispersions_in_Water_and_in_WaterGlycerol_Solutions ).
- **Extensional viscosity**: Crosslinked Carbopols behave as soft gels rather than entangled solutions; storage modulus >> loss modulus, so they store elastic energy but do not flow well into a thin film.
- **Pros**: Super-absorbent; very high viscosity per ppm.
- **Cons**: Anionic — same calcium intolerance as HPAM, worse for gelled grades. Carbopol must be neutralised (by triethanolamine or similar) to thicken, adding a process step. The gel structure resists drawing into a film.
- **Niche**: Not recommended as primary giant-bubble polymer. Could play a role in a very-low-shear-rate, low-drainage display bubble but not a record stretch.

### PVA (polyvinyl alcohol)

- **Mw / grades**: Mowiol grades span "Mowiol 4-88 (~31,000 g/mol), Mowiol 8-88 (~67,000 g/mol), Mowiol 10-98 (~61,000 g/mol)" up to Mowiol 56-98 around 195,000 g/mol ( https://www.sigmaaldrich.com/US/en/product/aldrich/81365 ; https://ia803101.us.archive.org/35/items/polyvinylalcoholmanufacturemanual/Mowiol%20manual.pdf ). These molecular weights are *orders of magnitude lower* than PEO or HPAM giant-bubble grades.
- **Foam behaviour**: PVA foams readily even at low concentration: "CTR ≈ 10 mg/L for PVA 4-88, 8-88, 18-88 … >500 mg/L for PVA with 98% degree of hydrolysis" ( https://www.sciencedirect.com/science/article/pii/S092777572301912X ).
- **Pros**: Films are tough mechanically; commonly used in foam-formed paper as a foam stabiliser.
- **Cons**: MW is too low to drive bulk extensional viscosity comparable to PEO or HPAM. PVA contributes by film-mechanical and Marangoni-elasticity mechanisms rather than by extensional bulk rheology. "The combination role of high interfacial tension and lower interfacial dilational viscoelasticity leads to the increase of the rupture possibility with either low PVA concentration or high PVA molecular weight" — i.e. the operating window is narrow ( https://www.sciencedirect.com/science/article/abs/pii/S0360319919343514 ).
- **Niche**: Interesting as a *surfactant adjunct* rather than a polymer scaffold. Could play a role in a hybrid film stability strategy but cannot replace the PEO or HPAM extensional viscosity.

### Summary table

| Polymer | Mw (Da) | Trouton ratio | Calcium tolerance | Shear stability | Cost ($/kg, indicative) | Best role |
|---|---|---|---|---|---|---|
| PEO WSR-301 | 4 × 10⁶ | high (≥40) | excellent | poor — needs gentle mix | 60–100 | Primary giant-bubble polymer |
| PEO WSR-303 | 7 × 10⁶ | very high | excellent | very poor | 80–120 | High-elasticity, expert use |
| J-Lube (PEO) | up to 8 × 10⁶ polydisperse | very high | excellent | poor | 100–200 | Most robust polydisperse choice |
| HPAM Flopaam 3630S | 18–20 × 10⁶ | very high | poor (Ca-sensitive) | poor | 20–40 | Trace IPN scaffold, deionized water |
| Guar gum | ~3 × 10⁶ | ~20 | good | moderate (heat/shear) | 5–15 | Cheap beginner; pre-disperse in IPA |
| HEC (Cellosize QP-100MH) | ~1.5 × 10⁶ | 10–20 | excellent | good | 25–40 | Reliable Ca-tolerant supplement |
| Xanthan gum | 2–20 × 10⁶ | ~40 (but low extensibility) | good | excellent | 10–20 | Trace drainage-delay only |
| Sodium polyacrylate / Carbopol | 10⁵–10⁷ | low (gel-like) | poor (anionic) | varies | 15–40 | Not recommended |
| PVA (Mowiol 56-98) | 1.95 × 10⁵ | low | excellent | excellent | 20–60 | Adjunct, not scaffold |

**Verdict**: No alternative beats PEO + HPAM for combined extensional viscosity, polydispersity and scalability. Guar is the practical fallback; HEC is the calcium-tolerant supplement; xanthan, sodium polyacrylate and PVA are niche.

---

## Synthesis — optimal polymer scaffold for a metric-scale record attempt

The polymer system below is what the published rheology, the EOR scission literature, the Frazier–Burton polydispersity finding and the Pasquet 2022 optimisation point at.

### Polymer system

For a 10 L batch in deionized water:

- **Polyox WSR-301 (4 MDa monodisperse-leaning)** — 1.50 g (150 ppm). Solid, reproducible base PEO.
- **J-Lube (up to 8 MDa polydisperse PEO, 25% by mass)** — 1.60 g powder (40 ppm effective PEO). Adds the broad high-MW polydisperse tail.
- **HPAM Flopaam 3430S (~13 MDa)** — 0.50 g (50 ppm). The semi-IPN scaffold; trace concentration to add a long-relaxation-time mode without destabilising under mixing shear.
- **HEC Cellosize QP-100MH (~1.5 MDa)** — 0.50 g (50 ppm). Calcium-tolerant supplement to broaden the relaxation-time spectrum further and to give the film a stable Newtonian-leaning baseline if humidity is variable.

Total polymer load: 290 ppm by mass. Effective PEO ~190 ppm; HPAM 50 ppm; HEC 50 ppm. The total is below the published "1M PEO films lasting longer than 80 seconds while 8M PEO films never last longer than 60 seconds" upper-limit warning ( https://link.aps.org/accepted/10.1103/PhysRevFluids.5.013304 ) — i.e. we deliberately stay in the intermediate regime that Frazier and Burton identified as optimal.

If Flopaam 3630S (18–20 MDa) is available and water is reliably deionized, drop the HPAM concentration to 30 ppm and switch to that grade; the longer chain at lower concentration delivers more extensional viscosity per ppm at the cost of mechanical fragility during mixing.

### Mixing order to avoid shear scission

The order is dictated by what is most fragile to shear, and what hydrates slowest. The protocol below is adapted from the Sovereign IPN protocol and the soap-bubble-community PEO-mixing consensus ( https://soapbubble.fandom.com/wiki/Polymers_-_Mixing ):

1. **Dry premix** — weigh PEO WSR-301, J-Lube, HPAM Flopaam 3430S and HEC into a dry, sterile cup and shake gently until visibly even. (Wetting all four together prevents any one from forming a partial gel before the others have wetted.)
2. **Vortex induction (≤30 seconds, high shear)** — make a deep vortex in 10 L deionized water using a propeller mixer at ~1000 rpm. Pour the dry premix into the vortex shoulder so each grain wets instantly. Turn off high shear at 30 s. This is the *only* phase where high shear is permitted, and even then for HPAM it is already costing chain length; minimise it.
3. **Low-shear hydration (2–3 hours, ≤200 rpm paddle)** — switch to a wide-blade paddle or hand-stir gently. No cavitation, no foam. PEO and HPAM unspool slowly; HEC HHR-grade R-coating delays hydration deliberately to give time for the others to disperse before its viscosity climbs.
4. **Entropic rest (12–24 hours)** — cover and leave undisturbed. Trapped microbubbles float out, polymer chains relax into their equilibrium configurations, and the long-tail HPAM equilibrates with the surfactant pool to be added next.
5. **Surfactant integration (low shear)** — gently fold in the SLES/AOS + CAPB + LDAO surfactant blend with a paddle, not a blender. SDS-class anionic surfactants will form cooperative aggregates along the PEO chains within minutes ( https://pubmed.ncbi.nlm.nih.gov/18684464/ ); HPAM extensional viscosity will jump 3× as the surfactant reaches ~CMC ( https://pmc.ncbi.nlm.nih.gov/articles/PMC7726756/ ).
6. **pH lock** — adjust to pH 6.0–6.5 with a weak organic acid (sorbic, citric) to put CAPB into its zwitterionic state and to suppress any HPAM hydrolysis drift.
7. **Glycerol last** — 5–15% v/v glycerol after pH is locked. Glycerol primarily slows evaporation rather than affecting bulk rheology; Pasquet 2022 confirms that "the addition of glycerol provides improved bubble stability by preventing evaporation" ( https://link.springer.com/article/10.1140/epje/s10189-022-00255-6 ; https://arxiv.org/abs/2209.04435 ).

### Why this should beat any single-polymer recipe

This scaffold delivers, in a single fluid:

- A *low total polymer concentration* (290 ppm) that sits squarely in the Frazier–Burton "intermediate-concentration robust" sweet spot.
- A *relaxation-time spectrum spanning at least two decades*, from HEC's millisecond range through PEO's tens-of-milliseconds to HPAM's hundreds-of-milliseconds-to-seconds (Acharya measured 0.299 s for 1000 ppm Flopaam 3630S; at 50 ppm it will be ~10–20× shorter but still the longest mode in the fluid).
- A *polydispersity built two ways*: width within the J-Lube PEO distribution (already broad from manufacture), plus discontinuous jumps between four different polymer chemistries.
- A *mechanism for surfactant–polymer extensional synergy on two channels*: PEO–anionic-surfactant micellar binding *and* HPAM–ionic-strength response.
- *Calcium tolerance* from the HEC and PEO components covering the HPAM's weakness, so the recipe is forgiving of small water-quality variations.
- An *operationally tractable mixing protocol* that respects each polymer's shear sensitivity in the right order.

The single biggest risk to this scaffold is the HPAM. If your mixer overshoots 30 s of vortex induction or your water is unexpectedly hard, the HPAM contribution collapses and you are left with a PEO+HEC system — still very good, but down by perhaps a factor of two in the longest extensional mode. For the first batch of any new mix it is worth running a CaBER-style capillary thinning test (a slow drop pulled from a teaspoon and timed until it pinches) to confirm the long-mode tail survived hydration.

For a metric-scale world-record attempt this is the polymer scaffold I would commit to.
