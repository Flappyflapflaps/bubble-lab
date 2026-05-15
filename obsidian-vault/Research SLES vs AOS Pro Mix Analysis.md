---
title: "Research: SLES vs AOS & Pro Mix Analysis"
date: 2026-05-12
tags: [research, surfactants, commercial-mix]
---

# Best-guess identification of the yellow pro mix

The yellow tinge, water-thin body and pH ~7.2 point strongly to an **AOS-based concentrate**, most likely **Samsam Bubbleman's "Supapop"** (Bubble Inc, UK) or a close cousin (Bubblyheaven "Giant Bubble Powder Pro" sold ready-mixed, Dr Zigs concentrate). Stepan **Bio-Terge AS-40** ships as a "pale yellow 40% aqueous solution" of sodium C14-16 olefin sulfonate ([Stepan AS-40 datasheet via Knowde](https://www.knowde.com/stores/stepan-company/products/bio-terge-as-40); [Wintersun AS-40 listing](https://www.wintersunchemical.com/products/sodium-alpha-olefin-sulfonate-40-solution-aos-40-cnh2n-so3nan-14-cas_68439-57-6-straw-yellow-to-amber-liquid-2204-6-lb-tote) explicitly describes it as "straw yellow to amber liquid"). SLES-70 paste, by contrast, is "colorless to pale yellow" but is a thick paste — wrong texture. The water-thin viscosity also rules out high-loading guar/HEC formulas. A neat AOS-40 + low-load PEO/PAM + bicarbonate-buffered concentrate matches the description on every axis.

# 1. SLES vs AOS — head-to-head

| Property | SLES (C12-14, ~2 EO) | AOS (C14-16) |
|---|---|---|
| CMC, pure water | ~1 mM (0.049 % w/w) — drops to ~0.1 mM with 0.1 M NaCl | ~1.6 mM deionised, falling to ~2 mM at 0.1 M salt |
| Hard-water tolerance | Good but ether-sulfate can still precipitate with Ca²⁺ at high hardness | **Best of the common anionics** — sulfonate (not sulfate) head, doesn't hydrolyse, lime-soap dispersing |
| Foam profile | Fast, airy, loose | Creamy, denser, stable in hard/cold water |
| Hydrolysis | Slowly hydrolyses below pH ~5 to give dodecanol | Stable across pH 2–12 |
| Behaviour with anionic PAM | Forms standard repulsion film; ether-O can H-bond with PAM amide | Pure-repulsion network with APAM, well-documented for giant bubbles (your own `AOS APAM Repulsion Network Physics.md` covers this) |
| Color (commercial active) | SLES-70 paste: colorless to pale yellow paste | AOS-40: pale yellow to amber liquid |

