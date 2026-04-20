---
title: Example sub-entry
description: Demonstrates frontmatter, body conventions, and cross-linking patterns. Delete with the rest of the example folder once you have real content.
tags: [meta, example]
sensitivity: internal
related:
  - example/index
  - meta/sensitivity
---

This is what a typical sub-entry looks like.

## Body structure

Lead with the *what & why* in 2-3 sentences so the reader knows whether to keep going. Then the *how / details*. Section headings (`##`) improve readability; they don't change parsing.

## Cross-linking

Two ways to point at other entries:

- **Wikilinks** for terse internal references: see [[example/index]] for the parent folder index, or [[meta/sensitivity]] for tier policy.
- **Markdown links** when you want different display text: read the [sensitivity policy](../meta/sensitivity.md) before authoring confidential content.

External URLs stay as plain markdown links (`https://...`) and are ignored by the related-ref collector.

## Sensitivity reminder

This entry is `internal` because it's documentation for the team. If it described a real customer incident, a vuln, or a contract term, it would be `confidential`. See [[meta/sensitivity]].
