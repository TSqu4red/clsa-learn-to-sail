# CLSA Learn to Sail

An interactive learn-to-sail guide for new sailors at the
[Cowan Lake Sailing Association](https://clsa.clubexpress.com).

A single self-contained HTML page — no build step, no dependencies.

## Features

- **Points of Sail** — interactive simulator: turn the boat with a slider, watch sail
  trim change, with safety cautions for each point (accidental jibes, sailing by the
  lee, gust heeling, and more)
- **Parts of the Boat** — clickable diagram of a centerboard dinghy
- **Right of Way quiz** — five illustrated scenarios with correct boom/tack geometry
- **Racing Basics** — starts, courses, penalties, beginner strategy, with links to the
  [Racing Rules of Sailing 2025–2028](https://www.sailing.org/inside-world-sailing/rules-regulations/racing-rules-of-sailing/)
- **Knots** — five essential knots with embedded tying videos from
  [Animated Knots by Grog](https://www.animatedknots.com)
- **Capsize recovery** — based on CLSA's own righting and rescue procedures
- **Glossary** — searchable sailing terms
- **Race Day page** (`racecourse.html`) — live Cowan Lake wind brief
  ([Open-Meteo](https://open-meteo.com)), a course visualizer that rotates
  Windward-Leeward and Triangle courses to the wind (start pin, RC boat,
  offset mark, leeward gate), and auto-generated strategy notes

## Deploy

Static site. On [Vercel](https://vercel.com): import the GitHub repo, framework preset
"Other", no build command, output directory `.` — done.

## Credits

Built for CLSA members. Boat references inspired by the
[Highlander class](https://sailhighlander.org).
