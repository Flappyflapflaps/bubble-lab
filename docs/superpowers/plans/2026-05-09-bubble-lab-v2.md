# Bubble Lab v2 Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Extend the single-file Bubble Lab app with batch tracking, field session logging, performance ratings, and a recipe leaderboard.

**Architecture:** All new code is added to `index.html` inside the existing `<script type="text/babel">` block, following the current pattern of React components and a `useReducer` state machine. New state (batches, sessions) is added to the existing localStorage schema with a v2→v3 migration. The bottom tab bar replaces the current "Reset to defaults" footer.

**Tech Stack:** React 18 (CDN), TailwindCSS (CDN), Babel standalone (CDN), localStorage

---

## File Structure

**Single file:** `index.html`

All modifications are to this one file. New code is inserted between existing sections following the comment-block pattern already in the file (e.g. `/* === UTILS === */`). Task descriptions reference logical positions (e.g. "after `fmtG`") rather than line numbers since lines shift as code is added.

---

### Task 1: Schema v2→v3 + reducer expansion

**Files:**
- Modify: `index.html` — `SCHEMA_VERSION`, `saveState`, `migrate`, `reducer`

- [ ] **Step 1: Update SCHEMA_VERSION**

Find `const SCHEMA_VERSION = 2;` and change to:
```js
const SCHEMA_VERSION = 3;
```

- [ ] **Step 2: Update saveState to persist new fields**

Replace the existing `saveState` function:
```js
function saveState(state) {
  try {
    localStorage.setItem(STORAGE_KEY, JSON.stringify({
      version: SCHEMA_VERSION,
      recipes: state.recipes,
      batches: state.batches,
      sessions: state.sessions,
      next_batch_number: state.next_batch_number,
    }));
  } catch (e) { console.error(e); }
}
```

- [ ] **Step 3: Update migrate() to handle v2→v3**

Replace the entire `migrate` function:
```js
function migrate(loaded) {
  if (!loaded) return {
    version: SCHEMA_VERSION, recipes: seedRecipes(),
    batches: [], sessions: [], next_batch_number: 1,
  };

  // v2 data: recipes already have rows array
  if ((loaded.recipes || []).every(r => Array.isArray(r.rows))) {
    return {
      version: SCHEMA_VERSION,
      recipes: loaded.recipes,
      batches: loaded.batches || [],
      sessions: loaded.sessions || [],
      next_batch_number: loaded.next_batch_number || 1,
    };
  }

  // v1 → v2 migration (original logic preserved)
  const stocksById = {};
  for (const s of loaded.stocks || []) stocksById[s.id] = s;

  const migrated = (loaded.recipes || []).map(r => {
    if (Array.isArray(r.rows)) return r;
    const liters = (r.target_volume_mL || 1000) / 1000;
    const rows = (r.ingredients || []).map(ing => {
      const stock = stocksById[ing.stock_id];
      if (!stock) return null;
      let gramsPerL = 0, activeGperL = null;
      if (ing.target_type === 'mass_g') {
        gramsPerL = ing.target_value / liters;
        if (stock.category === 'polymer') activeGperL = gramsPerL;
      } else if (ing.target_type === 'volume_mL') {
        gramsPerL = ing.target_value / liters;
      } else if (ing.target_type === 'ppm') {
        if (stock.ingredient_type === 'polymer_concentrate' && stock.concentration_unit === 'g_per_mL') {
          activeGperL = ing.target_value / 1000;
          gramsPerL = activeGperL / stock.concentration_value;
        } else { gramsPerL = ing.target_value / 1000; activeGperL = gramsPerL; }
      } else if (ing.target_type === 'percent_active') {
        activeGperL = ing.target_value * 10;
        const af = stock.concentration_unit === 'percent_active' ? stock.concentration_value / 100 : 1;
        gramsPerL = af > 0 ? activeGperL / af : 0;
      }
      let role = 'other', short = null;
      if (['anionic', 'amphoteric', 'nonionic'].includes(stock.category)) {
        role = 'surfactant'; short = shortenSurfactantName(stock.name);
      } else if (stock.category === 'polymer') { role = 'polymer'; short = stock.polymer_type || null; }
      return { id: uuid(), role, label: stock.name, grams_per_L: round(gramsPerL, 4),
               active_g_per_L: activeGperL != null ? round(activeGperL, 4) : null, short };
    }).filter(Boolean);
    return { id: r.id || uuid(), custom_name: null, notes: r.protocol_notes || '', rows };
  });

  const seeds = seedRecipes();
  const existingNames = new Set(migrated.map(autoName));
  const toAdd = seeds.filter(s => !existingNames.has(autoName(s)));
  return {
    version: SCHEMA_VERSION,
    recipes: [...migrated, ...toAdd],
    batches: [], sessions: [], next_batch_number: 1,
  };
}
```

- [ ] **Step 4: Add new reducer cases**

Inside the `reducer` function, add these cases before `default`:
```js
case 'ADD_BATCH':
  return { ...state, batches: [...state.batches, a.batch], next_batch_number: state.next_batch_number + 1 };
case 'UPDATE_BATCH':
  return { ...state, batches: state.batches.map(b => b.id === a.batch.id ? a.batch : b) };
case 'DELETE_BATCH':
  return { ...state, batches: state.batches.filter(b => b.id !== a.id) };
case 'ADD_SESSION':
  return { ...state, sessions: [...state.sessions, a.session] };
case 'UPDATE_SESSION':
  return { ...state, sessions: state.sessions.map(s => s.id === a.session.id ? a.session : s) };
```

- [ ] **Step 5: Verify in browser**

Open `index.html`. Open DevTools → Application → Local Storage. The stored JSON should now include `"version":3`, `"batches":[]`, `"sessions":[]`, `"next_batch_number":1`. Existing recipes still show in the list.

- [ ] **Step 6: Commit**
```
git add index.html
git commit -m "feat: schema v3 — batches, sessions, next_batch_number"
```

---

### Task 2: Helper functions + constants

**Files:**
- Modify: `index.html` — add to `CONSTANTS` and `UTILS` sections

- [ ] **Step 1: Add RATING_PROPERTIES constant**

Add after the `COMMON_OTHERS` array (still in the CONSTANTS section):
```js
const RATING_PROPERTIES = [
  { key: 'thickness',      label: 'Thickness',      section: 'Mixture' },
  { key: 'stringiness',    label: 'Stringiness',    section: 'Mixture' },
  { key: 'expansion_rate', label: 'Expansion rate', section: 'Bubble' },
  { key: 'closure_rate',   label: 'Closure rate',   section: 'Bubble' },
  { key: 'tube_length',    label: 'Tube length',    section: 'Bubble' },
  { key: 'size',           label: 'Size',           section: 'Bubble' },
  { key: 'weight',         label: 'Weight',         section: 'Bubble' },
  { key: 'ghosting',       label: 'Ghosting',       section: 'Other'  },
];
```

- [ ] **Step 2: Add fmtAge helper**

