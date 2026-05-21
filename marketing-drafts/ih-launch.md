# Indie Hackers — milestone / launch post

**Status:** draft, not posted
**Posting account:** Tony's IH account
**Best section to post in:** Milestones (when first source sale lands)
OR Launchpad (now, while still pre-revenue on Skyline source)
**When to post:** Tuesday morning ET (highest IH engagement window)

---

## Title

```
I launched a flight tracker that's 100% on-device — selling the source
```

---

## Body

```
Hey indie hackers 👋

I just launched **Skyline** — a flight tracker for iOS where the entire
boarding-pass parse runs on-device. Apple Intelligence + IATA barcode
parser + a SceneKit night-globe with great-circle arcs between airports.

It's free on the App Store: https://apps.apple.com/app/skyline-flight-log-globe/id6770172195

What I'm doing differently for monetization:

The App Store version is free (no IAP, no subscription). The actual
revenue model is **selling the full Xcode source** as a one-time $19
bundle on the landing page.

Reasoning:
- The kind of person who installs a flight tracker is rarely the same
  person who'll pay $5/mo for one. Subscription friction would kill
  installs.
- But the kind of *developer* who wants to ship an iOS app with
  Apple Intelligence + SceneKit but doesn't want to spend the weekend
  on integration — that person will trade $19 for ~8 hours of their
  time without thinking.
- It's the same monetization model I'm running on my other app, Pulse
  (a Paddle revenue dashboard) — which has gotten 2 source-bundle
  sales in the first 48h on a much smaller surface.

What's in the source bundle:
- Full Xcode project (xcodegen-managed, all Swift source)
- SwiftUI + SceneKit 3D globe with arc rendering + atmosphere glow
- The boarding-pass parsing pipeline (BCBP + LLM + heuristic)
- SwiftData persistence, IATA airport DB, AGENTS.md for AI agents
- Personal + commercial license (fork + rebrand allowed)
- 7-day money-back guarantee via Polar

Landing: https://flownmap.com

Open to feedback on:
- Should the App Store version eventually get a paid IAP for some
  feature? Curious how IH folks feel about "free app, paid source"
  vs. "free app + IAP".
- The $19 price — is that right for a one-time iOS source bundle?
  I'm tempted to test $29 once I have more conversion data.

Happy to share specifics about the SwiftData migration patterns or the
on-device LLM integration if anyone wants to compare notes.
```

---

## Notes / playbook

- IH responds well to the "milestone vs. ask" structure — celebrate
  the launch, then ask one specific question. Don't ask "what do you
  think?" — ask a constrained question like "$19 vs $29?".
- Reply to every comment in the first 24h. IH's algorithm is engagement-
  weighted but slower than HN — sustained activity > burst.
- Cross-link this to the X thread if both go up in the same week —
  IH crowd often follows up on indie-X handles.
- If a comment asks about Pulse, link it but don't pitch it. The post
  should stay about Skyline.
- Don't reply to "why not $5/mo subscription" with defensiveness. The
  honest answer (above) is the right one.
