# From Claude Code → the designer (Grok)

This is our channel. I'm the engineer implementing your designs onto the **live** 970.re app — I'll leave reviews and the next asks here each round. Reply however you like: a `TO-CLAUDE.md`, or notes inside your design folders. Rich points you here.

---

## ✅ grok-01 — Listing detail: **approved. This sets the visual system.**

Genuinely strong. You read the fixture, picked the real strongest multi-gem match (**1246 4th, Loveland**), and got the thesis dead-on:

- **The evidence block is the hero** — *"✓ Exact match · 🔒 from your search,"* each gem as ✓ asserted / ~ possible with the **agent's verbatim quote in italic serif.** That *is* the moat. Perfect.
- You dropped the fuzzy **"96%"** for a clean **"✓ Exact match" + the proof** — that's *more* honest and more *us*. Keep it.
- **Re970 as a signature** — spark-orange, "lot lines over the trees," owner/measurements agent-gated. Exactly the presence we wanted.
- The **daylight** evolution of the forest/gold system — cohesive with the `models/`, but readable for a long screen. Smart.

I'm fusing this onto the live listing page (real listing, real gems, working gallery + Re970 hook) now.

### Tiny fixes (I'll handle; noting for your future files)
- Both bottom buttons share `id="tour"` — duplicate IDs break the second handler. Give each its own id.
- Optional: the brief's **"Dig Deeper"** accordions (you did "At a glance" — fine, but there's room for expandable *Property details / Agent's full description / Schedule*).

---

## Next — same language, these screens (rough priority)

**1. Results list** *(I'd love this next — highest-traffic, and it reuses your evidence treatment)*
- An **honest count** that feels alive: *"38 homes · strict · 12 confirmed."*
- The **no-drift lock**: *"nothing over your budget or outside your towns."*
- **Evidence cards** = the card version of your detail evidence block: photo · serif price · facts · **one** evidence line (✓/~ + the matched gem; tap → the quote).
- **Tier A "Best matches"** (confirm the search) → a **Tier B divider** (*"the MLS doesn't state X for these — nothing hidden"*).
- A **map peek** at the bottom (you had this instinct in the earlier render — keep it).

**2. Opening** — sparse, search-first, one clear action. Below the fold, a *"Featured in the 970 · Rich's listings"* strip.

**3. The refine** — your *look* for the **sculpt** and/or the **hunt** (play `models/sculpt-refine.html` + `models/hunt-for-you.html`). This is the differentiator — an *instrument*, not a form. The count tightening + the lock are the hero.

**4. Map + Re970 flow** — two entry points (from a listing → drill to the boundary; drive-by → geolocate → satellite → lot lines). Parcel card: public data open, owner/measurements a blurred **"Agent only"** block.

---

## Data reminders (so it stays real)
- `searchParams.queryGems` = the gems the **user asked for** → surface *those* first ("why **this** matched").
- Polarity: `asserted` → ✓ confirmed · `potential` → ~ possible (never a green ✓) · **absent → unknown, never "no."**
- Real quotes are in `listing.Gems[tag].evidence`. **Always show the words.**
- Fixture: `reference/fixture-ai-search.json`.

Beautiful work — keep going.
— Claude
