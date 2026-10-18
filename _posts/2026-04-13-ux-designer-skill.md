---
layout: post
title: "ux-designer-skill: 19 Quellen versprochen — aber Quellen nennen ist nicht Quellen anwenden"
date: 2026-04-13
category: Skill-Evaluation
skill_reviewed: "szilu/ux-designer-skill"
verdict: vorsicht
reading_time: 10
last_audited: "13. April 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "19 real existierende und anerkannte Quellen namentlich genannt; ob sie korrekt in die 24 Referenzdateien portiert wurden, ist ohne direkten Repository-Zugang nicht prüfbar"
  transparenz: 2
  transparenz_note: "Breites 'comprehensive'-Versprechen kombiniert mit automatischem Auslöser ohne explizite Grenzkommunikation gegenüber LLM-Limitationen"
  validierbarkeit: 3
  validierbarkeit_note: "24 Referenzdateien mit ~10.700 Zeilen belegen strukturellen Aufwand; keine Testfälle, Referenz-Outputs oder Before/After-Beispiele dokumentiert"
  wartbarkeit: 2
  wartbarkeit_note: "Einzelner Maintainer Szilard Hajba; keine öffentliche Community-Diskussion, kein Aktivitätssignal, Lizenz nicht bestätigt auffindbar"

tags:
  - quellennachweis
  - nielsen-heuristiken
  - wcag
  - laws-of-ux
  - material-design
  - apple-hig
  - quellen-portierung
  - einzelmaintainer
  - vorsicht-beispiel
  - skill-evaluation
---

Das Versprechen klingt vertrauenerweckend. Ein Claude-Skill synthetisiert Designwissen aus 19 anerkannten Autoritätsquellen. Genannt werden Nielsen Norman Group, WCAG 2.2, Material Design, Apple HIG, Laws of UX, Google PAIR, Microsoft HAX Toolkit, Baymard Institute, The A11y Project und web.dev. Eine beliebige Zusammenstellung ist das nicht. Es sind die Institutionen und Publikationen, auf die sich professionelle UX-Arbeit tagtäglich stützt.

`szilu/ux-designer-skill` ist damit eines der ambitioniertesten Quellenversprechen im Claude-Skill-Ökosystem. Es ist auch ein lehrreiches Beispiel. Quellen nennen und Quellen korrekt anwenden sind zwei verschiedene Dinge.

## Was das Repository anbietet

Der Skill ist als umfassende UX-Designberatung positioniert. Claude soll damit Interfaces und Komponenten nach korrekten Patterns gestalten. Bestehenden Code soll es auf UX-Probleme prüfen. Technisch besteht das Repository aus einer zentralen SKILL.md mit 297 Zeilen und 24 Referenzdateien mit insgesamt rund 10.700 Zeilen. Dieser Umfang signalisiert echten Entwicklungsaufwand.

Man kann den Skill manuell über `/ux-designer` aufrufen. Er ist auch automatisch aktiv, sobald UX-relevante Themen in der Konversation auftreten. Diese Breitenwirkung ist ein Designentscheid mit Konsequenzen. Darauf komme ich zurück.

## Die 19-Quellen-These: Wer prüft das wirklich?

Die Behauptung lautet: Dieser Skill synthetisiert Designwissen aus 19 autorisierten Quellen. Verglichen mit dem Rest des Ökosystems ist das ein ungewöhnlich expliziter Quellenanspruch. Die meisten Skills zitieren keine Quellen. Oder sie erfinden Kategorien ohne Herkunftsnachweis.

Der Unterschied ist real. Ob Nielsen Normans zehn Usability-Heuristiken korrekt in das Skill-Wissensmodell portiert wurden, ist prüfbar. Für WCAG 2.2 Erfolgskriterien gilt dasselbe. Die Quellen selbst sind öffentlich zugänglich und eindeutig definiert.

Das ist die entscheidende Lernfrage, die dieser Skill im Unterricht provoziert. Nicht „Welche Quellen werden genannt?", sondern „Sind sie korrekt übersetzt worden?"

<div class="callout">
<div class="callout__title">Quellen nennen ist nicht Quellen anwenden</div>
Ein Skill, der „auf Nielsen Norman basiert", kann Nielsens Heuristik Nummer 5, „Error Prevention", korrekt beschreiben. Er kann sie ebenso falsch anwenden oder aus dem Kontext herauslösen. Die Quelle legitimiert die Portierung nicht automatisch. Studierende sollten einzelne Prinzipien explizit gegen die Originalquellen vergleichen. Was sagt die NN/G tatsächlich zu „Visibility of System Status"? Was steht in WCAG 2.2 Success Criterion 1.3.1 „Info and Relationships"? Die Abweichungen, falls vorhanden, sind der eigentliche Lernstoff.
</div>

