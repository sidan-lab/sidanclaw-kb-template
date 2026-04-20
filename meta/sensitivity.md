---
title: Sensitivity policy
description: Canonical guide for tagging entries with `public`, `internal`, or `confidential`. New entries should match this policy or update it in the same change.
tags: [meta, policy, sensitivity]
sensitivity: internal
---

Every entry must declare a `sensitivity` tier in its frontmatter. The tier controls which assistants can read it — an assistant with `clearance: public` cannot see `internal` or `confidential` entries; one with `clearance: internal` cannot see `confidential`; one with `clearance: confidential` sees everything.

Default when omitted is `internal`. **Do not rely on the default for sensitive content** — always set it explicitly when an entry could plausibly be confidential.

## Tier definitions

### `public`

Safe for any assistant — including customer-facing bots — to read and quote externally.

Use for:

- Product overviews, FAQs, public-API documentation
- Pricing pages, marketing copy, brand guidelines
- Anything you would publish on a public docs site

Do not use for: anything that names a specific customer, internal hostname, employee, vendor contract term, or roadmap item.

### `internal` (default)

Safe for the whole team. Not for external-facing output.

Use for:

- Architecture documentation
- Process / workflow / runbook documentation
- Roadmap, planning notes
- Most engineering documentation

This is the default when `sensitivity:` is omitted.

### `confidential`

Restricted to assistants explicitly granted `clearance: confidential`.

Use for:

- Anything naming a specific customer (incident reports, accounts, deals)
- Security-relevant material (auth flows, key management, vuln reports)
- Vendor / partner contract terms, legal positions
- Cap table, fundraising terms, internal financials
- Personally identifying information

When in doubt between `internal` and `confidential`, pick `confidential`. Downgrade later if needed; an over-restricted entry is recoverable, an under-restricted one is not.

## How tier affects authoring

- **Cross-references in `frontmatter.related[]`** are filtered by the reader's clearance — above-clearance entries are silently dropped from the array. Safe.
- **Cross-references in body text** (wikilinks `[[...]]` or markdown links) render the path as text regardless of the target's tier. A `public` entry whose body says `[[security/key-rotation]]` leaks the path string `security/key-rotation` to a public-cleared reader, even though the resolved entry is hidden. **Use `frontmatter.related[]` instead of body links when crossing tiers.**
- **An `index.md` for a mixed-tier folder** must be at least the highest tier that its body lists by name. If `products/index.md` enumerates a `confidential` sub-entry in body, the index must be `confidential` too — or omit that sub-entry from the index body and let the children-listing logic handle it.

## Auditing

Run the `kb lint` CLI before merging changes — it flags missing `sensitivity`, cross-tier body links, and mixed-tier indices.
