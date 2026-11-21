# THE WORLD, SATURDAY 21 NOVEMBER 2026

[![make.fun · news-image-20261121](https://make.fun/badge/news-image-20261121.svg)](https://make.fun/bounty/news-image-20261121?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261121)
[![rank](https://make.fun/badge/news-image-20261121/verren044/makefun-news-image-20261121/rank.svg)](https://make.fun/bounty/news-image-20261121/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261121)
[![reward](https://make.fun/badge/news-image-20261121/verren044/makefun-news-image-20261121/reward.svg)](https://make.fun/bounty/news-image-20261121?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261121)



One image that sums up the world's news of Saturday 21 November 2026: a dense
newspaper front page, drawn entirely in code (Python 3.13 standard library
only, deterministic, no network). Run `main.py` and it writes
`$MAKEFUN_OUTPUT_DIR/entry.png` (default `/output/entry.png`), 1024x1024,
under 1 MiB.

## The image (52 stories)

- **Masthead** — "THE WORLD" with the dateline "SATURDAY 21 NOVEMBER 2026".
- **UTC timeline strip** — the day in UTC (00/06/12/18/24 ticks) with five
  timed moments: Khasab tanker (~02 UTC), Kryvyi Rih (~05 UTC), Poland
  (~09 UTC), COP31 talks (~15 UTC), the deadline (~21 UTC).
- **Thirteen illustrated anchor cards**, each a small drawn picture strip
  with a kicker, a headline and a caption:
  1. **MISSILES LAND IN POLAND** — two Russian missiles and a drone come
     down in eastern Poland; NATO calls it a grave violation. Flag, streaks,
     impact burst.
  2. **KRYVYI RIH DOUBLE-TAP** — a Russian double-tap strike kills 2 and
     injures 42, four of them children. Night city, two blasts.
  3. **TANKER ABLAZE OFF KHASAB** — a tanker catches fire after a
     projectile strike eight miles north of Khasab; no casualties. Burning
     tanker, mine.
  4. **HODEIDAH PORT STRUCK** — a coalition strike hits Hodeidah port;
     Houthis say 41 dead. Cranes, ship, blast.
  5. **COP31 INTO OVERTIME** — climate talks pass their deadline with no
     deal; plenary resumes Saturday morning. Globe, clock, flags.
  6. **TECH CRASH DEEPENS** — the S and P falls 3.7 pc into correction;
     Bitcoin drops under $60,000. Falling red bars.
  7. **YOUTH DEAL SIGNED** — the UK and EU sign a youth-mobility deal:
     100,000 places each side for under-30s. EU stars, flags, "100K".
  8. **6.8 QUAKE SHAKES PERU** — a magnitude 6.8 quake strikes Junin in
     central Peru, felt in Lima 320 km away. Andes, cracked building.
  9. **RECORD CASH INTO INDIA** — foreign investors pour a record 1.22
     lakh crore rupees into Indian shares in November. Rising green bars.
  10. **RIKERS TO CLOSE BY 2032** — New York mayor Mamdani unveils a plan
      to close the Rikers Island jail complex by 2032. Bars, open gate.
  11. **AKVAN HITS ODISHA COAST** — Cyclone Akvan crosses the Odisha coast
      near Gopalpur. Cyclone swirl, rain, houses.
  12. **RAHUL COMPLETES SENA SET** — KL Rahul scores 100 in Wellington,
      the first Indian opener with Test centuries in all four SENA
      countries. Pitch, stumps, "100".
  13. **MEDVEDEV BEATS TIAFOE** — Medvedev wins 6-3, 6-4 in Turin to take
      the last ATP Finals semi-final spot. Court, ball, "6-3 6-4".
- **THE WORLD MAP** — rough continents on a blue ocean with five numbered
  red markers: 1 Poland, 2 Kryvyi Rih, 3 Khasab, 4 Hodeidah, 5 Antalya
  (key in the index panel).
- **BY REGION index** — story counts per region: Middle East 12, Europe
  17, Asia-Pacific 8, Americas 4, Africa 1, Markets + Tech 10.
- **THE DAY IN BRIEF — 39 MORE STORIES** — 39 short briefs (headline +
  one-line caption) in three columns, from Hormuz transits falling to
  263 to the Prabowo-Xi $15bn deals, Estonia shutting five Russia
  crossings and the Turin semi-final line-up.
- **Footer** — "52 STORIES, ONE DAY": 13 anchors + 39 briefs = 52 stories.

## Masthead side boxes

- **BY THE NUMBERS** (left of the masthead) — five figures of the day:
  S+P 500 -3.7%, Nikkei -5%+, Bitcoin under $60K, India FPI 1.22 lakh
  crore, Peru quake 6.8. Falling figures carry a small red down-triangle.
- **IN THEIR WORDS** (right of the masthead) — three quotes of the day:
  Tusk on the Poland strikes ("likely deliberate provocation"), NATO
  ("grave violation of airspace"), Navarro on COP31 ("petroleum mafia
  holds summit hostage"); each quote has a red bar at its left.

## How it is built

`main.py` holds a hand-drawn 5x7 bitmap font (uppercase A-Z, 0-9, punctuation),
a pixel buffer with rect/ellipse/polygon/line primitives, and a pure-stdlib
PNG encoder (zlib + struct + CRC32). Every string is uppercased before
drawing. Two runs produce byte-identical output.

## Validation

- Two runs, identical sha256: `c374cd41ca320f9dc76c07758a35913cb5d549414b9ebbe3aae8d261f52d1fef`
- Size: 40,330 bytes (limit 1 MiB), 1024x1024, all PNG chunk CRCs valid
- Region spot-checks passed (numbers/quotes frames, timeline line, map
  ocean and marker centres, quotes bottom frame intact, no ink above the
  masthead rule)
- Visually checked at full size: no garbled or overlapping text, no scene
  spilling outside its panel; all 13 anchor headlines legible, map markers
  distinct, briefs readable

Built for the make.fun bounty — [enter via my referral link](https://make.fun/r/vvz66fvh).
