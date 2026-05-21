# X (Twitter) — Skyline source launch thread

**Status:** draft, not posted
**Target audience:** iOS devs / indie makers / "build your own X" Twitter
**Goal:** sell the source bundle ($19) — App Store app is just legitimacy
**Posting account:** @trungdq88
**Cadence:** main tweet → wait for 30+ likes → drop the source-sale reply
**When to post:** Tony's call. Best windows historically: weekdays
8-10 PM ICT (= 8-10 AM PT, dev-Twitter prime time).

---

## Main tweet (with attached video / GIF of the globe scanning)

```
I built a flight tracker that's 100% on-device.

Snap a boarding pass → it parses on-device with Apple Intelligence + IATA
barcode → pins the flight as a glowing arc on a 3D night-lit globe.

No account. No servers. Works in Airplane Mode.
It's on the App Store, but I also sell the source.

flownmap.com 🌍
```

**Media:** the existing `shots/1-globe.png` (post-compression, 64KB) or
better — a short screen recording of the scan→pin animation. If we don't
have one yet, I should capture one before Tony posts (TODO: build out a
30-sec recording from the simulator next cycle).

---

## Reply 1 (the "how it works" thread — fires automatically when main hits ~30 likes)

```
The pipeline is the part I'm proudest of.

A boarding pass goes through three stages, all on-device:

1. IATA BCBP barcode parser — when the QR is readable, this gives
   ground truth in <50ms.
2. On-device LLM extractor (Apple Intelligence) — for passes where the
   barcode is missing or damaged, it reads the visible text.
3. Heuristic fallback — last resort if the LLM can't lock on.

The barcode and LLM cross-check each other when both fire. Verification
is logged — you can see exactly which stage produced each field.

It's iOS 18+ for the LLM bit. Older devices use steps 1 and 3.
```

---

## Reply 2 (the source pitch — the conversion ask)

```
I'm also selling the full Xcode project as a one-time $19 buy.

- Full Swift source (SwiftUI + SceneKit night-globe + boarding-pass parser)
- The 3D globe (atmosphere glow, arcs, IATA airport DB)
- AGENTS.md — feed it to Claude/Cursor and your AI agent gets oriented
  in seconds
- Personal + commercial license — fork it, rebrand it, ship your own
- 7-day money-back guarantee

If you've been wanting to ship an iOS app that uses Apple Intelligence
+ SceneKit but didn't want to spend a weekend wiring it up:

flownmap.com (scroll to "Own the source")
```

---

## Alt main tweet (if first doesn't pop in 24h — swap and reschedule)

```
"Snap a boarding pass" apps usually feel magical and slightly slow.

I rebuilt Skyline so the entire parse pipeline is on-device. The barcode
parser hits ground truth in <50ms; Apple Intelligence handles the rest.
Then I pin the flight as an arc on a night-lit 3D globe.

No accounts. No servers. Works on planes.

App Store + source code: flownmap.com
```

---

## Notes for future Tony

- Keep the third stage of the pipeline (heuristic) in the thread —
  devs respect "defense in depth" as a sign of real production work.
- Don't lead with the source-sale. Lead with the visual. Source-sale
  is reply 2 — by then the algorithm has surfaced the post to people
  predisposed to engineering details.
- If the main tweet stalls under 10 likes in 6h, kill it and try the alt
  — don't bury it in the thread, the algorithm sees engagement-per-impression
  and a flat main tweet hurts the reply pickup.
