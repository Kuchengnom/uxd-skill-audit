---
layout: post
title: "Anthropics frontend-design: Der offizielle Skill mit einem fundamentalen Denkfehler"
date: 2026-03-05
category: Skill-Evaluation
skill_reviewed: "anthropics/claude-code — plugins/frontend-design"
skill_github: "anthropics/claude-code"
lang: de
lang_url: "/en/2026/03/05/anthropic-frontend-design-evaluation/"
verdict: vorsicht
reading_time: 9
last_audited: "5. März 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "Ästhetisch durchdacht, aber kein UX-Fundament"
  transparenz: 2
  transparenz_note: "Kommuniziert nicht, was Claude epistemisch nicht leisten kann"
  validierbarkeit: 3
  validierbarkeit_note: "Öffentliches Repo mit PR-Prozess — Fehler werden korrigiert"
  wartbarkeit: 5
  wartbarkeit_note: "Maintainer ist Anthropic selbst — bestmögliche Wartungsgarantie"

tags:
  - anthropic
  - offiziell
  - frontend
  - epistemik
  - skill-evaluation
---

Diesem Skill wird am meisten vertraut. Anthropic steht dahinter. Das ist ein guter Grund, ihn besonders genau anzusehen. Pull Request #210 hat darin einen Fehler gefunden.

## Was der Skill tut

Der offizielle `frontend-design`-Skill von Anthropic generiert „distinctive, production-grade frontend interfaces". Er etabliert vor dem Coden einen Designrahmen. Der Rahmen umfasst Zweck, Zielgruppe und ästhetische Richtung. Als Richtungen nennt er brutalist, maximalist, retro-futuristic, luxury oder playful. Er verbannt explizit generische AI-Ästhetik. Dazu zählen keine overused Fonts wie Inter, Roboto und Arial. Clichéhafte Farbschemata sind tabu, vor allem Purple-Gradient auf Weiß. Vorhersehbare Layouts sind es ebenfalls.

Das Ziel ist klar formuliert. Auch die Framework-Agnostik ist korrekt. Als Ausgangspunkt für Frontend-Arbeit ist das nützlich.

## Der fundamentale Denkfehler

<div class="callout">
<div class="callout__title">Entdeckt in Pull Request #210</div>
Die ursprüngliche SKILL.md enthielt die Anweisung „NEVER converge on common choices (Space Grotesk, for example) across generations" und „No design should be the same." Ein Contributor hat das korrekt identifiziert. Die Anweisung ist für Claude nicht ausführbar.
</div>

Claude sieht keine anderen Konversationen. Jede Session startet ohne Gedächtnis an vorherige Generationen. Die Anweisung „Verwende nicht was du in anderen Generationen verwendet hast" ist epistemisch unmöglich zu befolgen. Claude kann es schlicht nicht wissen.

Ein kleines Versehen ist es nicht. Es zeigt ein Missverständnis darüber, wie LLMs funktionieren. Dieses Missverständnis ist direkt in die offizielle Referenzimplementierung geflossen. PR #210 hat das korrigiert. Die ursprüngliche Version war aber monatelang in Gebrauch.

## Was das lehrt

Offizielle Skills sind nicht per se korrekt. Anthropic hat eine bessere Wartungsinfrastruktur als die meisten Community-Maintainer. Auch Anthropics Skill-Team hat aber blinde Flecken. Externe Reviews decken sie auf. Das öffentliche Repo mit PR-Prozess ist hier ein echter Vorteil. Fehler werden sichtbar und korrigiert.

Anweisungen müssen mit den Fähigkeiten des Modells übereinstimmen. Eine SKILL.md ist kein Wunschzettel. Sie ist ein Prompt. Ein Prompt, der sich auf Informationen bezieht, die das Modell nicht haben kann, erzeugt unvorhersehbares Verhalten. Oder er wird still ignoriert.

Ästhetik-Verbote sind kein Usability-Rahmen. Auch dieser offizielle Skill adressiert keine Usability-Fragen. Er behandelt keine Cognitive Load. Accessibility steht höchstens in Randnotizen. Die Frage „Wird dieses Interface von seinen Nutzern verstanden?" taucht nicht auf.

## Was der Skill gut macht

Zuerst Zweck und Zielgruppe zu definieren und dann Code zu generieren, ist methodisch richtig. Das hebt diesen Skill von reinen Ästhetik-Präferenz-Dateien ab. Die explizite Nennung von Ästhetik-Richtungen gibt Claude einen handhabbaren Rahmen. Vage „sei kreativ"-Anweisungen lassen ihn allein.

Das Repo ist öffentlich. Es hat einen PR-Prozess. Anthropic maintained es. Kleinigkeiten sind das nicht.

## Empfehlung

Einsetzen, aber mit Verständnis dafür, was er nicht ist. Der Skill verbessert die visuelle Qualität von AI-generiertem Frontend. Er ersetzt keinen Accessibility-Audit, kein Usability-Testing und keine Nutzerforschung.

Für den Unterricht ist dieser Skill besonders wertvoll als Beispiel. Selbst eine offiziell kuratierte, aktiv gewartete Referenzimplementierung kann epistemisch fehlerhafte Anweisungen enthalten. Genau hinzulesen ist der einzige Weg, das zu erkennen.
