# sidanclaw-kb-template

A starter repository for a [sidanclaw](https://ai.sidan.io) team knowledge base.

## What this is

sidanclaw teams sync a GitHub repository of markdown files into a searchable, browsable knowledge base. The assistant queries it via the `searchKnowledge`, `browseKnowledge`, and `readKnowledgeEntry` tools.

This template ships an opinionated skeleton: a root index, a sensitivity-tier glossary, a tag glossary, and one example folder showing the `index.md` + sub-entry pattern. Fork it, edit the meta files to match your team's policy, then add your content.

## Get started

1. Click **Use this template** → **Create a new repository** (or `gh repo create my-team-kb --template sidan-lab/sidanclaw-kb-template --public` / `--private`).
2. Edit `meta/sensitivity.md` to encode your team's tier policy.
3. Edit `meta/tags.md` to set your canonical tag vocabulary.
4. Edit `index.md` to introduce your KB.
5. Replace or extend the `example/` folder with your real content.
6. In the sidanclaw web app, go to your team's settings → **Knowledge** → connect this repo.
7. Wait up to 15 minutes for the first sync, or trigger a sync manually.

## Authoring

Every entry is a markdown file with YAML frontmatter. Minimum:

```markdown
---
title: <Display title>
description: <One-sentence summary, shown in search/browse listings>
tags: [<3-6 tags>]
sensitivity: internal
---

Body content...
```

See `index.md` and `example/index.md` for working examples. For deeper guidance — when to pick which tier, how to cross-link, what to migrate from an existing `docs/` tree — invoke the `kb-author` skill in any sidanclaw conversation, or run the `@sidanclaw/kb` CLI for an interactive author flow.

## Sensitivity

Three tiers (`public` < `internal` < `confidential`). Each entry's `sensitivity` field controls which assistants can read it: an assistant only sees entries at or below its configured `clearance`. Default tier when omitted is `internal`. See `meta/sensitivity.md` for your team's policy and `docs/architecture/platform/sensitivity.md` in the sidanclaw repo for the full design.

## License

MIT — feel free to fork and adapt.
