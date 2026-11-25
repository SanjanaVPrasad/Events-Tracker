# Product decision log

Recorded 25 November 2026 from the public source. Rationales below describe the design and constraints, not measured user preferences.

| Choice | Benefit / rationale | Tradeoff / follow-up |
| --- | --- | --- |
| One HTML file with embedded styles, logic and dataset | Easy standalone prototype and local setup | Harder to maintain and test as data grows |
| Group by city with type and cost filters | Support location-led browsing | Test discovery for remote users and cross-city travel |
| Separate My Plans, wishlist and cart | Distinguish interest from planned spending | Users may confuse them; test labels and explain budget effects |
| Include fees and travel in cost estimates | Reflect more than the headline ticket price | Manual estimates and fixed GST assumption can be wrong |
| February–January budget year | Preserve the original personal planning model | Unusual for other users; test need for configurable periods |
| Browser localStorage | Keep the standalone prototype simple | No portable sync or built-in recovery; write failures need clearer feedback |
| Static dataset and imported relevance labels | Operate without search APIs or model cost | Dates, prices and recommendations become stale |
| Classify dates against meta.last_scan | Reproduce the snapshot view | Misleading as time passes; separate today's date from last verification |

For each future decision, retain: date, user problem, alternatives, evidence, chosen approach, consequence and reconsideration trigger.
