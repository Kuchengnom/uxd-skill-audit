---
layout: post
title: "ui-ux-pro-max: Wenn eine Datenbank zur Methodik erklärt wird"
date: 2026-03-14
category: Skill-Evaluation
skill_reviewed: "nextlevelbuilder/ui-ux-pro-max-skill"
lang: de
lang_url: "/en/2026/03/14/nextlevelbuilder-ui-ux-pro-max-evaluation/"
verdict: vorsicht
reading_time: 10
last_audited: "14. März 2026"

skill_scores:
  methodische_fundierung: 2
  methodische_fundierung_note: "344 Ressourcen, aber keine nachvollziehbare Herkunft der 99 UX-Richtlinien"
  transparenz: 2
  transparenz_note: "Grenze zwischen Datenbank-Matching und echtem UX-Urteil bleibt unsichtbar"
  validierbarkeit: 2
  validierbarkeit_note: "CSV-Dateien sind einsehbar — aber nicht validiert gegen reale Nutzerdaten"
  wartbarkeit: 3
  wartbarkeit_note: "Aktiv, v2.0 erschienen, aber Einzelprojekt mit unklarer Nachfolge"

tags:
  - datenbank
  - ui-ux
  - quantität
  - skill-evaluation
---

Der Skill klingt nach dem vollständigsten Designwerkzeug im Ökosystem. Er nennt 161 Farbpaletten, 57 Schriftpaare, 99 UX-Richtlinien, 25 Chart-Typen, 161 Produkttypen und 10 Technologie-Stacks. Wäre Vollständigkeit eine Methodik, wäre das hier die Referenz.

Aber Vollständigkeit ist keine Methodik.

## Was der Skill ist

`ui-ux-pro-max` von nextlevelbuilder ist im Kern eine durchsuchbare Datenbank. Im `data/`-Verzeichnis liegen CSV-Dateien mit Design-Ressourcen. Sie enthalten Styles, Farben, Typografie und Produkttypen. Ein Python-basiertes Such-Interface durchsucht sie mit dem Befehl `--design-system`. Als Grundlage dienen die Projektanforderungen. In Sekunden entsteht ein „komplettes, maßgeschneidertes Design-System".

Das Flaggschiff von v2.0 ist der *Design System Generator*. Er ist eine „AI-powered reasoning engine". Sie analysiert Anforderungen und spielt passende Design-Entscheidungen aus. Das klingt nach intelligentem Urteilen. Es ist Pattern-Matching auf CSV-Daten.

## Das Qualitätsproblem der 99 UX-Richtlinien

<div class="callout">
<div class="callout__title">Die entscheidende Frage bei jeder Wissensdatenbank</div>
Wer hat diese Richtlinien formuliert? Worauf stützt sich das?
</div>

Die 99 UX-Richtlinien sind nach Priorität gerankt. Sie decken Accessibility, Touch-Interaktion, Performance und Responsive Layout ab. Das klingt strukturiert. Keine einzige Richtlinie im öffentlichen Repository verweist aber auf eine Quelle. Es gibt kein WCAG-Mapping, keine Nielsen-Referenz und keine Verlinkung zu Studienergebnissen.

Das bedeutet nicht, dass die Richtlinien falsch sind. Es bedeutet: Man kann es nicht überprüfen. Was man nicht überprüfen kann, dem sollte man in einem Lehrkontext nicht blind vertrauen.

WCAG 2.1 zeigt zum Vergleich, wie es aussieht. Jede Richtlinie hat eine Quellenangabe. Dazu gehören eine Erfolgskriterien-Hierarchie und Testverfahren. Das ist der Standard für nachvollziehbare UX-Richtlinien.

## Quantität als Qualitätssignal

161 Farbpaletten. 14 unterstützte Coding-Agenten. „344+ Design-Ressourcen." Diese Zahlen sind das Hauptargument des Projekts. Website, README und Beschreibungen betonen Quantität.

Studierende sollen hier ein Muster erkennen. Größe ist kein Gütezeichen. Eine Datenbank mit 1000 Farbpaletten ohne Herkunft und Kontext ist weniger wertvoll als ein durchdachtes Farbsystem mit 12 Tokens und klarer Semantik.

Mehr ist nur dann mehr, wenn das Mehr auch besser ist. Bei diesem Skill ist das unklar.

## Was der Skill nützlich macht

Das Matching-Prinzip hat einen echten Nutzen für Prototyping. „Ich baue eine FinTech-App im Minimal-Stil" erzeugt konkrete Vorschläge für Farben, Fonts und Komponenten. Das ist schneller als eine leere Seite. In explorativen Phasen zählt Richtung mehr als Präzision. Dort kann das nützlich sein.

Die CSV-Struktur macht die Datenbank transparent einsehbar. Wer die Quellen der 99 Richtlinien selbst validieren will, kann in die Dateien schauen. Die Richtlinien selbst nennen keine Quellen.

## Empfehlung

Mit explizitem Kontext einsetzen. Dieser Skill generiert Vorschläge aus einer Datenbank. Er liefert keine Urteile aus Nutzerforschung. Was er ausspielt, ist ein Ausgangspunkt und kein Ergebnis.

Für Studierende ist der Skill ein gutes Lehrobjekt für eine Frage. Was ist der Unterschied zwischen einer Wissenssammlung und einer Methodik? Eine Methodik erklärt nicht nur *was* zu tun ist. Sie erklärt auch *warum*, *für wen* und *wie man überprüfen kann ob es funktioniert hat*.

Die 344 Ressourcen in diesem Skill beantworten die erste Frage. Die anderen drei bleiben offen.
