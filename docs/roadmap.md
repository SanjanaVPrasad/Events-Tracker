# Proposed roadmap: Events Tracker

Planning document, 25 November 2026. These are proposals; this documentation commit does not implement them.

| Priority | Work | Acceptance criteria |
| --- | --- | --- |
| P0 — Next | Separate current date from last verified date | Past/upcoming follows a testable current date; snapshot date remains visible; boundary scenarios pass |
| P0 — Next | Document and execute event-data verification | Each changed listing has an organiser source, verification date and explicit unknown fields; stale/cancelled handling defined |
| P1 — Soon | Backup/recovery and storage-failure feedback | User can export and restore a sample plan; invalid imports are handled safely; failed saves have visible feedback |
| P1 — Soon | Test discovery and budget usability with five people | Anonymised observations, assistance and errors recorded; repeated problems prioritised |
| P1 — Soon | Cover budget and filtering logic with tests | Arithmetic, unknown prices, wishlist exclusion, year boundaries and combined filters checked |
| P2 — Later | Separate data from interface and configure preferences | Documented data schema; safe defaults; configurable locations and budget periods supported by research |
| P3 — Explore | Evaluate personalised event recommendations | Defined test set and ordinary-filter/ranking baseline; compare relevance, factual accuracy, abstention, cost and latency before any API integration |

## Optional AI PM experiment — not implemented

Use a fixed event snapshot and synthetic profiles. Compare a simple rule-based shortlist with a proposed model on the same labelled cases. Include missing dates/prices, incompatible locations and no suitable event. Measure constraint satisfaction and source-supported facts, not just persuasive explanations. Set acceptance thresholds and an experiment spending cap before running it. Preserve ordinary filters as a fallback and let users inspect or reject suggestions. Do not announce a recommender or quality score until it exists and has been evaluated.

## Contribution workflow

Track a specific user problem in an issue with acceptance criteria. Submit a focused change and a pull request explaining the behaviour change, validation and limits. Use generic data for demonstrations. Attach research and release evidence to the case study; document AI assistance and human review honestly.
