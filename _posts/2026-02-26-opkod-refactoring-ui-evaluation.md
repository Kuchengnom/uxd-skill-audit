---
layout: post
title: "opkod-france/refactoring-ui: Gute Quelle, fragliche Portierung — und dann das Archiv"
date: 2026-02-26
category: Skill-Evaluation
skill_reviewed: "opkod-france/claude-skill-refactoring-ui"
lang: de
lang_url: "/en/2026/02/26/opkod-refactoring-ui-evaluation/"
verdict: ablehnen
reading_time: 7
last_audited: "26. Februar 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "Refactoring UI ist ein legitimes Buch — aber nur Tailwind/shadcn portiert"
  transparenz: 2
  transparenz_note: "Keine Kommunikation der Framework-Abhängigkeit oder Grenzen"
  validierbarkeit: 1
  validierbarkeit_note: "Keine Testfälle, keine ausführbaren Werkzeuge"
  wartbarkeit: 1
  wartbarkeit_note: "Archiviert am 24. Feb. 2026 — kein aktiver Maintainer mehr"

tags:
  - refactoring-ui
  - tailwind
  - archiviert
  - skill-evaluation
---

Dieser Skill wurde am 24. Februar 2026 archiviert, zwei Tage vor diesem Post. Ironie ist es nicht. Es ist eine Lektion.

## Was der Skill war

`claude-skill-refactoring-ui` von OPKOD France wendete Prinzipien aus dem Buch *Refactoring UI* von Adam Wathan und Steve Schoger auf Tailwind CSS und shadcn/ui an. Der Skill aktivierte automatisch bei UI-Aufgaben. Dazu zählten Settings-Seiten mit Formularen, Dashboard-Layouts und Komponenten, die "professioneller" aussehen sollen.

Die Quelle ist unbestreitbar solide. *Refactoring UI* gilt als eines der wenigen Design-Bücher, das Entwickler tatsächlich lesen und anwenden. Die Prinzipien sind gut begründet und praxiserprobt. Weißraum vor Schatten. Hierarchie durch Größe statt Farbe. Ränder reduzieren.

## Das Problem mit der Portierung

<div class="callout">
<div class="callout__title">Kernfrage bei jeder buchbasierten Portierung</div>
Wie viel vom Original ist angekommen? Und was wurde stillschweigend weggelassen?
</div>

*Refactoring UI* ist ein Framework-agnostisches Buch. Die Portierung in einen Tailwind/shadcn-spezifischen Skill ist eine legitime Designentscheidung. Sie muss aber kommuniziert werden. Das gilt für Svelte-Projekte, Django-Templates und native Android-Interfaces. Dort gibt es keine Warnung. Es gibt nur Code, der nicht passt.

Das Buch behandelt visuelle Hierarchie, Farbsysteme und Spacing. Usability-Testing, Cognitive Load und nutzerforschungsbasierte Designentscheidungen behandelt es nicht. Auch Accessibility geht nicht über Kontrast hinaus. Ein Skill, der das verschweigt, suggeriert ein breiteres Fundament als vorhanden.

## Das Archivierungsproblem

Am 24. Februar 2026 wurde das Repo archiviert und auf `opkod-france/opkod-claude-code-plugins` weitergeleitet. Dieses Monorepo erlaubt Maintainern, mehrere Skills unter einem Dach zu verwalten.

Organisatorisch ist es sinnvoll. Für Nutzer ist es ein Problem.

Das alte Repo findet man heute über einen Blog-Post, einen Reddit-Thread oder eine Kurs-Empfehlung. Wer es installiert, bekommt einen archivierten Skill ohne aktive Wartung. Es gibt kein automatisches Update. Es gibt keine Deprecation-Warnung im Skill selbst. Auch die SKILL.md leitet nicht weiter.

Das ist das fundamentale Wartungsproblem des Skill-Ökosystems. Skills werden nicht deinstalliert. Sie verstauben still.

## Was das für Studierende bedeutet

Vor der Installation eines Skills sollte man drei Fragen stellen:

1. Wann wurde das Repo zuletzt aktualisiert? Mehr als 3 Monate ohne Commit ist ein Warnsignal.
2. Gibt es offene Issues ohne Antwort? Das zeigt ob der Maintainer noch aktiv ist.
3. Steht ein Team oder eine Einzelperson dahinter? Einzelpersonen-Projekte sterben mit dem Interesse des Maintainers.

## Fazit

Der Skill hatte eine solide Grundlage und ein echtes Problem. Auch die Quelle war gut gewählt. Die Portierung war aber framework-gebunden und kommunizierte das nicht. Es gab keine Testfälle. Nun ist das Projekt archiviert. Für den Einsatz heute gibt es keinen triftigen Grund mehr.

Wer Refactoring-UI-Prinzipien in Claude einbringen will, schreibt besser einen eigenen CLAUDE.md-Abschnitt. Er sollte gut dokumentiert sein. Ein archivierter Skill eines unbekannten Drittanbieters ist die schlechtere Wahl.
