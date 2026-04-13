---
layout: post
title: "ui-ux-pro-max: When a Database Gets Called a Methodology"
date: 2026-03-14
category: Skill-Evaluation
skill_reviewed: "nextlevelbuilder/ui-ux-pro-max-skill"
verdict: vorsicht
reading_time: 10
last_audited: "March 14, 2026"
lang: en
lang_url: /2026/03/14/nextlevelbuilder-ui-ux-pro-max-evaluation/

skill_scores:
  methodische_fundierung: 2
  methodische_fundierung_note: "344 resources, but no traceable origin for the 99 UX guidelines"
  transparenz: 2
  transparenz_note: "Boundary between database-matching and real UX judgment remains invisible"
  validierbarkeit: 2
  validierbarkeit_note: "CSV files are visible — but not validated against real user data"
  wartbarkeit: 3
  wartbarkeit_note: "Active, v2.0 released, but solo project with unclear succession"

tags:
  - database
  - ui-ux
  - quantity
  - skill-evaluation
---

The skill sounds like the most complete design tool in the ecosystem: 161 color palettes, 57 font pairings, 99 UX guidelines, 25 chart types, 161 product types, 10 technology stacks. If completeness were a methodology, this would be the reference.

But completeness is not a methodology.

## What the Skill Is

`ui-ux-pro-max` by nextlevelbuilder is, at its core, a searchable database. CSV files in the `data/` directory store design resources: styles, colors, typography, product types. A Python-based search interface (`--design-system` command) searches this database based on project requirements and generates a "complete, custom-tailored design system" in seconds.

The flagship of v2.0 is the *Design System Generator* — an "AI-powered reasoning engine" that analyzes requirements and outputs matching design decisions. That sounds like intelligent judgment. It is pattern-matching on CSV data.

## The Quality Problem of the 99 UX Guidelines

<div class="callout">
<div class="callout__title">The decisive question for any knowledge database</div>
Who formulated these guidelines, and on what basis?
</div>

The 99 UX guidelines are ranked by priority and cover accessibility, touch interaction, performance and responsive layout. That sounds structured. But: not a single guideline in the public repository references a source. There is no WCAG mapping, no Nielsen reference, no link to study results.

That does not mean the guidelines are wrong. It means: they cannot be verified. And what cannot be verified should not be trusted blindly in a teaching context.

By comparison: WCAG 2.1 has a source citation, a success criteria hierarchy and test procedures for every guideline. That is the standard for traceable UX guidelines.

## Quantity as a Quality Signal

161 color palettes. 14 supported coding agents. "344+ design resources." These numbers are the project's main argument — the website, the README, the descriptions all emphasize quantity.

This is a pattern students should recognize: **Size is not a quality indicator.** A database with 1000 color palettes without provenance and context is less valuable than a well-considered color system with 12 tokens and clear semantics.

More is only more when the more is also better. With this skill, that is unclear.

## What Makes the Skill Useful

The matching principle has real utility for prototyping: "I'm building a FinTech app in a minimal style" generates concrete suggestions for colors, fonts and components. That is faster than a blank page. For exploratory phases, where direction matters more than precision, this can be useful.

The CSV structure also means the database is transparently visible. Anyone wanting to validate the sources of the 99 guidelines themselves can look at the files — even if the guidelines themselves cite no sources.

## Recommendation

Use with explicit context: this skill generates suggestions from a database, not judgments from user research. What it outputs is a starting point — not a result.

For students, this skill is a good teaching object for a specific question: What is the difference between a knowledge collection and a methodology? A methodology does not only explain *what* to do, but *why*, *for whom*, and *how to verify whether it has worked*.

The 344 resources in this skill answer the first question. The other three remain open.
