# AIFDETW — Taiwan AI FDE Job Radar

A version-controlled job-tracking workspace for Taiwan-based AI Forward Deployed Engineer (FDE) and adjacent roles.

## Goals

- Track new, changed, closed, and unconfirmed job postings with source URLs.
- Keep durable job records and weekly snapshots outside long-running chat threads.
- Publish concise weekly delta reports and monthly market trend summaries.
- Preserve provenance and avoid treating missing search results as proof that a job has closed.

## Data policy

- `data/jobs.csv` is the current normalized job ledger.
- `data/change_log.csv` records evidence-backed changes.
- `snapshots/YYYY-Www.json` stores the observation set for each weekly scan.
- `reports/weekly/YYYY-Www.md` contains only new findings, meaningful changes, top matches, and market signals.
- `reports/monthly/YYYY-MM.md` contains trend analysis, not a copy of every weekly report.
- Unknown values remain blank or `unknown`; never invent salary, status, or requirements.
- A job not found in one search is `unconfirmed`, not automatically `closed`.

## Weekly workflow

1. Read the configuration and the latest snapshot/ledger.
2. Search public sources, prioritizing 104 and LinkedIn; retain direct source URLs and observation timestamps.
3. Normalize records and deduplicate conservatively by URL, company, title, and location.
4. Compare with prior records and label changes as `new`, `changed`, `still_active`, `unconfirmed`, or `closed_verified` only when supported by evidence.
5. Update the ledger, append evidence-backed changes, save a dated snapshot, and write a concise weekly delta report.
6. If GitHub write access is unavailable during a run, report that limitation explicitly and do not claim the repository was updated.

## Repository map

- `config/`: search scope, scoring rubric, and source policy.
- `data/`: normalized ledger and change history.
- `schemas/`: JSON schema for records.
- `snapshots/`: dated raw normalized observations.
- `reports/weekly/`: compact weekly reports.
- `reports/monthly/`: monthly market summaries.
- `prompts/`: reusable agent instructions.

## Current scope

Search for AI FDE / Forward Deployed Engineer and closely related Senior FDE, AI Solutions Engineer, GenAI Engineer, and AI Solution Architect roles in Taiwan. Prioritize roles combining software, AI agents, enterprise deployment/integration, manufacturing, energy, cloud, and systems engineering. Salary must be sourced or clearly marked as an estimate with its basis.
