# Events Tracker — India Tech Events

An event whisperer for discovering tech conferences, meetups, workshops, hackathons and expos across India, with a personal planning and budget interface.

Built with HTML, CSS and vanilla JavaScript. One file, no installation or build step, and no paid AI API required.

## Features

- Browse events grouped by city and filter by event type
- Filter top picks, free events and certificate opportunities
- Sort by date or published ticket price
- Mark events for My Plans, maintain a wishlist and hide or restore listings
- Plan ticket tiers, quantities, GST, booking fees and travel costs
- Track custom expenses and spending within a February–January budget year
- Responsive interface with light and dark color support

## Run locally

With Python 3 installed, run from this repository's folder:

```sh
python3 -m http.server 8000
```

Open http://localhost:8000. `index.html` contains the complete app, styles, scripts and event data. No dependency installation is needed.

## Event data and limitations

This export contains **79 event listings and 46 watchlist entries**, based on a **2 November 2026 snapshot**. Some listed events have already passed. Dates, venues, ticket prices and availability can change; confirm details on the organizer's page before making plans or paying.

The app does not automatically discover events or refresh its dataset. Edit the JSON inside `<script id="events-data" type="application/json">` to update listings. The current implementation uses `meta.last_scan` as its reference date for classifying past and upcoming events, so classifications reflect the dataset snapshot until that value is updated. “Verified” badges were supplied with the imported dataset; the GitHub upload did not independently reverify those claims.

## Privacy and persistence

Public source has been prepared without the original user's attendance marks or taste profile. The ₹10,000 default budget is an illustrative starter amount, not a record of actual spending. Cart, wishlist, custom expenses and spending start empty.

Plans save to this browser's localStorage. They are not committed to GitHub, and do not sync automatically across devices or website origins. Clearing browser data can remove them. This version has no backup import/export interface.

An optional Claude account database hook is retained from the original artifact. It only attempts to run when `window.claude.use` is provided by the host. A normal local or static-hosted copy uses browser storage instead; no Claude account synchronization is promised outside that environment. Google Fonts is an external stylesheet dependency; fallback fonts are provided.

## Public version and original artifact

This is a standalone portfolio copy adapted from the uploaded Claude artifact export. Privacy edits remove personal preferences and replace the budget default. Update wording now describes the static snapshot rather than promising automatic monthly refreshes. The original Claude artifact and its saved data are unchanged.

## Validation

Before upload: embedded JSON parsed successfully; event IDs were checked for duplicates; listing URLs were checked for HTTP(S); personal profile and attendance defaults were checked; the application JavaScript passed a syntax check. Browser interactions and external event facts were not reverified during this upload.

## Possible next improvements

- Add backup export and import
- Separate event data from presentation code
- Add a documented event verification and update workflow
- Test filtering, budget calculations and storage failure behavior
