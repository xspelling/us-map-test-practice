# US Map Test Practice

A single-file study tool for a US states-and-capitals map test. Open `index.html`
in any browser — no build step, no server, no dependencies.

**Live site:** https://xspelling.github.io/us-map-test-practice/

## What it does

- **Study mode** — hover or tap any state to see its name, its capital, and a dot
  where the capital is. Toggle all names, all capitals, or hide everything.
- **Practice mode** — one state at a time. Type the state name and capital, then
  click where the capital is. Instant green/red feedback with the correct spelling
  shown, streak and score tracking, and an option to drill only the states you miss.
- **Test mode** — the whole map, like the real test. Timer runs, you click a state to
  answer it, and finished states turn gray. Submit for a score out of 50 states,
  50 capitals, and 50 capital locations, with every mistake listed against what you
  typed, plus a "retake missed only" button.

## Details

- Capital placement counts as correct when your click is inside the right state **and**
  within 40 SVG units (about 100 miles) of the real capital.
- Spelling is checked case-insensitively, ignoring extra spaces, periods, and
  apostrophes. `"St. Paul"` and `"Saint Paul"` are both accepted; everything else
  must be exact. Two-letter postal codes are also accepted for state names.
- Rhode Island, Delaware, Connecticut, New Jersey, Massachusetts, Vermont, New
  Hampshire, and Maryland are hard to hit, so there is a **Northeast** zoom button,
  a follow-cursor **Lens** magnifier you can click through, and clicks snap to the
  nearest state if they land within a few pixels.
- Michigan's two peninsulas are one path, so they always highlight together.
- Enter moves State box → Capital box → submit.
- Missed states, best streak, and best score are saved in `localStorage`.

## Map data

State boundaries come from the US Census Bureau 2010 cartographic boundary files
(20m resolution, public domain), projected with an Albers equal-area conic
projection (lat0 23, standard parallels 29.5/45.5, central meridian −96). Alaska
and Hawaii are placed as textbook-style insets in the bottom left. Every capital
coordinate runs through the same projection, so each dot lands inside its own state.
