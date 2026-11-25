# Publishing — The Lenwood Gazette

## Edition build (each of Morning / Midday / Evening)
1. Poll the Safety Wire: AlertSCC, City of San Jose emergency alerts, SJFD/SJPD public
   feeds, CHP Golden Gate incidents, NWS Bay Area, Valley Water, VTA service alerts.
2. Pull Today's + Week Ahead public events from the paper's own events desk:
   City of San Jose events calendar, SAP Center, San Jose Theaters, Children's Discovery
   Museum, The Tech Interactive, San Jose Public Library events.
3. Around Town: city public notices, road-work/permit postings, public meeting agendas.
4. Community Wire: official/public Facebook pages only — summarize in our own words,
   attribute to the posting page, link the original. Never copy wholesale. No private
   groups unless Dave names them; never join a group unilaterally.
5. Weather: NWS API, San Jose / Bay Area zone.
6. Write the Lead by editor's judgment. Quiet day = honest quiet-day lead.
7. **This Day in History (standing feature, added Oct 31, 2026 at Dave's direction):**
   keyed to the edition's calendar date. The **Morning Edition sets it**; Midday and
   Evening **carry it forward unchanged** unless correcting it. A few crisp items, each
   with its year, in our own words from public historical sources, attributed/linked.
   **Local first** — San Jose & Santa Clara Valley (1777 pueblo founding, the 1850
   first-state-capital era, the orchard years, Winchester and tech milestones; standing
   sources: San Jose Public Library's history timeline, History San José, NPS/local
   landmark records). A wider California/national item runs only when the local well
   runs dry for that date — and the section may say so honestly. Lives in the front
   page sidebar (`#history`, after Weather). (An Oct 31 relay briefly moved it and
   the Star Chart into the main column; Dave clarified that layout call was for the
   Fiddletown paper only, and the move was reverted the same morning.)
8. **Weather Events (standing treatment, added Oct 31, 2026 at Dave's direction —
   "obviously the weather events"):** weather *events* are news, not just a forecast
   box. Each Morning Edition scans the NWS Bay Area forecast discussion and outlooks
   for events — storm systems moving in, atmospheric rivers, heat and freeze events,
   wind events, air-quality changes — and writes them as news items in the Weather
   Events block (`#weather-events`, under the Safety Wire): what it is, when it
   lands, what it changes. **Safety-relevant events are promoted into the Safety
   Wire itself**, and qualifying ones (severe-weather warning, flood notice) fire the
   out-of-cycle banner per the hourly poll rule. Set in the Morning; updated at
   Midday/Evening whenever the event picture changes.
9. **Car Shows (standing section, added Nov 1, 2026 at Dave's direction):** the paper
   carries a 🏁 Car Shows section (`#car-shows`, main column after The Week Ahead)
   listing Bay Area car shows — **South Bay first** (San Jose, Willow Glen, Morgan Hill,
   Los Gatos, Santa Clara, Gilroy, the Peninsula), **North Bay included** (Marin, Sonoma,
   Napa), and a rare "worth the drive" exception for a major show just outside (e.g.
   Goodguys at Pleasanton). One-off shows AND recurring meets (cars & coffee, cruise-ins)
   both count. The car-show desk sweeps the public calendars every edition
   (CarCruiseFinder, NorCal Car Culture, club calendars like the Redwood Empire Early
   Ford V8 Club, Goodguys, Eventbrite public listings), verifies date/time/place
   against the listing, and writes items in our own words with the source credited.
   Each Morning Edition rebuilds the section (this weekend first, then the next two
   weeks); Midday/Evening carry it forward unless a listing changes. Public events
   only, same privacy gate.
   **LINKS RULE (Dave, Nov 1, 2026): every listed event's name links to its real event
   or source page** — the organizer's event page, the venue's event page, or the
   calendar page the listing was sourced from. Only URLs actually verified (opened or
   returned by search) — never a guessed or constructed address. An event with no
   findable page runs unlinked, and the edition report names it as unlinked. Verify
   date/day/terms against the ORGANIZER's current page when one exists — calendar
   aggregators go stale (the Nov 1 Cars & Croissants correction: the organizer's 2026
   season runs Sundays, not the fourth-Saturday pattern the blogs still repeat).
10. **Star Chart (standing feature, added Oct 31, 2026 at Dave's direction):** tonight's
   sky over San Jose & the valley — an evening star chart, moon phase, which planets
   are up, and notable events (meteor showers, bright passes, eclipses when they
   come). **Pitched honestly for valley light pollution:** lead with what a city
   reader can actually see (Moon, planets, boldest stars), then what a short drive
   up Mt. Hamilton toward Lick Observatory opens up. Public astronomy sources
   (EarthSky, StarWalk, timeanddate, Almanac), in our own words, attributed/linked.
   Set in the Morning Edition; carried forward at Midday/Evening unless correcting.
   Lives in the sidebar (`#sky`, after This Day in History).

## Pre-publish privacy gate — EVERY item, EVERY edition
- [ ] Public source? (agency alert, public notice, venue/business public posting)
- [ ] Public event? (openly published public listing, for events)
- [ ] No private names or addresses? (no residents' private data, no home addresses,
      nothing from Dave's mail, calendar, or private accounts)

Any box unchecked → the item does not print.

## Hourly safety poll
Between editions, re-poll the Safety Wire hourly. A qualifying event (evacuation order
or warning, major freeway closure, severe-weather warning, flood notice) triggers an
out-of-cycle banner at the top of `index.html` (`#safety-banner`), stamped with its time.
Routine changes wait for the next edition.

## Archive
Each edition is saved as `editions/YYYY-MM-DD-{morning,midday,evening}.html` and linked
from `archive.html`. The masthead always shows when the front page was last rebuilt;
every item carries a timestamp and source.


**Standing element — pull-to-refresh (added Nov 1, 2026, at Dave's direction):** the
front page and archive carry a `PTR:BEGIN … PTR:END` block before `</body>` (indicator
pill + touch handler that reloads the page on a pull from the top). Every edition
rebuild must PRESERVE this block verbatim. Added to both gazettes the same day.

**Standing element — the TICKER BAR table of contents (added Nov 4, 2026, at Dave's
direction; designed on The Fiddletown Gazette and ported here the same day):** the
front page carries a `<nav id="toc">` "IN THIS EDITION" strip under the masthead —
ONE sticky row in ticker style that sticks directly under the sticky topbar (JS
measures the topbar height; CSS fallback top:52px) while the section list slides
horizontally: drag with a mouse, swipe on touch, • separators, edge fades + chevrons
at whichever end has more to slide to, one gentle nudge on load (never under
prefers-reduced-motion, never auto-scrolls). It is SELF-BUILDING: the builder script
before the PTR block rebuilds the items on every load from the page's own <h2>s —
an <h2>'s own id wins, then its content div's id; an <h2> with neither gets a slug
id assigned at runtime. Anchors are baked in for the lead (`#the-lead` on the
section) and the rail headings (`#around-town`, `#weather`, `#history`,
`#star-chart`). Every edition rebuild must PRESERVE: the nav block, the ticker
styles in <head>, the builder + ticker-behavior scripts, and the
[id]{scroll-margin-top} rules (jumps land below both sticky rows). The static items
in #toc-list are only a no-JS fallback; never maintain them by hand.
**Ticker behavior UPGRADED Nov 22, 2026 (Dave's bug report: "the ticker sits
static while the rest of the page scrolls" — Lenwood still carried the Nov 4
script above; the Nov 5–16 upgrades had landed on Fiddletown only).** The
behavior script is now Fiddletown's current one, transplanted verbatim: the
tape **drifts on its own at 36 px/s in a seamless loop** (the item set is
duplicated once and the scroll position normalized inside the seam) at the
top of the page; a **scroll-spy** tracks the reader — as the page scrolls,
the current section's chip lights up (`.ticker-item.on`: accent + gold
underline) and the tape re-aligns so that chip is on screen, the drift
parking while the reader is down in the paper; drag by mouse or touch
pauses the drift (resuming after an idle beat) and a hand placement stands
until another section is reached; the "In this edition" slug is also a
drop-down menu of the same items. All of it stands down under
prefers-reduced-motion. Supporting styles: `.ticker-item.on`,
`.ticker-slug{cursor:pointer}` + `.tm-caret`, `#ticker-menu`, and
`#toc-list{touch-action:pan-x pan-y}`. Edition rebuilds preserve the
transplanted script and these styles exactly — do NOT regress to the
Nov 4 behavior described above (kept for history).

**Site icons (added Nov 1, 2026):** the site root carries Dave's custom icon set —
`favicon.ico`, `favicon-16.png`, `favicon-32.png`, `apple-touch-icon.png`,
`icon-192.png`, `icon-512.png`, and `site.webmanifest`. The `<head>` icon/manifest
link tags on index.html and archive.html are standing elements: every edition
rebuild preserves them (and new snapshots inherit them from the front page).


**Standing element — photo viewer (added Nov 1, 2026, at Dave's direction):** the
front page and archive carry an `LBX:BEGIN … LBX:END` block before `</body>` — a
full-screen photo viewer: tapping any photo opens it fit-to-screen on a dark backdrop;
the way out is a 56px ✕ button (top right, unmissable), a tap on the backdrop, or Esc.
Markup and script travel together in the one block (a sibling page once shipped viewer
markup after its scripts and taps silently did nothing — never split this block).
Every edition rebuild must PRESERVE it verbatim.


**Section removals — batch 2 (Dave's direction, Tue Nov 24, 2026):** the standalone lower **Weather** section (`#weather`, which ran below the Community Wire here) is REMOVED from this paper too — weather lives in the forecast panel up top and the Safety Wire; the 🌦️ Weather Events section up top is a different section and STAYS. **What We're Listening To** has never run in the Lenwood Gazette — nothing to remove, and do not add it (removed fleet-wide the same day; Fiddletown's Listening Archive page stands as an archive).


**Section removals — fleet-wide (Dave's direction, Tue Nov 24, 2026):** Date Night, Featured Pets, and On the Wing were removed from the Gazette lineup. Checked against this paper the same day: **none of the three has ever run in the Lenwood Gazette** — nothing to remove here, and do not add them; the removal stands as the lineup rule for both papers.


**"Why This Paper Is Free" (Dave's piece, approved as drafted Tue Nov 24, 2026):** the publisher's standing statement, Lenwood-localized (neighbor project not a business; no ads and no tracking — readers are neighbors, not inventory; honest about costs, the tip jar as thanks, never a pitch; the promise that the paper stays free whether anyone tips or not). It runs in a new **From the Editor's Desk** section on the front page from Tue Nov 24, 2026 (four-day clock — retire from the front page in the Sat Nov 28 Morning edition) AND stands permanently at **why-free.html**, linked from the colophon (this paper's About surface). Text is Dave-approved VERBATIM — carry exactly; the only presentation added is the tip-jar link. The Fiddletown Gazette carries its own localized twin under the same arrangement. **The Struck Cookie (placed Nov 24, 2026 at the foot of the item, Jonny's polished PNG at `images/struck-cookie-mark.png`, identical to Fiddletown's): Dave ruled the same day that the cookie block is STANDING — when this piece retires in the Sat Nov 28 Morning edition, MOVE the block (mark + "This paper sets no cookies." / "Struck through by the editor — permanently." / the local-notes footnote, unchanged) into the front-page COLOPHON as standing furniture; until that edition it stays at the foot of the piece. Add it alongside the colophon's existing lines without altering them.**


**Standing element — THE PRIVACY SEAL — REMOVED at Dave’s direction Wed Nov 25, 2026 (stood Nov 23–25, 2026; do NOT restore in any rebuild — the anchor, its style block, and the 38px masthead clearance margin are gone from the front page; the Nov 24 drawer-clearance fix and the tip-pill flag in this passage are CLOSED as moot; the asset file remains in the repo, unused). Historical record of the seal as it ran: (Jonny's Seal 2, Dave's pick + build order, Nov 23, 2026):** the die-cut Privacy Seal (rim "WE COUNT READERS · NEVER TRACK THEM", center ALWAYS FREE, "tips welcome") stands on the masthead's bottom-left corner in EVERY edition — preserve it in every rebuild. Form: `<a class="gz-seal">` as the masthead's last child, asset `images/seal-2-lenwood.png`, linking https://ko-fi.com/davedellaquila (the same destination as the header tip pill — no new plumbing); styles in `<style id="gz-seal-style">` (100px, +7° tilt, bottom:-33px so a third hangs below the rule, z-index 60; phone 96px — never below 92px). Design record: ~/workspace/gazette-always-free/design.md (Decision section). The seal and the older gradient header tip pill now both invite tips in the header stack — the pill is RETAINED until Dave rules (flagged to him Nov 23, 2026). The Fiddletown Gazette carries the same seal in its own dress under the same rule. **Drawer clearance (Nov 24, 2026, from Dave’s iPad screenshot of the Fiddletown paper; same collision confirmed here):** the seal’s z-60 beat both section menus, so with a menu open the sticker floated over its left entries. The seal style block now hides the seal while either menu is open (`body:has(#brand-menu:not([hidden])) .gz-seal, body:has(#ticker-menu:not([hidden])) .gz-seal{visibility:hidden}`) and restores it on close; placement and size unchanged. Preserve the rule in every rebuild.


**Standing element — tip jar crossings with the pause (added Nov 5, 2026, at Dave's
direction):** the front page carries a `TIPFLY:BEGIN … TIPFLY:END` block before
`</body>` — the traveling tip jar (the sister paper's repertoire: race / tumble /
march / bounce / sneak / victory, first crossing ~40s after load, then about one
every couple of minutes, smoke puffs on the race, all skipped under
prefers-reduced-motion). Dave's rule: **on every crossing the jar PAUSES about a
second directly underneath the Tip Jar pill** (its position is measured from the
pill's live rect, it settles just below the pill with a small bow, and the pill
glows during the pause) — and during the pause the jar performs ONE brief effect
picked at random from Dave's menu (spin · bounce · expand · grow · shrink ·
pulsate), never the same effect twice in a row — then continues its route
unchanged. Every effect lands back at neutral as the pause ends, so the
crossing resumes without a snap, and the system works across all six gaits. Every edition
rebuild must PRESERVE this block verbatim.


**Standing element — text-size control with the REBASED scale (added Nov 5, 2026, at
Dave's direction):** the front page and archive carry Dave's text-size control in the
top bar (small A · five dots · big A, before the Tip Jar; boot script `fsctl-boot` +
`fsctl-style` in the head, behavior script `fsctl-script` before </body> — preserve
all three pieces in every rebuild). **The scale, rebased Nov 5, 2026 (with Dave's ceiling amendment the same evening):**
seven levels — **1 = 100%, 2 = 108%, 3 = 116%, 4 = 125%, 5 = 135%, 6 = 145%,
7 = 155%** — where level 1 (100%, the old middle "normal") is both the SMALLEST
setting and the DEFAULT: a reader who never touches the control gets exactly
today's reading size. Standing spec: floor = the old normal, ceiling = at least
two sizes above the old 116% maximum — this scale's 155% top clears that with
room to spare, and the steps stay ~8–10 points apart (extended, not stretched). The choice persists per
reader in localStorage under 'lg-font-size'. (Same control and same rebase on the
sister paper; her storage key is 'fg-font-size'.)

**Standing layout — top bar distribution (Dave's direction, Nov 22, 2026):**
the top bar's items (paper name · nav · text-size control · reader count ·
Tip Jar) spread EVENLY across the row's full width — `.topbar` carries
`justify-content:space-between` and NO auto margins push groups around (the
old `nav{margin-left:auto}` bunching is gone). At ≤640px (phone portrait)
the row groups deliberately instead of crowding (Dave's addendum, Nov 22):
Tip Jar takes order 1 so row 1 is paper name + Tip Jar spread edge to edge;
the text-size control and the reader count take order 2 on row 2, also
spread; the nav drops to its own full-width row (order 3) and spreads its
links with `justify-content:space-between` too; the Tip Jar carries no auto
margin.
Applies to the front page, the archive, and every standing page that clones
the top bar; edition rebuilds preserve it.


**Standing element — visitor counter beacon (Analytics Buddy; recorded Nov 6,
2026; endpoint LIVE Nov 15, 2026):** Dave chose a Dave-owned Cloudflare Worker
counter for the fleet (this paper, Fiddletown, the dashboard, dellaquila.com):
unique visitors per page/edition via a daily-rotating salted hash (sha256 of
daily salt | site | IP | UA) — hashes only, deleted at day close, no cookies, no
raw IPs, aggregate counts only. **Dave completed the Cloudflare deploy on
Nov 15, 2026; Astro verified the Worker end-to-end, and the desk wired it the
same day.** The live endpoint is
`https://visitor-counter.dave-5d7.workers.dev` — the beacon block travels as
`BEACON:BEGIN…BEACON:END` before `</body>`:
- `<script async src="https://visitor-counter.dave-5d7.workers.dev/beacon.js" data-site="lenwood-gazette"></script>`
  rides the front page, the Editions Archive, and every future edition snapshot
  (snapshots are born carrying it; counts are fetched live at view time, so frozen
  snapshots are NEVER edited after publication to change a count).
- Counts show with `<span data-visitor-count></span>` (counts the page it sits
  on) — the front page carries it in the colophon "Readers:" line; on archive
  listings use `<span data-visitor-count data-count-path="/editions/YYYY-MM-DD-<edition>.html"></span>`.
- Editions published before the beacon landed (before Nov 15, 2026) cannot be
  counted retroactively; they start at zero under the archive's "tally from
  Nov 15, 2026" note.
- **Header reader count (added Nov 22, 2026, Dave's request — same treatment
  as the Fiddletown Gazette's masthead):** the front page's top bar carries
  `<span class="tb-readers" title="…">👁 <span data-rc-today></span> /
  <span data-rc-total></span></span>` immediately before the Tip Jar pill
  (readers today / all-time). **Fill mechanics (verified Nov 22, 2026 by
  reading the served beacon.js):** beacon.js fills ONLY `[data-visitor-count]`
  spans — it never touches the rc pair (Fiddletown's rc numbers are static
  text baked into its HTML). So the BEACON block carries a small RC filler
  script after the beacon tag that fetches `/counts?site=lenwood-gazette&paths=/`
  and fills the pair live from the front-page counts; it fails silent.
  Rebuilds preserve the filler with the rest of the BEACON block. Front page
  only — the archive does not carry the header pair (matching Fiddletown). The tooltip is
  Fiddletown-style and honest: today over all-time, one count per reader per
  day by a scrambled code discarded nightly, and it states THIS paper's first
  counted day — **Nov 15, 2026** (beacon wired and live that day, commit
  aca2e8c; the date coincides with Fiddletown's because Dave deployed the
  Worker for both papers the same day — it is Lenwood's own date, verified in
  this repo's history, not copied). First-reader red: the CSS rule
  `html.vc-new-today [data-rc-today]{color:#c0271b}` paints the today number
  red when the beacon's `vc-new-today` signal says this reader is being
  counted for the first time today (Analytics Buddy API doc, Nov 21, 2026).
  `.tb-readers{white-space:nowrap;font-weight:600;color:var(--ink)}`. This is
  part of the preserved header — edition rebuilds keep the span and both CSS
  rules like the rest of the top bar. **COUNTER LINK — TRIED AND REVERTED (Tue Nov 24, 2026):** Dave directed that tapping the reader count go to "the analytics page"; the desk first linked the counter to the Analytics Buddy dashboard homepage, and Dave corrected it the same morning — the target must be a PUBLIC stats page (Fiddletown's counters now link to its own Stats for Nerds page). **This paper has no stats page**, so rather than link Lenwood readers to Fiddletown's page or the internal one, the desk REVERTED Lenwood's counters to plain spans the same morning and flagged the gap to Dave. If Dave directs a Lenwood stats page, link the `.tb-readers` counter (front page + standing pages carrying the pair) to it then, in the anchor form with the `#rc-link-style` block, counts/tooltip/red rule unchanged.
This beacon is a preserved standing element — rebuilds keep it like
PTR / LBX / TIPFLY / fsctl.
**Counts caveat (Nov 15, 2026, Analytics Buddy):** the counter's same-day
dedupe over-counts repeat visits from the same reader. The fix is built and
committed (analytics-buddy 4c326a3) but needs Dave to re-paste worker.js in
Cloudflare. Until Analytics Buddy sends the all-clear, the desk does NOT quote
reader counts in editions or reports — the on-page spans fill themselves in and
are the reader's own business; the desk just doesn't cite the numbers yet.

**Standing element — section 👍 voting (added Nov 22, 2026, Dave's
direction; mirrors the Fiddletown Gazette's treatment, live there since
Nov 19, 2026):** every content section of the front page carries one small
👍 at its foot — one tap is one vote for keeping that section in the paper.
Pieces, all preserved in every rebuild:
- `thumbs.js` at the repo root, loaded by the front page only via the
  `THUMBS:BEGIN…THUMBS:END` tag before the BEACON block. It injects the
  buttons at runtime (nothing to hand-place per section): for each
  `main h2, aside h2` it finds the section's host (first following sibling
  carrying an id) and appends the control at the host's foot. The Free
  Stuff block (`#free-stuff`) is skipped — a running classified, not an
  editorial section. **The script self-disables on any page under
  `/editions/`, so frozen snapshots never sprout live controls** even
  though they carry the tag; snapshots therefore need no special handling.
- The explainer card `#thumbs-notice` ("A quick word about the 👍") as the
  first item of the main column, and the footer block `#lg-tallies`
  ("👍 Today's thumbs.") as the first item of the colophon, with its
  `.lg-tally-list` filled live by the script.
- Counting is Analytics Buddy's votes API (same Worker as the counter):
  POST /vote, site `lenwood-gazette`, target_type `section`. **Tallies are
  DAY-scoped** — target_id `<YYYY-MM-DD>/<section-id>`, edition
  `<YYYY-MM-DD>` — so one board runs across the day's three editions and
  clears at day's end. The script derives the day from the
  `<meta name="lg-edition" content="YYYY-MM-DD-<edition>">` tag in the
  head: **every edition rebuild sets that meta alongside EDITION:DATE /
  EDITION:NAME** (morning/midday/evening suffix included; the script uses
  the date part). The reader's browser marker lives in localStorage as
  `lg-voter`, their picks as `lg-thumbs-v1`; the server stores only a
  salted hash of the marker. One vote per reader per section per day,
  up-only (no 👎). Votes are reader feedback for the desk — they are NOT
  quoted as results in editions; the footer board is the reader's own
  display, like the reader counts.

**Standing element — 📬 The Suggestion Box (added Nov 22, 2026, Dave's
direction; mirrors the Fiddletown Gazette's box):** after the grid and
before the colophon, the front page carries an `<h2>📬 The Suggestion
Box</h2>` and the `#suggestion-box` card: the standing intro ("Feedback,
comments, corrections, and story tips for this edition — all welcome…"),
a "Your name (optional)" field (`#sugg-name`), a "Your suggestion"
textarea (`#sugg-text`), and an "✉️ Send by email" button (`#sugg-send`),
with the how-it-works note printed under it. The page is static — nothing
is collected or stored: the `SUGGEST:BEGIN…SUGGEST:END` handler after the
footer composes a **mailto to dave@dellaquila.com** with subject
"Lenwood Gazette suggestion — " + the page title and the typed suggestion
(plus the name, if given) in the body, and opens it in the reader's own
email app for them to send. The "write directly" link in the box uses
subject `Lenwood Gazette suggestion` — the Lenwood subject line is what
keeps the two papers' suggestion mail distinguishable. Form styling is
the `.sugg` rules in the main stylesheet. The box sits OUTSIDE main/aside
on purpose: the edition ticker picks its h2 up automatically (chip:
"📬 The Suggestion Box" → #suggestion-box), and the section-thumbs script
never decorates it. Edition rebuilds preserve the box, its styles, and
the handler verbatim; frozen snapshots keep a working box (a mailto
still composes from an archived edition — that's fine and intended).

**Standing sidebar section — 💿 Album of the Day (added Nov 22, 2026, Dave's
direction):** the sidebar carries an `ALBUM:BEGIN…ALBUM:END` block (h2 +
card, both `id="album-of-the-day"`, between the Weather and History
cards) printing **Music Buddy's daily pick verbatim** — artist (linked to
its Apple Music artist page), album title (linked to its Apple Music
album page), year, and Music Buddy's own write-up — the same content as
Dave's Album of the Day email. The desk NEVER writes or edits the blurb.
**Refresh rule:** the Morning edition replaces the block with the day's
pick, lifted from the AOTD block on Music Buddy's homepage
(https://davedellaquila.github.io/buddy-system/music-buddy/) or from the
pick Music Buddy sends this desk directly; Midday and Evening editions
carry the block forward unchanged. The meta line names the pick's date
and credits Music Buddy with a link to their page. If a morning's pick
can't be obtained, carry yesterday's block and say so in the edition
report — never substitute a desk-written pick. Coordination CONFIRMED
with Music Buddy (Nov 22, 2026): the homepage AOTD block is word-for-word
the email's pick (the email adds only framing), and Music Buddy's
routine runs 5:11 AM PT with the homepage updated and verified live by
~5:30–5:45 AM — ahead of the 6:00 AM Morning edition. Lift from the
homepage each morning; no direct send needed.
**Album archive page (added Nov 22, 2026, Dave's direction):**
`album-archive.html` lists every pick so far — date, artist + album
Apple Music links, year, and Music Buddy's full write-up — newest first,
inside `AOTD-ARCHIVE:BEGIN…END` markers. Its source is the
`AOTD-FULL` block in Music Buddy's homepage archive
(https://davedellaquila.github.io/buddy-system/music-buddy/#aotd-archive),
which grows automatically with each pick; the Morning edition refreshes
the Gazette's archive page from that block alongside the daily pick. The
front-page Album card links to it with a standing line AFTER the
`ALBUM:END` marker ("📚 Every Album of the Day so far — browse the
archive") — outside the verbatim block, carried by every rebuild.

**Standing element — masthead section menu (added Nov 22, 2026, Dave's
direction; mirrors the Fiddletown Gazette's brand menu):** the paper's
name at the left of the top bar is a button (`#brand-btn`, wrapped in
`.brand-wrap`, with a gold ▾ affordance) opening a dropdown
(`#brand-menu`) headed "Jump to a section." The `BRAND:BEGIN…BRAND:END`
script builds the list live from the page's own `<h2>`s — the same
section set as the edition ticker, resolved the same way — so sections
that come and go stay right with no hand maintenance; it appends a
separator and the Editions Archive link. Choosing a section jumps to it
and closes the menu; an outside tap/click or Esc also closes;
`aria-expanded` tracks the state. The menu is anchored left under the
name (Lenwood's name sits at the bar's left edge — NOT centered like
Fiddletown's) with `max-width:88vw`. Edition rebuilds preserve the
button markup, the `.brand-wrap`/`#brand-menu` styles, and the BRAND
block verbatim; the top bar's even distribution and phone grouping are
unaffected (the wrap is the flex item the plain name span used to be).
Front page only for now — the guide pages keep their own navigation.

**Phone header rule (Nov 22, 2026, Dave's direction):** at ≤640px the
header is NOT sticky — `.topbar{position:static}` and (where the page has
one) `#toc{position:static}` inside the existing phone media block, so
the whole header zone scrolls away with the page on iPhone instead of
eating the small screen; wider screens keep the sticky bars. The phone
`[id]{scroll-margin-top}` drops to 12px with it (the old 150px phone
value existed to clear the pinned stack; with nothing pinned, jumps
should land flush). Applies to every page carrying the top bar: front
page, Editions Archive, and both holiday guides. The ticker's stickTop
script still sets the bar's top offset inline — inert while static, and
correct again at wider widths. Edition rebuilds preserve the rule.

**Running item — 🎁 Free Stuff: the tanker desk (Dave's direction, Nov 16,
2026):** the front page carries a `FREEBIE:BEGIN…FREEBIE:END` block (main
column, after the Community Wire) offering Dave's vintage steel tanker desk
FREE, with its three photos (`images/tanker-desk-hero.jpg`,
`tanker-desk-office.jpg`, `tanker-desk-drawers.jpg`), pickup at 18231 Llagas
Creek Dr, Morgan Hill, pointing readers to the Facebook Marketplace listing
(item 1447887447530120, verified Available/FREE Nov 16). Editions CARRY THE
BLOCK FORWARD unchanged until the desk is gone — Dave or Marketplace Buddy
gives the word — then remove it and note the removal in that edition's report.
The publisher directed this item and its pickup address himself; it sets no
privacy-gate precedent for anything else. (The same item runs in the
Fiddletown and Llagas Creek Gazettes.)

## Christmas Lights Guide (standing seasonal page — added Nov 19, 2026, at Dave's direction)
- `christmas-lights.html` is a standing guide page (not an edition snapshot): the valley's 2026 Christmas lights — the big walk-throughs, neighborhood displays, town tree lightings, worth-the-drive spots, and a "Not This Year" list. Researched Nov 19, 2026 from official organizer/city/county sources; every entry links its official page; unconfirmed items (Downtown Ice dates, Widmer-World) are flagged in print as unconfirmed.
- The front page carries a `LIGHTS:BEGIN…LIGHTS:END` pointer block right after the Lead. Editions carry it forward unchanged through Jan 3, 2027; remove it in the first edition after that date (or when Dave says).
- Update the guide page itself as flagged items confirm or facts change; it is a living page, unlike edition snapshots. Key 2026 facts: NO drive-thru in Santa Clara County (Blinky's paused — official); Fantasy of Lights walk-through only, Dec 5/6/12/13, advance tickets required; Christmas in the Park Nov 27–Jan 3 per the official FAQ (secondary listings differ).
- **Willow Glen GPX link (Nov 19, 2026, Dave's direction):** the guide's Willow Glen entry links `willow-glen-christmas-lights.gpx` (site root) — the Gazette's own 22-point inRoute-native driving route (source of truth: lenwood-gazette-buddy repo `routes/`; Dave road-tested it to "Nailed it"). If the route is ever revised, update BOTH copies.

## Christmas Events Guide (standing seasonal page — added Nov 22, 2026, at Dave's direction)
- `christmas-events.html` is the events companion to the Lights Guide: the season's DATED happenings — tree lightings & parades, Nutcracker & holiday theater, concerts, markets & fairs, Santa & holiday trains, rinks & venue specials — valley first, wider Bay Area where worth the drive. Researched Nov 22, 2026 (deep-research sweep, official sources first); unconfirmed items are flagged in print (Downtown Ice's 2026-27 season still unposted by the rink; the History Park Children's Heritage Holiday date conflict — Dec 19 per HSJ's calendar vs Dec 12 in one HSJ post — printed with a confirm-at-source note; the You-Sing-It Messiah listing). Sold-out items print as sold out with the still-open alternatives (Train of Lights, Caltrain Holiday Train ride vs its free Diridon station party). The two guides cross-link both ways.
- The front page carries an `EVENTS:BEGIN…EVENTS:END` pointer block right after the LIGHTS pointer. Editions carry BOTH pointers forward unchanged through Jan 3, 2027; remove them in the first edition after that date (or when Dave says).
- Like the Lights Guide, the events page is a living page: update it as flagged items confirm (Downtown Ice dates above all) or facts change.
- Both guide pages carry the current top bar including the header reader-count pair (`.tb-readers` + the RC filler in the BEACON block, added to the Lights Guide Nov 22, 2026 for consistency with the front page).

## Pass Cameras panel (standing, added Nov 25, 2026 at Dave's direction)
- `<h2>🏔️ Pass Cameras — the high country, live</h2>` + `<div class="item" id="pass-cams">` sits in MAIN immediately after the Safety Wire block. Preserve on every rebuild.
- Six stills, in this order: Carson Pass (Caltrans SR-88 at Pine Grove — the only SR-88 camera; caption says so), Echo Summit (US-50), Donner Summit (I-80), Luther Pass (US-50 at Meyers), Ebbetts Pass (Bear Valley Summit Cam still), Sonora Pass (Dodge Ridge Summit Cam still). Resort stills are the resorts' live-stream thumbnails, credited to the resort, never to Caltrans. Every caption names the camera's ACTUAL location — no borrowed views.
- Stills refresh in place every 2 minutes (`#pass-cams-script`); a still that fails to load hides its own tile. Tapping a still opens the paper's photo viewer.
- The panel foot links the full tracker: https://passes.fiddletowngazette.com/. The same panel runs in the Fiddletown Gazette with a foothills intro line.
