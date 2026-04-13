---
layout: post
title: "emilkowalski/skill: This Is What a Skill Should Look Like"
date: 2026-03-26
category: Skill-Evaluation
skill_reviewed: "emilkowalski/skill"
verdict: solide
reading_time: 9
last_audited: "March 26, 2026"
lang: en
lang_url: /2026/03/26/emilkowalski-skill-evaluation/

skill_scores:
  methodische_fundierung: 5
  methodische_fundierung_note: "Every principle is traceable to published articles and independently verifiable"
  transparenz: 4
  transparenz_note: "Explicitly declared as context-dependent — not a universal tool"
  validierbarkeit: 4
  validierbarkeit_note: "Source articles are the test cases; principles demonstrated on real projects"
  wartbarkeit: 4
  wartbarkeit_note: "Active maintainer with verifiable expertise and public track record"

tags:
  - motion
  - design-engineering
  - positive-example
  - skill-evaluation
---

The previous posts on this blog have described gaps: missing citations, epistemically unfulfillable instructions, archived repos, databases passing as methodology. This post describes the opposite.

## Who Emil Kowalski Is — and Why That Matters

Before evaluating the skill, the author must be evaluated. That sounds like an ad hominem argument, but in the skill ecosystem it is structurally necessary: a skill is distilled judgment. Whose judgment is inside?

Emil Kowalski is a Design Engineer at Linear (previously Vercel), author of the open-source libraries Sonner (toast notifications) and Vaul (drawer components), and course creator at [animations.dev](https://animations.dev). His work is in production products used by millions of users daily. That is a verifiable track record — not self-description.

That plays a decisive role for the first dimension.

## What the `/skill` Page Does Differently

The entry point for this skill is not a GitHub README. It is a dedicated page on his personal website that explains what the skill is, where it comes from, and — crucially — how to use it correctly.

Emil explicitly recommends: use the skill **context-dependently**, not as a permanent background configuration. This simple formulation communicates a limitation that most other skills silently ignore. He is saying: I know what this skill can do, and I know what it cannot do — and you should know that too.

## Why Methodological Traceability Works Here

<div class="callout">
<div class="callout__title">The Core Principle of Good Skill Quality</div>
A skill whose principles are readable, verifiable and discussable independently of the skill itself is a skill that can be trusted.
</div>

Emil's SKILL.md is distilled from articles on his blog. That means: every principle has a source. Anyone wanting to know why he recommends `clip-path` as a preferred animation primitive can read the corresponding article. Anyone wanting to know why he keeps animations under 300ms and cites Raycast as an example of an app that works better without animation can find the reasoning.

That is the difference between a skill that *claims* and a skill that *argues*. The claim is not verifiable. The argument is.

For comparison: the 99 UX guidelines in `ui-ux-pro-max` have not a single source citation. Both skills make statements about good design. Only one of them shows the work.

## What the Skill Actually Covers

The scope is clear and honest: **UI animation and design engineering**. Not usability, not user research, not accessibility compliance. Animation timing (under 300ms), spring parameters, contextual decision-making about whether to animate at all, performance considerations (CSS over JavaScript for critical paths).

That is little compared to skills promising "344+ design resources" or "26 roles and 60 commands." But it is little that is *complete*. A clearly scoped skill with depth is more valuable than a broad skill without foundation.

## What Is Still Missing — Here Too

A perfect score is not awarded, because it has not been earned. Two points remain open:

**Accessibility**: `prefers-reduced-motion` is mentioned in the skill, but not treated as a systematic requirement. Animations that feel "inevitable and natural" to the average user can be problematic for users with vestibular disorders. That deserves more than a side note.

**Formal test cases**: The source articles are the de facto reference, but there are no structured expectations (Input X → Output Y) that would be testable. That is not a severe deficiency for this skill type, but it is a limitation.

## What Students Can Learn Here

This skill concretely shows what the four evaluation dimensions mean in practice:

**Methodological rigor** is not the number of rules included. It is the traceability of the reasoning behind them.

**Transparency** is not the disclaimer at the end. It is the way the skill describes itself: as a context-dependent tool, not a universal solution.

**Testability** is not the presence of examples. It is the ability to verify the principles independently of the skill itself — through source articles, real projects, traceable argumentation.

**Maintainability** is not commit count. It is a maintainer with verifiable judgment and skin in the game.

---

This skill meets all four dimensions with deductions for accessibility depth and formal testability. That is enough for the highest rating in this blog — not because it is perfect, but because it shows what a solid skill must structurally deliver.
