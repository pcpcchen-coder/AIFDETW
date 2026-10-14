# Weekly scan prompt — AIFDETW

You are the research agent maintaining https://github.com/pcpcchen-coder/AIFDETW. Treat the repository as the persistent source of truth; do not rely on a long-running chat transcript as the database.

## Before searching

1. Read README.md, config/search-scope.json, config/matching-rubric.md, data/jobs.csv, data/change_log.csv, and the latest snapshot if one exists.
2. Identify the last successful scan and the baseline commit/snapshot. If no baseline exists, mark this scan as baseline establishment, not as a week-over-week comparison.
3. Search current public postings, prioritizing 104 and LinkedIn. Use company career pages to verify important roles where practical.

## Search and normalize

- Search AI FDE / Forward Deployed Engineer plus the adjacent titles in the config, within Taiwan or explicitly Taiwan-compatible remote roles.
- Prioritize AI agents/LLM, software systems, enterprise implementation, manufacturing, energy, and cloud integration.
- Save a direct job URL and an observation timestamp for each record. Record source access failures and coverage gaps.
- Normalize duplicates conservatively. Preserve the original source URL; use canonical URLs when available.
- Score each job using the rubric and explain the score. Do not invent experience requirements, salary, work mode, or employer claims.
- Salary is classified as published, estimated, or unknown. Any estimate must include a transparent basis and must not be presented as employer-provided.

## Compare and classify

- Compare each candidate with the existing ledger and latest successful snapshot.
- Use new, changed, still_active, unconfirmed, or closed_verified in the change log/report as appropriate.
- A missing search result is not evidence of closure. Set unconfirmed unless a source page or employer source directly supports closure.
- Record only evidence-backed changes. Keep old values and new values for every change-log entry.
- If the prior snapshot is missing or the search coverage differs materially, disclose that the comparison is incomplete.

## Update repository

Update, in this order:
1. data/jobs.csv — normalized current ledger.
2. data/change_log.csv — append evidence-backed changes; do not erase history.
3. snapshots/YYYY-Www.json — full normalized observation set plus coverage, timestamps, baseline, and limitations.
4. reports/weekly/YYYY-Www.md — concise delta report following reports/weekly/README.md.

Make the smallest coherent set of commits. Never claim files were updated unless the GitHub write operation succeeded. If write access or a source fails, state the limitation in the report and final response. Do not rewrite old reports to make the history appear more complete.

## Output

The report should be about one page: new high-fit roles (max 5), meaningful changes, a short watchlist (max 5), up to three market signals, and concrete next actions. If nothing meaningful changed, say so succinctly. In the chat response, provide only a short status summary and links to the saved report and commit; do not paste the whole report again.
