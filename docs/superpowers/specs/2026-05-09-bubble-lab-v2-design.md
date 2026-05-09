# Bubble Lab v2 — Design Spec

**Date:** 2026-05-09  
**Author:** Nick Leisk  
**Status:** Approved  

---

## Overview

Extend the existing single-file Bubble Lab app (recipe list + mixing checklist) with batch tracking, field session logging, performance ratings, and a recipe rankings leaderboard. No build step. All state in localStorage.

---

## 1. Navigation

Three bottom tabs replace the current footer:

| Tab | Purpose |
|-----|---------|
| **Recipes** | Existing app — recipe list, volume picker, checklist, editor |
| **Field** | Start/resume sessions, view active batches |
| **History** | Past sessions log + recipe rankings |

The Recipes tab is unchanged. Field and History are new.

---

## 2. Data Model

### Batch

```js
{
  id: uuid,
  number: integer,          // global sequential: 1, 2, 3…
  recipe_id: uuid,
  volume_L: number,         // 1–5
  created_at: ISO datetime, // age calculated live from this
  notes: string,            // optional
  status: 'aging' | 'ready' | 'tested'
}
```

- `number` is a global counter stored in app state (increments on each new batch)
- `status` defaults to `'aging'`; user manually marks ready; becomes `'tested'` once rated in a session

### Session

```js
{
  id: uuid,
  started_at: ISO datetime,
  ended_at: ISO datetime | null,
  conditions: {
    weather: 'cold' | 'mild' | 'warm' | 'hot',
    wind:    'calm' | 'light' | 'moderate' | 'strong'
  },
  batch_ratings: [BatchRating]
}
```

### BatchRating

```js
{
  id: uuid,
  batch_id: uuid,
  ratings: {
    // Mixture
    thickness:       { stars: 1–5 | null, note: string },
    stringiness:     { stars: 1–5 | null, note: string },
    // Bubble
    expansion_rate:  { stars: 1–5 | null, note: string },
    closure_rate:    { stars: 1–5 | null, note: string },
    tube_length:     { stars: 1–5 | null, note: string },
    size:            { stars: 1–5 | null, note: string },
    weight:          { stars: 1–5 | null, note: string },
    // Other
    ghosting:        { stars: 1–5 | null, note: string }
  },
  overall_note: string      // optional free text for the batch overall
}
```

### App state shape

```js
{
  version: 3,
  recipes:  [...],          // existing
  batches:  [...],          // new
  sessions: [...],          // new
  next_batch_number: integer
}
```

---

## 3. Recipes Tab (existing — no changes)

- Recipe list, sorted alphabetically
- Tap → volume picker (1–5 L) → ingredient checklist
- Recipe editor (add/edit/delete ingredients, notes, custom name)
- **New:** "Make Batch" button on the volume picker screen (alongside the existing Edit / Delete buttons)
  - Opens a small form: volume (1–5L picker, pre-filled with current selection), optional notes
  - Creates a Batch record, auto-assigns the next batch number, status defaults to `'aging'`
  - Batch appears immediately in the Field tab batch list

---

## 4. Field Tab

### 4.1 Field tab home

- If no active session: shows a **"Start Session"** button + a list of all batches (number, recipe name, age, status badge)
- If a session is active: shows the active session card with "Resume" as the primary action
- Batch status can be changed by tapping the status badge on a batch row: cycles `aging → ready → aging`. `tested` is set automatically when a batch has been rated in a session.

### 4.2 Start Session flow

1. **Pick batches** — multi-select from all batches. At least one required.
2. **Set conditions** — weather (Cold / Mild / Warm / Hot) and wind (Calm / Light / Moderate / Strong) — both required.
3. Session is created and opened.

### 4.3 Active Session screen

Header: session date, conditions (weather + wind badge).  
Body: list of selected batches, each showing:
- Batch number, recipe name, age at session start
- Rating completion indicator (e.g. "6 / 8 rated")
- Tap to open the rating screen for that batch

Sticky footer: **"End Session"** button (enabled at any time — partial ratings are fine).

### 4.4 Batch Rating screen

Header: "Batch #N · [Recipe Name]"  
Sections: **Mixture**, **Bubble**, **Other**  

Each property shows:
- Label
- 1–5 star tap row (tap again to deselect / clear)
- Collapsed text field that expands on tap ("Add note…")

Footer: optional overall note field + **"Done"** button (returns to session screen).

---

## 5. History Tab

Two segments: **Sessions** | **Rankings**

### 5.1 Sessions

Reverse-chronological list of ended sessions.  
Each row: date, conditions badges, number of batches tested.  
Tap → session detail: conditions header + each batch's full ratings (read-only).

### 5.2 Rankings

Recipes ranked by average star score across all their rated batches.  
Condition filter at top: **All / Cold / Mild / Warm / Hot** (filters which batch ratings are included in the average).

Each recipe row shows:
- Recipe name
- Average overall score (mean of all **rated** properties across all qualifying batches — unrated properties excluded from the average)
- Number of batches rated

Tap a recipe → per-property breakdown: average star score for each of the 8 properties, plus a list of contributing batch ratings with dates and conditions.

---

## 6. Settings

Accessible via a gear icon in the Recipes tab header (or a fourth tab — keep as icon to avoid crowding).

- **Export data** — triggers JSON download of full app state (recipes, batches, sessions)
- **Reset to defaults** — clears everything and reseeds example recipes (existing behavior)

---

## 7. Schema Migration

Current schema version is 2. New version is 3.  
Migration from v2 → v3: add `batches: []`, `sessions: []`, `next_batch_number: 1` to existing state. Recipes carry over unchanged.

---

## 8. UI / UX Notes

- All existing visual style retained (white, black borders, Tailwind, mobile-first)
- Bottom tab bar replaces current "Reset to default recipes" footer
- Batch age displayed as "Xd Yh" (e.g. "2d 6h"), calculated live
- Stars: filled circle = rated, empty circle = not rated; tap to set, tap again to clear
- Condition badges: small pill labels (e.g. "Mild · Light wind")
- No confirmation dialogs for rating actions (low-stakes); keep confirm for destructive actions (delete recipe, reset data, end session)
- Sessions persist across browser close — `ended_at: null` means active

---

## 9. Out of Scope

- Stocks management
- Live ingredient additions in the field
- pH logging
- Recipe cloning / tagging / search
- Batch cost tracking
- Photo capture
- Multi-user / cloud sync
