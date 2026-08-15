# 970.re — Design Brief (for Grok)

**Design the whole visual system — it's yours. Take a real aesthetic risk. Below is only what must stay *true*, never how it must *look*. Where you'd normally follow a spec, design instead.**

---

## What it is
970.re is a Northern Colorado home search built by **Rich Kopcho**, a broker who's worked the "970" for 50 years. Same MLS listings as Zillow / Redfin / Homes.com — the reason to switch is **trust**.

## The one idea (the whole thesis)
Every other portal **drifts**: you ask for Loveland under $500K and they quietly show Windsor at $560K to pad inventory, sort by *their* algorithm, and their "search the description" is a dumb keyword grep. **We hold your exact line, and we prove *why* each home fits — quoted from the agent's own words.** Precision you can watch and trust. *Skip the noise.*

## Non-negotiables (product truths — everything else is yours)
1. **No drift.** Strict on the hard asks (price, location, beds) — a home outside them never appears. Make it *visible* so the user *feels* the search holding the line: an honest, live count; a "strict" lock; "0 homes over your budget."
2. **Evidence, quoted.** Show *why* a home matched with the **agent's verbatim words** — e.g. *"✓ Fenced yard — 'new 6-ft privacy fence, 2023'."* Show **confidence**: confirmed (✓) vs. possible (~). The quote is the proof — a bare "96% match" isn't enough on its own; the words are what nobody can fake.
3. **Never render *unknown* as *no*.** Never hide a home for something we can't verify. Best matches (confirmed) first; then the rest, honestly labeled ("the MLS doesn't state X for these — nothing hidden").
4. **Refine is a conversation, not a 25-item form.** Zillow makes you tweak 25 filters and hit Apply. We either let you **sculpt** (tap a criterion, watch the count tighten live) or the app **asks the one question that matters** ("22 of these back to a busy road — quiet only?") and narrows itself. *(We have working interactive models of both — ask to see them.)*
5. **Agent-tier gating.** Public: boundaries, zoning, lot size. **Owner name / mailing address / precise measurements are behind an agent sign-in** (blurred "Agent only" until unlocked).

## The surfaces (MVP)
- **Opening** — sparse, search-first, one clear action: describe your home. *(You already nailed this — "Find the right home. Skip the noise.")*
- **Results** — evidence cards + a best-matches / rest split + an honest count. *(Keep your "map peek at the bottom of the list" — that's great.)*
- **Refine** — the sculpt / question-asking narrowing (not a filter drawer).
- **Listing** — photos, the exact-match + the **quoted** evidence, "dig deeper," talk-to-Rich.
- **Map** — results as **price dots that cluster** when zoomed out; **draw-an-area**: trace a shape and it keeps only the homes inside, still honoring every other filter.
- **Re970 parcels** — the moat (below).
- **Saved / Alerts** — the zero-results moment is the conversion: *"Nobody's selling this exact home today — I'll text you the minute one hits."*
- **Agent (Rich) + "What's my home worth?"** — lead-gen woven in, not bolted on.

## How the Map + Re970 work (our differentiator — design these with love)
Two ways in, one parcel view:
- **From a listing:** tap the map → drill in on the *same* map until the **parcel boundary draws** over the property.
- **Drive-by:** she's passing a vacant lot, or a house where trees hide the lot lines. She hits the **Re970 button** → it **geolocates her, flips to satellite, and draws the lot lines right over the trees.** Tap any parcel → its card.
- **Parcel card:** public data open (address, lot size, zoning, parcel ID); **owner / mailing / precise measurements = a blurred "Agent only" block** with "sign in to unlock." Source: the free statewide Colorado parcel layer (2.6M parcels).

Re970 should feel like a **signature action** — it's the thing Zillow *can't* do. Give it presence.

## Voice / identity
Northern Colorado. **Rich Kopcho**, BHGRE Neuhaus, Loveland. Real towns: Loveland, Fort Collins, Windsor, Greeley, Berthoud. Confident, honest, a little proud of the 970. **It's `970.re`** — not a generic "Homely," not Seattle/Phoenix/Austin.

## Your freedom
The look is entirely yours — palette, type, motion, layout, personality, the whole language. The only fixed stars are the truths above. Surprise us.
