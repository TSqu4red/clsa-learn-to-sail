# CLSA Learn to Sail — Roadmap

Cross-device source of truth for what's built, what's next, and what's parked.

## Done

- **Series Scorer** (July 2026) — Low Point System per RRS Appendix A on the Race Day
  page: throwouts, scoring codes (DNF, DNS, DSQ, DNE…), A8 tie-breaks. State lives in
  `localStorage` under `clsa-race-scoring`.
- **Mobile fixes** — app bar + nav drawer on small screens, Points of Sail slider
  under the boat, drawer display/toggle repairs.
- **Race day records + CSV** (August 2026) — series/fleet/date metadata on the scorer;
  "Save this race day" archives full results (grid + standings) to `localStorage`
  under `clsa-race-archive`, with load / per-day CSV / delete; "Download results (CSV)"
  exports current standings with raw race entries including codes.
- **Offline service worker** (August 2026) — `sw.js` precaches all four pages,
  network-first with cache fallback for same-origin GETs; weather API passes through.
  **Bump `VERSION` in `sw.js` on any deploy that should invalidate cached pages.**

## Next up

- **Per-fleet rigging pages** — blocked on photos/steps from fleet captains.
- **Header-less embed variants** for the ClubExpress integration — pending board
  approval.

## Parked

- **Shared/synced standings** — needs a backend; out of scope until the club asks.

## Workflow notes

- The chat sandbox cannot push; the repo is the only source of truth — commit
  everything that matters.
- Vercel auto-deploys from `main`.
