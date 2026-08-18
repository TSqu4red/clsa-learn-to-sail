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
- **Multi-fleet scoring** (August 2026) — per-boat Fleet column in the scorer grid;
  each fleet is placed and scored as its own regatta (entrants+1 codes, throwouts,
  A8 tie-breaks all within the fleet). Standings group by fleet; CSV gains a Fleet
  column; archive winner shows first place per fleet.
- **Share-a-link results** (August 2026) — "Share results (link)" packs the whole race
  day (gzip → base64url) into the page URL hash; recipients see a read-only results
  card on their phones and can save a copy to their own archive. No backend; uses the
  phone share sheet where available, clipboard otherwise.
- **Season standings + easier grid editing** (August 2026) — "Season standings" under
  the archive merges all saved race days of a series into one score (boats matched by
  name across days, DNC for a boat absent a whole day, throwouts from the scorer's
  setting), with season CSV and share link. Also − Boat / − Race buttons beside the
  + buttons.
- **Scoring on its own page** (August 2026) — everything scorer-related moved from
  the Race Day page to `scoring.html` (same localStorage keys, so browser data
  carried over untouched). Race Day keeps a pointer card, and old
  `racecourse.html#day=…` share links redirect to `scoring.html` preserving the
  hash. SW `VERSION` bumped to `clsa-v2` with `scoring.html` precached.
- **Offline service worker** (August 2026) — `sw.js` precaches all four pages,
  network-first with cache fallback for same-origin GETs; weather API passes through.
  **Bump `VERSION` in `sw.js` on any deploy that should invalidate cached pages.**

## Next up

- **Align scorer with the club's paper form** (Race-Form-3): relabel Boat →
  "Boat / Sail #" (club records sail numbers); pre-seed the fleet autocomplete with
  the club's seven fleets (Thistle, Highlander, MC Scow, Lightning, Snipe,
  Flying Scot, Laser/Handicap); add optional Recorder and Conditions/notes fields
  (course sailed, wind) saved into the archive record and CSV.
- **Per-fleet rigging pages** — blocked on photos/steps from fleet captains.
- **Header-less embed variants** for the ClubExpress integration — pending board
  approval.

## Open questions (need answers from the club / PRC)

- **Handicap (corrected-time) scoring** — the paper form's Laser/Handicap column
  records Class + finish Time, i.e. Portsmouth-yardstick corrected-time scoring,
  which the app can't do (it scores placings only). Does the club want the app to
  score the handicap fleet from elapsed times? If yes: standard US Sailing
  Portsmouth numbers, or club-adjusted ratings?
- **Season throwout rule** — season standings currently reuse the scorer's
  worst-1/worst-2 setting. Do CLSA sailing instructions use a formula instead
  (e.g. one throwout per N races completed)?

## Parked

- **Shared/synced standings (permanent results page)** — the club asked (Aug 2026);
  share-a-link covers the immediate need. A live results page on the site still needs
  a small backend (Vercel KV/Blob + publish PIN); revisit if the club wants a lasting
  archive every visitor can browse.

## Workflow notes

- The chat sandbox cannot push; the repo is the only source of truth — commit
  everything that matters.
- Vercel auto-deploys from `main`.
