---
layout: post
title: "ui-ux-pro-max: Wenn eine Datenbank zur Methodik erklärt wird"
date: 2026-03-14
category: Skill-Evaluation
skill_reviewed: "nextlevelbuilder/ui-ux-pro-max-skill"
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
  - quantitaet
  - skill-evaluation
---

Der Skill klingt nach dem vollstaendigsten Designwerkzeug im Oekosystem: 161 Farbpaletten, 57 Schriftpaare, 99 UX-Richtlinien, 25 Chart-Typen, 161 Produkttypen, 10 Technologie-Stacks. Wenn Vollstaendigkeit eine Methodik waere, waere das hier die Referenz.

Aber Vollstaendigkeit ist keine Methodik.

## Was der Skill ist

`ui-ux-pro-max` von nextlevelbuilder ist im Kern eine durchsuchbare Datenbank. CSV-Dateien im `data/`-Verzeichnis speichern Design-Ressourcen: Styles, Farben, Typografie, Produkttypen. Ein Python-basiertes Such-Interface (`--design-system`-Befehl) durchsucht diese Datenbank anhand von Projektanforderungen und generiert in Sekunden ein "komplettes, massgeschneidertes Design-System."

Das Flaggschiff von v2.0 ist der *Design System Generator* — ein "AI-powered reasoning engine" der Anforderungen analysiert und passende Design-Entscheidungen ausspielt. Das klingt nach intelligentem Urteilen. Es ist Pattern-Matching auf CSV-Daten.

## Das Qualitaetsproblem der 99 UX-Richtlinien

<div class="callout">
<div class="callout__title">Die entscheidende Frage bei jeder Wissensdatenbank</div>
Wer hat diese Richtlinien formuliert, und auf welcher Grundlage?
</div>

Die 99 UX-Richtlinien sind nach Prioritaet gerankt und decken Accessibility, Touch-Interaktion, Performance und Responsive Layout ab. Das klingt strukturiert. Aber: Keine einzige Richtlinie im oeffentlichen Repository verweist auf eine Quelle. Es gibt kein WCAG-Mapping, keine Nielsen-Referenz, keine Verlinkung zu Studienergebnissen.

Das bedeutet nicht, dass die Richtlinien falsch sind. Es bedeutet: Man kann es nicht ueberpruefen. Und was man nicht ueberpruefen kann, dem sollte man in einem Lehrkontext nicht blind vertrauen.

Zum Vergleich: WCAG 2.1 hat fuer jede Richtlinie eine Quellenangabe, eine Erfolgskriterien-Hierarchie und Testverfahren. Das ist der Standard fuer nachvollziehbare UX-Richtlinien.

## Quantitaet als Qualitaetssignal

161 Farbpaletten. 14 unterstuetzte Coding-Agenten. "344+ Design-Ressourcen." Diese Zahlen sind das Hauptargument des Projekts — die Website, die README, die Beschreibungen betonen Quantitaet.

Das ist ein Muster, das Studierende erkennen sollen: **Groesse ist kein Guetezeichen.** Eine Datenbank mit 1000 Farbpaletten ohne Herkunft und Kontext ist weniger wertvoll als ein durchdachtes Farbsystem mit 12 Tokens und klarer Semantik.

Mehr ist nur dann mehr, wenn das Mehr auch besser ist. Bei diesem Skill ist das unklar.

## Was der Skill genutzlich macht

Das Matching-Prinzip hat einen echten Nutzen fuer Prototyping: "Ich baue eine FinTech-App im Minimal-Stil" erzeugt konkrete Vorschlaege fuer Farben, Fonts und Komponenten. Das ist schneller als eine leere Seite. Fuer explorative Phasen, wo Richtung wichtiger ist als Praezision, kann das genutzlich sein.

Die CSV-Struktur bedeutet ausserdem: Die Datenbank ist transparent einsehbar. Wer die Quellen der 99 Richtlinien selbst validieren will, kann in die Dateien schauen — auch wenn die Richtlinien selbst keine Quellen nennen.

## Empfehlung

Mit explizitem Kontext einsetzen: Dieser Skill generiert Vorschlaege aus einer Datenbank, keine Urteile aus Nutzerforschung. Was er ausspielt, ist ein Ausgangspunkt — kein Ergebnis.

Fuer Studierende ist dieser Skill ein gutes Lehrobjekt fuer eine spezifische Frage: Was ist der Unterschied zwischen einer Wissenssammlung und einer Methodik? Eine Methodik erklaert nicht nur *was* zu tun ist, sondern *warum*, *fuer wen*, und *wie man ueberpruefen kann ob es funktioniert hat*.

Die 344 Ressourcen in diesem Skill beantworten die erste Frage. Die anderen drei bleiben offen.
