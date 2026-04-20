---
title: Team Knowledge Base
description: Root entry for the team knowledge base. Lists top-level domains and points to the meta glossary.
tags: [meta, index]
sensitivity: internal
---

Welcome to the team knowledge base.

This is the entry point. The assistant lands here when browsing without a path, so it should orient a fresh reader: what this KB covers, who it's for, where to start.

## Top-level areas

Replace this list with your real folders.

- [Example](example/index.md) — illustrative folder showing the index + sub-entry pattern. Delete once you have real content.

## Meta

- [Sensitivity policy](meta/sensitivity.md) — when to tag entries `public`, `internal`, or `confidential`
- [Tag glossary](meta/tags.md) — canonical tag vocabulary

## Conventions

- Every directory has an `index.md`. It's the canonical "what is this folder" answer.
- Every entry has `title`, `description`, and `sensitivity` in frontmatter.
- Cross-link with wikilinks (`[[absolute/path]]`) or markdown links (`[text](path.md)`).
- New tags get added to `meta/tags.md` in the same change.
- Content gets edited via PR. The sync worker re-parses every 15 minutes.
