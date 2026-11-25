# Validation and research plan

## What is and is not established

The existing README records earlier JSON parsing, duplicate-ID, HTTP(S)-URL, sanitised-default and JavaScript syntax checks. This documentation update reviewed source behaviour but did not rerun a browser test suite or reverify event facts. Neither user adoption nor ROI has been measured. The following is proposed validation, not completed results.

## Proposed usability study

Observe five potential users using synthetic preferences and costs. Ask each to find a relevant event, explain its freshness, shortlist it, estimate attendance cost, move it between wishlist and cart, and restore a hidden event. Record completion without assistance, time, errors, unexpected totals and comments. Set success criteria before testing. Publish anonymised observations and retest the most repeated obstacle after fixing it.

| Participant / date | Task | Completion / assistance | Observation | Decision | Retest |
| --- | --- | --- | --- | --- | --- |
| To collect | To collect | To collect | To collect | To decide | To collect |

## Proposed functional checks

| Scenario | Expected behaviour to verify |
| --- | --- |
| Combined filters | Main city list satisfies each active filter; separate summaries are understood |
| Unknown price sorting | Unknown prices appear last in both price directions |
| Cart arithmetic | ₹1,000 × 2 × 1.18 + ₹100 fees + ₹500 travel = ₹2,960 |
| Budget arithmetic | ₹10,000 budget − ₹1,000 already spent − ₹2,960 cart = ₹6,040 left |
| Wishlist | Does not increase used budget until moved to cart |
| Year boundary | 31 January belongs to the prior February–January year; 1 February starts the next |
| Hidden listing | Can be restored; hiding does not silently delete its cart entry |
| Reload | Plan persists on the same origin when storage works |
| Storage failure | Identify the current silent-failure risk and verify a future warning/fallback |
| Date freshness | Reproduce the current snapshot-date limitation; verify a future live-date fix separately |
| Mobile and keyboard | Filters, event links, budget fields, sheet close and focus are usable |

Use source fixtures for calculations and deterministic dates. Keep external event-fact verification separate from application tests. For each run record environment, source commit, steps, expected/actual result and unresolved gaps.

## Research to collect before claiming ROI

Compare a participant's current discovery-and-cost-estimation process with the prototype on a comparable task. Record actual time and errors, along with maintenance effort to keep listings current. Do not publish percentage savings until measured.
