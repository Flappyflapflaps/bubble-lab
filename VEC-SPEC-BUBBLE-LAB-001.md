# VEC-SPEC-BUBBLE-LAB-001

**Project:** Bubble Formulation Lab
**Owner:** Nick Leisk
**Status:** Draft v1.0
**Date:** 2026-05-08

---

## 1. Purpose

A two-mode application for systematic bubble juice formulation development. Replaces ad-hoc spreadsheets and notebook scribbles with structured recipe management, automated concentrate calculations, ordered mixing checklists, and live field-adjustment tracking with full observation logging.

Primary user: solo operator (Nick) running iterative formulation experiments. Optimized for mobile-first field use with desktop-friendly lab use.

---

## 2. Problem statement

Current workflow pain points:

- Manual recalculation of polymer concentrate volumes for every batch (e.g., "1.8 g/500 mL stock → how much for 0.18 g/L target?")
- Mixing order is critical (slurry polymers first, surfactants last, etc.) but easy to forget under time pressure
- Field adjustments ("added 7 g CAPB at 14:30, then 5 g more at 14:45, then bubbles improved") are lost without structured logging
- Comparing what worked vs what didn't across batches relies on memory
- No persistent library of "this recipe + these conditions = this result"

The cost of these problems is wasted batches, untestable hypotheses, and slow iteration.

---

## 3. Scope

### In scope (v1)

- Stock management for polymer concentrates and dry ingredients
- Recipe library with target-driven formulation (set ppm, get mass)
- Auto-generated ordered mixing checklists
- Lab batch logging with mixing notes
- Field mode with live ingredient adjustment and observation logging
- Real-time ratio and active-matter recalculation
- Local persistence across sessions
- Mobile-first responsive UI with offline capability after first load

### Out of scope (v1)

- Multi-user / sharing
- Cloud sync (browser local storage only)
- Photo capture or image analysis
- Charts / analytics dashboards
- Weather/wind API integration
- Predictive recipe generation
- Print/export to PDF
- Stock depletion tracking with reorder warnings

### Deferred to v2 if v1 proves itself

- Recipe comparison view (side-by-side)
- Test plan mode (suggests next variable to change)
- Shared recipe library for Stuart/Chris/David
- Stock depletion tracking
- Export functionality

---

## 4. Architecture

### 4.1 Stack

- **Frontend:** Single HTML file. Vanilla JS or lightweight framework (React via CDN acceptable). No build step required.
- **Persistence:** Browser localStorage (or IndexedDB if dataset grows beyond ~5 MB).
- **Hosting:** Static file. Can run locally, served from any web host, or installed as PWA.
- **Offline:** Must function fully offline after first load. No external API calls during normal use.

### 4.2 Mobile-first

- Primary target: iPhone Safari, Android Chrome
- Touch-friendly tap targets (min 44 px)
- Bottom navigation for thumb reachability
- Numeric inputs use `inputmode="decimal"` for proper keyboard
- Critical actions (Add ingredient, Log observation) accessible within one tap from active batch screen

### 4.3 Data model

```
Stocks {
  id: uuid
  ingredient_type: "polymer_concentrate" | "dry_ingredient" | "liquid_ingredient"
  name: string  // "PEO WSR-301 concentrate", "AOS-40", "CAPB-35%"
  concentration: { value: number, unit: "g_per_mL" | "percent_active" | "pure" }
  date_made: ISO date  // for polymer concentrates
  notes: string
  ppm_factor: number  // optional: for active-matter calculations (e.g., AOS-40 = 0.40)
}

Recipe {
  id: uuid
  name: string
  date_created: ISO date
  target_volume_mL: number
  target_pH: number
  ingredients: [
    {
      stock_id: uuid (references Stocks)
      target_type: "ppm" | "mass_g" | "volume_mL" | "percent_active"
      target_value: number
      mixing_step: number  // determines order
    }
  ]
  protocol_notes: string  // freeform mixing notes
  tags: [string]  // "AOS lean", "high PEO", "lock attempt"
  parent_recipe_id: uuid | null  // for clones
}

Batch {
  id: uuid
  recipe_id: uuid
  date_started: ISO datetime
  date_completed: ISO datetime | null
  actual_masses: { stock_id: actual_grams }  // in case of deviation
  conditions: { weather: string, wind_kmh: number, humidity_pct: number, temp_c: number }
  lab_notes: string
  status: "mixing" | "aging" | "ready" | "tested" | "discarded"
}

FieldTest {
  id: uuid
  batch_id: uuid
  date: ISO datetime
  conditions: { wind_kmh: number, weather: string, location: string }
  adjustments: [
    {
      timestamp: ISO datetime
      stock_id: uuid
      mass_added_g: number
      note: string
    }
  ]
  observations: [
    {
      timestamp: ISO datetime
      type: "preset" | "freeform"
      preset_label: string | null  // e.g., "Brown from start"
      freeform_text: string | null
      linked_adjustment_id: uuid | null  // optional: ties observation to last addition
    }
  ]
  pH_readings: [{ timestamp: ISO datetime, value: number }]
  saved_as_variant_recipe_id: uuid | null  // if user clicked "Save variant"
}
```

