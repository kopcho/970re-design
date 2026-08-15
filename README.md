# 970.re — Design Collab

A shared, **sandboxed** workspace for designing the 970.re app. There is **no production code here** — design freely; nothing in this repo can touch the live app.

*970.re is a Northern Colorado home search by Rich Kopcho, a broker who's worked the "970" for 50 years.*

## Start here
1. **`BRIEF.md`** — the creative brief. What must stay *true* (the thesis + a handful of invariants) and **total freedom on the look.** Read this first.
2. **`models/`** — two **working, interactive** prototypes of the refine experience. Open the `.html` in a browser or on your phone:
   - `sculpt-refine.html` — tune the criteria, **watch the home-count tighten live** (no drift). Two-handle price range with detents.
   - `hunt-for-you.html` — the app **asks the one question that matters** ("22 of these back to a busy road — quiet only?") and narrows itself. No 25-item filter form.
   These are the *interactions we've proven with Rich.* Design their **look** — you don't need to reinvent the mechanics.
3. **`reference/`** — a **real API response** (`fixture-ai-search.json`, with gems + verbatim evidence) plus prior renders (`grok-render-*.jpg`) and competitor notes.
4. **`brand/`** — the approved 970.re logo (color + white).
5. **`API-AND-DATA.md`** — the data you render against: the search API, the **gems** (our moat), and the evidence model.

## The one line
Every portal **drifts** — ask for Loveland under $500K and they show Windsor at $560K to pad inventory, and their "search the description" is a dumb keyword grep. **We hold your exact line, and prove *why* each home fits with the agent's own words.** Precision you can watch and trust. *Skip the noise.*

## How we collaborate
- **Grok:** drop your work in **`designs/`** — one folder per pass (`designs/grok-01/`, etc.): images, HTML, tokens, whatever. Go bold.
- **Claude Code:** implements the winning direction onto the live engine (the real search, gems, map, parcels).
- **Rich:** steers.

Design what you'd be proud to ship on day one. The only fixed stars are in `BRIEF.md`.
