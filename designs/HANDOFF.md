# HANDOFF — Grok ↔ Claude Code

**How we use this file**
- Newest entry always at the **top**.
- Grok writes design decisions, what was delivered, and what Claude should implement or react to.
- Claude Code writes what it implemented, any deviations, questions, or blockers back to Grok.
- Keep entries short, dated, and actionable. This is our conversation log + engineering handoff.

---

## 2026-08-15 — Grok → Claude (Listing Detail v2)

### Delivered
- `designs/grok-01/listing.html` — self-contained, mobile-first, clickable mock of the **listing detail** screen.
- `designs/grok-01/NOTES.md` — type + palette rationale.

### Core product truths locked in this screen
1. **Exact Match is the badge**, but the *agent’s verbatim quote* is the proof. No bare “96%” or “98% Exact Match”.
2. Confirmed gems show `✓` + green treatment + the exact quote from the MLS remarks.
3. Potential gems show `~` + amber + “(possible)” — never rendered as “no”.
4. Missing gems are simply absent (never shown as negative).
5. Re970 is treated as a **signature action** (burnt-orange `#E85D04`), not a generic map button.
6. Lead-gen is woven in: dual CTAs (“Schedule a look” + “Text Rich”) + Rich’s agent card.

### Real data used
Listing from `reference/fixture-ai-search.json`:
- **1246 4th St, Loveland** — `$640,000`
- Strongest multi-gem match in the fixture (hot tub + new roof + solar all *asserted*).

### Visual direction (current)
- Light paper background (`#FAF9F5`) + deep forest ink (`#0F2C1C`).
- Clean, modern, high-trust (evolved from the earlier light mocks Rich liked).
- Serif for price + evidence quotes; system sans for UI; mono for labels.
- Gold for confirmed evidence accents; orange reserved for Re970 only.
- BHGRE green is acknowledged but we are not locked to pure `#339933` — current palette is a richer Northern Colorado interpretation.

### What I need from Claude Code
1. **Implement this listing detail screen** against the real data shape in `API-AND-DATA.md` and the fixture.
2. Preserve the evidence model exactly (asserted → ✓ + quote, potential → ~ + quote, absent → nothing).
3. Make the gallery, save, share, schedule, and Re970 actions real (or clearly stubbed with the same visual weight).
4. Flag any data fields that are missing or need clarification before you ship.
5. Once the listing detail feels solid, we should next tackle **Results cards** (so the Exact Match treatment is consistent from list → detail).

### Open questions for Claude / Rich
- Do we want the bottom sticky bar to always show “Message / Request info”, or should it change based on auth state?
- Is the current light palette close enough, or should we pull harder toward official BHGRE `#339933` + coral?

— Grok
