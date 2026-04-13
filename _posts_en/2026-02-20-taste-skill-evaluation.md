---
layout: post
title: "taste-skill: When Aesthetic Preferences Are Dressed Up as Design Methodology"
date: 2026-02-20
category: Skill-Evaluation
skill_reviewed: "Leonxlnx/taste-skill"
verdict: vorsicht
reading_time: 8
last_audited: "February 20, 2026"
lang: en
lang_url: /2026/02/20/taste-skill-evaluation/

skill_scores:
  methodische_fundierung: 2
  methodische_fundierung_note: "No recognized UX methodology — pure aesthetic preferences"
  transparenz: 2
  transparenz_note: "Does not communicate that outputs have no usability foundation"
  validierbarkeit: 2
  validierbarkeit_note: "No test cases, no comparison with user tests"
  wartbarkeit: 4
  wartbarkeit_note: "Actively maintained, own domain, multiple variants"

tags:
  - frontend
  - aesthetics
  - critique
  - skill-evaluation
---

Leon Lin's taste-skill went viral — its own domain, seven variants, a Tessl Registry entry. It solves a real problem: AI-generated frontend too often looks the same. And yet it's worth looking carefully at what is actually being claimed here.

## What the Skill Does

taste-skill gives Claude an aesthetic framework for frontend development. The 3-dial system — `DESIGN_VARIANCE` (1–10), `MOTION_INTENSITY` (1–10), `VISUAL_DENSITY` (1–10) — sounds like controlled parameterization. The SKILL.md file explicitly bans specific patterns: no "3 equally wide feature cards", no "AI-Purple", no isolated dark sections in light-mode pages.

The principle is clear: instead of vaguely saying "be creative", the skill provides anti-pattern rules. Claude knows what is forbidden and deviates from statistical midpoints.

## The Central Misunderstanding

<div class="callout">
<div class="callout__title">Critical Point</div>
The skill solves an aesthetic problem, not a usability problem. This distinction is entirely absent.
</div>

"Slop" — the generic sameness of AI-generated UIs — is a legitimate problem. But taste-skill replaces one statistical midpoint with another: the "Premium Soft UI" aesthetic with expensive fonts, lots of whitespace, spring animations and subtle shadows. That is 2024 SaaS aesthetics as dogma.

The questions that a UX framework would need to answer — Is this interface understandable for its target audience? Does it reduce cognitive load? Is it accessible? — are not answered by the skill. It answers: Does it look like an expensive product?

Both are legitimate questions. But they are not the same question.

## What This Means for Students

Anyone using taste-skill without context learns:

- That aesthetics = quality
- That pattern bans = methodology
- That "premium" = user-centered

None of that is true. A high `DESIGN_VARIANCE` value produces more interesting layouts — but interesting and understandable are different axes. Lots of whitespace helps some users, overwhelms others. Spring animations can be harmful for users under cognitive load or with vestibular disorders.

The skill contains no `prefers-reduced-motion` logic. WCAG criterion 2.3.3 (Animation from Interactions) is not mentioned.

## What the Skill Does Well

This is not a complete rejection. The anti-pattern approach — explicit bans rather than vague encouragement — is didactically valuable. The framework-agnostic implementation is correct. And the problem the skill solves (AI output looks too similar) is real.

For prototyping and exploratory design phases, where aesthetics take priority over usability, taste-skill is a useful tool.

## How to Use the Skill Correctly

```markdown
# Add to your own SKILL.md or prompt:

After applying taste-skill:
1. Check WCAG AA contrast (target: 4.5:1 for normal text)
2. Ensure all animations respect prefers-reduced-motion
3. Test the layout at 320px width (mobile minimum case)
4. Ask: Is every design decision also understandable for first-time users?
```

The aesthetic decisions of the skill can serve as a starting point — but they do not replace a usability review.

## Verdict

taste-skill is an honest aesthetic tool that does not explicitly disguise itself as UX methodology — but also does not communicate what it is *not*. For experienced users with UX foundations, that is not a problem. For students learning what design quality means, that context is precisely what is missing.

**Recommendation:** Use with explicit augmentation by an accessibility audit skill. Never use alone as a quality criterion.