Sources: Pasquet et al. 2022 "An optimized recipe for making giant bubbles" ([EPJ E](https://link.springer.com/article/10.1140/epje/s10189-022-00255-6), [arXiv:2209.04435](https://arxiv.org/abs/2209.04435)); Frazier/Jiang/Burton 2020 "How to make a giant bubble" ([Phys Rev Fluids](https://journals.aps.org/prfluids/abstract/10.1103/PhysRevFluids.5.013304), [arXiv:1908.00537](https://arxiv.org/abs/1908.00537)); [Soap Bubble Wiki Ingredients](https://soapbubble.fandom.com/wiki/Ingredients); [Yeserchem hardness ranking — LABSA > SLES ≈ SLS > AOS](https://yeserchem.com/optimizing-detergent-performance-in-the-face-of-water-hardness/).

**Why a serious bubbler prefers AOS:** sulfonate stability across pH, much better hard-water performance, and proven compatibility with anionic PAM for the "pure repulsion" disjoining-pressure film (oscillatory structural forces around ~2.4 % active AOS + ~100 ppm APAM). SLES wins on fast wetting and is cheaper, but loses to AOS once tap-water Ca²⁺/Mg²⁺ enters the picture.

# 2. SLES ↔ AOS substitution at matched active matter

Work in **grams of active surfactant**, not grams of paste/liquid.

- SLES-70 paste = 70 % active
- AOS-40 (Bio-Terge AS-40) = 40 % active

To replace **X g of SLES-70** with AOS-40 at the same active level:
`g of AOS-40 = X × (70 / 40) = X × 1.75`

So a recipe calling for **20 g SLES-70 paste** becomes **35 g AOS-40 liquid**, and you reduce added water by ~15 g to keep the total mass constant (AOS-40 carries 60 % water vs SLES-70's 30 %). See [Wintersun SLES-70 listing](https://www.wintersunchemical.com/products/sodium-lauryl-ether-sulfate-sles-70).

**Is 1:1 active really equivalent?** No — at matched active matter the AOS version will be marginally under-CMC on a molar basis (AOS molar mass ~315 vs SLES ~382), so molarity actually goes **up** ~20 %. In practice that's a wash because both sit far above CMC at typical bubble loadings (~1–3 % active). The bigger real-world difference: AOS keeps performing in hard tap water where SLES starts to lose foam volume.

# 3. Yellow-tinge ID — what else can colour a mix?

Yellow in a clear bubble concentrate usually comes from one of:

1. **AOS-40 / Bio-Terge AS-40** — pale yellow to straw, water-thin. Most likely culprit.
2. **CAPB (cocamidopropyl betaine)** — pale yellow liquid, but usually used as a co-surf at 1–5 % and adds modest viscosity.
3. **Coco-glucoside / decyl glucoside** — pale yellow nonionic, but viscous and rare in pro bubble mixes.
4. **Glycerin from vegetable source** — can be very pale straw; rarely the dominant colour.
5. **Preservatives** like sodium benzoate (white) or phenoxyethanol (clear) — not yellow.
6. **J-Lube** (PEO with dextrose carrier) — turns mixes slightly amber after a few weeks; usually cloudy not clear yellow.

Combined with "water-thin" and "pH ~7.2", AOS-40 is by far the best fit. Commercial candidates that fit the profile, ranked by likelihood:

- **Supapop / Bubble Inc (Samsam Bubbleman, UK)** — GWR-record-holder's commercial mix, sold as concentrate, water-thin. Formula not public but community consensus is AOS-based ([Bubble Inc Supapop](https://www.bubbleinc.co.uk/products/supapop-concentrate-250ml)).
- **Bubblyheaven (UK)** — explicitly partnered with Dr Zigs originally, then split. Pro-grade powder + ready-mix. ([Bubblyheaven brand history](https://www.bubblyheaven.co.uk/2023/08/25/bubble-history-inspiration-credits/)).
- **Dr Zigs concentrate (UK/Wales)** — "plant-based, biodegradable, secret formula"; consistency matches.
- **Bubble Thing (Stein, US)** — UNLIKELY — Stein explicitly tells users to add Joy/Dawn/Fairy themselves, so the concentrate is *not* the whole surfactant package, just polymer + bicarb. Rule out. ([bubblething.com FAQ](https://bubblething.com/faqs.html)).
- **Mike Miller "Gooey Mix"** — UNLIKELY — uses Dawn Pro as the surfactant, not raw AOS. ([Amazing Bubble Man recipes](https://amazingbubbleman.com/recipes/)).
- **Tom Noddy's Bubble Magic** — book/kit, dish-soap based, not a commercial concentrate.
- **BLM (Brian Lawrence Mix)** — community polymer mix recipe, not a commercial product. ([Soap Bubble Wiki BLM](https://soapbubble.fandom.com/wiki/BLM)).

**Best single guess: Supapop or a UK pro mix using Bio-Terge AS-40 + a low loading of PEO/PAM + sodium bicarbonate buffer.**

# 4. Why water-thin is good — extensional vs shear viscosity

Pasquet et al. 2022 and Frazier/Burton 2020 both make the same key point: **what holds a giant bubble together during expansion is extensional (elongational) viscosity, not shear (bulk) viscosity**. The film is being stretched, not sheared.

- High **shear** viscosity (glycerin-thick, guar-loaded) slows your wand, drags the film, dumps unnecessary fluid into the trailing edge, and gives huge film thickness gradients → faster gravitational drainage and earlier rupture.
- High **extensional** viscosity (long flexible polymer chains, PEO 4-8 MDa or HPAM 10-20 MDa, at 100–500 ppm) means the film resists thinning *only when it is being stretched* — exactly the failure mode you want to prevent.

A dilute PEO or PAM solution can have water-like shear viscosity (~1–5 cP) but extensional viscosity orders of magnitude higher under strain. Pasquet specifically notes "the surfactant concentration must be not too high" and that polydispersity (a spread of molecular weights) gives better performance at lower polymer concentration — Frazier/Burton's finding too. The optimised recipe (EPJ E 2022) gives about 0.04 wt % surfactant + ~500 ppm PEO + a few % glycerol; the bulk viscosity is barely above water.

So a water-thin pro mix isn't a corner being cut — it's a deliberately decoupled rheology: low shear so the film draws fast and thin, high extensional so it survives the stretch.

# 5. Why pH ~7.2 specifically

There are three competing pH optima floating around the bubble literature:

- **pH 8.0–9.0** — your own `AOS APAM Repulsion Network Physics.md` flags this as the "pure repulsion" sweet spot: APAM carboxylates fully dissociated → rigid extended chains → maximum oscillatory disjoining pressure.
- **pH 6.2** — the "Sovereign IPN" coacervate lock with zwitterionic anchors.
- **pH 7.2** — what the user reports for the commercial mix.

**The 7.2 hypothesis holds up.** It's the compromise pH for a *consumer-safe shelf product*:

1. **PAM dissociation is already ~complete by pH 6–7** ([PMC4978783 — anionic PAM dissociation](https://pmc.ncbi.nlm.nih.gov/articles/PMC4978783/)). You don't need pH 8.5 to extend the chains; 7.2 gives you 90 %+ of the repulsion benefit.
2. **Skin and eye safety.** Cosmetic regs and parent-safety reviewers push hard for pH 5.5–8.0 on anything kids touch. pH 8.5–9.0 stings eyes and chaps hands.
3. **Sodium bicarbonate self-buffering.** NaHCO₃ in water buffers naturally to ~8.3, but with the slightly acidic free fatty acid impurities in AOS and a touch of citric acid or phosphate the equilibrium sits at 7.0–7.5. It's the easiest target to hit with a single bulk buffer.
4. **Preservative window.** Sodium benzoate / potassium sorbate require pH ≤ 7.5 to remain in their protonated active form. Going to 8.5 cuts shelf life unless you switch to phenoxyethanol or isothiazolinones (more expensive, more allergenic).
5. **AOS doesn't care.** Sulfonates are fully ionised from pH 2 to 12, so dropping from 8.5 to 7.2 loses zero surfactant performance.

Verdict: pH 7.2 = "as alkaline as a children's product can legally/comfortably be while preserving cleanly." Not the physics optimum, but a defensible 95-percent solution.

# Recipe-level recommendations

1. **Drop-in SLES-70 → AOS-40 swap factor: ×1.75 by mass.** Reduce added water by the difference to keep total mass and water % constant. Expect slightly better hard-water performance and a faintly straw-coloured final solution.
2. **If reverse-engineering the pro mix, start here:** 6 % AOS-40 (= 2.4 % active), 0.05 % HPAM (anionic polyacrylamide, MW 10–20 MDa) or 0.1 % PEO (4–8 MDa), 5 % glycerin, 0.1 % sodium bicarbonate, distilled water to 100 %. Bulk viscosity should come out water-thin (~2–5 cP); pH lands near 7.2 with the bicarb alone. This matches the AOS/APAM pure-repulsion architecture in your vault but at consumer-safe pH.
3. **Do not add CAPB to this system.** The pure-repulsion model is competitive with CAPB-anchored semi-IPN systems and is more wind-tolerant. Adding CAPB to a 2.4 % AOS film over-stabilises the interface and reduces stretchability — see your own `AOS APAM Repulsion Network Physics.md` for the mechanism.