Add after the `fmtG` function (in the UTILS section):
```js
function fmtAge(createdAt) {
  const ms = Date.now() - new Date(createdAt).getTime();
  const totalMins = Math.floor(ms / 60000);
  const days = Math.floor(totalMins / 1440);
  const hrs  = Math.floor((totalMins % 1440) / 60);
  if (days > 0) return `${days}d ${hrs}h`;
  if (hrs > 0) return `${hrs}h`;
  return `${totalMins}m`;
}
```

- [ ] **Step 3: Add ratingCount helper**

Add after `fmtAge`:
```js
function ratingCount(batchRating) {
  if (!batchRating || !batchRating.ratings) return 0;
  return RATING_PROPERTIES.filter(p => batchRating.ratings[p.key]?.stars != null).length;
}
```

- [ ] **Step 4: Add avgScore helper**

Add after `ratingCount`:
```js
function avgScore(batchRating) {
  if (!batchRating || !batchRating.ratings) return null;
  const vals = RATING_PROPERTIES.map(p => batchRating.ratings[p.key]?.stars).filter(v => v != null);
  if (vals.length === 0) return null;
  return vals.reduce((a, b) => a + b, 0) / vals.length;
}
```

- [ ] **Step 5: Add emptyRatings factory**

Add after `avgScore`:
```js
function emptyRatings() {
  const r = {};
  for (const p of RATING_PROPERTIES) r[p.key] = { stars: null, note: '' };
  return r;
}
```

- [ ] **Step 6: Add computeRankings**

Add after `emptyRatings`:
```js
function computeRankings(recipes, batches, sessions, weatherFilter) {
  const eligible = sessions.filter(s =>
    s.ended_at !== null && (weatherFilter === 'all' || s.conditions.weather === weatherFilter)
  );
  const map = {};
  for (const session of eligible) {
    for (const br of (session.batch_ratings || [])) {
      const batch = batches.find(b => b.id === br.batch_id);
      if (!batch) continue;
      const rid = batch.recipe_id;
      if (!map[rid]) map[rid] = { recipeId: rid, scores: [], perProperty: {}, batchEntries: [] };
      const vals = RATING_PROPERTIES.map(p => br.ratings?.[p.key]?.stars).filter(v => v != null);
      if (vals.length === 0) continue;
      const avg = vals.reduce((a, b) => a + b, 0) / vals.length;
      map[rid].scores.push(avg);
      for (const p of RATING_PROPERTIES) {
        const s = br.ratings?.[p.key]?.stars;
        if (s != null) {
          if (!map[rid].perProperty[p.key]) map[rid].perProperty[p.key] = [];
          map[rid].perProperty[p.key].push(s);
        }
      }
      map[rid].batchEntries.push({ batchNumber: batch.number, avg, date: session.ended_at, conditions: session.conditions });
    }
  }
  return Object.values(map)
    .map(e => ({
      recipeId: e.recipeId,
      avgScore: e.scores.length ? e.scores.reduce((a, b) => a + b, 0) / e.scores.length : null,
      batchCount: e.scores.length,
      perProperty: e.perProperty,
      batchEntries: e.batchEntries,
    }))
    .filter(e => e.avgScore !== null)
    .sort((a, b) => b.avgScore - a.avgScore);
}
```

- [ ] **Step 7: Commit**
```
git add index.html
git commit -m "feat: rating helpers — fmtAge, ratingCount, avgScore, emptyRatings, computeRankings"
```

---

### Task 3: Tab navigation + App wiring

**Files:**
- Modify: `index.html` — add `TabBar`, update `App`, update `RecipeList`

- [ ] **Step 1: Add TabBar component**

Add after the `SecondaryBtn` component (before the RECIPE LIST section):
```jsx
function TabBar({ tab, setTab }) {
  const tabs = [
    { id: 'recipes', label: 'Recipes' },
    { id: 'field',   label: 'Field'   },
    { id: 'history', label: 'History' },
  ];
  return (
    <div className="safe-bottom border-t border-gray-200 bg-white flex">
      {tabs.map(t => (
        <button key={t.id} onClick={() => setTab(t.id)}
          className={classNames(
            'tap flex-1 py-2 text-sm font-semibold',
            tab === t.id ? 'text-black border-t-2 border-black -mt-px' : 'text-gray-400'
          )}>
          {t.label}
        </button>
      ))}
    </div>
  );
}
```

- [ ] **Step 2: Add stub components for new tabs**

