# Publishing — The Lenwood Gazette

## Edition build (each of Morning / Midday / Evening)
1. Poll the Safety Wire: AlertSCC, City of San Jose emergency alerts, SJFD/SJPD public
   feeds, CHP Golden Gate incidents, NWS Bay Area, Valley Water, VTA service alerts.
2. Pull Today's + Week Ahead public events from the paper's own events desk:
   City of San Jose events calendar, SAP Center, San Jose Theaters, Children's Discovery
   Museum, The Tech Interactive, San Jose Public Library events. **Santa Cruz is in
   the events beat (Dave's direction, Nov 25, 2026 — it is the far side of the SR-17
   run the Hill & Mountain Roads panel covers):** City of Santa Cruz events, Santa
   Cruz Beach Boardwalk, Santa Cruz County parks & libraries, the MAH (Museum of
   Art & History), Kuumbwa Jazz Center, Rio Theatre, Kaiser Permanente Arena.
   Santa Cruz listings run in Today in the Valley + The Week Ahead alongside the
   South Bay, town-named like any other listing, through this same desk step.
   **The Highway 1 coastal towns are in the events beat too (Dave's direction,
   Nov 25, 2026):** the Pacifica → Half Moon Bay → Pescadero → Davenport stretch —
   Pacifica, Montara, Moss Beach, El Granada, Half Moon Bay, San Gregorio,
   Pescadero, Davenport and their neighbors. Desk sources: City of Pacifica and
   City of Half Moon Bay calendars, San Mateo County parks & libraries, Pacifica
   Performances, Año Nuevo State Park, Pigeon Point Light Station, Harley Farms,
   Pie Ranch and the coast's standing venues. Coastal listings run in the same
   two sections, town-named like the rest. **Lenwood's events map is now: South
   Bay + Santa Cruz + the Hwy 1 coastal towns.**
   **The Santa Cruz Mountains wineries are in the beat too (Dave's direction,
   Nov 25, 2026):** winery events, tastings and releases from the Santa Cruz
   Mountains AVA — the Ridge / Mount Eden / Thomas Fogarty / Testarossa country
   above Los Gatos, Saratoga and Cupertino, and down toward Santa Cruz —
   belong in the Lenwood listings alongside the South Bay, Santa Cruz and the
   Hwy 1 towns. Desk sources: the Santa Cruz Mountains Winegrowers
   Association events calendar and the wineries' own event pages, verified
   like any other listing.
   **Saratoga is named explicitly in the beat (Dave's direction, Nov 25,
   2026):** its events and venues — Montalvo Arts Center, The Mountain
   Winery's concert season, the village, Hakone Gardens — belong in the
   Lenwood listings, at the foot of SR-9 where the South Bay meets the
   Santa Cruz Mountains. Desk sources: the venues' own calendars plus the
   City of Saratoga and Saratoga Chamber listings.
   **The Catalyst is a named standing source (Dave's direction, Nov 25,
   2026):** the Santa Cruz concert hall on Pacific Ave — its concert
   calendar is watched as a standing source for the Lenwood listings, the
   way a named venue gets watched rather than swept occasionally. Shows
   there run in the events sections, town-named Santa Cruz, credited to
   the venue's own calendar.
   **The wineries get a standing section of their own (Dave's direction,
   Nov 25, 2026):** 🍇 Santa Cruz Mountains Wineries (`#scm-wineries`, MAIN
   column after Car Shows) — a directory built from the places database's
   Santa Cruz Mountains winery records (33 at launch: Ridge, Mount Eden,
   Thomas Fogarty, Testarossa, Rhys, Cooper-Garrod, Kathryn Kennedy, Bonny
   Doon and 25 more), grouped by slope (the ridge above the valley —
   Cupertino/Saratoga/Los Gatos · Skyline · the Santa Cruz side). DB-fed:
   each Morning Edition rebuilds it from the places feed (locations,
   category=winery, published, in the Santa Clara / San Mateo / Santa Cruz
   county set — the AVA set Events Buddy maintains); each winery's name
   links its own detail card in the **Santa Cruz & South Bay Places
   database** (`https://places.lenwoodgazette.com/#/place/<slug>`) and
   the section's foot line credits that database ("From the Santa Cruz
   & South Bay places database →", linking https://places.lenwoodgazette.com/).
   These are SOUTHERN records — never credit or link the Gold Country
   places database in this paper (Dave's correction, Nov 25, 2026, after
   the section first ran with the Gold Country credit). Midday/Evening carry it
   forward. Dated winery events still run in the events sections via the
   winery desk — the section is the standing directory, not a second
   events listing.
