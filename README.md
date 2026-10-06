# corpus-cisa

One CISA corpus: cybersecurity and ICS advisories plus the Known Exploited
Vulnerabilities (KEV) catalog, mirrored as plain files for retrieval.
Unofficial mirror, not affiliated with CISA. The authoritative sources are
https://www.cisa.gov/news-events/cybersecurity-advisories and
https://www.cisa.gov/known-exploited-vulnerabilities-catalog .

Layout:

- `alerts/` CISA cybersecurity advisories as markdown (2025-05 to 2026-10
  window), front-matter: title, type, id, date, source.
- `ics/` ICS-CERT advisories (ICSA/ICSN records), same front-matter.
- `kev/` one plain-text record per KEV entry. Each opens with a one-sentence
  plain-English view ("KEV record: CVE-... is listed in the CISA Known
  Exploited Vulnerabilities catalog. ... remediation due ...") so a natural
  question matches the record; the original fields follow verbatim below it.
- `README-kev.md`, `LICENSE-kev`: provenance of the KEV half.
- `tools/` build scripts from the alerts mirror.

Quality passes at merge (2026-10-06), both recorded in the hub manifest:

1. The 72 weekly "CISA adds N known exploited vulnerabilities" announcement
   alerts were dropped. Every fact in them is a field of the corresponding
   `kev/CVE-*.txt` record, and their titles crowded per-CVE queries.
2. Each KEV record gained the one-sentence plain-English view (fields below
   it stay verbatim), and the raw feed blob left the tree: indexing one
   1.7 MB JSON that contains every record is a crowding source, not a
   retrieval unit. Feed provenance: catalogVersion 2026.10.04, file
   known_exploited_vulnerabilities.json, sha256
   f51fed1c9213e7b797104fcd6dbeb1b0dc0c7073a80467b9d4b1fc25e7dd786b.

Advisory and ICS bodies are byte-verbatim from the source mirrors; nothing
else was edited.

Merged from xerj-org/corpus-cisa-alerts and xerj-org/corpus-cisa-kev at their
2026-10-04 pins (see the hub manifest review blocks for the licence review of
each half). This repository is the merged, quality-passed single source.

Licences: CISA advisories are US-government works (17 USC 105); co-published
advisories (ASD/NCSC and partners, flagged `co-published:` in front-matter)
may carry partner-nation copyright, treat those per partner. The KEV catalog
is CC0-1.0. See LICENSE.md and LICENSE-kev.
