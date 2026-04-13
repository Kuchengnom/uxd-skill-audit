---
layout: default
title: The 4-Dimension Framework
permalink: /en/methodology/
lang: en
lang_url: /methodik/
example_scores:
  methodische_fundierung: 4
  transparenz: 3
  validierbarkeit: 4
  wartbarkeit: 5
---

<div class="post-header">
  <div class="container">
    <span class="post-category">Methodology</span>
    <h1 class="post-title">How Skills Are Evaluated</h1>
    <p style="color: var(--color-text-muted); font-family: var(--font-ui); max-width: 55ch;">
      A skill that sounds good is not a skill that works well. This framework makes the difference visible.
    </p>
  </div>
</div>

<div class="post-content container" markdown="1">

The skill ecosystem for Claude is growing faster than it is being evaluated. GitHub stars, viral tweets and beautifully formatted READMEs say nothing about the methodological quality of a skill. This blog therefore uses four dimensions for evaluation.

---

## The Four-Dimension Model — Visualized

<div class="scorecard-wrapper">
  <div style="width: 300px; margin: 0 auto;">
    {% include skill-radar.html scores=page.example_scores size="full" %}
  </div>
  <p style="color: var(--color-text-muted); font-family: var(--font-ui); margin-top: var(--space-l); text-align: center; font-size: 0.9rem;">
    <strong>Example:</strong> A skill with high maintainability (5), solid methodology (4) and testability (4), but weaker transparency about limitations (3).
  </p>
</div>

---

## Dimension 1: Methodological Rigor (1–5)

Is the underlying technique recognized, correctly understood and accurately ported into the skill?

A skill claiming to implement Nielsen's 10 heuristics must reproduce all ten correctly. A skill offering Cognitive Walkthroughs must know the method of Wharton et al., not a simplified variant. Points are deducted when:

- Terminology is invented or used inaccurately
- The source is not cited or is cited incorrectly
- The method is simplified without communicating the simplification
- AI output is presented as a substitute for human expertise

## Dimension 2: Transparency of Limitations (1–5)

Does the skill clearly communicate what it cannot do?

This is the most critical dimension for the teaching context. A heuristic evaluation skill that has not interviewed any users cannot *prove* usability problems — it can only generate hypotheses. A skill that does not communicate this misleads students. Points are deducted when:

- Generated artifacts are attributed scientific authority
- There is no warning where human expertise remains irreplaceable
- Scores and ratings are presented without statistical basis
- The skill implies it *replaces* user research rather than *supporting* it

## Dimension 3: Testability (1–5)

Are there test cases, reference outputs or comparisons with human expert work?

A good skill can prove what it does. That means: example inputs with documented expectations, Python scripts that verify outputs, or at minimum a before/after with explanation. Points are deducted when:

- No examples are provided
- No executable tools are included
- There is no comparison between skill output and expert judgment
- The skill is not reproducible

## Dimension 4: Maintainability (1–5)

Who is behind it, what is the versioning, when was it last updated?

An archived skill, an anonymous maintainer or a missing license are red flags. Points are deducted when:

- The repository has not been updated for more than 6 months
- There is no license
- A single maintainer exists without a successor
- Issues and pull requests are being ignored

---

## How to Read These Evaluations

No dimension is more important than the others — but the combination decides. A skill with high maintainability and low methodological rigor is well-maintained nonsense. A skill with high rigor and no testability is unverifiable theory.

The evaluations on this blog are snapshots at the stated date. Skills change, and we update where possible.

</div>
