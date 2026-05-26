---
layout: post
title: "pbakaus/impeccable: The Design Upgrade Promise — Does It Deliver?"
date: 2026-02-28
category: Skill-Evaluation
skill_reviewed: "pbakaus/impeccable"
verdict: vertrauen
reading_time: 11
last_audited: "February 28, 2026"
lang: en
lang_url: /2026/02/28/pbakaus-impeccable-evaluation/

skill_scores:
  methodische_fundierung: 4
  methodische_fundierung_note: "Reference files have sources, but porting is partially superficial"
  transparenz: 3
  transparenz_note: "Marketing rhetoric of 'upgrade' obscures where trade-offs lie"
  validierbarkeit: 3
  validierbarkeit_note: "20 slash commands are documented, but no comparison to baseline"
  wartbarkeit: 4
  wartbarkeit_note: "Active author with Google/Raycast background; own domain; active GitHub"

tags:
  - design-frontend
  - upgrade-fallacy
  - critical-example
  - skill-evaluation
---

The most discussed skill of recent weeks, 10,000 GitHub stars in three weeks: a big promise. Paul Bakaus explicitly positions `impeccable` as what Anthropic's `frontend-design` could have been — more complete, more practical, unobstructed. But big promises require big scrutiny.

## Paul Bakaus — The Foundation Is Right

We need to settle this first: Paul Bakaus is not just any designer with a domain name. Ex-Google, co-creator of Raycast (the app many of us live in daily), speaker at international conferences. That is verifiable judgment.

And yes, impeccable.style is *his* domain, not a repository with a marketing-sounding name. That counts.

But reputation is not method. Let's look inside.

## Structure: 7 Files, 20 Slash Commands

The skill is openly structured: seven reference files (Typography, OKLCH color space, motion, interaction, spacing, dark mode, accessibility) and 20 slash commands covering all aspects. That is not breadth for breadth's sake — it is appropriate scope for "frontend design." Compared to other skills, that is refreshingly focused.

The problem: we need to actually read the reference files to know what is inside.

## The First Critical Problem: What Are the "References" Actually?

Here it gets interesting. The skill claims to have seven reference files:

1. **Typography** — Presumably web typography. But by whose standard? Robert Bringhurst's 10 core principles? Material Design? Apple's Guidelines? Or simply "good practices"?
2. **OKLCH-Color** — A color space. That is mathematically defined, not interpretable. Good. But how is color selection methodologically justified?
3. **Motion** — 300ms as magic number. We know that from Emil Kowalski. Is Kowalski cited? Or is the number adopted without context?
4. **Interaction** — What does "good interaction" mean? Speed? Feedback? Predictability?
5. **Spacing** — Probably 8px grid or modular scale. But which source does this follow?

This is the suspicious spot: **The categories exist, but are they actually bound to sources, or merely named?**

Our job as a blog is to verify this. A skill that says "Nielsen's 10 heuristics" or "Don Norman's principles" but only correctly ports 3 of them is problematic.

## The Second Problem: The "Upgrade" Claim Is Marketing, Not Method

The entire pitch is: "What Anthropic's `frontend-design` should have been."

That is an implicit attack. And probably not entirely unfair — Anthropic's skill is broader and less coherent. But this blog does not evaluate *competition between skills*, it evaluates *quality of individual skills*.

And this is precisely where `impeccable` loses a point: it defines itself through comparison rather than through its own substance.

A solid skill says: "This is what I am. Here are the limitations. Here are the sources." A marketing skill says: "This is what I am but also better."

## An Honest Assessment of What the Skill Delivers

The 20 commands are consistent and follow a recognizable logic: `/suggest-typography` and `/optimize-spacing` are related, both grounded in mathematical design principles. Scope is clear — frontend design, not "everything for UX."

What's missing: if I run `/suggest-color-palette`, how do I verify whether the output is good? A skill could show this — "With base design X, the palette should satisfy properties [A, B, C]" — that would be testable. And if `impeccable` is supposed to be better than Anthropic's `frontend-design`: where are the metrics for that?

## The Four Dimensions in Detail

### Methodological rigor: 4/5

The references exist and have names. That is better than 10 principles without sources. But the porting of the methods is not fully documented. A footnote "Typography based on Robert Bringhurst, Thinking with Type" would clarify everything. It does not exist.

### Transparency of limitations: 3/5

The skill does not say: "I cannot enforce inclusive design" or "Dark mode is only calculated based on mechanical contrasts, not perceptual contexts." Instead, "Accessibility" is presented as one file among seven — as if a single file solves the problem. That is not malicious. But it is a promise larger than the truth.

### Testability: 3/5

The commands are documented, that is verifiable. But there is no quality standard. Which output is "good"? A framework like Nielsen or Kowalski could show this: "With this input definition, this output should emerge." Without test cases, the skill cannot be objectively verified.

### Maintainability: 4/5

Paul Bakaus is an active author, the repositories are maintained, there are releases. Solid. The only note: it is still very new (3 weeks). How long will the maintenance last? Kowalski has years of production expertise behind him. Bakaus has an enthusiastic community but not yet a long-term track record.

## What the Skill Is Good For — and What It Is Not

For designers wanting a structured entry into frontend constraints, the skill works well. The organization is logical, the breadth adequate. Teams that need to prove their design decisions are methodologically sound won't get far with it — for that, you need sources and test cases. And students should know: the skill provides constraints, not a complete design system.

## Verdict: Trust, Not Solid

The skill earns trust because the author has verifiable knowledge, the structure is logical, and the commands are practical. It does not earn "Solid Foundation" because the source bases are not transparent, the Anthropic comparison is a marketing framing rather than a methodological one, and no test cases exist to verify quality.

---

**A final note for educators:**

This skill is a teaching example of how understandable structure and personal credibility can mask methodological weaknesses. Paul Bakaus is credible. The skill *looks* rigorous. But "looks rigorous" is not "is rigorous."

That is what scrutiny means.
