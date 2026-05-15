---
title: "World-record bubble recipes — reverse engineering and analysis"
date: 2026-05-15
tags: [research, recipes, world-record, giant-bubbles]
---

# World-record bubble recipes — reverse engineering and analysis

This note collects what is known, what is rumoured, and what can be inferred about the recipes behind the largest free-floating bubbles ever recorded, plus the two academic papers that put numbers behind the craft. It deliberately stays away from beginner Fairy-plus-bicarb formulations and focuses on the pro-grade mixes used by record holders and tested by physicists.

The picture that emerges is unusually consistent: under 3 wt% active surfactant, somewhere between 100 and 500 ppm of a long flexible polymer (PEO, anionic PAM, or food-grade guar) selected for **polydispersity** as much as average molecular weight, 5-10 % glycerol as a humectant, and a near-neutral pH. Everything else — citric acid, bicarb, EDTA, alcohol, preservative — is housekeeping. The convergent design principles section at the bottom pulls these threads together.

---

## 1. Gary Pearlman — Guinness World Record holder (outdoor, 2015)

### The record

On 20 June 2015 (some sources cite 20 July 2015 for the certification — the attempt itself was 20 June) Gary Pearlman blew a single free-floating bubble of **96.27 m³ (3,399.7 ft³)** at Wade Oval Park, Cleveland, Ohio, USA. The volume was measured photogrammetrically by an independent scientist from multi-angle photographs. The apparatus was deliberately low-tech: two fishing poles with a length of cotton string strung between them, dipped into a tray of solution and walked apart while the wind expanded the film ([Guinness World Records — Largest free-floating soap bubble outdoors](https://www.guinnessworldrecords.com/world-records/largest-free-floating-soap-bubble); [Drur Awesome record write-up](https://drurawesome.com/largest-free-floating-soap-bubble-outdoor-2/); [RecordSetter listing](https://recordsetter.com/world-record/free-floating-soap-bubble/39035)).

Pearlman previously held the indoor record as well, certified at 100.18 m³ in Mentor, Ohio ([Guinness — Largest free-floating soap bubble indoors](https://www.guinnessworldrecords.com/world-records/102145-largest-free-floating-soap-bubble-indoors); [Pearlman & Ryndes interview, Cleveland Jewish News](https://www.clevelandjewishnews.com/news/local_news/pearlman-ryndes-seek-five-bubble-blowing-world-records/article_bd87cfde-ed98-11ed-93ad-c3630e4d3582.html)). He is the founder of bubblesmiths.com and the most cited "primary source" for serious US bubble formulators.

### What Pearlman has publicly said about his recipe

Pearlman has never published a numerically exact recipe under his own name. What is in the public record is:

- The solution contains **"water, soap, and polymer additives"** — confirmed by Guinness's own description of the apparatus and methodology ([Guinness Largest free-floating soap bubble outdoors](https://www.guinnessworldrecords.com/world-records/largest-free-floating-soap-bubble)).
- In interviews around the record attempt, Pearlman and other top US bubblers refer to **Dawn Professional (Dawn Pro)** as the preferred dish detergent, plus a mixture of **polyethylene oxide (PEO, also called polyox / polyethylene glycol) and guar gum** for the polymer scaffold ([MIT Technology Review, "The chemistry behind how you make a record-breaking giant soap bubble"](https://www.technologyreview.com/2019/08/24/102697/the-chemistry-behind-how-you-make-a-record-breaking-giant-soap-bubble/)).
- The MIT Technology Review piece, which interviews researchers who studied Pearlman's methods, states: *"the best bubble mixtures contain water, a detergent in the form of dishwashing liquid (Dawn Pro seems to be the favorite), and a mix of polymers, long chain-like molecules that increase the viscosity of the fluid"* ([MIT Tech Review](https://www.technologyreview.com/2019/08/24/102697/the-chemistry-behind-how-you-make-a-record-breaking-giant-soap-bubble/)). The same article notes that **a mix of polymer molecular weights — i.e. polydispersity — outperforms any single monodisperse polymer** at the same total concentration, which Pearlman discovered empirically through aged PEO drums before academia confirmed it.

### Best-guess Pearlman-class recipe (community consensus)

Cross-referencing the Soap Bubble Fanciers community (whose recipes Pearlman has discussed in workshops), the Mike Miller "Gooey Mix" used by adjacent US bubblers, and the Mega Bubble Man recipe — all of which sit within the same family — the community consensus formulation for a Pearlman-class outdoor mix is roughly:

| Component | Amount (per 1 gallon ≈ 3.8 L) | Role |
|---|---|---|
| Distilled or RO water | 3.5 L | base solvent — low Ca²⁺/Mg²⁺ critical |
| Dawn Professional Detergent | 200–250 mL (~5-7 %) | anionic surfactant package (SLES + AEC + amphoteric) |
| J-Lube powder (PEO ~5 MDa in dextrose carrier) | 4–8 g | extensional viscosity scaffold |
| Guar gum (food grade) | 2–3 g | secondary polymer, locks free water |
| Vegetable glycerin | 50–100 mL (~1.5-3 %) | humectant, slows evaporation |
| Baking powder (NaHCO₃ + cream of tartar) | 2–5 g | mild buffer to pH ~7.2-7.6 |

Sources for the family: [Mega Bubble Man formula (Syracuse NY)](https://www.megabubbleman.com/mega-bubble-formula-mobile); [Amazing Bubble Man — Mike Miller's Gooey Mix](https://amazingbubbleman.com/recipes/); [Bubblyheaven recipe page](https://www.bubblyheaven.co.uk/giant-bubble-recipe-that-actually-works/); [BLM "Brian's Lube Mix" Soap Bubble Wiki entry](https://soapbubble.fandom.com/wiki/BLM).

The key Pearlman-specific tweaks reported in interviews are:

1. **Aged J-Lube or aged PEO.** Pearlman publicly attributes part of his record performance to having used a drum of PEO that had been sitting for over a year. This was the empirical observation that catalysed the Frazier/Burton 2020 study (see section 4). Aged PEO has undergone chain scission and contains a broad polydispersity of chain lengths — which is exactly the rheological property that makes the film stretch without rupture ([MIT Tech Review, "The chemistry behind"](https://www.technologyreview.com/2019/08/24/102697/the-chemistry-behind-how-you-make-a-record-breaking-giant-soap-bubble/); [Emory News Center — Physics of Giant Soap Bubbles](https://news.emory.edu/features/2020/01/physics-of-bubbles/index.html)).
2. **Low-mineral water.** Cleveland tap is moderately hard; serious Pearlman-class attempts use distilled or RO water to prevent Ca²⁺ from collapsing the polymer network.
3. **24-48 h hydration before use.** Standard practice across all polymer-loaded mixes.

There is **no published full Pearlman recipe with named brand and exact masses** that this researcher could find, despite extensive searching of bubblesmiths.com mirrors, the Soap Bubble Wiki, the Soap Bubble Fanciers Yahoo Group archives (now Groups.io), and the Cleveland Jewish News interview. Pearlman, like Sam Heath in the UK, deliberately keeps his exact ratios private. What is public is the architecture: Dawn Pro + PEO/J-Lube + a touch of guar + glycerin + bicarb buffer in distilled water.

---

## 2. Sam Heath / Samsam Bubbleman → Bubble Inc / Supapop (UK)

### The man and the records

Sam Heath, performing as "Samsam Bubbleman", traces his bubble obsession to a Glastonbury Festival epiphany in 1990 ([Bubble Inc — Our Story](https://www.bubbleinc.co.uk/pages/about-1)). He spent the next decade collecting bubble equipment and refining solutions, then founded Bubble Inc in 2000 as a Portobello Road market stall in London. He now holds **twelve Guinness World Records**, including the largest free-floating bubble at the time of his first big attempt and the most people inside a bubble ([Blooloop interview with Samsam Bubbleman](https://blooloop.com/uncategorised/in-depth/attractions-industry-happy-bubbling-with-samsam-bubbleman/); [Bubble Inc — Samsam product page](https://www.bubbleinc.co.uk/products/samsam)).

His best-known free-floating-bubble record was set on **5 August 2009 at Finsbury Park, London**, with a bubble of **roughly 20 ft × 5 ft × 5 ft (~500 ft³, ~14 m³)** — measurements vary in press reports, with World Record Academy citing those dimensions ([World Record Academy — Samsam Bubbleman](http://www.worldrecordacademy.com/games/largest_free-floating_soap_bubble-Samsam_Bubbleman_sets_world_record_90306.htm)). A 2015 attempt under the London Eye produced a 23.3 m³ bubble. Both records were superseded by Pearlman's 96.27 m³ in 2015 but remain the largest in Europe.

Heath, like Pearlman, has consistently declined to publish his formula. From the Finsbury Park record press: *"It's all about having the right bubble solution... the recipe is secret"* ([World Record Academy](http://www.worldrecordacademy.com/games/largest_free-floating_soap_bubble-Samsam_Bubbleman_sets_world_record_90306.htm)). The Blooloop interview reinforces this: he has *"spent 21 years perfecting and experimenting"* and adjusts the solution for wind, temperature, and humidity rather than running a single fixed recipe ([Blooloop](https://blooloop.com/uncategorised/in-depth/attractions-industry-happy-bubbling-with-samsam-bubbleman/)).

### Supapop — the commercial concentrate

Heath sells his retail product as **"Supapop"**, a 500 mL concentrate that makes 2 L of working solution at £12.99 ([Bubble Inc Supapop 500 mL](https://www.bubbleinc.co.uk/products/supapop-concentrate-500ml); [Supapop 250 mL](https://www.bubbleinc.co.uk/products/supapop-concentrate-250ml)). The product page lists no ingredients but is marketed as Guinness World Record-breaking, used by the Moscow State Circus, and compatible with all giant-bubble wand types.

Reverse-engineering Supapop from physical observation (water-thin viscosity, pale yellow / straw colour, neutral pH ~7.2 reported by users, no thickening on dilution, no precipitation in hard water) gives the following hypothesis:

### Hypothesised Supapop formula (AOS-40 + low-load anionic PAM)

The combination of features that has to be explained:

1. **Pale yellow to straw colour** — rules out clear nonionic glucoside concentrates and clear SLES paste; consistent with **Sodium C14-16 Olefin Sulfonate** (AOS) at ~40 % active matter, sold commercially as **Stepan Bio-Terge AS-40** ([Stepan Bio-Terge AS-40 datasheet](https://www.stepan.com/content/stepan-dot-com/en/products-markets/product/BIOTERGEAS40.html); [Knowde Bio-Terge AS-40 page](https://www.knowde.com/stores/stepan-company/products/bio-terge-as-40); [Wintersun AOS-40 listing — "straw yellow to amber liquid"](https://www.wintersunchemical.com/products/sodium-alpha-olefin-sulfonate-40-solution-aos-40-cnh2n-so3nan-14-cas_68439-57-6-straw-yellow-to-amber-liquid-2204-6-lb-tote)).
2. **Water-thin** — rules out SLES-70 paste (thick), guar-loaded (very viscous), HEC-loaded (gel-like). Consistent with neat AOS-40 + low-ppm polymer.
3. **pH ~7.2** — the sweet spot between full APAM dissociation (which begins ~pH 6 and is complete by pH 9) and consumer/skin safety. AOS sulfonate is fully ionised across pH 2-12, so 7.2 loses nothing in surfactant performance ([Soap Bubble Wiki — pH Adjusters and Water Conditioners](https://soapbubble.fandom.com/wiki/PH_Adjusters_and_Water_Conditioners) noting most P&G detergent-based bubble juice optimises at pH 7.2-7.8). For the polymer/repulsion physics see your vault note [`AOS APAM Repulsion Network Physics.md`].
4. **No precipitation in UK hard water** — sulfonate surfactants tolerate Ca²⁺/Mg²⁺ better than sulfates; AOS is the standard hard-water choice ([Yeserchem — hardness ranking of common surfactants](https://yeserchem.com/optimizing-detergent-performance-in-the-face-of-water-hardness/)).

Putting it together, the likely Supapop concentrate is roughly:

- **40–60 wt% AOS-40 liquid** (= 16-24 % active AOS), diluted 1:3 with water at point of use → working concentration ~4-6 % active AOS
- **0.1-0.3 wt% anionic polyacrylamide (HPAM, MW 10-20 MDa)** OR equivalent high-MW PEO (4-8 MDa) for extensional viscosity
- **5-10 wt% glycerol or propylene glycol** humectant
- **~0.1 wt% sodium bicarbonate** to land pH at 7.2
- **Sodium benzoate or potassium sorbate** at preservative level (pH-dependent, hence the neutral target)
- Trace EDTA for hard-water tolerance

This matches the "pure repulsion network" architecture described in [`AOS APAM Repulsion Network Physics.md`] — 2.4 % active AOS + 100 ppm anionic PAM at neutral-to-alkaline pH delivers oscillatory disjoining pressure peaks up to 200 Pa, enough to counteract capillary suction in a 14 m³ free-floater.

### How Supapop compares to other UK pro mixes

| UK product | Likely architecture | Sold as | Notes |
|---|---|---|---|
| **Supapop (Bubble Inc / Samsam)** | AOS-40 + low-load HPAM/PEO + glycerol, neutral pH | 500 mL concentrate | Yellow tinge, water-thin, secretive formula ([Bubble Inc product page](https://www.bubbleinc.co.uk/products/supapop-concentrate-500ml)) |
| **Bubblyheaven Giant Bubble Powder Pro** | Synthetic polymer powder; user adds Fairy Liquid + water | Powder kit | Explicitly "synthetic polymer, not food-grade" — likely PEO/PAM blend. Requires Fairy Original Green or Dawn Original specifically ([Bubblyheaven Giant Bubble Powder Pro](https://www.bubblyheaven.co.uk/product/giant-bubble-powder-professional/)) |
| **Dr Zigs Original Giant Bubble Mix** (Wales) | Plant-based concentrate + ready-mix; vegan, biodegradable, phosphate-free, palm-oil-free | 100 mL & 1 L bottles, 5 L concentrate | Ingredient list undisclosed; positioning suggests AOS or coco-glucoside surfactant + guar or HEC polymer ([Dr Zigs giant bubble mix page](https://drzigs.com/products/giant-bubbles-ready-to-go-1-ltr-mix); [Dr Zigs concentrate](https://drzigs.com/products/c5-1l-5-litres)) |
| **Bubblyheaven Original Powder** | Polymer-only powder (J-Lube or HEC), add Fairy + water | Powder | Slightly weaker than Pro; cheaper |
| **Big Bubble Co / generic UK retail** | Variable; usually Fairy-liquid + guar gum + glycerin retail blends | — | Not a single-brand pro product; mostly hobbyist-grade |

The architectural common ground across the UK pro tier is: **low-active-matter sulfonate or sulfate surfactant** + **trace high-MW polymer** + **glycerol humectant** + neutral pH for consumer safety. The differentiator is which polymer family (PEO, HPAM, guar, HEC) and which surfactant family (AOS, SLES, dish-soap blend) is used.

---

## 3. Pasquet et al. 2022 — the optimised academic recipe (EPJ E)

### Bibliographic anchor

Marina Pasquet, Laura Wallon, Pierre-Yves Fusier, Frédéric Restagno, and Emmanuelle Rio, **"An optimized recipe for making giant bubbles"**, *European Physical Journal E* 45, 101 (December 2022). DOI: 10.1140/epje/s10189-022-00255-6. Preprint as [arXiv:2209.04435](https://arxiv.org/abs/2209.04435); published version at [Springer Nature](https://link.springer.com/article/10.1140/epje/s10189-022-00255-6) and [EPJ E direct](https://epje.epj.org/articles/epje/abs/2022/12/10189_2022_Article_255/10189_2022_Article_255.html); PubMed [36547787](https://pubmed.ncbi.nlm.nih.gov/36547787/); also covered in [C&EN, "Better bubbles, massive mammals"](https://cen.acs.org/pharmaceuticals/process-chemistry/Better-bubbles-massive-mammals/100/i35) and the Laboratoire de Physique des Solides press release ([LPS press release](https://www.lps.u-psud.fr/en/what-is-the-best-recipe-to-blow-giant-bubbles/)).

### The experimental approach

Pasquet et al. did something unusual for academic physics: they took an artist's recipe — specifically the kind of mix street performers use — and added one ingredient at a time, measuring at each step the **ease of bubble generation** (probability the film survives wand expansion) and the **bubble lifetime** (time-to-burst at fixed humidity). This let them assign causal roles to each component rather than reasoning in pure-rheology abstractions.

### The headline numbers

From the paper and the subsequent press coverage:

- **Dish soap (artist mix surfactant package): ~4 vol% (40 mL liquid dishwashing soap per 960 mL water)** — the paper explicitly notes that **higher surfactant concentration makes generation worse, not better**, contradicting the intuition that "more soap = stronger film" ([arXiv:2209.04435 abstract](https://arxiv.org/abs/2209.04435); [PubMed](https://pubmed.ncbi.nlm.nih.gov/36547787/)).
- **Polymer: long flexible water-soluble polymer at 0.15-0.30 wt%** (i.e. 1500-3000 ppm), specifically guar gum or J-Lube (J-Lube being a PEO + dextrose carrier veterinary lubricant that contains roughly 25 % PEO by mass, so effective PEO content lands at ~375-750 ppm) ([Springer Nature abstract](https://link.springer.com/article/10.1140/epje/s10189-022-00255-6)).
- **Glycerol: 10 vol%** — chosen because below 10% there is insufficient retardation of evaporation; above 10% the bulk viscosity starts to slow film generation. At 10% they measured a **factor of 140 increase in bubble lifetime** at fixed humidity vs the no-glycerol control, with no measurable cost to the ease of generation ([LPS press release](https://www.lps.u-psud.fr/en/what-is-the-best-recipe-to-blow-giant-bubbles/)).

### Design rationale per ingredient

The paper's three-leg argument:

1. **Surfactant.** Provides the Marangoni elasticity — i.e. the restoring force that resists local thinning by drawing surfactant-rich fluid into thinned spots. But once the interface is saturated (i.e. at or above CMC), adding more surfactant brings two bads: (a) higher CMC-shifted bulk viscosity and (b) increased likelihood of micelle-mediated thinning. Hence "not too high" is a real physical constraint, not just frugality.
2. **Polymer.** Provides the extensional (elongational) viscosity that resists thinning specifically under stretch. At 1500-3000 ppm of a long flexible polymer (guar or J-Lube), the film survives the rapid expansion phase of wand opening without rupturing. Below ~500 ppm there is not enough chain entanglement; above ~5000 ppm the bulk viscosity drags too much fluid into the trailing edge of the wand, causing gravity-driven drainage failure.
3. **Glycerol.** Hygroscopic humectant that reduces water activity at the film-air interface, slowing the rate of evaporation and therefore the rate of film thinning. Pasquet's 140× lifetime gain at 10 % glycerol is the strongest single-ingredient effect they report.

### Polydispersity

The paper's polydispersity story is more nuanced than Frazier/Burton's. Pasquet et al. work with guar gum and J-Lube (both naturally polydisperse by virtue of their source — guar from plant extraction has a distribution of chain lengths, J-Lube is a commercial PEO grade with industrial polydispersity index ~2-3). They do not run a controlled polydispersity sweep at constant average MW. What they conclude is **architecturally** equivalent to Frazier/Burton's: long flexible chains at modest concentration are what matters, and the natural polydispersity of food and veterinary-grade polymers is *good enough* — the lab-grade monodisperse PEO standards used in physics experiments are actually *worse* for bubble-making at matched concentration.

### The final efficient recipe (Pasquet)

From the paper's recommendation, scaled to 1 L of final solution:

| Component | Amount | Working concentration |
|---|---|---|
| Distilled water | 860 mL | ~86 % |
| Dish soap (anionic surfactant package, e.g. Fairy or French equivalent) | 40 mL | ~4 % vol |
| Glycerol | 100 mL | ~10 % vol |
| Guar gum OR J-Lube | 1.5-3 g | 0.15-0.30 wt % |

Total surfactant active matter is on the order of 0.5-1 % (since dish soap is typically 10-25 % active); polymer is ~2000 ppm of guar (= ~500 ppm PEO equivalent if using J-Lube); humectant 10 %. **Bulk viscosity is barely above water — the high performance comes from the extensional rheology of the polymer chains under stretch, not from a thickened solution.**

---

## 4. Frazier, Jiang & Burton 2020 — Emory Phys Rev Fluids paper

### Bibliographic anchor

Stephen Frazier, Xinyi Jiang, and Justin C. Burton, **"How to make a giant bubble"**, *Physical Review Fluids* 5, 013304 (30 January 2020). DOI: 10.1103/PhysRevFluids.5.013304. Preprint as [arXiv:1908.00537](https://arxiv.org/abs/1908.00537); published version at [APS Phys Rev Fluids](https://journals.aps.org/prfluids/abstract/10.1103/PhysRevFluids.5.013304); covered in [Emory News Center](https://news.emory.edu/features/2020/01/physics-of-bubbles/index.html), [Phys.org](https://phys.org/news/2020-01-physics-giant-secret-fluid-mechanics.html), [Science Daily](https://www.sciencedaily.com/releases/2020/01/200130130958.htm), [Futurity](https://www.futurity.org/giant-bubbles-physics-2270532/), [EurekAlert](https://www.eurekalert.org/news-releases/865302), and [SciTechDaily](https://scitechdaily.com/fluid-mechanics-discovery-inspired-by-street-performers-making-gigantic-soap-bubbles/).

### The origin story

Justin Burton's group at Emory was studying soap-film thinning when Burton encountered street performers in Barcelona blowing bubbles "the diameter of a hula hoop and as much as a car-length long" ([SciTechDaily — Fluid Mechanics Discovery](https://scitechdaily.com/fluid-mechanics-discovery-inspired-by-street-performers-making-gigantic-soap-bubbles/)). He took the question to the lab and ran a methodical scan of surfactant systems, polymers (varying MW from 100 kDa to 8 MDa for PEO; also guar at varying concentrations), and additives.

### The polydispersity discovery — the headline finding

This is the most important contribution of the paper from a recipe-design standpoint. Burton's lab ran PEO at six monodisperse molecular weights — **0.1, 0.6, 1.0, 2.0, 4.0, and 8.0 MDa** (MilliporeSigma stock). At any single MW they could find a concentration that produced acceptable bubbles, but the optimum was always near the upper end of the MW range and required notable concentration tuning.

Then they observed something accidentally: **PEO from a container that had aged ~6 months produced visibly stronger films than fresh PEO at the same nominal MW and concentration** ([Emory News Center](https://news.emory.edu/features/2020/01/physics-of-bubbles/index.html); [Futurity](https://www.futurity.org/giant-bubbles-physics-2270532/)). Investigation showed the aged PEO had undergone chain scission and now contained a distribution of molecular weights — i.e. it had become polydisperse. Burton's conclusion, as quoted across the press coverage: *"polymers of different sizes become even more entangled than single-sized polymers, strengthening the elasticity of the film"* ([Emory News](https://news.emory.edu/features/2020/01/physics-of-bubbles/index.html)).

The mechanistic picture: long chains provide the load-bearing extensional network; shorter chains slot into the gaps and bridge between long chains, increasing the effective entanglement density at the same total mass. A polydisperse mixture therefore reaches higher extensional viscosity at lower total polymer mass than a monodisperse one — exactly the trade-off you want for a thin, drag-free film that resists tearing.

This finding **explains why Pearlman's aged J-Lube performed better than fresh** (J-Lube's PEO undergoes chain scission in storage, especially in the presence of dextrose and trace moisture) and **predicts that Sam Heath's solution-adjustment ritual (mixing fresh batches and letting them age days to weeks before use) is rheologically meaningful, not just superstition.**

### Marangoni elasticity vs extensional viscosity — the rheological conclusion

This is the second important contribution. The paper sets up the question: which rheological property — Marangoni (interfacial) elasticity, or extensional (bulk) viscosity — actually limits how big a bubble can get?

The Frazier/Burton answer is unambiguously **extensional viscosity dominates the failure mode of giant bubbles**. The Marangoni elasticity sets the *static* stability against perturbations and is responsible for soap films lasting at all (without surfactant the film thins by capillary suction in milliseconds). But during the rapid expansion of a wand opening, the dominant stress on the film is *extensional* — biaxial stretching as area grows by orders of magnitude in seconds — and the dominant rheological response is the chain-stretching of long flexible polymers. Adding polymer to a dish-soap solution increased measured film thicknesses by an order of magnitude and increased bubble area at failure by a similar factor, while Marangoni-elasticity proxies (CMC-shifted surface tension, dynamic surface tension at saturated interface) changed only marginally between successful and unsuccessful mixes ([arXiv:1908.00537](https://arxiv.org/abs/1908.00537); [Phys Rev Fluids](https://journals.aps.org/prfluids/abstract/10.1103/PhysRevFluids.5.013304)).

The practical implication: **a "perfectly Marangoni-active" surfactant package without the polymer scaffold will fail to make a giant bubble.** Conversely, a modest dish-soap package with the right polymer addition can make a record-class bubble. This reframes the recipe-design problem: don't chase the most exotic surfactant blend, chase the right polydisperse polymer at the right concentration.

### The Burton recommended recipe (Emory, January 2020)

From the press coverage (Emory News, SciTechDaily, EurekAlert all quote the same):

| Component | Amount (1 L batch) | Note |
|---|---|---|
| Water | 1000 mL | distilled preferred |
| **Dawn Professional dish detergent** | 50 mL | ~5 vol% — explicitly Dawn Pro, not consumer Dawn |
| Guar gum powder | 2-3 g | 0.2-0.3 wt% |
| 70 % isopropyl rubbing alcohol | 50 mL | used to slurry the guar (prevents clumping) |
| Baking powder (not soda) | 2 g | mild buffer to neutral pH |

Source: [Emory News Center](https://news.emory.edu/features/2020/01/physics-of-bubbles/index.html), [SciTechDaily](https://scitechdaily.com/fluid-mechanics-discovery-inspired-by-street-performers-making-gigantic-soap-bubbles/), [Science Daily](https://www.sciencedaily.com/releases/2020/01/200130130958.htm).

### What the Burton recipe leaves on the table

Two notable absences vs Pasquet:

- **No glycerol.** Burton's recipe relies on the polymer + surfactant for survival; Pasquet's 10 % glycerol gives a 140× lifetime improvement that Burton does not capture. The two recipes are complementary: Burton optimises "ease of generation and how big you can get it before pop"; Pasquet adds "how long it lasts in air after release".
- **Guar over PEO in the final recipe** despite the paper's central polydispersity argument being framed around PEO. The reasoning is practical: guar is naturally polydisperse, cheap, food-grade, and stable; PEO requires either aged stock or a custom polydisperse blend. The science says either works as long as polydispersity is high.

The Burton paper also explicitly recommends **Dawn Pro over generic SDS** as the surfactant: *"Dawn Pro dish detergent dramatically increases the stability of the film compared to pure SDS"* ([summarised from press coverage of the paper](https://news.emory.edu/features/2020/01/physics-of-bubbles/index.html)). The reason is that Dawn Pro contains an SLES + alkyl ether carboxylate + CAPB + amine oxide blend, which gives a more cohesive interfacial layer than the simple SDS monolayer used in academic controls. This is consistent with Pasquet's "use an artist's recipe as the starting point" framing.

---

## Comparative recipe table

All values are per 1 L of working solution unless noted. "—" means the recipe does not specify or is undisclosed.

| Component | Pearlman class (community consensus, US) | Sam Heath / Supapop (hypothesised, UK) | Pasquet et al. 2022 (French academic) | Frazier/Burton 2020 (US academic) |
|---|---|---|---|---|
| **Water** | ~870 mL distilled | ~750 mL (post-dilution from concentrate) | 860 mL distilled | 900 mL distilled |
| **Surfactant** | 50-65 mL Dawn Professional (5-7 %) | 4-6 % active AOS (= ~15 % of AOS-40 liquid) | 40 mL dish soap (4 vol %) | 50 mL Dawn Professional (5 vol %) |
| **Polymer 1** | 1-2 g J-Lube (= ~250-500 ppm PEO) | ~100-300 ppm HPAM or PEO 4-8 MDa | 1.5-3 g guar OR J-Lube (1500-3000 ppm) | 2-3 g guar (2000-3000 ppm) |
| **Polymer 2** | 0.5-1 g guar | — | — | — |
| **Humectant** | 15-25 mL glycerin (1.5-2.5 %) | 5-10 % glycerol (likely) | 100 mL glycerol (10 vol %) | none |
| **pH buffer** | 0.5-1 g baking powder | ~0.1 % NaHCO₃ → pH 7.2 | not specified (artist-recipe default ~7-8) | 2 g baking powder |
| **Other** | — | preservative (sodium benzoate?), EDTA | — | 50 mL 70 % IPA (slurry guar) |
| **Single-line takeaway** | Dawn Pro + J-Lube + guar + glycerin + bicarb in distilled water — the de facto US giant-bubble template | AOS-40 + low-load HPAM + glycerol + neutral buffer — sulfonate-based, water-thin, hard-water tolerant, deliberately neutral pH for consumer safety | "Surfactant low, polymer moderate, glycerol 10 %" — the optimisation paper says glycerol is the under-appreciated lifetime multiplier (140×) | "Polydispersity beats molecular weight" — aged PEO entanglement is the rheology lever; extensional viscosity dominates Marangoni for giant bubbles |

---

## Convergent design principles

Pulling out what every record-class recipe and academic study agrees on:

1. **Total surfactant active matter sits between 0.5 and 3 wt%.** Above this, the film generates poorly (Pasquet's central finding); below this, the interface is not saturated and Marangoni restoration is too weak. Pearlman, Supapop, Pasquet, and Burton all land in this window. The MIT Tech Review summary of Burton's work calls this *"intermediate concentrations"* explicitly ([MIT Tech Review](https://www.technologyreview.com/2019/08/24/102697/the-chemistry-behind-how-you-make-a-record-breaking-giant-soap-bubble/)).

2. **Polymer at low ppm, selected for polydispersity not just average MW.** Every recipe uses one of: PEO (typically 4-8 MDa, polydispersity index ≥ 2 from natural ageing or industrial sourcing), anionic PAM (10-20 MDa), guar gum (naturally polydisperse), J-Lube (PEO/dextrose, polydisperses on storage), or a combination. The total polymer mass lands between 100 and 3000 ppm. The Frazier/Burton 2020 finding makes this explicit: **"polymers of different sizes become even more entangled than single-sized polymers"** ([Emory News](https://news.emory.edu/features/2020/01/physics-of-bubbles/index.html)). Pasquet et al. arrive at the same place by using food/vet-grade polymers that are polydisperse by source.

3. **Neutral to slightly alkaline pH (7.0-8.0).** This balances:
   - Anionic polymer dissociation (carboxylates fully ionised by pH 7-9 — see [PMC 4978783](https://pmc.ncbi.nlm.nih.gov/articles/PMC4978783/)) for full chain extension and oscillatory disjoining pressure
   - Consumer/skin safety (regulators push toward pH 5.5-8 for kid-safe products)
   - Preservative window (benzoate/sorbate active below pH 7.5)
   - Surfactant stability (sulfonates indifferent; sulfates degrade below pH 5)
   The Soap Bubble Wiki notes most Procter & Gamble detergent-based mixes optimise at pH 7.2-7.8 ([Soap Bubble Wiki — pH](https://soapbubble.fandom.com/wiki/PH_Adjusters_and_Water_Conditioners)). Supapop is reported at pH 7.2 by users; Pearlman-class mixes buffered with baking powder land at 7.4-7.6; Pasquet does not specify but the artist recipes they base on sit in this range.

4. **A humectant (glycerol or glycerin) at 5-10 % to slow evaporation.** Pasquet quantifies this explicitly as a 140× lifetime improvement; Pearlman uses 1.5-3 %; Supapop almost certainly uses 5-10 %; only Frazier/Burton omit it (because they optimise for generation, not lifetime). The mechanism is hygroscopic reduction of water activity at the film-air interface, slowing the rate-limiting evaporation step that drives the film toward critical rupture thickness.

5. **Distilled or low-mineral water.** Ca²⁺ and Mg²⁺ in tap water collapse polyelectrolyte chains (PAM, guar carboxymethylates), screen surfactant headgroup repulsion, and cause precipitation with sulfate surfactants. Every record-class US recipe uses distilled or RO water; UK mixes that use neat AOS tolerate hard water better but still benefit from low-mineral water. The [Soap Bubble Wiki Water page](https://soapbubble.fandom.com/wiki/Water) makes this universal.

6. **Extensional viscosity is the dominant failure-mode rheology, not shear viscosity or Marangoni elasticity alone.** This is Burton's punchline and Pasquet's implicit framing. Practical consequence: a water-thin solution can still hold a 100 m² film if the polymer chains stretch correctly under biaxial extension. Loading more shear-viscosity (more guar, more glycerin, more HEC) past the optimum *hurts* performance because it drags fluid into the trailing edge of the wand and accelerates gravitational drainage. Pearlman, Supapop, Pasquet, and Burton all converge on solutions that are between 1-5 cP shear viscosity — barely above water.

7. **Architectural minimalism beats exotic ingredient stacking.** Pearlman's mix is five ingredients. Supapop is plausibly six. Pasquet is four. Burton is five. None of the record-class recipes uses CAPB, lauramine oxide, lactic acid, phosphate buffers, or complex semi-IPN coacervate locks. The vault's own [`Master Recipe for Colossal Bubble Physics.md`] proposes such a "Sovereign IPN" architecture; the empirical record-holder data does not support it. Stick to: surfactant + polymer + humectant + buffer + water.

8. **Aging the solution for 24 h to several days is universally recommended.** Pearlman, Sam Heath, Bubblyheaven, and Mike Miller all describe a hydration / aging step. The mechanism is at least three-fold: full hydration of polymer chains (especially guar and HEC, which need overnight to swell), partial chain scission of stored polymer (which improves polydispersity per Burton 2020), and equilibration of micelle structure in the surfactant phase. The 24-hour rest is not folklore — it is doing measurable rheological work.

The unifying picture: a giant bubble is a chemically thin film that survives by virtue of polymer chain entanglement, not by virtue of surface chemistry alone. Get the polymer architecture right — long, flexible, polydisperse, at modest concentration — and almost any half-decent anionic surfactant will get you to record class. Get the polymer wrong and no surfactant package will save you.

Cross-references in vault: [`AOS APAM Repulsion Network Physics.md`] (pure-repulsion mechanism), [`Polymer Degradation Dynamics in Giant Bubble Formulations.md`] (J-Lube and PEO ageing), [`Giant Soap Film Formulation Science.md`] (general rheology framing), [`Research SLES vs AOS Pro Mix Analysis.md`] (Supapop reverse-engineering done in more detail).