### 4.4 Calculation engine

Core formulas, exposed as pure functions:

```js
// Calculate polymer concentrate volume needed
concentrate_volume_mL(target_ppm, target_volume_mL, stock_g_per_mL) {
  const target_mass_g = (target_ppm / 1000) * target_volume_mL;
  return target_mass_g / stock_g_per_mL;
}

// Calculate active mass from surfactant paste
active_mass_g(paste_mass_g, active_pct) {
  return paste_mass_g * (active_pct / 100);
}

// Recipe ratios (for displayed metrics)
calculate_ratios(recipe) {
  // returns:
  // - total_active_pct
  // - anionic:amphoteric:nonionic ratio
  // - PEO:PAM ratio
  // - polymer total ppm
}

// Live ratio recalc for field mode
recalc_with_addition(current_state, addition) {
  // returns updated ratios after adding mass to current batch
}
```

These must be **unit-tested** before UI is built. Bench math errors will destroy trust in the app.

---

## 5. Functional requirements

### 5.1 Stocks management

**FR-S1.** User can create, edit, and delete stocks.

**FR-S2.** Polymer concentrate stocks track:
- Stock name (e.g., "PEO WSR-301 concentrate")
- Concentration (g per mL, e.g., 0.0036 g/mL = 1.8 g in 500 mL)
- Date made
- Optional notes (e.g., "made from severely aged PEO batch")

**FR-S3.** Dry/liquid ingredient stocks track:
- Name (e.g., "AOS-40", "CAPB-35%", "Glycerin")
- Active percentage if applicable (e.g., AOS-40 = 40%)
- Notes

**FR-S4.** Polymer concentrates older than 14 days display a soft warning indicator (yellow). Older than 30 days display a stronger warning (orange). User configurable thresholds in settings.

**FR-S5.** Default stocks pre-populated on first launch:
- PEO WSR-301 concentrate (placeholder, user enters their stock)
- Anionic PAM HMW concentrate (placeholder)
- AOS-40 (40% active)
- SLES (70% active)
- CAPB-35% (35% active)
- LDAO-30% (30% active)
- Vegetable glycerin (100%)
- IPA 99%
- Sorbic acid (pure)
- Dipotassium phosphate (pure)
- EDTA tetrasodium (pure)
- Lactic acid (80% typical, configurable)
- Distilled water (pure)

### 5.2 Recipe library

**FR-R1.** User can create, edit, clone, and delete recipes.

**FR-R2.** Recipe creation flow:
- Set target volume (default 1000 mL)
- Set target pH (default 7.0)
- Add ingredients one at a time:
  - Pick from stocks
  - Choose target type: ppm (polymers), mass (surfactants), volume (water), percent active (alternative for surfactants)
  - Enter target value
  - Set mixing step number (or accept default ordering)
- Add tags
- Add protocol notes