## Das Transparenzproblem: Wenn „comprehensive" keine Grenze kennt

Der Skill beschreibt sich selbst als „comprehensive UX/UI design guidance". Er löst automatisch aus, sobald UX-Themen in einem Gespräch auftreten. Zusammen ergeben beide Signale ein Muster. Der Skill kommuniziert keine Grenze dessen, was er können soll.

Methodisch ist das problematisch. Ein Skill kann kein WCAG-Compliance-Audit durchführen wie ein automatisiertes Accessibility-Prüfwerkzeug. Contrast-Ratios kann er nicht messen. Screen-Reader-Kompatibilität kann er nicht testen. Er kann Baymard-Institut-Erkenntnisse zu E-Commerce-Formularen aktivieren. Ob ein spezifisches Checkout-Formular Baymards Empfehlungen tatsächlich erfüllt, kann er nicht prüfen.

Diese Unterscheidung verläuft zwischen „informiertes Analysieren mit einem Framework" und „normkonforme Prüfung nach einem Standard". Das Repository kommuniziert sie nach aktuellem Recherchestand nicht explizit. Ein Skill gilt als „comprehensive" und wird automatisch für jedes UX-Thema aktiviert. Einen Einschränkungshinweis gibt es nicht. So entsteht eine stille Überversprechung.

## Umfang als Signal, aber nicht als Garant

24 Referenzdateien mit rund 10.700 Zeilen sind kein Zufall. Das ist ernsthafte Arbeit. Skills, die in 50 Zeilen „vollständiges UX-Wissen" versprechen, bieten weniger. Dieser Umfang signalisiert eine andere Qualitätsambition.

Das Problem liegt woanders. Umfang ersetzt keine Verifizierbarkeit. Soweit recherchierbar gibt es keine öffentlich dokumentierten Testfälle, keine Before/After-Beispiele und keine Vergleiche zwischen Skill-Output und Expertenurteil. Wie gut der Skill tatsächlich arbeitet, zeigt nur eine eigenständige Prüfung. Jemand muss die 24 Referenzdateien mit den Originalquellen vergleichen. Dazu muss er Skill-Outputs gegen Expertenanalysen stellen.

Unüberwindbar ist das nicht. Es ist eine Einladung zu einer produktiven Übungsaufgabe. Als Grundlage für einen unkritischen Produktionseinsatz reicht Umfang allein trotzdem nicht.

## Wartbarkeit: Einzelne Person, unbekannte Aktivität

Szilard Hajba pflegt den Skill unter dem GitHub-Namen szilu. Er ist Einzelmaintainer, wie es für Community-Skills in diesem Ökosystem typisch ist. Problematischer ist das Fehlen öffentlicher Signale. Es gibt keine nachweisbare Community-Diskussion, keine Aktivitätshinweise auf X/Twitter und keine Issues-Diskussionen im öffentlichen Recherchezugang. Ob der Skill aktiv weiterentwickelt wird, ist unklar. Ob er bei Versionsänderungen der Quellstandards aktualisiert wird, ist ebenso unklar. WCAG 3.0 ist bereits in Vorbereitung.

Die Lizenz konnte bei dieser Evaluation nicht bestätigt werden. Vor einem Lehreinsatz sollte man das klären.

## Empfehlung für den Unterrichtseinsatz

`szilu/ux-designer-skill` eignet sich gut als Prüfgegenstand. Als unkritisches Werkzeug eignet er sich nicht.

Der Skill passt zu einer Lehrsequenz rund um die Frage „Was bedeutet es, auf Autoritätsquellen zu verweisen?" Studierende können konkret arbeiten. Sie wählen eine der 19 Quellen aus, zum Beispiel Nielsens Heuristik 1 „Visibility of System Status". Sie lesen die Originalquelle, aktivieren dann den Skill und vergleichen die Outputs. Stimmen die Definitionen überein? Wird der Kontext korrekt abgebildet? Fehlen Nuancen?

Die Übung macht aus der abstrakten Kritik „Quellen nennen ist nicht Quellen anwenden" eine erfahrbare Erkenntnis. Sie trainiert zugleich den kritischen Umgang mit Skill-Dokumentation. Im professionellen Designalltag wird er zunehmend relevant.

Das Urteil ist **vorsicht**. Der Skill ist nicht wertlos, fordert aber aktive Prüfung ein. Wer ihn ohne Quellenvergleich im Produktionseinsatz nutzt, verlässt sich auf ein Versprechen, dessen Einlösung er selbst nicht verifiziert hat.
