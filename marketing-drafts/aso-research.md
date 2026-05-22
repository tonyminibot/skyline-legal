# Skyline — ASO research + keyword proposals

**Status:** research doc, not applied yet
**When to apply:** next App Store version after 2.0.3 lands (since
 changing keywords on the in-review version risks delaying the
 localization release). Realistic window: when shipping v2.0.4.

---

## Current en-US ASO state (as of 2026-05-22)

- **App name:** "Skyline: Flight Log & Globe" (29/30 chars)
- **Subtitle:** ⚠️ **empty** — biggest miss. Subtitle is a top-3
  ranking signal in App Store search.
- **Keywords field (89/100 chars):**
  ```
  flight,boarding pass,travel log,globe,trip,airline,passport,miles,private,offline,scanner
  ```
- **Promotional text:** "Snap a boarding pass — Skyline reads it
  with on-device AI and pins the flight on a living 3D globe…"

## Issues with current keyword field

1. **"passport"** — Skyline doesn't scan passports; ranking for that
   keyword brings the wrong-intent traffic. Drop.
2. **"travel log"** — accurate but already covered by "log" implicit
   from name. Spend the 9 chars on something else.
3. **"trip"** — too generic, low intent.
4. **No "tracker"** — "flight tracker" is the #1 query for this niche.
5. **No "itinerary" / "journey"** — both moderate-intent travel terms.
6. **No "airport"** — Skyline shows airports + their codes; should rank.

## Proposed keyword field (95/100 chars)

```
flight tracker,flight log,boarding pass,airline,journey,airport,globe,scanner,offline,private
```

Char-count: 95. Leaves 5 chars headroom.

What I dropped:
- `passport` (wrong intent)
- `travel log` (subsumed by "flight log")
- `trip` (low intent)
- `miles` (low intent on its own; "frequent flyer" would be better but doesn't fit char budget)

What I added:
- `flight tracker` — top query
- `journey` — synonym, moderate intent
- `airport` — direct match for airport-code searches

What I kept:
- All others.

## Proposed subtitle

The subtitle field is 30 chars max. Currently empty.

Options:

A. **"Boarding pass to 3D globe"** (24 chars)
   — pure mechanic; pairs with the name's "Flight Log".

B. **"Snap a pass, see your map"** (26 chars)
   — verb-led, emphasizes ease of use.

C. **"Your flight history, mapped"** (27 chars)
   — emphasizes the storage/visualization value.

D. **"Scan a pass, log a flight"** (25 chars)
   — explains the loop clearly.

Recommendation: **C — "Your flight history, mapped"**. Pairs naturally
with the name ("Skyline: Flight Log & Globe / Your flight history,
mapped"), reads cleanly, contains a ranking keyword ("flight").

## Promotional text — already strong

Current promo is good. Keep it.

## Localized keyword fields

For the 14 new locales, the keywords were translated via Gemini in the
2026-05-22 batch. They mostly mirror the English structure. As part of
the v2.0.4 update I should re-translate against the IMPROVED English
field so the locale fields stay accurate.

## Estimated impact

Hard to predict without baseline data (DataFast doesn't track App
Store search; ASC analytics is the source). Conservative estimate:

- Filling the empty subtitle → +5-15% search impressions (it's a
  ranking field).
- "flight tracker" keyword → captures the top niche query that
  currently rates Skyline poorly.
- Net: maybe +10-20% conversion-quality impressions in en-US.

## Action items for next deep-work cycle (after 2.0.3 approves)

- [ ] Bump version to 2.0.4 in project.yml
- [ ] Update en-US keywords + subtitle via ASC REST
- [ ] Re-translate keywords + add subtitle for the 14 new locales
- [ ] Ship a new build (no functional changes; just for the metadata
      bump). Or piggyback on the next feature build.
- [ ] Submit for review