**FR-R3.** When viewing a recipe, user sees:
- All ingredients with calculated final masses for the target volume
- Live readout of total active %, anionic:amphoteric:nonionic ratio, PEO:PAM ratio, polymer total ppm
- Warning flags if outside known-working ranges:
  - PAM > 50 ppm: "Gel-block risk above 50 ppm"
  - AOS:CAPB active ratio > 6:1: "Lean amphoteric — may underperform"
  - AOS:CAPB active ratio < 2:1: "Heavy amphoteric — past optimum"
  - PEO:PAM ratio < 4:1: "Below community comfort zone (Doc 4)"
  - Total active > 5%: "Over-surfacted risk — film may form thin"
  - pH < 5.5 with SLES present: "SLES hydrolysis risk below pH 5"

**FR-R4.** "Clone recipe" creates a duplicate with a prompt for "what changed in this variant" stored as a tag/note.

**FR-R5.** Recipes can be filtered/searched by name or tag.

**FR-R6.** Pre-populated example recipes on first launch (so user has working examples to clone):
- "Bench-validated SLES baseline" (your proven Recipe A: 35 g SLES-70%, 14 g CAPB-35%, 5 g LDAO-30%, 100 ppm PEO, 12.5 ppm PAM, glycerin 100 g, pH 7.0)
- "AOS exploration baseline" (Recipe B from spec: 36 g AOS-40, 7 g CAPB-35%, 6 g LDAO-30%, 180 ppm PEO, 50 ppm PAM, pH 7.2)

### 5.3 Mixing checklist (Lab mode)

**FR-M1.** From a recipe, user can "Start a batch" which creates a Batch record and opens the mixing checklist.

**FR-M2.** Checklist auto-generates from recipe ingredients in the correct order:
1. Slurry polymers (PEO, PAM, HEC) into IPA + glycerin
2. Dissolve sorbic acid into slurry
3. Hydrate with distilled water (specifies volume)
4. Dissolve buffer (DPP, EDTA) in warm water separately, add
5. Add surfactants in order: primary anionic (AOS/SLES), then CAPB, then LDAO
6. pH check + adjust
7. Age (specifies time, default 48 h)

**FR-M3.** Each step shows:
- The specific masses for this batch (auto-calculated)
- A checkbox to mark complete
- Per-step notes field (optional)
- Timer button if step has a timing requirement (10 min stir, 1 hr rest, 24 hr age)

**FR-M4.** Timer functions:
- 10-min mix steps: simple countdown with audible/visual alert
- Long rest periods (1 hr+): notification-style timestamp captured, no countdown needed (user comes back later)
- Age periods (24-48 hr): mark batch as "aging" with completion date, list shows time remaining

**FR-M5.** "Complete batch" action records actual masses (defaults to recipe values, editable if user deviated), captures conditions, and saves the lab notes.

**FR-M6.** Conditions captured: weather (text), temperature (°C), humidity (%) — all optional, manual entry.

### 5.4 Field mode

**FR-F1.** User selects a batch (must be in "ready" or "tested" status) to take into the field.

**FR-F2.** Field test screen displays:
- Recipe name and base composition (collapsible)
- "Current state" — base recipe + any adjustments made today
- Live ratio readout (anionic:amphoteric:nonionic, total active %, polymer ppm)
- Deviation indicator (visual: how far drifted from base)
- Two primary action buttons: **Add Ingredient** and **Log Observation**

**FR-F3.** Add Ingredient flow:
- Pick from stocks (recent/likely-relevant ones surfaced first)
- Enter mass in grams (numeric pad)
- Optional note
- Auto-timestamps
- Updates live state

**FR-F4.** Log Observation flow:
- Quick-tap presets in a grid:
  - "Brown from start" (over-surfacted indicator)
  - "Spectral colors" (working zone)
  - "Popped on extension" (under-PEO indicator)
  - "Shredded under wind" (over-rigidified PAM)
  - "Heavy belly" (loading/wand issue)
  - "Drained fast" (under-PAM/scaffold)
  - "Wand wouldn't open" (over-thick or ionic-lock failure)
  - "Huge bubbles" (positive)
  - "Long lifetime" (positive)
- Free-text option below presets
- Optional checkbox: "tie this observation to last adjustment"
- Auto-timestamps

**FR-F5.** pH log:
- Manual entry, timestamped
- Display recent pH readings as a list

**FR-F6.** Adjustment + observation history shown as a chronological feed at the bottom of the screen, easily scrollable.

**FR-F7.** "Save variant" action:
- Creates a new recipe based on current state (base + all adjustments)
- Prompts for name and "what made this variant interesting" note
- Auto-tags with parent recipe