Add these after `RecipeEditor` (they'll be replaced in later tasks):
```jsx
function SettingsScreen({ state, onBack, onReset }) {
  return (
    <div className="flex flex-col h-full">
      <Header left={<button onClick={onBack} className="tap px-2 -ml-2 text-base">‹ Back</button>} title="Settings" />
      <div className="flex-1 overflow-y-auto p-4 space-y-4">
        <button onClick={onReset}
          className="tap w-full rounded-xl px-4 py-3 border border-red-300 text-red-600 font-semibold active:bg-red-50">
          Reset to default recipes
        </button>
      </div>
    </div>
  );
}

function FieldTab({ state, dispatch }) {
  return (
    <div className="flex flex-col h-full">
      <Header title="Field" />
      <div className="flex-1 flex items-center justify-center text-gray-400">Coming soon</div>
    </div>
  );
}

function HistoryTab({ state }) {
  return (
    <div className="flex flex-col h-full">
      <Header title="History" />
      <div className="flex-1 flex items-center justify-center text-gray-400">Coming soon</div>
    </div>
  );
}
```

- [ ] **Step 3: Replace the App component**

Replace the entire `App` function:
```jsx
function App() {
  const [state, dispatch] = useReducer(reducer, null, () => migrate(loadState()));
  useEffect(() => { saveState(state); }, [state]);

  const [tab, setTab] = useState('recipes');
  const [view, setView] = useState({ kind: 'list' });

  let content = null;

  if (tab === 'recipes') {
    if (view.kind === 'list') {
      content = <RecipeList
        recipes={state.recipes}
        onOpen={(id) => setView({ kind: 'recipe', id, liters: null, checked: {} })}
        onNew={() => setView({ kind: 'edit', id: null })}
        onResetAll={() => {
          if (window.confirm('Reset all recipes to defaults? This will replace everything.')) {
            dispatch({ type: 'RESET' });
          }
        }}
        onSettings={() => setView({ kind: 'settings' })}
      />;
    } else if (view.kind === 'recipe') {
      const recipe = state.recipes.find(r => r.id === view.id);
      if (!recipe) { setView({ kind: 'list' }); return null; }
      content = <RecipeDetail
        recipe={recipe}
        viewState={view}
        setViewState={setView}
        onBack={() => setView({ kind: 'list' })}
        onEdit={() => setView({ kind: 'edit', id: recipe.id })}
        onDelete={() => {
          if (window.confirm(`Delete "${autoName(recipe)}"?`)) {
            dispatch({ type: 'DELETE_RECIPE', id: recipe.id });
            setView({ kind: 'list' });
          }
        }}
        onMakeBatch={(batch) => dispatch({ type: 'ADD_BATCH', batch })}
        nextBatchNumber={state.next_batch_number}
      />;
    } else if (view.kind === 'edit') {
      const recipe = view.id ? state.recipes.find(r => r.id === view.id) : null;
      content = <RecipeEditor
        recipe={recipe}
        onCancel={() => setView(recipe
          ? { kind: 'recipe', id: recipe.id, liters: null, checked: {} }
          : { kind: 'list' })}
        onSave={(saved) => {
          if (recipe) dispatch({ type: 'UPDATE_RECIPE', recipe: saved });
          else dispatch({ type: 'ADD_RECIPE', recipe: saved });
          setView({ kind: 'recipe', id: saved.id, liters: null, checked: {} });
        }}
        onDelete={recipe ? () => {
          if (window.confirm(`Delete "${autoName(recipe)}"?`)) {
            dispatch({ type: 'DELETE_RECIPE', id: recipe.id });
            setView({ kind: 'list' });
          }
        } : null}
      />;
    } else if (view.kind === 'settings') {
      content = <SettingsScreen
        state={state}
        onBack={() => setView({ kind: 'list' })}
        onReset={() => {
          if (window.confirm('Reset all data to defaults? This cannot be undone.')) {
            dispatch({ type: 'RESET' });
            setView({ kind: 'list' });
          }
        }}
      />;
    }
  } else if (tab === 'field') {
    content = <FieldTab state={state} dispatch={dispatch} />;
  } else if (tab === 'history') {
    content = <HistoryTab state={state} />;
  }

  return (
    <div className="flex flex-col h-full">
      <div className="flex-1 overflow-hidden relative">{content}</div>
      <TabBar tab={tab} setTab={setTab} />
    </div>
  );
}
```

- [ ] **Step 4: Update RecipeList — add onSettings prop + gear icon + remove old footer**

Change the function signature:
```jsx
function RecipeList({ recipes, onOpen, onNew, onResetAll, onSettings }) {
```

Replace the `<Header>` inside RecipeList:
```jsx
<Header
  left={<button onClick={onSettings} className="tap px-3 -ml-3 text-xl">⚙️</button>}
  title="Recipes"
  right={<button onClick={onNew} className="tap px-3 -mr-3 text-base font-semibold">+ New</button>}
/>
```

Remove the old footer div at the bottom of RecipeList (the one containing the "Reset to default recipes" link) — the TabBar replaces it:
```jsx
// DELETE this block from RecipeList:
<div className="safe-bottom border-t border-gray-200 p-3 text-center">
  <button onClick={onResetAll} className="text-sm text-gray-500 underline">Reset to default recipes</button>
</div>
```

- [ ] **Step 5: Verify in browser**

Three tabs appear at the bottom: Recipes, Field, History. Recipes tab works as before. Gear icon in Recipes header opens Settings. Settings "Reset to default recipes" works. Field and History show "Coming soon".

- [ ] **Step 6: Commit**
```
git add index.html
git commit -m "feat: three-tab navigation with Settings stub"
```

---

### Task 4: "Make Batch" from volume picker

**Files:**
- Modify: `index.html` — add `MakeBatchSheet`, update `RecipeDetail`

- [ ] **Step 1: Add MakeBatchSheet component**

Add after `AddRowSheet`:
```jsx
function MakeBatchSheet({ recipe, defaultVolume, nextBatchNumber, onMake, onCancel }) {
  const [volume, setVolume] = useState(defaultVolume || 1);
  const [notes, setNotes] = useState('');

  const submit = () => {
    onMake({
      id: uuid(),
      number: nextBatchNumber,
      recipe_id: recipe.id,
      volume_L: volume,
      created_at: new Date().toISOString(),
      notes,
      status: 'aging',
    });
    onCancel();
  };

  return (
    <div className="fixed inset-0 z-30 flex items-end" onClick={onCancel}>
      <div className="absolute inset-0 bg-black/40" />
      <div className="relative w-full bg-white rounded-t-2xl border-t border-gray-200 sheet-enter safe-bottom"
           onClick={e => e.stopPropagation()}>
        <div className="sticky top-0 bg-white border-b border-gray-200 px-4 py-3 flex items-center justify-between">
          <div className="font-semibold text-lg">Make Batch #{nextBatchNumber}</div>
          <button onClick={onCancel} className="tap text-base text-gray-500 px-2">Close</button>
        </div>
        <div className="p-4 space-y-4">
          <div>
            <div className="text-xs font-bold uppercase tracking-wide text-gray-500 mb-1">Recipe</div>
            <div className="text-base font-semibold">{autoName(recipe)}</div>
          </div>
          <div>
            <div className="text-xs font-bold uppercase tracking-wide text-gray-500 mb-2">Volume (liters)</div>
            <div className="grid grid-cols-5 gap-2">
              {[1, 2, 3, 4, 5].map(L => (
                <button key={L} onClick={() => setVolume(L)}
                  className={classNames(
                    'tap rounded-xl border-2 py-3 text-lg font-bold',
                    volume === L ? 'border-black bg-black text-white' : 'border-gray-300 bg-white active:bg-gray-50'
                  )}>{L}L</button>
              ))}
            </div>
          </div>
          <div>
            <div className="text-xs font-bold uppercase tracking-wide text-gray-500 mb-2">Notes (optional)</div>
            <input value={notes} onChange={e => setNotes(e.target.value)}
              placeholder="e.g. fresh PEO batch, aged 48h"
              className="w-full rounded-xl border border-gray-300 px-3 py-3 text-base" />
          </div>
          <div className="flex gap-2 pt-2">
            <SecondaryBtn onClick={onCancel} className="flex-1">Cancel</SecondaryBtn>
            <PrimaryBtn onClick={submit} className="flex-1">Make Batch #{nextBatchNumber}</PrimaryBtn>
          </div>
        </div>
      </div>
    </div>
  );
}
```

- [ ] **Step 2: Update RecipeDetail signature and add local state**

Change the function signature:
```jsx
function RecipeDetail({ recipe, viewState, setViewState, onBack, onEdit, onDelete, onMakeBatch, nextBatchNumber }) {
```

Add at the top of the function body (after `const liters = viewState.liters;`):
```js
const [makingBatch, setMakingBatch] = useState(false);
```

- [ ] **Step 3: Add "Make Batch" button to the volume picker view**

In the volume picker view (the `if (!liters)` branch), find the button row with Edit and Delete and replace it:
```jsx
<div className="mt-12 w-full max-w-md flex gap-2">
  <SecondaryBtn onClick={onEdit} className="flex-1">Edit</SecondaryBtn>
  <SecondaryBtn onClick={() => setMakingBatch(true)} className="flex-1">Make Batch</SecondaryBtn>
  <SecondaryBtn onClick={onDelete} className="flex-1 text-red-600 border-red-300 active:bg-red-50">Delete</SecondaryBtn>
</div>
```

- [ ] **Step 4: Render MakeBatchSheet at the bottom of the volume picker view's return**

Inside the `if (!liters)` branch, just before the closing `</div>` of the outer flex container, add:
```jsx
{makingBatch && (
  <MakeBatchSheet
    recipe={recipe}
    defaultVolume={viewState.liters || 1}
    nextBatchNumber={nextBatchNumber}
    onMake={onMakeBatch}
    onCancel={() => setMakingBatch(false)}
  />
)}
```

- [ ] **Step 5: Verify in browser**

Open a recipe → volume picker screen. Three buttons appear: Edit, Make Batch, Delete. "Make Batch" opens the sheet with recipe name pre-filled, volume picker, notes. Submit → check DevTools localStorage `batches` array contains the new batch with correct `number`, `recipe_id`, `volume_L`, `created_at`, `status: "aging"`.

- [ ] **Step 6: Commit**
```
git add index.html
git commit -m "feat: Make Batch sheet from volume picker"
```

---

### Task 5: Field tab — batch list + status toggle

**Files:**
- Modify: `index.html` — add `StatusBadge`, replace `FieldTab` stub, add sub-screen stubs

- [ ] **Step 1: Add StatusBadge component**

Add before the `FieldTab` stub:
```jsx
const STATUS_STYLE = {
  aging:  'bg-yellow-100 text-yellow-800 border-yellow-300',
  ready:  'bg-green-100  text-green-800  border-green-300',
  tested: 'bg-gray-100   text-gray-500   border-gray-200',
};

function StatusBadge({ status, onClick }) {
  return (
    <button onClick={onClick} disabled={!onClick}
      className={classNames(
        'rounded-full border px-2 py-0.5 text-xs font-semibold capitalize',
        STATUS_STYLE[status] || STATUS_STYLE.aging,
        onClick ? 'active:opacity-70' : 'cursor-default'
      )}>
      {status}
    </button>
  );
}
```

- [ ] **Step 2: Replace FieldTab stub**

```jsx
function FieldTab({ state, dispatch }) {
  const [fieldView, setFieldView] = useState({ kind: 'home' });
  const activeSession = state.sessions.find(s => s.ended_at === null);
  const recipes = state.recipes;

  // guard: if viewing session/rating but no active session exists, go home
  if ((fieldView.kind === 'session' || fieldView.kind === 'rating') && !activeSession) {
    setFieldView({ kind: 'home' });
    return null;
  }

  if (fieldView.kind === 'start-session') {
    return <StartSessionSheet
      batches={state.batches}
      recipes={recipes}
      onCancel={() => setFieldView({ kind: 'home' })}
      onCreate={(session) => {
        dispatch({ type: 'ADD_SESSION', session });
        setFieldView({ kind: 'session' });
      }}
    />;
  }

  if (fieldView.kind === 'session') {
    return <ActiveSessionScreen
      session={activeSession}
      batches={state.batches}
      recipes={recipes}
      onRate={(batchId) => setFieldView({ kind: 'rating', batchId })}
      onEnd={() => {
        dispatch({ type: 'UPDATE_SESSION', session: { ...activeSession, ended_at: new Date().toISOString() } });
        setFieldView({ kind: 'home' });
      }}
    />;
  }

  if (fieldView.kind === 'rating') {
    const existing = activeSession?.batch_ratings?.find(r => r.batch_id === fieldView.batchId);
    return <BatchRatingScreen
      batchId={fieldView.batchId}
      batches={state.batches}
      recipes={recipes}
      initialRating={existing}
      onDone={(batchRating) => {
        const updatedRatings = existing
          ? activeSession.batch_ratings.map(r => r.batch_id === fieldView.batchId ? batchRating : r)
          : [...(activeSession.batch_ratings || []), batchRating];
        dispatch({ type: 'UPDATE_SESSION', session: { ...activeSession, batch_ratings: updatedRatings } });
        const batch = state.batches.find(b => b.id === fieldView.batchId);
        if (batch && batch.status !== 'tested') {
          dispatch({ type: 'UPDATE_BATCH', batch: { ...batch, status: 'tested' } });
        }
        setFieldView({ kind: 'session' });
      }}
      onBack={() => setFieldView({ kind: 'session' })}
    />;
  }

  // home view
  const toggleStatus = (batch) => {
    const next = batch.status === 'aging' ? 'ready' : 'aging';
    dispatch({ type: 'UPDATE_BATCH', batch: { ...batch, status: next } });
  };

  const sorted = [...state.batches].sort((a, b) => new Date(b.created_at) - new Date(a.created_at));

  return (
    <div className="flex flex-col h-full">
      <Header title="Field" />
      <div className="flex-1 overflow-y-auto">
        <div className="px-4 pt-4">
          {activeSession ? (
            <div className="rounded-xl border-2 border-black p-4 mb-4">
              <div className="text-xs font-bold uppercase tracking-wide text-gray-500 mb-1">Active session</div>
              <div className="font-semibold capitalize">
                {activeSession.conditions.weather} · {activeSession.conditions.wind} wind
              </div>
              <div className="text-sm text-gray-500 mt-0.5">
                {activeSession.batch_ratings?.length || 0} / {activeSession.batch_ids?.length || 0} batches rated
              </div>
              <div className="mt-3">
                <PrimaryBtn onClick={() => setFieldView({ kind: 'session' })}>Resume session</PrimaryBtn>
              </div>
            </div>
          ) : (
            <>
              <PrimaryBtn
                onClick={() => setFieldView({ kind: 'start-session' })}
                disabled={state.batches.length === 0}>
                + Start session
              </PrimaryBtn>
              {state.batches.length === 0 && (
                <div className="text-sm text-gray-500 text-center mt-2">Make a batch from a recipe first.</div>
              )}
            </>
          )}
        </div>

        <div className="px-4 pt-5">
          <div className="text-xs font-bold uppercase tracking-wide text-gray-500 mb-2">
            Batches ({sorted.length})
          </div>
          {sorted.length === 0 ? (
            <div className="text-sm text-gray-400 py-4 text-center">No batches yet.</div>
          ) : (
            <ul>
              {sorted.map(b => {
                const recipe = recipes.find(r => r.id === b.recipe_id);
                return (
                  <li key={b.id} className="flex items-center gap-3 py-3 border-b border-gray-100">
                    <div className="flex-1 min-w-0">
                      <div className="font-semibold text-base">
                        #{b.number} · {recipe ? autoName(recipe) : 'Unknown recipe'}
                      </div>
                      <div className="text-sm text-gray-500">{b.volume_L}L · {fmtAge(b.created_at)} old</div>
                      {b.notes ? <div className="text-xs text-gray-400 mt-0.5 truncate">{b.notes}</div> : null}
                    </div>
                    <StatusBadge
                      status={b.status}
                      onClick={b.status !== 'tested' ? () => toggleStatus(b) : null}
                    />
                  </li>
                );
              })}
            </ul>
          )}
        </div>
      </div>
    </div>
  );
}
```

- [ ] **Step 3: Add sub-screen stubs**

Add after `FieldTab`:
```jsx
function StartSessionSheet({ batches, recipes, onCancel, onCreate }) {
  return (
    <div className="flex flex-col h-full">
      <Header left={<button onClick={onCancel} className="tap px-2 -ml-2 text-base">Cancel</button>} title="Start Session" />
      <div className="flex-1 flex items-center justify-center text-gray-400">Coming soon</div>
    </div>
  );
}

function ActiveSessionScreen({ session, batches, recipes, onRate, onEnd }) {
  return (
    <div className="flex flex-col h-full">
      <Header title="Session" right={<button onClick={onEnd} className="tap px-2 -mr-2 text-sm text-red-600 font-semibold">End</button>} />
      <div className="flex-1 flex items-center justify-center text-gray-400">Coming soon</div>
    </div>
  );
}

function BatchRatingScreen({ batchId, batches, recipes, initialRating, onDone, onBack }) {
  return (
    <div className="flex flex-col h-full">
      <Header left={<button onClick={onBack} className="tap px-2 -ml-2 text-base">‹ Back</button>} title="Rate batch" />
      <div className="flex-1 flex items-center justify-center text-gray-400">Coming soon</div>
    </div>
  );
}
```

- [ ] **Step 4: Verify in browser**

Field tab shows batch list (or empty state). Make a batch from Recipes tab, return to Field — it appears with age and an "aging" badge. Tapping the badge toggles to "ready" and back. "Start session" button appears but field sub-screens show "Coming soon".

- [ ] **Step 5: Commit**
```
git add index.html
git commit -m "feat: Field tab batch list with status toggle"
```

---

### Task 6: Start Session flow

**Files:**
- Modify: `index.html` — replace `StartSessionSheet` stub

- [ ] **Step 1: Replace StartSessionSheet stub**

```jsx
function StartSessionSheet({ batches, recipes, onCancel, onCreate }) {
  const [step, setStep] = useState(1);
  const [selectedIds, setSelectedIds] = useState([]);
  const [weather, setWeather] = useState(null);
  const [wind, setWind] = useState(null);

  const toggleBatch = (id) =>
    setSelectedIds(prev => prev.includes(id) ? prev.filter(x => x !== id) : [...prev, id]);

  const submit = () => {
    onCreate({
      id: uuid(),
      started_at: new Date().toISOString(),
      ended_at: null,
      conditions: { weather, wind },
      batch_ids: selectedIds,
      batch_ratings: [],
    });
  };

  const sorted = [...batches].sort((a, b) => new Date(b.created_at) - new Date(a.created_at));

  return (
    <div className="flex flex-col h-full">
      <Header
        left={
          <button onClick={step === 1 ? onCancel : () => setStep(1)} className="tap px-2 -ml-2 text-base">
            {step === 1 ? 'Cancel' : '‹ Back'}
          </button>
        }
        title={step === 1 ? 'Pick batches' : 'Conditions'}
        right={
          step === 1
            ? <button onClick={() => setStep(2)} disabled={selectedIds.length === 0}
                className={classNames('tap px-2 -mr-2 text-base font-bold', selectedIds.length === 0 ? 'text-gray-400' : '')}>
                Next
              </button>
            : <button onClick={submit} disabled={!weather || !wind}
                className={classNames('tap px-2 -mr-2 text-base font-bold', (!weather || !wind) ? 'text-gray-400' : '')}>
                Start
              </button>
        }
      />
      <div className="flex-1 overflow-y-auto pb-8">
        {step === 1 && (
          <div className="px-4 pt-4">
            <div className="text-sm text-gray-500 mb-4">Select which batches you're testing today.</div>
            {sorted.length === 0 ? (
              <div className="text-sm text-gray-400 text-center py-8">No batches yet.</div>
            ) : (
              <ul>
                {sorted.map(b => {
                  const recipe = recipes.find(r => r.id === b.recipe_id);
                  const selected = selectedIds.includes(b.id);
                  return (
                    <li key={b.id}>
                      <button onClick={() => toggleBatch(b.id)}
                        className="w-full flex items-center gap-3 py-3 border-b border-gray-100 text-left active:bg-gray-50">
                        <span className={classNames(
                          'w-7 h-7 rounded-full border-2 flex items-center justify-center shrink-0 text-base',
                          selected ? 'bg-black border-black text-white' : 'border-gray-400 bg-white'
                        )}>{selected ? '✓' : ''}</span>
                        <span className="flex-1 min-w-0">
                          <span className="font-semibold block">
                            #{b.number} · {recipe ? autoName(recipe) : 'Unknown'}
                          </span>
                          <span className="text-sm text-gray-500">
                            {b.volume_L}L · {fmtAge(b.created_at)} old · {b.status}
                          </span>
                        </span>
                      </button>
                    </li>
                  );
                })}
              </ul>
            )}
          </div>
        )}
        {step === 2 && (
          <div className="px-4 pt-4 space-y-6">
            <div>
              <div className="text-xs font-bold uppercase tracking-wide text-gray-500 mb-3">Weather</div>
              <div className="grid grid-cols-2 gap-2">
                {['cold', 'mild', 'warm', 'hot'].map(w => (
                  <button key={w} onClick={() => setWeather(w)}
                    className={classNames(
                      'tap rounded-xl border-2 py-3 text-base capitalize font-semibold',
                      weather === w ? 'border-black bg-black text-white' : 'border-gray-300 bg-white active:bg-gray-50'
                    )}>{w}</button>
                ))}
              </div>
            </div>
            <div>
              <div className="text-xs font-bold uppercase tracking-wide text-gray-500 mb-3">Wind</div>
              <div className="grid grid-cols-2 gap-2">
                {['calm', 'light', 'moderate', 'strong'].map(w => (
                  <button key={w} onClick={() => setWind(w)}
                    className={classNames(
                      'tap rounded-xl border-2 py-3 text-base capitalize font-semibold',
                      wind === w ? 'border-black bg-black text-white' : 'border-gray-300 bg-white active:bg-gray-50'
                    )}>{w}</button>
                ))}
              </div>
            </div>
          </div>
        )}
      </div>
    </div>
  );
}
```

- [ ] **Step 2: Verify in browser**

Field tab → Start Session (requires at least one batch). Step 1: batch list with checkboxes; selecting none keeps Next disabled; selecting one enables it. Step 2: weather + wind pickers; Start disabled until both set. After Start: active session card appears on Field home with correct conditions. Check DevTools — session in `sessions` array with `ended_at: null` and `batch_ids`.

- [ ] **Step 3: Commit**
```
git add index.html
git commit -m "feat: Start Session two-step flow"
```

---

### Task 7: Active Session screen

**Files:**
- Modify: `index.html` — replace `ActiveSessionScreen` stub

- [ ] **Step 1: Replace ActiveSessionScreen stub**

```jsx
function ActiveSessionScreen({ session, batches, recipes, onRate, onEnd }) {
  const sessionBatches = (session.batch_ids || [])
    .map(id => batches.find(b => b.id === id))
    .filter(Boolean);

  return (
    <div className="flex flex-col h-full">
      <Header
        title="Active Session"
        right={
          <button
            onClick={() => { if (window.confirm('End this session?')) onEnd(); }}
            className="tap px-2 -mr-2 text-sm text-red-600 font-semibold">
            End
          </button>
        }
      />
      <div className="flex-1 overflow-y-auto">
        <div className="px-4 pt-4 pb-3 border-b border-gray-100">
          <div className="flex gap-2 flex-wrap">
            <span className="rounded-full border border-gray-300 px-3 py-1 text-sm capitalize">
              {session.conditions.weather}
            </span>
            <span className="rounded-full border border-gray-300 px-3 py-1 text-sm capitalize">
              {session.conditions.wind} wind
            </span>
          </div>
          <div className="text-xs text-gray-400 mt-2">
            {new Date(session.started_at).toLocaleString()}
          </div>
        </div>

        <div className="px-4 pt-4">
          <div className="text-xs font-bold uppercase tracking-wide text-gray-500 mb-2">Batches</div>
          <ul>
            {sessionBatches.map(b => {
              const recipe = recipes.find(r => r.id === b.recipe_id);
              const batchRating = session.batch_ratings?.find(r => r.batch_id === b.id);
              const rated = ratingCount(batchRating);
              return (
                <li key={b.id}>
                  <button onClick={() => onRate(b.id)}
                    className="w-full flex items-center gap-3 py-4 border-b border-gray-100 text-left active:bg-gray-50">
                    <div className="flex-1 min-w-0">
                      <div className="font-semibold text-base">
                        #{b.number} · {recipe ? autoName(recipe) : 'Unknown'}
                      </div>
                      <div className="text-sm text-gray-500">{b.volume_L}L · {fmtAge(b.created_at)} old</div>
                    </div>
                    <div className="text-right shrink-0">
                      <div className="text-sm font-semibold">
                        {rated} / {RATING_PROPERTIES.length}
                      </div>
                      <div className="text-xs text-gray-400">rated ›</div>
                    </div>
                  </button>
                </li>
              );
            })}
          </ul>
        </div>
        <div className="h-8" />
      </div>
    </div>
  );
}
```

- [ ] **Step 2: Verify in browser**

Resume a session. Screen shows conditions badges, date, and each selected batch with "0 / 8 rated" counter. Tapping End shows a confirm dialog and returns to Field home (session ends). "Resume session" card disappears. Session appears in History.

- [ ] **Step 3: Commit**
```
git add index.html
git commit -m "feat: Active Session screen"
```

---

### Task 8: Batch Rating screen

**Files:**
- Modify: `index.html` — add `StarRow`, replace `BatchRatingScreen` stub

- [ ] **Step 1: Add StarRow component**

Add just before `BatchRatingScreen`:
```jsx
function StarRow({ value, onChange }) {
  return (
    <div className="flex gap-2">
      {[1, 2, 3, 4, 5].map(n => (
        <button key={n} onClick={() => onChange(value === n ? null : n)}
          className={classNames(
            'w-10 h-10 rounded-full border-2 flex items-center justify-center text-base font-bold tap',
            value != null && value >= n
              ? 'bg-black border-black text-white'
              : 'border-gray-300 bg-white text-gray-300'
          )}>{n}</button>
      ))}
    </div>
  );
}
```

- [ ] **Step 2: Replace BatchRatingScreen stub**

```jsx
function BatchRatingScreen({ batchId, batches, recipes, initialRating, onDone, onBack }) {
  const batch = batches.find(b => b.id === batchId);
  const recipe = recipes.find(r => r.id === batch?.recipe_id);
  const [ratings, setRatings] = useState(() => initialRating?.ratings || emptyRatings());
  const [overallNote, setOverallNote] = useState(initialRating?.overall_note || '');
  const [expandedNote, setExpandedNote] = useState(null);

  const setStars = (key, val) =>
    setRatings(r => ({ ...r, [key]: { ...r[key], stars: val } }));
  const setNote = (key, val) =>
    setRatings(r => ({ ...r, [key]: { ...r[key], note: val } }));

  const sections = ['Mixture', 'Bubble', 'Other'];

  return (
    <div className="flex flex-col h-full">
      <Header
        left={<button onClick={onBack} className="tap px-2 -ml-2 text-base">‹ Back</button>}
        title={batch ? `Batch #${batch.number}` : 'Rate Batch'}
      />
      <div className="flex-1 overflow-y-auto pb-32">
        {recipe && (
          <div className="px-4 pt-3 pb-3 border-b border-gray-100 text-sm text-gray-500">
            {autoName(recipe)}
          </div>
        )}
        {sections.map(sec => (
          <div key={sec} className="px-4 pt-5">
            <div className="text-xs font-bold uppercase tracking-wide text-gray-500 mb-4">{sec}</div>
            {RATING_PROPERTIES.filter(p => p.section === sec).map(p => (
              <div key={p.key} className="mb-6">
                <div className="flex items-center justify-between mb-2">
                  <div className="text-base font-semibold">{p.label}</div>
                  <button onClick={() => setExpandedNote(expandedNote === p.key ? null : p.key)}
                    className="text-xs text-gray-400 tap px-1">
                    {ratings[p.key]?.note ? '✎ note' : '+ note'}
                  </button>
                </div>
                <StarRow value={ratings[p.key]?.stars} onChange={(v) => setStars(p.key, v)} />
                {expandedNote === p.key && (
                  <input autoFocus
                    value={ratings[p.key]?.note || ''}
                    onChange={e => setNote(p.key, e.target.value)}
                    placeholder={`Note on ${p.label.toLowerCase()}…`}
                    className="mt-2 w-full rounded-xl border border-gray-300 px-3 py-2 text-base"
                  />
                )}
              </div>
            ))}
          </div>
        ))}
        <div className="px-4 pt-2 pb-4">
          <div className="text-xs font-bold uppercase tracking-wide text-gray-500 mb-2">Overall note</div>
          <textarea value={overallNote} onChange={e => setOverallNote(e.target.value)}
            rows={3} placeholder="Anything else worth noting…"
            className="w-full rounded-xl border border-gray-300 px-3 py-3 text-base" />
        </div>
      </div>
      <div className="safe-bottom sticky bottom-0 bg-white border-t border-gray-200 p-3">
        <PrimaryBtn onClick={() => onDone({ id: initialRating?.id || uuid(), batch_id: batchId, ratings, overall_note: overallNote })}>
          Done
        </PrimaryBtn>
      </div>
    </div>
  );
}
```

- [ ] **Step 3: Verify in browser**

Start a session → tap a batch → rating screen shows three sections (Mixture, Bubble, Other) with all 8 properties. Each has a 1–5 star row. Tapping a star fills it and all lower numbers. Tapping the same star again clears. "+ note" expands an input. Done saves and returns to session screen; the count updates from "0 / 8" to the number of properties rated. Batch status becomes "tested".

- [ ] **Step 4: Commit**
```
git add index.html
git commit -m "feat: Batch Rating screen with StarRow"
```

---

### Task 9: History tab — Sessions + Rankings

**Files:**
- Modify: `index.html` — add `SegmentedControl`, `SessionDetail`, `RankingsView`, replace `HistoryTab` stub

- [ ] **Step 1: Add SegmentedControl component**

Add before `HistoryTab`:
```jsx
function SegmentedControl({ options, value, onChange }) {
  return (
    <div className="flex bg-gray-100 rounded-xl p-1 gap-1">
      {options.map(o => (
        <button key={o.id} onClick={() => onChange(o.id)}
          className={classNames(
            'tap flex-1 py-2 rounded-lg text-sm font-semibold',
            value === o.id ? 'bg-white shadow-sm text-black' : 'text-gray-500'
          )}>{o.label}</button>
      ))}
    </div>
  );
}
```

- [ ] **Step 2: Add SessionDetail component**

Add before `HistoryTab`:
```jsx
function SessionDetail({ session, batches, recipes, onBack }) {
  const sessionBatches = (session.batch_ids || [])
    .map(id => batches.find(b => b.id === id)).filter(Boolean);

  return (
    <div className="flex flex-col h-full">
      <Header
        left={<button onClick={onBack} className="tap px-2 -ml-2 text-base">‹ Back</button>}
        title={new Date(session.ended_at).toLocaleDateString('en-GB', { day: 'numeric', month: 'short' })}
      />
      <div className="flex-1 overflow-y-auto">
        <div className="px-4 pt-4 pb-3 border-b border-gray-100">
          <div className="flex gap-2 flex-wrap">
            <span className="rounded-full border border-gray-300 px-3 py-1 text-sm capitalize">{session.conditions.weather}</span>
            <span className="rounded-full border border-gray-300 px-3 py-1 text-sm capitalize">{session.conditions.wind} wind</span>
          </div>
        </div>
        {sessionBatches.map(b => {
          const recipe = recipes.find(r => r.id === b.recipe_id);
          const rating = session.batch_ratings?.find(r => r.batch_id === b.id);
          return (
            <div key={b.id} className="px-4 pt-5 pb-4 border-b border-gray-100">
              <div className="font-semibold text-base mb-3">
                #{b.number} · {recipe ? autoName(recipe) : 'Unknown'}
              </div>
              {!rating ? (
                <div className="text-sm text-gray-400">Not rated this session.</div>
              ) : (
                <>
                  {RATING_PROPERTIES.map(p => {
                    const r = rating.ratings[p.key];
                    if (!r?.stars) return null;
                    return (
                      <div key={p.key} className="flex items-center gap-3 py-1.5">
                        <div className="text-sm text-gray-600 w-32 shrink-0">{p.label}</div>
                        <div className="flex gap-1">
                          {[1, 2, 3, 4, 5].map(n => (
                            <span key={n} className={classNames(
                              'w-5 h-5 rounded-full border flex items-center justify-center text-xs font-bold',
                              r.stars >= n ? 'bg-black border-black text-white' : 'border-gray-200 text-gray-200'
                            )}>{n}</span>
                          ))}
                        </div>
                        {r.note && <div className="text-xs text-gray-400 truncate flex-1">{r.note}</div>}
                      </div>
                    );
                  })}
                  {rating.overall_note && (
                    <div className="mt-3 text-sm text-gray-500 italic">"{rating.overall_note}"</div>
                  )}
                </>
              )}
            </div>
          );
        })}
        <div className="h-8" />
      </div>
    </div>
  );
}
```

- [ ] **Step 3: Add RankingsView component**

Add before `HistoryTab`:
```jsx
function RankingsView({ state }) {
  const [weatherFilter, setWeatherFilter] = useState('all');
  const [selectedRecipeId, setSelectedRecipeId] = useState(null);

  const rankings = useMemo(
    () => computeRankings(state.recipes, state.batches, state.sessions, weatherFilter),
    [state.recipes, state.batches, state.sessions, weatherFilter]
  );

  if (selectedRecipeId) {
    const entry = rankings.find(e => e.recipeId === selectedRecipeId);
    const recipe = state.recipes.find(r => r.id === selectedRecipeId);
    if (!entry || !recipe) { setSelectedRecipeId(null); return null; }
    return (
      <div>
        <div className="px-4 pt-4 pb-3 border-b border-gray-100">
          <button onClick={() => setSelectedRecipeId(null)} className="tap text-sm text-gray-500 mb-2 block">‹ Rankings</button>
          <div className="font-semibold text-lg">{autoName(recipe)}</div>
          <div className="text-sm text-gray-500">
            {entry.batchCount} batch{entry.batchCount !== 1 ? 'es' : ''} · avg {fmtNum(entry.avgScore)} / 5
          </div>
        </div>
        <div className="px-4 pt-4">
          <div className="text-xs font-bold uppercase tracking-wide text-gray-500 mb-3">Per property averages</div>
          {RATING_PROPERTIES.map(p => {
            const vals = entry.perProperty[p.key];
            if (!vals || vals.length === 0) return null;
            const avg = vals.reduce((a, b) => a + b, 0) / vals.length;
            return (
              <div key={p.key} className="flex items-center gap-3 py-2 border-b border-gray-50">
                <div className="text-sm text-gray-600 w-32 shrink-0">{p.label}</div>
                <div className="flex gap-1">
                  {[1, 2, 3, 4, 5].map(n => (
                    <span key={n} className={classNames(
                      'w-5 h-5 rounded-full border flex items-center justify-center text-xs font-bold',
                      avg >= n ? 'bg-black border-black text-white' : 'border-gray-200 text-gray-200'
                    )}>{n}</span>
                  ))}
                </div>
                <div className="text-xs text-gray-400">{fmtNum(avg)} avg</div>
              </div>
            );
          })}
          <div className="pt-5">
            <div className="text-xs font-bold uppercase tracking-wide text-gray-500 mb-3">Test history</div>
            {entry.batchEntries.map((e, i) => (
              <div key={i} className="flex items-center gap-3 py-2 border-b border-gray-50">
                <div className="text-sm font-semibold shrink-0">#{e.batchNumber}</div>
                <div className="flex gap-1 flex-wrap">
                  <span className="rounded-full border border-gray-200 px-2 py-0.5 text-xs capitalize">{e.conditions.weather}</span>
                  <span className="rounded-full border border-gray-200 px-2 py-0.5 text-xs capitalize">{e.conditions.wind}</span>
                </div>
                <div className="text-sm font-semibold ml-auto">{fmtNum(e.avg)} ★</div>
              </div>
            ))}
          </div>
        </div>
        <div className="h-8" />
      </div>
    );
  }

  return (
    <div>
      <div className="px-4 pt-3 pb-2">
        <div className="flex gap-2 overflow-x-auto pb-1 no-scrollbar">
          {['all', 'cold', 'mild', 'warm', 'hot'].map(w => (
            <button key={w} onClick={() => setWeatherFilter(w)}
              className={classNames(
                'tap shrink-0 rounded-full border px-3 py-1.5 text-sm capitalize font-semibold',
                weatherFilter === w ? 'bg-black text-white border-black' : 'border-gray-300 bg-white text-gray-600'
              )}>{w === 'all' ? 'All conditions' : w}</button>
          ))}
        </div>
      </div>
      {rankings.length === 0 ? (
        <div className="text-center py-12 px-4 text-gray-400">
          <div className="font-semibold">No data yet</div>
          <div className="text-sm mt-1">Complete sessions with ratings to see rankings.</div>
        </div>
      ) : (
        <ul className="px-4 pt-2">
          {rankings.map((entry, i) => {
            const recipe = state.recipes.find(r => r.id === entry.recipeId);
            return (
              <li key={entry.recipeId}>
                <button onClick={() => setSelectedRecipeId(entry.recipeId)}
                  className="w-full flex items-center gap-3 py-4 border-b border-gray-100 text-left active:bg-gray-50">
                  <div className="text-2xl font-bold text-gray-200 w-8 shrink-0 tabular-nums">#{i + 1}</div>
                  <div className="flex-1 min-w-0">
                    <div className="font-semibold text-base">{recipe ? autoName(recipe) : 'Unknown'}</div>
                    <div className="text-sm text-gray-500">
                      {entry.batchCount} batch{entry.batchCount !== 1 ? 'es' : ''} tested
                    </div>
                  </div>
                  <div className="text-right shrink-0">
                    <div className="font-bold text-lg tabular-nums">{fmtNum(entry.avgScore)}</div>
                    <div className="text-xs text-gray-400">/ 5 ★</div>
                  </div>
                </button>
              </li>
            );
          })}
        </ul>
      )}
    </div>
  );
}
```

- [ ] **Step 4: Replace HistoryTab stub**

```jsx
function HistoryTab({ state }) {
  const [segment, setSegment] = useState('sessions');
  const [selectedSessionId, setSelectedSessionId] = useState(null);

  const ended = state.sessions
    .filter(s => s.ended_at !== null)
    .sort((a, b) => new Date(b.ended_at) - new Date(a.ended_at));

  if (selectedSessionId) {
    const session = state.sessions.find(s => s.id === selectedSessionId);
    if (!session) { setSelectedSessionId(null); return null; }
    return <SessionDetail
      session={session}
      batches={state.batches}
      recipes={state.recipes}
      onBack={() => setSelectedSessionId(null)}
    />;
  }

  return (
    <div className="flex flex-col h-full">
      <Header title="History" />
      <div className="flex-1 overflow-y-auto">
        <div className="px-4 pt-4 pb-3">
          <SegmentedControl
            options={[{ id: 'sessions', label: 'Sessions' }, { id: 'rankings', label: 'Rankings' }]}
            value={segment}
            onChange={setSegment}
          />
        </div>

        {segment === 'sessions' && (
          ended.length === 0 ? (
            <div className="text-center py-16 px-4 text-gray-400">
              <div className="text-4xl mb-3">🫧</div>
              <div className="font-semibold">No sessions yet</div>
              <div className="text-sm mt-1">Complete a field session to see it here.</div>
            </div>
          ) : (
            <ul className="px-4">
              {ended.map(s => (
                <li key={s.id}>
                  <button onClick={() => setSelectedSessionId(s.id)}
                    className="w-full text-left py-4 border-b border-gray-100 active:bg-gray-50">
                    <div className="font-semibold text-base">
                      {new Date(s.ended_at).toLocaleDateString('en-GB', { day: 'numeric', month: 'short', year: 'numeric' })}
                    </div>
                    <div className="flex gap-2 mt-1 flex-wrap">
                      <span className="rounded-full border border-gray-300 px-2 py-0.5 text-xs capitalize">{s.conditions.weather}</span>
                      <span className="rounded-full border border-gray-300 px-2 py-0.5 text-xs capitalize">{s.conditions.wind} wind</span>
                    </div>
                    <div className="text-sm text-gray-500 mt-1">
                      {s.batch_ids?.length || 0} batch{s.batch_ids?.length !== 1 ? 'es' : ''} tested
                    </div>
                  </button>
                </li>
              ))}
            </ul>
          )
        )}

        {segment === 'rankings' && <RankingsView state={state} />}
      </div>
    </div>
  );
}
```

- [ ] **Step 5: Verify in browser**

End a session. History → Sessions: session appears with date, condition pills, batch count. Tap → detail shows each batch with per-property star ratings and overall note. History → Rankings: recipe appears with score and batch count. Condition filter chips correctly filter (test by checking a session under "mild" and filtering by "mild" vs "cold"). Tap recipe → per-property breakdown + test history.

- [ ] **Step 6: Commit**
```
git add index.html
git commit -m "feat: History tab — sessions list, session detail, rankings leaderboard"
```

---

### Task 10: Settings — JSON export

**Files:**
- Modify: `index.html` — replace `SettingsScreen` stub

- [ ] **Step 1: Replace SettingsScreen stub**

```jsx
function SettingsScreen({ state, onBack, onReset }) {
  const exportData = () => {
    const json = JSON.stringify({
      exported_at: new Date().toISOString(),
      version: SCHEMA_VERSION,
      recipes: state.recipes,
      batches: state.batches,
      sessions: state.sessions,
    }, null, 2);
    const blob = new Blob([json], { type: 'application/json' });
    const url = URL.createObjectURL(blob);
    const a = document.createElement('a');
    a.href = url;
    a.download = `bubble-lab-${new Date().toISOString().slice(0, 10)}.json`;
    a.click();
    URL.revokeObjectURL(url);
  };

  return (
    <div className="flex flex-col h-full">
      <Header
        left={<button onClick={onBack} className="tap px-2 -ml-2 text-base">‹ Back</button>}
        title="Settings"
      />
      <div className="flex-1 overflow-y-auto p-4 space-y-6">
        <div>
          <div className="text-xs font-bold uppercase tracking-wide text-gray-500 mb-2">Data</div>
          <SecondaryBtn onClick={exportData} className="w-full">Export all data (JSON)</SecondaryBtn>
          <div className="text-xs text-gray-400 mt-1 text-center">
            Downloads recipes, batches, and sessions as a backup file.
          </div>
        </div>
        <div>
          <div className="text-xs font-bold uppercase tracking-wide text-gray-500 mb-2">Danger zone</div>
          <button onClick={onReset}
            className="tap w-full rounded-xl px-4 py-3 border border-red-300 text-red-600 font-semibold active:bg-red-50">
            Reset to default recipes
          </button>
          <div className="text-xs text-gray-400 mt-1 text-center">
            Clears all batches, sessions, and custom recipes.
          </div>
        </div>
      </div>
    </div>
  );
}
```

- [ ] **Step 2: Verify in browser**

Recipes → gear icon → Settings. "Export all data" downloads a `.json` file. Open the file and verify it contains `recipes`, `batches`, `sessions`. "Reset to default recipes" shows confirm dialog, clears everything, returns to recipe list with seed recipes.

- [ ] **Step 3: Full end-to-end walkthrough**

1. Create a new recipe → verify it appears in list
2. Open recipe → volume picker → Make Batch → batch created (Field tab shows it)
3. Field tab → toggle batch status aging ↔ ready
4. Field tab → Start Session → select batch → mild, calm → Start
5. Resume session → tap batch → rate all 8 properties → Done
6. End Session
7. History → Sessions → tap session → see all ratings
8. History → Rankings → recipe appears scored; filter by "mild" → still shows; filter by "cold" → disappears
9. Tap recipe in Rankings → per-property breakdown + test history entry
10. Settings → Export → open JSON, verify all data present
11. Refresh page → all data persists (recipes, batches, sessions in localStorage)

- [ ] **Step 4: Commit**
```
git add index.html
git commit -m "feat: Settings screen with JSON export — v2 complete"
```
