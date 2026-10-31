# Publishing — The San Jose Gazette

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
   page sidebar (`#history`, after Weather).

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