**FR-F8.** Field test can be paused and resumed (state persists).

### 5.5 Settings

**FR-SET-1.** Polymer concentrate aging thresholds (default: warn at 14 days, strong warn at 30 days).

**FR-SET-2.** Default target volume (default 1000 mL).

**FR-SET-3.** Default target pH (default 7.0).

**FR-SET-4.** Data export — JSON dump of all stocks, recipes, batches, field tests for backup. (Import: deferred to v2.)

**FR-SET-5.** Reset all data — with strong confirmation.

---

## 6. Non-functional requirements

**NFR-1. Performance.** App must load and be interactive within 2 seconds on mobile 4G. State changes (add ingredient, log observation) must complete within 100 ms.

**NFR-2. Offline.** Once loaded, app must function fully without network. All data persists locally.

**NFR-3. Reliability.** No data loss on crash or browser close — every state change writes to localStorage immediately.

**NFR-4. Touch ergonomics.** All interactive elements ≥ 44 px tap target. Numeric inputs surface decimal keyboard. Primary actions reachable with thumb on phone.

**NFR-5. Visual hierarchy.** Field mode prioritizes adjustment + observation actions. Lab mode prioritizes mixing checklist clarity. Settings and library secondary.

**NFR-6. Data portability.** JSON export available for backup. Schema versioned for future migration support.

---

## 7. UI / UX specification

### 7.1 Navigation

**Top-level tabs:** Lab / Field

**Lab tab sub-navigation (bottom):**
- Recipes (default)
- Stocks
- Batches (history)
- Settings

**Field tab sub-navigation (bottom):**
- Active Test (default — shows current field test if one in progress)
- Pick Batch (start new field test)
- History (past field tests)

### 7.2 Lab mode — key screens

**Recipes screen.** List of saved recipes. Tap to open. Floating "+" button to create new. Search/filter bar at top.

**Recipe detail screen.** Recipe name, target volume + pH, ingredient list with calculated masses, ratios + warnings panel, "Start Batch" button (primary), Edit / Clone / Delete actions in menu.

**Mixing checklist screen.** Step-by-step checkboxes with masses inline. Step-specific notes expandable. Timers integrated. Bottom: "Complete Batch" button (primary, only enabled when all steps checked).

**Stocks screen.** Two sections: Polymer Concentrates (with age indicators), Dry/Liquid Ingredients. Tap to edit. "+" button to add new.

**Batches screen.** List sorted by date, status filter (mixing/aging/ready/tested/discarded), tap to view details and notes.

### 7.3 Field mode — key screens

**Active Test screen** (the screen Nick will use most):

```
┌──────────────────────────────────┐
│ Recipe: AOS Exploration v3       │
│ Started: 14:12                    │
│ ─────────────────────────────    │
│ CURRENT STATE                     │
│ AOS-40: 36g (base) +5g (14:32)   │
│ CAPB-35%: 7g (base) +7g (14:28)  │
│ Active total: 3.2%                │
│ Anionic:Ampho:Nonionic 5.4:2:0.74│
│ pH last reading: 7.0 (14:30)      │
│ ─────────────────────────────    │
│ [  + ADD INGREDIENT  ]            │
│ [  📝 LOG OBSERVATION  ]          │
│ [  📊 LOG pH  ]                   │
│ ─────────────────────────────    │
│ TIMELINE                          │
│ 14:35 OBS: Spectral colors ✓     │
│ 14:32 +5g AOS-40                  │
│ 14:30 pH: 7.0                     │
│ 14:28 +7g CAPB-35%                │
│ 14:25 OBS: Brown from start       │
│ 14:12 Test started                │
│ ─────────────────────────────    │
│ [  💾 SAVE AS VARIANT  ]          │
│ [  END TEST  ]                    │
└──────────────────────────────────┘
```

**Add Ingredient sheet** (slides up from bottom):
- Search/select stock
- Mass input (large numeric)
- Optional note
- Confirm button

**Log Observation sheet** (slides up from bottom):
- 3x3 grid of preset observation chips (color-coded: red = problem, green = positive, gray = neutral)
- Free-text input below
- "Tie to last adjustment" toggle
- Confirm button

