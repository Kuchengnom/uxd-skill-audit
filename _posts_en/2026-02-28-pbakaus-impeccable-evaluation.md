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

The skill is openly structured:
- **References**: Typography, OKLCH color space, motion, interaction, spacing, dark mode, accessibility
- **Commands**: 20 different commands covering all aspects

That is not breadth — it is *appropriate* breadth for the scope "frontend design." Compared to other skills, that is refreshingly focused.

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

Positive: The skill is **consistently implemented**. The 20 commands are not arbitrary. They follow a recognizable logic. `/suggest-typography` is related to `/optimize-spacing` — both follow mathematical/design principles.

Positive: **Scope clarity**. It is a frontend design skill, not "everything for UX."

Negative: **No structured test cases**. If I run `/suggest-color-palette`, how do I verify if the output is good? A skill could say: "With base design X, the palette should satisfy properties [A, B, C]." That I could test.

Negative: **No comparability to baseline**. Anthropic's `frontend-design` is a baseline. `impeccable` claims to be better. Where are the metrics for that?

## The Four Dimensions in Detail

**Methodological Rigor: 4/5**

The references exist and have names. That is better than 10 principles without sources. But the *porting* of the methods is not fully documented. A footnote "Typography based on Robert Bringhurst, Thinking with Type" would clarify everything. It does not exist.

**Transparency of Limitations: 3/5**

The skill does not say: "I cannot enforce inclusive design" or "I have no cultural sensitivity." It also does not say "Dark mode is only calculated based on mechanical contrasts, not perceptual contexts."

Instead, "Accessibility" is presented as one file among seven — as if a single file solves the problem.

**Testability: 3/5**

The commands are documented. That is verifiable. But there is no quality standard. Which output is "good"? A framework like Nielsen or Kowalski could show this: "With this input definition, this output should emerge." Without test cases, the skill cannot be objectively verified.

**Maintainability: 4/5**

Paul Bakaus is an active author, the repositories are maintained, there are releases. Solid. The only note: it is still very new (3 weeks). How long will the maintenance last? Kowalski has years of production expertise behind him. Bakaus has an enthusiastic community but not yet a long-term track record.

## What the Skill Is Good For — and What It Is Not

**Good for**: Designers wanting a structured entry into frontend constraints. The organization is logical. The breadth is adequate.

**Not good for**: Teams that need to *prove* their design decisions are methodologically sound. For that, you need sources and test cases.

**Risk**: Students might believe the skill generates a "complete design system." That is false. The skill provides constraints, not systems.

## Verdict: Trust, Not Solid

This skill deserves the trust of its users **because**:
- The author has verifiable knowledge
- The structure is logical
- The commands are practical

This skill does **not** deserve a "Solid Foundation" rating **because**:
- The source bases are not transparent
- The comparison to Anthropic is a marketing framing, not scientific
- No structured test cases exist to verify quality

---

**A final note for educators:**

This skill is a teaching example of how understandable structure and personal credibility can mask methodological weaknesses. Paul Bakaus is credible. The skill *looks* rigorous. But "looks rigorous" is not "is rigorous."

That is what scrutiny means.
