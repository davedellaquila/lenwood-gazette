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


**Standing element — visitor counter beacon (Analytics Buddy; endpoint pending,
recorded Nov 6, 2026):** Dave chose a Dave-owned Cloudflare Worker counter for the
fleet (this paper, Fiddletown, the dashboard, dellaquila.com): unique visitors per
page/edition via a daily-rotating salted hash (sha256 of daily salt | site | IP |
UA) — hashes only, deleted at day close, no cookies, no raw IPs, aggregate counts
only. **Once Analytics Buddy confirms the live ENDPOINT (Dave's one deploy step),
wire it the same day, exactly:**
- Add `<script async src="https://<ENDPOINT>/beacon.js" data-site="lenwood-gazette"></script>`
  to the front page, the Editions Archive, and every future edition snapshot
  (snapshots are born carrying it; counts are fetched live at view time, so frozen
  snapshots are NEVER edited after publication to change a count).
- Show counts with `<span data-visitor-count></span>` (counts the page it sits on);
  on archive listings use `<span data-visitor-count data-count-path="/editions/YYYY-MM-DD-<edition>.html"></span>`.
- NEVER ship the literal placeholder `<ENDPOINT>` — the real endpoint comes from
  Analytics Buddy. Editions published before the beacon lands cannot be counted
  retroactively; they start at zero under a "counting since <go-live date>" note.
Once wired, this beacon is a preserved standing element — rebuilds keep it like
PTR / LBX / TIPFLY / fsctl.
