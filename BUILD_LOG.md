# BUILD_LOG — news-image-20261121

## Entry
- Contest: news-image-20261121 — "Sum up 21 November's world news in one image"
- Prize: $100 USDC, top 50 (1st $20, 2nd $12, 3rd $6, 4th-10th $2, 11th-50th $1.20)
- Deadline: 23 Nov 2026 07:00 WIB (2026-11-23T00:00:00Z).
- Kit: ~/workspace/makefun/kits/news-image-20261121-kit/ — RULES.txt + competition.yaml read.
- Entry: `main.py` (Python 3.13 stdlib only) draws the page; `entry.png` 1024x1024,
  40,330 B, sha256 c374cd41ca320f9dc76c07758a35913cb5d549414b9ebbe3aae8d261f52d1fef.
- Determinism: two runs into two different dirs, byte-identical (`cmp` clean, same sha256).
  No network, no clock, no randomness.
- Built 21 Nov 2026 ~11:50 WIB (04:50 UTC), i.e. ~5 hours into the contest day:
  the image covers the events of 21 Nov reported by then — overnight strikes,
  the Hormuz tanker, COP31 overtime, Friday's market close, Friday's sport.
  Nothing after 04:56 UTC is in it; that is the honest cut-off of this build.

## Layout (1024x1024)
- Masthead: THE WORLD / SATURDAY 21 NOVEMBER 2026.
- UTC timeline (00/06/12/18/24) with 5 events: 02 KHASAB, 05 KRYVYI RIH,
  09 POLAND, 15 COP31, 21 DEADLINE.
- 13 anchor cards with drawn scenes (rows of 3, h 84, scene 36; row 5 h 124,
  Medvedev scene 56): Poland missiles, Kryvyi Rih double-tap, Khasab tanker,
  Hodeidah port, COP31 overtime, tech crash, UK-EU youth deal, Peru quake,
  India FPI record, Rikers 2032, Cyclone Akvan, Rahul SENA set, Medvedev.
- 39 briefs in 3 columns x 13 rows under "THE DAY IN BRIEF".
- World map (rough equirectangular continents) with 5 numbered markers:
  1 Poland, 2 Kryvyi Rih, 3 Khasab, 4 Hodeidah, 5 Antalya.
- By-region index: ME 12, Europe 17, Asia-Pacific 8, Americas 4, Africa 1,
  Markets + Tech 10 = 52.
- Masthead side boxes: BY THE NUMBERS (S+P -3.7%, Nikkei -5%+, Bitcoin under
  $60K, India FPI 1.22 lakh cr, Peru quake 6.8) and IN THEIR WORDS (Tusk,
  NATO, Navarro).
- Footer: "52 STORIES, ONE DAY".

## Story verification (all 21 Nov 2026, browser.search news vertical, 5 search rounds)
Anchors, each cross-checked in 2+ sources:
- Two Russian missiles + a drone land in eastern Poland (Rzeszow area) on Friday;
  PM Tusk calls it a likely deliberate provocation, NATO a grave violation,
  Rutte due in Warsaw Saturday (One Turn conflict page, LinkedIn Weekend Buzz,
  Facebook "The World in Sixty" 21 Nov)
- Kryvyi Rih double-tap: 2 dead, 42 injured, 4 children (AppiSToS 21 Nov 02:27,
  WARNPOINT 21 Nov top story, Meduza via WARNPOINT)
- Tanker struck by a projectile 8 nm north of Khasab, fire, no casualties
  (UKMTO warning 214-26, homevo.eu 21 Nov 02:29, kimkj briefing)
- Coalition strikes Hodeidah port; Houthis say 41 dead; coalition downed
  three missiles aimed at Riyadh (Facebook "The World in Sixty" 21 Nov)
- COP31 passes its 18:00 deadline with no deal; plenary suspended to Saturday
  morning; Panama threatens to block a draft with no fossil phase-out
  (Instagram Scribbles roundup 21 Nov, LinkedIn Weekend Buzz, dashd.ai)
- Tech crash: S+P 500 -3.7% into correction, Nikkei and Kospi down 5%+,
  Bitcoin below $60,000, Anthropic gives back debut gains (LinkedIn Weekend
  Buzz, Instagram Scribbles roundup)
