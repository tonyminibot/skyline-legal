# Hacker News — Show HN post

**Status:** draft, not posted
**Goal:** front-page discussion → traffic → source-bundle conversion
**Posting account:** Tony's own HN
**When to post:** Tuesday or Wednesday, **08:00 UTC** (the canonical HN
prime window). NEVER Friday afternoon or weekends.
**Pre-post:** make sure flownmap.com loads in <1s (already does after the
recent perf cycle) and the Polar checkout works.

---

## Title (keep under 80 chars; HN title rules are strict)

```
Show HN: Skyline – an on-device boarding-pass scanner with a 3D globe
```

(Variant if the above feels too marketing-y: `Show HN: I rebuilt my
flight tracker to be 100% on-device`)

---

## URL field

```
https://flownmap.com
```

---

## First comment (post immediately after submitting — HN convention)

```
Author here. Quick context on what's new vs. the dozens of other "log
your flights" apps:

The entire boarding-pass parse runs on-device. Three stages in order of
preference:

1. IATA BCBP barcode parser — when readable, ground truth in <50ms.
2. Apple Intelligence (the on-device LLM Apple shipped in iOS 18.1) —
   reads the visible text when the barcode is unreadable.
3. Heuristic OCR fallback for pre-AI devices.

Stages 1 and 2 cross-check each other when both fire, which catches
the failure mode where the LLM hallucinates an airport code that's
phonetically similar to a different one. The verification metadata
is shown in the UI so you can see exactly which stage produced
each field.

Other tradeoffs that might be interesting:

- SceneKit for the globe instead of a web map. The arcs are great-circle
  paths rendered as splines; the night-lit Earth texture is a single
  4K JPEG I hand-edited (NASA's blue marble is too vibrant at the small
  on-screen size).
- SwiftData for persistence — first app I've shipped where SwiftData
  was the right call instead of GRDB. The Flight model is small enough
  that the trade-off (less control over migrations vs. less boilerplate)
  came out in SwiftData's favor.
- No account, no servers, works in Airplane Mode (the boarding-pass
  parse fits the niche perfectly).

I'm also selling the full Xcode source as a one-time $19 bundle (on the
landing page) for folks who'd rather fork it than reverse-engineer it.
Personal + commercial license. Designed so an AI coding agent — with
the included AGENTS.md — can orient itself in seconds.

Happy to answer questions about the pipeline, the SceneKit globe, or
the on-device LLM bit specifically.
```

---

## Notes / playbook

- Do NOT preface the title with emojis or marketing adjectives. HN
  hates that. Mod team will edit the title or kill the post.
- Stay in the comments for the first 2h after posting. Reply to every
  question. HN's algorithm rewards author engagement.
- If someone asks about the price or compares to similar apps,
  acknowledge the alternatives by name. Defensiveness reads poorly.
- If the post hits the front page, expect ~3,000-8,000 visitors in
  24h. The Polar checkout has handled higher; no infrastructure prep
  needed. Just keep flownmap.com responsive.
- Don't link the source-bundle Polar URL in the title or first comment
  body directly. The landing page does the conversion; HN will downrank
  posts that look like pure sales pitches.
