---
layout: post
title: "Anthropics frontend-design: Der offizielle Skill mit einem fundamentalen Denkfehler"
date: 2026-03-05
category: Skill-Evaluation
skill_reviewed: "anthropics/claude-code — plugins/frontend-design"
skill_github: "anthropics/claude-code"
verdict: vorsicht
reading_time: 9
last_audited: "5. März 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "Aesthetisch durchdacht, aber kein UX-Fundament"
  transparenz: 2
  transparenz_note: "Kommuniziert nicht, was Claude epistemisch nicht leisten kann"
  validierbarkeit: 3
  validierbarkeit_note: "Oeffentliches Repo mit PR-Prozess — Fehler werden korrigiert"
  wartbarkeit: 5
  wartbarkeit_note: "Maintainer ist Anthropic selbst — bestmoegliche Wartungsgarantie"

tags:
  - anthropic
  - offiziell
  - frontend
  - epistemik
  - skill-evaluation
---

Das ist der Skill, dem am meisten vertraut wird — weil Anthropic dahintersteht. Das ist ein guter Grund, ihn besonders genau anzusehen.

## Was der Skill tut

Der offizielle `frontend-design`-Skill von Anthropic generiert "distinctive, production-grade frontend interfaces". Er etabliert vor dem Coden einen Designrahmen: Zweck, Zielgruppe, aesthetische Richtung (brutalist, maximalist, retro-futuristic, luxury, playful). Er verbannt explizit generische AI-Aesthetik: keine overused Fonts (Inter, Roboto, Arial), keine clichéhaften Farbschemata (vor allem: kein Purple-Gradient auf Weiss), keine vorhersehbaren Layouts.

Das Ziel ist klar formuliert und das Framework-Agnostik ist korrekt. Fuer einen schnellen Ausgangspunkt fuer Frontend-Arbeit ist das genutzlich.

## Der fundamentale Denkfehler

<div class="callout">
<div class="callout__title">Entdeckt in Pull Request #210</div>
Die urspruengliche SKILL.md enthielt die Anweisung: "NEVER converge on common choices (Space Grotesk, for example) across generations" und "No design should be the same." Ein Contributor hat das korrekt identifiziert: Diese Anweisung ist fuer Claude nicht ausfuehrbar.
</div>

Claude sieht keine anderen Konversationen. Jede Session startet ohne Gedaechtnis an vorherige Generationen. Die Anweisung "Verwende nicht was du in anderen Generationen verwendet hast" ist epistemisch unmoeglich zu befolgen — Claude kann es schlicht nicht wissen.

Das ist kein kleines Versehen. Es zeigt ein Missverstaendnis darueber wie LLMs funktionieren, das direkt in die offizielle Referenzimplementierung geflossen ist. PR #210 hat das korrigiert, aber die urspruengliche Version war monatelang in Gebrauch.

## Was das lehrt

Erstens: **Offizielle Skills sind nicht per se korrekt.** Anthropic hat eine bessere Wartungsinfrastruktur als die meisten Community-Maintainer — aber auch Anthropics Skill-Team hat blinde Flecken, die externe Reviews aufdecken. Das oeffentliche Repo mit PR-Prozess ist hier ein echter Vorteil: Fehler werden sichtbar und korrigiert.

Zweitens: **Anweisungen muessen mit den Faehigkeiten des Modells uebereinstimmen.** Eine SKILL.md ist kein Wunschzettel — sie ist ein Prompt. Und Prompts die auf Informationen referenzieren, die das Modell nicht haben kann, erzeugen Verhalten das unvorhersehbar ist oder still ignoriert wird.

Drittens: **Aesthetik-Verbote sind kein Usability-Rahmen.** Auch dieser offizielle Skill adressiert keine Usability-Fragen, keine Cognitive Load, keine Accessibility jenseits von erwaehnenswerten Randnotizen. Die Frage "Wird dieses Interface von seinen Nutzern verstanden?" taucht nicht auf.

## Was der Skill gut macht

Der Ansatz, zuerst Zweck und Zielgruppe zu definieren bevor Code generiert wird, ist methodisch richtig und hebt diesen Skill von reinen Aesthetik-Praeferenz-Dateien ab. Die explizite Nennung von Aesthetik-Richtungen (statt vager "sei kreativ"-Anweisungen) gibt Claude einen handhabbaren Rahmen.

Und: Das Repo ist oeffentlich, hat einen PR-Prozess, und wird von Anthropic maintained. Das sind keine Kleinigkeiten.

## Empfehlung

Einsetzen — aber mit Verstaendnis fuer was er nicht ist. Der Skill verbessert die visuelle Qualitaet von AI-generiertem Frontend. Er ersetzt keinen Accessibility-Audit, kein Usability-Testing, keine Nutzerforschung.

Fuer den Unterricht ist dieser Skill besonders wertvoll als Beispiel: Selbst eine offiziell kuratierte, aktiv gewartete Referenzimplementierung kann epistemisch fehlerhafte Anweisungen enthalten — und der einzige Weg das zu erkennen ist, genau hinzulesen.
