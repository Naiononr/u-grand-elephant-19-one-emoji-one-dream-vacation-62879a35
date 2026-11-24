# Build Log — One Emoji, One Dream Vacation

Competition: `u-grand-elephant-19-one-emoji-one-dream-vacation-62879a35` — "One Emoji, One Dream Vacation", $2, winner takes all.
Entries close 2026-11-28T11:55:00Z; blind round 1 cutoff 2026-11-25T11:55:57Z.
Gate: `/output/entry.txt` is UTF-8 text of 1 to 8 characters, not only white space.
Judge: pairwise AI judge (z-ai/glm-5.3-flash), criteria in order: (1) exactly one emoji, plainly a dream vacation; (2) vivid at a glance, like a postcard; (3) personal and specific, one particular dream; (4) wit or surprise, a fresh pick; (5) reads instantly across cultures and screens.

## The emoji

**`⛵`** — U+26F5 SAILBOAT, 1 code point, 1 grapheme cluster, 3 bytes UTF-8, no variation selector, no skin-tone modifier, no ZWJ sequence, no trailing newline.

## Why this emoji (against the judge's criteria, in order)

1. **On-subject:** a sailboat plainly names a dream vacation — and not just the transport to one: the boat IS the holiday. A stranger sees it and thinks "sailing holiday" before reading a word.
2. **Vivid at a glance:** a white sail against blue water is a whole postcard scene in one glyph — the sea, the sun, the slow drift. You can hear the water against the hull.
3. **Personal and specific:** it points at ONE particular dream — sailing somewhere far away, the Greek islands, the open sea — not "any holiday". A beach could be a day trip; a sailboat is a trip you dream about for years.
4. **Surprising angle:** the stock picks are the beach, the palm tree and the plane. A sailboat is the fresh angle — the vacation as weightlessness and elsewhere, the feeling of being untethered rather than the place everyone photographs.
5. **Reads instantly:** a sailboat is unmistakable at small size, needs no explanation, and is a single code point (U+26F5) with default emoji presentation, so it renders the same on every screen — no VS16 or ZWJ to break.

## Rejected alternatives

- **🏖️ beach with umbrella** — the most obvious pick, and the one a hundred entrants will send. Needs a variation selector (U+FE0F, 2 code points, 7 bytes). Loses on surprise (criterion 4) and on being the stock answer.
- **🌴 palm tree** — instantly tropical, but it is a postcard cliché: it says "somewhere hot" rather than one particular dream, and it is the second-most-obvious pick after the beach.
- **✈️ airplane** — plainly travel, but it names the journey, not the vacation; it needs a variation selector (2 code points, 6 bytes), and a plane is what everyone sends when they cannot think of the trip itself.
- **🌅 sunrise** — the "first morning somewhere new" angle is lovely and it is a single code point, but a sunrise could be at home too: it does not plainly say vacation (criterion 1), and it is a likely crowd pick.
- **🌺 hibiscus** — specific and tropical, single code point, but it reads as a flower first and a vacation second; at small size it is a pink blob, and it needs the viewer to make the leap to "island holiday" (criteria 1 and 5 suffer).
- **🌊 ocean wave** — vivid and universal, single code point, but it could be surfing, a storm, or just the sea; it points at no particular dream (criterion 3).
- **🥥 coconut** — witty and tropical, single code point, but at small size it is a brown blob, and a coconut does not plainly name a vacation (criteria 1 and 5).
- **🏝️ desert island** — the ultimate dream-vacation image, but it needs a variation selector (2 code points, 7 bytes) and without one renders as text on some platforms; the sailboat says the same dream with one clean code point.
- **🛫 airplane departure** — single code point, but it is departure, not arrival: the dream is the place, not the runway.
- **🐚 shell** — the souvenir you pocket on the beach is a sweet, personal angle, but at small size it is hard to read, and it whispers where the sailboat speaks (criteria 2 and 5).

## Files created

- `main.ts` — writes `⛵` exactly, no trailing newline, to `<MAKEFUN_OUTPUT_DIR or /output>/entry.txt`, mode 0644. Self-checks the emoji (exactly one code point, one grapheme, 1–8 characters, no whitespace/control/invisible characters, no variation selector, no ZWJ sequence, no skin-tone modifier, code point inside an emoji range); treats empty `MAKEFUN_OUTPUT_DIR` as unset; `mkdir -p` the output dir; writes to a temp file inside the output dir; chmod 0644 before rename; EXDEV fallback copy+chmod; verifies written bytes, mode, byte length, and no temp file left.
- `README.md` — title, the emoji as a blockquote, why it works, Run section, and the three live make.fun badges.
- `.makefun/owner.json` — agent wallet `G9SxNPRXVnxF8DUiv1ozskprvrSZ2CeGF8sWs8FFhjfr`.
- `BUILD_LOG.md` — this file.
- No LICENSE and no `.makefun/freshness.json` created (the coordinator generates those with the kit's `init` command).
- Nothing pushed to GitHub; no bundle, no submit (the coordinator handles those).

## Revision history (thinking_revised requirement)

1. Wrote `main.ts` (first version), ran it — passed.
2. **Revised `main.ts` in a separate later message:** added an independent grapheme-cluster self-check with `Intl.Segmenter` (granularity "grapheme"), so "exactly one emoji" is verified by segmentation as well as by code-point count — a multi-code-point sequence that renders as one glyph would still be caught. Then re-ran it twice — both passed, byte-identical outputs.

## Validation results

- Run 1 (`MAKEFUN_OUTPUT_DIR=/tmp/sail-out-a`, pre-revision): exit 0; `entry.txt` = `⛵`, 3 bytes, mode 644, no temp file left.
- Run 2 (`MAKEFUN_OUTPUT_DIR=/tmp/sail-out-b`, post-revision): exit 0; `entry.txt` = `⛵`, 3 bytes, mode 644.
- Run 3 (`MAKEFUN_OUTPUT_DIR=/tmp/sail-out-c`, post-revision): exit 0; `entry.txt` = `⛵`, 3 bytes, mode 644.
- `cmp` of runs 2 and 3: byte-identical.
- Final check on the output: `"⛵"`, code points: 1 (U+26F5), grapheme clusters: 1, bytes: 3, trailing newline: false. Gate range 1–8 characters: satisfied.
- No practice data and no local check command ship with this kit (the scorer runs on the server); the kit's own gate is the 1–8 character rule above, verified locally.
