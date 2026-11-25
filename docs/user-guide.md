# Events Tracker user guide

Reviewed 25 November 2026 against the public source snapshot. This is a standalone India tech events planner with a static dataset, not a live search or booking service.

## Start locally

From the repository root, run:

```sh
python3 -m http.server 8000
```

Open http://localhost:8000. No application build or paid AI API is required.

## Find an event

1. Pick a city or city group using the City chips.
2. Choose an event type. Optionally toggle Top picks, Free or Certificate; active filters combine.
3. Sort by Date or Price. Unpublished prices sort last. The displayed base price does not necessarily include all costs.
4. Expand a city section, use Expand all, or turn off Sections by city for one list.
5. Read the event details, then use **Open page** to check the organiser's current information.

The main city list uses these filters. My Plans and New since last month are separate summary sections and do not necessarily use the active city/type filters. Watching contains events without confirmed next dates; the displayed month is a guide, not a confirmed appointment.

## Plan, wishlist or budget?

| Control | Purpose | Budget effect |
| --- | --- | --- |
| + My plans | Mark an upcoming event for the My Plans section; Unmark reverses it | None by itself |
| Wishlist | Save an option for later | Excluded from used budget |
| Add to cart | Include an event in the attendance-cost plan | Adds its estimated cost |
| Open page | Visit the organiser or ticket page | No purchase inside this app |

Adding to cart removes an item from the wishlist. An item already in the cart cannot also be newly wishlisted without first moving it. My Plans is independent of the cart: a cost plan is not proof of attendance or a ticket purchase.

## Work with the budget

1. Choose **Open cart** in the bottom budget dock.
2. Select a February–January budget year.
3. Enter your Yearly budget and any Already spent amount.
4. Review each ticket tier and quantity. Add booking fees and travel/stay costs.
5. Tick Add 18% GST only when appropriate for the estimate. The implementation uses a fixed 18% assumption; confirm the actual final charge with the organiser.
6. For an event without a published price, type an estimate to include it. An unknown price otherwise contributes zero, so a low total can be incomplete.
7. Add a course, certification, exam or other custom cost using its name, amount, type and optional date.

Ticket line estimate = base ticket price × quantity × (1.18 when GST is selected, otherwise 1) + booking fees + travel/stay. Fees and travel are added once per cart line, not multiplied per ticket. The implementation rounds each ticket line to whole rupees. Used budget = Already spent + cart + custom items. Wishlist totals are separate.

Avoid counting a paid item both in Already spent and in the cart. There is no purchase reconciliation. The budget amount is shared across the displayed budget years; Already spent is stored per year. The ₹10,000 starter budget is illustrative. A dated custom cost follows its February–January year; one without a date uses the selected budget year. Watchlist entries without a confirmed date use provisional year logic and should not be treated as booked plans.

## Hide and restore

Use × on a listing to remove it from your page. Open **Removed by me** at the bottom and choose **Put back** to restore it. Hiding a listing is a display action; it does not automatically remove a corresponding cart cost.

## Saving and limitations

Changes save to browser localStorage after a short delay. Use the same browser profile and site address to return to the same records. Normal static hosting does not provide account sync. The optional original-host database hook runs only if that host supplies `window.claude.use`; it is not a portable account-sync feature.

There is no backup import/export interface in this version. Clearing browser data or moving to another origin can lose access to plans. A save message is not proof that storage succeeded: current local-storage write failures are caught without a reliable user warning.

## Dataset freshness

The source contains 79 event listings and 46 watchlist entries from a 2 November 2026 snapshot. Past/upcoming classification uses `meta.last_scan`, so it can be stale relative to today's date. Top picks and Verified labels come from the imported data, not a live personalised model or a verification performed for these docs. No automatic monthly refresh or watchlist promotion runs in the background.

## Troubleshooting

| Problem | What to check |
| --- | --- |
| No matching events | Clear city, type and toggle filters; hidden or past events are outside the main list |
| Saved item missing | Same browser/profile/origin; Removed by me; correct budget year |
| Total unexpectedly low | Unpublished prices, missing fees/travel and custom-cost year |
| Total unexpectedly high | Ticket quantity, GST setting and double counting Already spent |
| Event date looks old | Dataset snapshot and organiser's current page |
| Plans lost after clearing browser data | This version has no built-in recovery backup |
