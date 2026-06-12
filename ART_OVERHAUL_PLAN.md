# WAYHOME — Complete Graphic Overhaul Plan
### Target: "Amidev signature" — Mare Nostrum cozy-Mediterranean pixel language, 2025 modern setting

---

## Why the current art fails (root cause)

Every asset today is **procedural** — rectangles and ellipses placed by formulas.
That's why each restyle (Stardew pass, Eastward pass, MN palette) still reads "programmer art":
palettes changed, but shapes stayed math. Hand-pixel games look good because every sprite is
**authored** — a human (or careful pixel map) decides every cluster, every highlight.

**The fix: convert WAYHOME from procedural drawing to authored sprite sheets**, written as
pixel maps in code (same technique as the Robin sprite — the one asset that survived every
art pass, because it's authored).

---

## Art Direction Bible (Phase 0 — lock before drawing anything)

**Palette law** — derived from Mare Nostrum `sketch.js`:
- Earth: sand `#e0c898` / `#c4a878` · terracotta `#c45a38` · bark `#5a4028`
- Life: olive `#6a8e30` / `#4a6a20` · marble `#e8e0d4` / `#c8baa8`
- Sea & night: `#0d1220 → #162740 → #2a4a5a` · water `#2a6a9a` + shimmer `#7ad0c8`
- Light: lantern gold `rgb(255,180,80)` · HUD gold `#d4a040` · crystal tech glow `#44ffaa`
- Text: parchment `#e8d8b8` / bright `#f0f4e8`
- Master ramp: ~36 colors total. NOTHING outside the ramp. Deliverable: swatch sheet PNG.

**Shape law**:
- 1px soft-dark outline `#221e2c` on every sprite (MN uses alpha-180 black — same feel)
- 3-tone shading minimum (shadow / base / light) + 1 accent
- Light always from top-left; navy-tinted shadows, never grey
- Cluster detail (hand-placed 1–2px texture clumps), zero flat fills > 8px

**2025 setting law** (modern, not Roman):
- Expedition van with solar/Starlink stays — it IS 2025
- EV chargers next to gas pumps, modern road signs/guardrails, wind turbines on hills,
  container ships on the sea horizon, modern marble+terracotta towns (MN colors,
  contemporary buildings), e-scooters/cyclists in cities, café terraces
- Tech glows = `#44ffaa` (your crystal green) — phones, dashboards, chargers

---

## Phases (each ends with zoomed contact-sheet renders for your approval)

### Phase 1 — HERO ASSET: Poppy exterior (the most-seen sprite in the game)
Hand-authored pixel map ≈ **128×56**, full MN treatment:
authored panel shading, weathering clusters, decals, proper wheels with depth,
glass with sky reflection bands, roof gear silhouette designed (not stacked).
Plus 4-frame wheel rotation + 2-frame suspension bob baked as variants.
**Acceptance: a 6× zoom render you'd post on Twitter.**

### Phase 2 — World kit (driving scene is 80% of screen time)
- Tree set: 3 olive variants, 2 stone-pines, cypress, palm — all authored maps (~24–48px tall)
- Rock set ×3, guardrail, fence, modern bus stop, EV/gas station building
- Road: authored asphalt edge, worn center line, roadside gravel transition strip
- Ground: 4 authored 16×16 texture tiles per biome (not random dots)
- Sky: keep gradient engine; add authored cloud set ×4 and star clusters

### Phase 3 — Cast
- Robin v2: 16×24, 4-frame walk, idle breathing, sit pose (for the driver seat!)
- Visible Robin driving in the cab during drive mode
- Cat v2: walk ×2, sit, sleep, tail-flick
- 3 roadside NPC silhouettes (mechanic, hitchhiker, café owner)

### Phase 4 — Interior set re-author
All 16 furniture items redrawn as authored maps in the bible style;
interior shell (walls/floor/cab) gets authored paneling tiles.

### Phase 5 — Cities & landmarks
- Modern town kit: 6 authored building modules (marble + terracotta + glass storefronts,
  rooftop AC units, solar panels — 2025 Mediterranean)
- 10 landmark sprites re-authored (Eiffel, Colosseum, Atomium…) at 48–64px, real silhouette care
- Camp scenes (lake/alpine/forest/coast) as authored compositions

### Phase 6 — Post & atmosphere
Depth fog between parallax layers, authored sun/moon, rain splashes on road,
headlight cones with soft falloff, day/night color LUT tuned per biome.

---

## Process per phase
1. I author the pixel maps (in-code, zero external dependencies — stays one HTML file)
2. Render a **zoomed contact sheet** via the test rig → you approve/redline
3. Integrate → full-scene Playwright screenshots day/night → you approve
4. Next phase. No phase ships without your sign-off — it's your signature.

## Estimate
Phases 1–2 give ~70% of the visual win. Recommend starting there.
Phase order can be reshuffled; phases are independent.

## Alternative accelerator (optional)
If hand-authoring feels slow after Phase 1, we can mix in a CC0 asset pack
(e.g. Kenney pixel packs) recolored to the MN ramp — faster, slightly less "yours".
Decision point after Phase 1 review.
