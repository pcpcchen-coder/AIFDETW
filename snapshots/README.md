# Weekly snapshots

Create one JSON snapshot per scan using ISO week naming, for example 2026-W43.json.

Each snapshot should contain schema_version, scan_started_at, scan_completed_at in Asia/Taipei time, sources_checked with result counts and access limitations, baseline_commit or the previous snapshot filename used for comparison, jobs as normalized job observations with source URL/status/evidence, and scan_notes covering failures and caveats.

Do not fabricate a snapshot for a scan that did not happen. The repository was initialized on 2026-10-14 without importing an earlier verified job ledger; the first successful scan should establish a new baseline. It must not claim historical additions, closures, or salary changes without prior evidence.