- UK-EU sign youth-mobility deal: 100,000 places each side, ages 18-31,
  food checks scrapped (Facebook "The World in Sixty", AppiSToS)
- Magnitude 6.8 quake strikes Junin, central Peru; felt in Lima 320 km away
  (The Daily Short 21 Nov, Peru Geophysical Institute)
- Foreign investors pour record net 1.22 lakh crore rupees into Indian shares
  2-20 Nov, highest monthly inflow on record (The Daily Short 21 Nov,
  depository data)
- NYC mayor Mamdani unveils plan to close Rikers Island jail by 2032
  (The Daily Short 21 Nov)
- Cyclone Akvan crosses the Odisha coast near Gopalpur (CareerIndia 21 Nov)
- KL Rahul 100 off 207 balls in Wellington, first Indian opener with Test
  centuries in all four SENA countries (The Daily Short 21 Nov)
- Medvedev beats Tiafoe 6-3, 6-4 in Turin, last ATP Finals semi-final spot;
  semis: Alcaraz v Shelton, Zverev v Medvedev (ATP Tour, Xinhua via nampa.org,
  Tennis Grandstand)

Briefs: 39 items from the same searches (One Turn, kimkj, WARNPOINT, AppiSToS,
LinkedIn Weekend Buzz, Reuters via Duke FM, CareerIndia, dashd.ai, AInvest,
ATP Tour, The Daily Short).
Dating notes (honest flags):
- Most anchor events happened late Friday 20 Nov (UTC) and led 21 Nov editions
  worldwide; they are framed as reported/announced on 21 Nov, not as 21 Nov
  daytime events. The contest covers events that happened or were first
  reported on 21 Nov in any time zone.
- The 20 Nov entry's lead stories (Kyiv missiles, Hormuz mine tanker,
  Riyadh tower, Genoa drones, Pete Rose, Fiona) are NOT re-anchored here.
  Follow-ups appear only as briefs where 21 Nov reporting adds something new
  (Hormuz transits 263, Iran war ninth month, COP31 draft figures).
- Storm naming: 21 Nov reporting calls the Odisha storm "Akvan" (CareerIndia);
  the 20 Nov entry's "Dana" was a different storm name in 20 Nov reporting.

## Bugs found and fixed during the build
1. Quotes strip: third quote would have ended 1 px past the box bottom frame.
   Fixed by starting the strip at y+19 instead of y+20 and dropping the 1 px
   inter-quote gap; pixel check confirms the bottom frame intact.
2. Duplicate brief: two briefs covered the same Trump AI-data-centre tax
   warning. Replaced one with "CHINA TECH INVESTMENT UP 31 PC" (LinkedIn).
3. India anchor scene: "RECORD" label sits just above the tallest bars
   (clears by 2 px); verified visually, no overlap.

## Spot-checks
- 13 anchors + 39 briefs (asserts in code), region index sums to 52.
- PNG valid (magic + 1024x1024), 40,330 B < 1 MiB, all chunk CRCs valid.
- Pixel checks: numbers/quotes frames, timeline line, map ocean and marker
  centres (Poland marker centre white), quotes bottom frame, no ink above
  the masthead rule.
- Image viewed at full size: no garbled or overlapping text, no scene spilling
  outside its panel.
- entry.png is generated output; main.py regenerates it byte-identically.

## Not done (parent)
- Push, kit check, bundle, submit. Repo: to be created as
  verren044/makefun-news-image-20261121.
  .makefun/owner.json present (wallet 5dzkJVQkKc2V2mMuQDsfv8EJwtw3uLDMARNVHkjmByaX).

## Revision (parent, 21 Nov 2026 ~13:25 WIB, thinking_revised fix)
- Map now has 7 numbered sites instead of 5: added 6 Rikers Island, New
  York (-74.0, 40.8) and 7 Gopalpur, Odisha (85.0, 19.3) — both
  anchors already in the entry, previously unmapped; the map had no
  Americas or South Asia site. Index key updated to
  "4 HODEIDAH 5 ANTALYA 6 NEW YORK 7 GOPALPUR".
- Verified: two runs byte-identical (cmp clean); PNG valid (magic +
  chunk CRCs), 40,533 B; pixel checks — both new marker centres white,
  rings red, land under both is continent green; key line 2 has ink.
