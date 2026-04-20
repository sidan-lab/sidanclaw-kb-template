---
title: Tag glossary
description: Canonical tag vocabulary used across this knowledge base. New entries should reuse these tags before inventing new ones.
tags: [meta, glossary]
sensitivity: internal
---

Tags get FTS B-band weight in search, so consistency matters more than coverage. Pick from the lists below; only invent a new tag if nothing here fits, and add it to this glossary in the same change.

Aim for **3-6 tags per entry**: one or two from "kind", one or two from "domain", optionally one or two free.

## Kind tags

What *type* of entry this is.

- **spec** — architecture or behavioural specification (the source of truth)
- **runbook** — operational steps for a recurring task
- **reference** — lookup material (schemas, API surfaces, glossaries)
- **decision** — a recorded decision with rationale
- **glossary** — term definitions
- **policy** — rules the team has agreed to follow
- **postmortem** — incident write-up
- **meta** — about the KB itself, not about the product

## Domain tags

What *area* of the product / business this is about. Edit to match your team.

- **product** — top-level product surfaces
- **infra** — infrastructure, deployment, observability
- **security** — auth, secrets, threat model
- **billing** — pricing, subscriptions, invoicing
- **data** — data model, migrations, ETL
- **customer** — customer-facing flows, support
- **internal** — internal tooling, dev workflow

## Free tags

For entries that need a tag this glossary doesn't cover (e.g. a project codename, a specific vendor), add it here with a one-line definition. Resist the urge to over-categorise — three good tags beat eight redundant ones.
