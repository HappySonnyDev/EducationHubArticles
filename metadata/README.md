# Knowledge Base migration preview

Source snapshot: `ce9868828b2c91ffe8b4fea8c813dd7c94cb5676`.

`catalog.json` is a non-destructive sidecar. Article folders, Markdown bytes, dates,
authors and translations in the source remain unchanged. Canonical paths are
derived from the existing website's `/knowledge-base/[slug]` route and actual
locale filenames, not from historical candidate URLs.

`handoff.json` contains the supplied workbook's public taxonomy and classification
proposals, not its private analytics/evidence columns. `reconciliation.json`
records unmatched candidates, unresolved pins and source metadata problems.

All classifications remain pending editorial review. Exact-path matches,
historical grouping suggestions and translation inheritance are separately
identified. Grouping never changes a URL or authorizes a redirect. Unmatched
articles remain available in the general library instead of disappearing.
Blank metadata never overwrites existing frontmatter. Date normalization only
reuses the three corrections already implemented by the website parser.

Reproduce using the website repository's `scripts/prepare-kb-content.mjs` with
this checkout as its argument. Review classifications before production rollout.
Verify sourceSHA256/bodySHA256 before accepting any later frontmatter import.
