---
description: List or clean up Google Maps scrape jobs
argument-hint: "[list | delete <job-id> | download <job-id>]"
---
Manage scrape jobs via the API. Request: **$ARGUMENTS** (default to "list" if empty).

- **list** → `GET http://localhost:8080/api/v1/jobs`. Show a tidy table of `ID`, `Name`, `Status`, `Date` (newest first).
- **delete <job-id>** → `DELETE http://localhost:8080/api/v1/jobs/<job-id>` to free disk space, then confirm it returned HTTP 200.
- **download <job-id>** → download the raw CSV, then **always** convert with:
  `python3 scripts/scrape.py --from-csv <raw.csv> --out output/<name>.csv`
  The saved file must be the lean lead columns (`nome, telefone, emails, …`), never the raw 34-column dump.
  Show a short preview (nome | telefone) and the output path.

See the `google-maps-scraper` skill for the full API reference.