**FRONT-PAGE LAYOUT INVARIANTS (desk fix, Thu Nov 26, 2026 — never rebuild these away): (1) the base stylesheet carries `img{max-width:100%;height:auto}` — Lenwood shipped without it until today, so any unconstrained photo rendered at natural width; (2) the body grid's tracks are `minmax(0,1fr)` single-column and `minmax(0,2fr) minmax(0,1fr)` at ≥760px — the bare `1fr`/`2fr 1fr` forms let a wide item's min-content blow the tracks out (a 1200px photo in MAIN forced the main track to 1200px and squeezed the rail to ~146px on the live page, Nov 26, 2026; the Fiddletown paper's grid has used the minmax(0,…) forms all along). Any rebuild or restyle keeps both rules verbatim; a new section with a wide photo is exactly the case they protect. (3) PHONE STICKY TRAP (desk fix, Thu Nov 26, 2026): at ≤640px BOTH bars are static by design — but the base block's `#toc{position:static}` silently LOST on source order to the ticker block's later `#toc{position:sticky}` (same specificity), so the strip stuck alone at the topbar's height over the article on phones (Dave's screenshot). The winning twin — `@media (max-width:640px){#toc{position:static}}` — lives in the TICKER style block immediately after the sticky rule, with its comment; never move it earlier or remove it. Anchor landings: `[id]` scroll-margin-top is 112px desktop, 144px in the 641–900px band (the topbar wraps to ~85px there; combined bars ~129px), 12px on phone where nothing sticks.**

   **📍 Landmark of the Day (Dave's commission, Nov 26, 2026 — the name is
   his pick):** a standing daily feature in MAIN immediately after
   `#scm-wineries`, before The Community Wire: `<h2>📍 Landmark of the
   Day</h2>` + `<div class="item" id="landmark-of-the-day">`, with its
   ticker item beside the SCM one. ONE place a day from the Santa Cruz &
   South Bay places database — the pool is every published record in the
   Santa Clara / San Mateo / Santa Cruz county region set (63 at launch:
   33 wineries + 30 food, Alice's Restaurant among them; the pool grows
   as southern records are published, and new records join the un-drawn
   remainder mid-cycle). **Selection is a SHUFFLED DRAW** (the principle
   Dave set for the Fiddletown Featured Marker the same day): no set
   order, NO REPEATS until the pool runs through, then a fresh cycle;
   the database order itself never changes. The desk keeps the run
   ledger (`~/workspace/projects/gazette-buddy/lenwood-places-featured.json`)
   and the next-pick file (`lenwood-places-next.json`, same repo).
   **The Morning Edition sets the day's card:** feature EXACTLY the slug
   the next-pick file names for that file's date, append the ledger entry
   in the same flow, then draw the next day's pick (at random from the
   published pool minus the ledger) and write it into the next-pick file.
   **ADVANCE CHECK:** the card's kicker must carry TODAY's date and No. =
   the ledger's last n + 1 — a card carried forward unchanged is a FAILED
   build (the Fiddletown marker's Nov 20 lesson). Midday/Evening carry
   the card unchanged. **Card format:** kicker "ONE PLACE A DAY FROM THE
   SANTA CRUZ & SOUTH BAY PLACES DATABASE · No. <n> · <DAY MON D, YYYY> ·
   DRAWN IN NO SET ORDER — NO REPEATS UNTIL EVERY PLACE HAS HAD ITS DAY";
   a photo figure ONLY when the record carries a real photo (real-or-none
   — most records have none; the card is text-first by design), captioned
   with the record's photo credit; the body = bold "Name — Town." + the
   record's short_description (the name prefix dropped, the rest
   verbatim); the closing line links the place's own detail card
   (`https://places.lenwoodgazette.com/#/place/<slug>`) and, where the
   record carries coordinates, an Apple Maps link built from them
   (`https://maps.apple.com/?ll=<lat>,<lon>&q=<name>`). Launched Thu
   Nov 26, 2026 with No. 1 = Alice's Restaurant (placed by the desk).
   **Boulder Creek and Felton are in the beat (Dave's direction, Nov 25,
   2026):** the San Lorenzo Valley towns along SR-9 in the Santa Cruz
   Mountains. Their events join the listings with the rest of the expanded
   map (South Bay + Santa Cruz + Hwy 1 coastal towns + SCM wineries +
   Alice's). Desk sources: San Lorenzo Valley Chamber of Commerce, the
   towns' community calendars, Roaring Camp Railroads (Felton), Henry
   Cowell Redwoods State Park, the SLV Museum and the towns' standing
   venues.
   **DWA events print from the database (Dave's direction, Nov 25, 2026):**
   DWA — the driving club behind the Sierra Rally — is a standing source;
   Events Buddy enters its announcements in the Gold Country events
   database as they appear. Each edition also checks that database for
   DWA events falling inside this paper's coverage map (rally and tour
   days run in the Bay Area, the Santa Cruz Mountains and the coast as
   well as the Sierra) and prints them in the events sections like any
   other listing — the event name linked to its database detail page
   (https://events.fiddletowngazette.com/?event=<slug>#/event/<slug>) and
   credited to the database, per the database link rule. **SCBMCC joins on
   the same terms (Dave, Nov 25, 2026):** the same database check covers
   SCBMCC events — a standing source whose events print from the DB
   wherever they fall in the map.
   **Alice's Restaurant is a named standing venue in the beat (Dave's direction,
   Nov 25, 2026):** the landmark at the SR-84 × Skyline Blvd crossroads in
   Woodside (17288 Skyline Blvd) — the Peninsula's classic car-and-bike
   gathering spot, in the middle of the roads the Hill & Mountain Roads panel
   covers. Its events and gatherings belong in the Lenwood listings — dated
   events in the events sections, and its weekend car/bike gatherings watched
   by the Car Shows desk under step 9. Source: the restaurant's own site and
   posted event listings, verified like any other listing.
   (The Fiddletown Gazette is unchanged — its beat stays Amador/Foothills-local.)
   **EVENT ORDERING (Dave's standing rule, Thu Nov 26, 2026): everywhere the
   paper lists events — Today in the Valley, The Week Ahead, Car Shows, and the
   dated items inside Around Town — events print in DATE ORDER: soonest first,
   furthest away last, no exceptions by section. Within one day, holiday
   events list before non-holiday ones, then by start time (Dave's Nov 22
   design, confirmed Nov 26, 2026); a day's untimed items follow its timed
   ones. A multi-day event sorts by its FIRST day. Closures and standing notes are not events and keep their places
   after the day's events.** (First audit, Nov 26, 2026: Today in the Valley
   printed the 8:30 AM Turkey Trot ahead of the 5:30 AM Turkey Cup — swapped on
   the spot.)
   **NO DAY HEADINGS IN LENWOOD'S OWN LISTINGS (Dave's correction, Fri Nov
   27, 2026): the by-day grouping belongs on the Christmas events page, NOT
   on this paper. Lenwood's Today in the Valley and The Week Ahead stay a
   continuous stream in the date order above — do not regroup them under
   day headings. (A grouping shipped briefly on Nov 27 was reverted the
   same day at Dave's direction.)**
   **THE WEEK AHEAD STARTS TOMORROW (Dave's content rule, Sat Nov 28,
   2026): The Week Ahead must NOT repeat today's events — they are already
   covered in Today in the Valley above it. The Week Ahead covers tomorrow
   through the days after only; when building it from the events database
   or any listing source, EXCLUDE the edition's own date. An event dated
   today belongs in the today sections only, never in The Week Ahead. (A
   continuing multi-day run may appear in The Week Ahead dated from
   tomorrow, as Christmas in the Park does.) First check, Nov 28, 2026:
   the live Week Ahead already ran Sun Nov 29 → Sat Dec 5 with zero items
   dated the edition's own day — the rule is recorded so rebuilds keep it
   that way.**
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
   only, same privacy gate. **Alice's Restaurant (Woodside, SR-84 × Skyline Blvd)
   is a standing watch for this desk** — its weekend car-and-bike gatherings are
   in scope whenever they are publicly posted (Dave, Nov 25, 2026).
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

**Standing element — section collapse toggles (experiment, Dave's direction,
Nov 25, 2026):** the front page carries `<style id="gz-collapse-style">` +
`<script id="gz-collapse-script">` before `</body>` — PRESERVE BOTH verbatim in
every rebuild. The script turns the leading icon of every section heading (h2)
into a collapse switch (headings with no icon get a ▾ chevron switch): clicking
hides the section's body (the siblings up to the next h2, never scripts/styles,
never the colophon footer), clicking again re-expands; the choice persists in
the reader's localStorage keyed by the section's stable id, so it survives
reloads and carries across editions; a jump link into a collapsed section
auto-expands it. **New-content rule (Dave, Nov 25, 2026):** alongside the
collapsed flag the script stores a hash of the section body the reader last
saw (vote UI excluded); on load, a section whose body differs from the stored
hash renders EXPANDED and the marker refreshes — updated content opens on its
own, and a re-collapse then holds until the content changes again. The script
is generic — it binds whatever h2 sections the rebuilt page contains — so no
per-edition wiring is needed beyond preserving the two blocks.

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

**Text-size MECHANISM (Dave, Sat Nov 28, 2026 — supersedes the zoom mechanism in the
passage above):** the control scales BODY COPY ONLY. The fs levels set `font-size` on
the page's content container (`:is(.grid,.footer)` on the front page, `main` on the
standing pages, the entries `ul` on the archive) at 16/20/24.8/31.2/39.2/48.8/60.8px;
headers, the masthead, the top bar and the tip jar keep their designed size and
position at every level, so the sticky furniture and the jar crossings are never
disturbed by a size change. The whole-page CSS-zoom mechanism (including the Nov 27,
2026 widenings to 3.8×) is RETIRED — at enlarged zooms it broke the sticky top
bar/ticker and displaced the tip-jar flyby. The `text-size-adjust:none` rule STAYS
(it stops iOS Safari's autosizer from re-pinning the enlarged body text), and the
enlarged levels carry an `overflow-wrap:break-word` rule for unbreakable strings.
Storage key, boot, dots and buttons unchanged.
**Scope REFINED (Dave, Sat Nov 28, 2026): the control scales ONLY the running
text within a section. Fixed at every setting: headlines and section headlines;
the masthead and tip jar; and special-feature blocks — Dave's named example is
the summary paragraph at the top of the page (the Lead's body paragraph) —
scaling those makes them wrap weird. The model: prose inside a section scales;
everything structural or feature-boxed doesn't.** (The weather block was named
as a fixed example in the first version of this refinement; Dave WITHDREW that
example the same morning — see MARK #1 below.)
**TYPE-SCOPE MARKS (Dave, Sat Nov 28, 2026 — he is marking elements one by
one and his marks are the spec; HOLD finalizing the implementation until he
says he's done marking, then implement the whole set at once):**
- **MARK #1 — the weather/conditions summary block directly under the
  masthead (Lenwood's `.weatherbug`): SCALES.** (Marked first on the
  Fiddletown paper's dark conditions/road-status card; same mark applied to
  Lenwood's equivalent block.) Supersedes the withdrawn "weather block
  fixed" example above. Implementation note for finalization: the
  weatherbug currently sits outside the scaled containers at a fixed
  13.5px — to scale it, bring it under the fs scale (e.g. an fs-level
  font-size rule of its own, 13.5px at level 1 climbing the same ladder).
- **MARK #2 (provisional) — the top summary paragraph (Lenwood's Lead body
  paragraph, the long prose paragraph near the top summarizing the day's
  events and weather): SCALES.** Circled by Dave with no caption on the
  Fiddletown paper; recorded as SCALES per Mark #1's convention, and
  PROVISIONAL — Dave was told to correct it if he meant stays, and any flip
  will be relayed and recorded immediately. Supersedes (provisionally) the
  refinement's "summary paragraph fixed" example and the default below.
  Implementation note for finalization: the Lead sits outside the scaled
  containers at an inherited 16px — to scale it, give the Lead body
  paragraph an fs-level font-size rule of its own (16px at level 1,
  climbing the same ladder); the Lead's headline and meta stay fixed.
- Defaults until marked otherwise: headlines/section headlines FIXED,
  masthead FIXED, tip jar FIXED, section prose SCALES, the Lead's summary
  paragraph SCALES (provisional, per MARK #2). On this paper the fixed pieces hold by construction —
headlines are px-sized, and the weatherbug, the Lead, the safety banner and the
guide-pointer banners all sit outside the scaled containers — and the desk
VERIFIED it by measurement on Nov 28, 2026 (headless Chromium, min vs max level,
1280px and 390px): masthead, tip jar, weatherbug (13.5px), Lead headline and
summary paragraph (16px), section h2s (22px), safety banner, ticker and the
Suggestion Box controls identical at both levels; only section prose moved
(16 → 60.8px at max); zero horizontal overflow at either width. The guide pages
and archive were spot-checked the same day — same behavior. Rebuilds must keep
this scope: never move the Lead, the weatherbug or a feature banner inside a
scaled container, and never size a headline in em.

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

**Section 👍 voting — REMOVED Nov 28, 2026 (Dave's decision: "nobody's
voting, so take the thumbs-up out for now — until a better way to make
voting work is figured out").** The reader-facing controls are OUT of the
paper: rebuilds must NOT carry the `THUMBS:BEGIN…THUMBS:END` script tag,
the `#thumbs-notice` explainer card, or the `#lg-tallies` footer block
(the live page carries an HTML comment at the old tag's spot recording
the removal). The machinery stays intact and reversible: `thumbs.js`
remains in the repo, the votes API and all recorded votes are untouched,
and nothing about the removal deletes data. Restore only on Dave's
direction. The original spec follows, for that return:

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

**Standing format — the Editions Archive (Dave, Nov 25, 2026 —
matched to the Fiddletown Gazette's editions page so the two papers'
archives feel like siblings):** `archive.html` is a FLAT newest-first
list (Evening → Midday → Morning within a day), one
`<li class="arch-entry">` per edition: a floated thumbnail of that
edition's front page (a real 480×360 capture of the edition's top —
masthead + dateline + weather banner + lead — saved as
`editions/thumbs/<same-name>.jpg`, shown with the `#ed-thumbs-style`
treatment: float left at 168×126 desktop / 118×92 phone, the entry's
text wrapping around it, `.arch-entry` a plain block with clearfix,
never flex), then the edition's title link, its published time, the
👁 reader-count span, and a SHORT italic summary — the edition's lede
plus a headline fact or two, roughly 200–350 characters, condensed
from the edition's own recap; the sweep-by-sweep bookkeeping belongs
in the edition report, NOT the archive. Every edition job adds its
entry AND its thumbnail in the same push that archives the edition
(capture route in this sandbox: render the archived HTML locally and
screenshot its top — `~/workspace/tmp-gazette/make_lenwood_thumbs.py`
is the desk's batch tool). An entry whose thumbnail genuinely cannot
be captured ships text-only — never a placeholder or another edition's
image. The Nov 25, 2026 rebuild converted all 73 editions (Nov 1–25)
to this format; the day-card format it replaced is retired — do not
revive it.

**Standing element — masthead coverage callout (Dave's pick, Nov 25,
2026):** the masthead carries the paper's coverage callout directly
under the nameplate, verbatim: "San Jose to Santa Cruz — and the
mountains between" (`.mast-callout`, styles in
`<style id="mast-callout-style">`). Preserve it in every rebuild,
word for word — it is the one-line statement of the paper's expanded
map (South Bay + Santa Cruz + the Hwy 1 towns + the Santa Cruz
Mountains between them). Lenwood only; Fiddletown's masthead is
unchanged.

**Standing element — masthead treatment, the rotating effects (Dave's
direction, Nov 25, 2026; installs in the Fri Nov 27, 2026 Morning
edition):** the masthead carries the same doghouse treatment as the
Fiddletown Gazette. The CONSTANT is the doghouse: the beagle atop
his doghouse at the masthead's bottom-left, his two windows (a round
gable window, a mullioned front window) glowing warm amber in EVERY
edition. Layered on top, ONE effect per edition, ROTATING — never
the same effect twice in a row. The pool: **fx-smoke** (chimney
smoke curling up) · **fx-twinkle** (warm bulbs along the roofline
and eave, twinkling in three phases) · **fx-leaves** (autumn leaves
drifting down the masthead) · **fx-snow** (gentle snowfall). The
active effect is ONE class on the masthead:
`<header class="masthead fx-smoke">` (etc.). **ROTATION FORMULA:
N = 3 × (days since Fri Nov 27, 2026) + (Morning 0 · Midday 1 ·
Evening 2); N mod 4 → 0 fx-smoke · 1 fx-twinkle · 2 fx-leaves ·
3 fx-snow.** First cycles: Fri Nov 27 smoke/twinkle/leaves · Sat
Nov 28 snow/smoke/twinkle · Sun Nov 29 leaves/snow/smoke · Mon
Nov 30 twinkle/leaves/snow · Tue Dec 1 smoke/twinkle/leaves (the
pattern repeats every 4 days). **Every edition build SETS the class
from the formula — the fx class is NEVER carried forward unchanged;
after pushing, grep the served copy's masthead class and confirm it
matches the formula before reporting the edition.** Canonical
fragment: `sections/masthead-fx.html` (a
`<style id="mast-fx-style">` block + the `.fx-vignette` SVG + the
leaves/snow layers); install = splice the whole fragment as the
FIRST child of `<header class="masthead">` AND set that edition's
fx class on the header. Every edition preserves the FRAGMENT
verbatim; only the class changes. Reduced-motion readers: smoke
shows one still wisp, bulbs and window glow hold steady, leaves and
snow do not fall. Desk-verified before staging (Nov 25, 2026): all
four effects rendered; layer gating exact in Chromium; tag balance
clean on the spliced page.

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

## Hill & Mountain Roads panel (standing, added Nov 25, 2026 at Dave's direction; replaces a Sierra pass-cameras panel placed the same morning and corrected by Dave)
- `<h2>🏔️ Hill & Mountain Roads — the crossings, live</h2>` + `<div class="item" id="hill-roads">` sits in MAIN immediately after the Safety Wire block. Preserve on every rebuild. Lenwood carries NO Sierra pass material (Dave's correction, Nov 25, 2026).
- Two Caltrans stills, in this order: SR-17 just south of Summit Rd (the top of the Santa Cruz Mountains climb), the Sunol Grade (I-680 at Koopman Rd, Sunol). The Caldecott corridor (SR-24) is NOT in the panel (Dave’s refinement, Nov 25, 2026). Captions name each camera's actual location; stills refresh every 2 minutes (`#hill-roads-script`); a failed still hides its tile; tapping opens the photo viewer.
- Five roads carry a status line instead of a picture, because Caltrans has no camera on the climb (verified against the District 4/5 camera inventories, Nov 25, 2026): SR-9, Skyline Blvd (SR-35), Mt. Hamilton Road (SR-130), SR-92 over the hill (its cameras watch the San Mateo Bridge — never borrow that view for the hill), and Niles Canyon (SR-84). Each line links the route's Caltrans road report (roads.dot.ca.gov/roadscell.php?roadnumber=N). Never print a borrowed or distant view as a road's picture.
