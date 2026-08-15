# The data you render against

You don't need the backend — build against `reference/fixture-ai-search.json` (a real response). This is the shape.

## Search
```
POST https://api.970.re/ai-search        (the app calls a same-origin proxy: /api/ai-search)
body:   { "query": "<natural language>", "semantic": true }
```
Returns:
```jsonc
{
  "listings": [ /* see below */ ],
  "total": 344,
  "summary": "Found 344 homes …",          // human recap — good for a results header
  "chips":   [ /* the parsed query — the criteria row */ ],
  "searchParams": { /* resolved query, incl. queryGems */ }
}
```

## A listing (the fields you'll render)
`ListingKey · ListPrice · UnparsedAddress · City · PostalCode · BedroomsTotal · BathroomsTotalInteger · LivingArea · LotSizeAcres · GarageSpaces · StandardStatus · PhotosCount · Media[{MediaURL, Order}] · Latitude · Longitude · Gems`

Photo = `Media[0].MediaURL` (real, ordered — don't guess). Status pill when `StandardStatus !== "Active"` (Coming Soon, Pending…).

## Gems — the moat (evidence mined from the agent's own remarks)
```jsonc
listing.Gems = {
  "new_roof": { "evidence": "the roof is outfitted with premium Class 4 shingles",
                "polarity": "asserted", "confidence": 0.9 },
  ...
}
```
- **`asserted` → confirmed (✓).  `potential` → possible (~).  key absent → *unknown* (never "no").**
- The **11 tags** (→ human label): `pool`→Pool · `hot_tub_included`→Hot tub · `new_roof`→New roof · `solar`→Solar · `mother_in_law_suite`→Mother-in-law suite · `financing_incentive`→Financing incentive · `no_exterior_maintenance`→No exterior maintenance · `furnished_included`→Furnished · `motivated_seller`→Motivated seller · `no_upstairs_neighbors`→No upstairs neighbors · `main_floor_laundry`→Main-floor laundry
- `searchParams.queryGems` = the gems the user asked for.

## The card's "why" (the thing that makes us un-fakeable)
```
matched = queryGems.filter(t => listing.Gems?.[t])
```
- Prefer an **asserted** match → **`✓ <label> — "<evidence quote>"`**
- If only **potential** → **`~ <label> (possible) — "<quote>"`** (quieter, amber, not a green ✓)
- If **none** → no evidence line (this is a Tier-B "matches everything else")
- **Never** claim a feature whose gem tag isn't present. **The quote is the proof** — a bare "96% match" is not enough on its own; show the words.

## Tier A / Tier B (honest grouping — never hide)
- **Tier A — "Best matches":** confirms every requested gem (`asserted`). Shown first.
- **Tier B — the rest:** honestly labeled ("the MLS doesn't state X for these — nothing hidden"). Still fully reachable.

## No-drift (the promise to make visible)
The engine is **strict** on the hard asks (price / location / beds) — a home outside them **never** appears. There's a live, honest count that only moves when *you* change the plan. Make the user *feel* that: a lock, "0 over your budget," the count tightening. See `models/` — both prototypes are built around this.

## Fixture
`reference/fixture-ai-search.json` — a real response for *"Loveland under $700K, 3+ bed, pool or hot tub, new roof"* (6 listings with real gems + quotes, e.g. *4204 Martinson, Loveland → new_roof, asserted, "premium Class 4 shingles"*).
