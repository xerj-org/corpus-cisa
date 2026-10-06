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
- `kev/` one plain-text record per KEV entry: cve, vendorProject, product,
  vulnerabilityName, shortDescription, dateAdded, dueDate,
  knownRansomwareCampaignUse, and friends. `kev-source/` keeps the raw feed.
- `README-kev.md`, `LICENSE-kev`: provenance of the KEV half.
- `tools/` build scripts from the alerts mirror.

Quality pass at merge (2026-10-06): the 72 weekly "CISA adds N known
exploited vulnerabilities" announcement alerts were dropped. Every fact in
them (which CVE, added when, due when) is a field of the corresponding
`kev/CVE-*.txt` record; kept in one place, and per-CVE queries stop being
crowded out by announcement titles. Advisory and ICS bodies are byte-verbatim
from the source mirrors; nothing else was edited.

Merged from xerj-org/corpus-cisa-alerts and xerj-org/corpus-cisa-kev at their
2026-10-04 pins (see the hub manifest review blocks for the licence review of
each half). This repository is the merged, quality-passed single source.

Licences: CISA advisories are US-government works (17 USC 105); co-published
advisories (ASD/NCSC and partners, flagged `co-published:` in front-matter)
may carry partner-nation copyright, treat those per partner. The KEV catalog
is CC0-1.0. See LICENSE.md and LICENSE-kev.