### 7.4 Visual style

- Clean, high-contrast, minimal chrome
- Bench-functional aesthetic — not "polished consumer app"
- Color coding for warnings: yellow (soft warn), orange (strong warn), red (problem observation)
- Color coding for positive: green (good observation, in-spec ratios)
- Sans-serif system fonts for legibility on phone
- Dark mode optional — useful for outdoor use in bright light, paradoxically

---

## 8. Acceptance criteria

The app is considered v1-complete when:

1. User can create polymer concentrate stocks, including the user's actual current stocks (PEO 1.8 g/500 mL, PAM 0.25 g/500 mL).
2. User can create a recipe with target ppm for polymers, and the app calculates correct concentrate volumes.
3. User can start a batch from a recipe and follow the auto-generated mixing checklist with correct ordering and timing.
4. User can launch field mode from a completed batch, add ingredients with timestamped logging, log observations from presets and freeform, and see live ratio recalculation.
5. User can save a field test variant as a new recipe.
6. All data persists across browser close/reopen.
7. App is fully usable on iPhone Safari with one-handed thumb operation.
8. JSON export produces valid backup file.

---

## 9. Implementation notes for Claude Code

### 9.1 Suggested approach

- Build the calculation engine first as pure functions with unit tests.
- Build the data layer (localStorage CRUD) next, with schema validation.
- Build the Lab mode screens (Stocks → Recipes → Mixing checklist) before Field mode.
- Field mode is highest-value-per-line-of-code — invest in good UX here.
- Pre-populate example recipes and stocks on first launch so the user can immediately see the app working.

### 9.2 Tech recommendations

- React via CDN (no build step) or vanilla JS — Nick's preference. React likely faster to develop with given the state management needs.
- TailwindCSS via CDN for styling.
- No router — single-page with view state in component state.
- Use `crypto.randomUUID()` for IDs.
- Use `Date.now()` and `new Date().toISOString()` for timestamps.

### 9.3 Pitfalls to avoid

- Don't lose state on accidental refresh — write to localStorage on every change.
- Don't make the Field mode require many taps to log an observation. The whole point is rapid capture.
- Don't auto-submit forms — Nick should always confirm an addition or observation, in case of mis-tap.
- Don't show calculated values to absurd precision (e.g., "0.18000003 g") — round sensibly (3 sig figs for masses, 1 decimal for percentages and ratios).
- Don't crash if stocks are missing for a recipe — show a clear error and prompt to add the stock.

### 9.4 Testing recommendations

- Unit test the calculation engine extensively. The math is the single biggest trust factor.
- Manual test the field flow on actual phone, not desktop browser. Touch behavior differs.
- Test offline mode by toggling airplane mode after first load.
- Test with realistic data volume (50+ recipes, 200+ batches) for performance regression.

---

## 10. Open questions

- **Q1.** Should the app store ingredient cost per gram for batch-cost calculation? — Defer to v2 unless cost-tracking becomes a near-term need for commercial pricing.
- **Q2.** Should the app support metric only or imperial? — Metric only for v1. All bubble formulation literature is metric.
- **Q3.** Should pH adjustments (adding lactic acid, sorbic acid in IPA) be tracked as ingredient additions or as separate pH-adjustment events? — Track as ingredient additions for consistency. The pH log captures the result.
- **Q4.** Should there be a "wand notes" section per field test? Wand type/material affects results. — Add as an optional field on the FieldTest record. Don't make it mandatory.

---

## 11. Future enhancements (deferred)

- Recipe comparison view — pick 2-4 recipes, see side-by-side ingredient + ratio differences
- Test plan mode — given a base recipe and a goal ("improve film thickness"), suggest the next variable to change
- Batch cost tracking — given ingredient costs, calculate per-litre cost of each recipe
- Photo attachment per field test (deferred per Nick's call to skip cameras)
- Recipe sharing — export/import individual recipes for sharing with Stuart, Chris, David
- Stock depletion tracking — every batch debits stock, app warns when running low
- Wind/weather correlation — over time, see which recipes work in which conditions
- Predictive recipe generator — given a target outcome, propose a recipe based on prior bench results

---

**End of spec.**
