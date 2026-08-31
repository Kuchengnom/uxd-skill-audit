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
  methodische_fundierung_note: "19 real existierende und anerkannte Quellen namentlich genannt; ob sie korrekt in die 24 Referenzdateien portiert wurden, ist ohne direkten Repository-Zugang nicht pruefbar"
  transparenz: 2
  transparenz_note: "Breites 'comprehensive'-Versprechen kombiniert mit automatischem Ausloeser ohne explizite Grenzkommunikation gegenueber LLM-Limitationen"
  validierbarkeit: 3
  validierbarkeit_note: "24 Referenzdateien mit ~10.700 Zeilen belegen strukturellen Aufwand; keine Testfaelle, Referenz-Outputs oder Before/After-Beispiele dokumentiert"
  wartbarkeit: 2
  wartbarkeit_note: "Einzelner Maintainer Szilard Hajba; keine oeffentliche Community-Diskussion, kein Aktivitaetssignal, Lizenz nicht bestaetigt auffindbar"

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

Das Versprechen klingt vertrauenerweckend: ein Claude-Skill der Designwissen aus 19 anerkannten Autoritätsquellen synthetisiert. Nielsen Norman Group, WCAG 2.2, Material Design, Apple HIG, Laws of UX, Google PAIR, Microsoft HAX Toolkit, Baymard Institute, The A11y Project, web.dev. Das ist keine beliebige Zusammenstellung. Das sind die Institutionen und Publikationen auf die sich professionelle UX-Arbeit tagtäglich stützt.

`szilu/ux-designer-skill` ist damit eines der ambitioniertesten Quellenversprechen im Claude-Skill-Ökosystem. Es ist auch ein lehrreiches Beispiel dafür, warum Quellen nennen und Quellen korrekt anwenden zwei verschiedene Dinge sind.

## Was das Repository anbietet

Der Skill ist als umfassende UX-Designberatung positioniert: Claude soll damit Interfaces und Komponenten nach korrekten Patterns gestalten und bestehenden Code auf UX-Probleme prüfen können. Technisch besteht das Repository aus einer zentralen SKILL.md mit 297 Zeilen und 24 Referenzdateien mit insgesamt rund 10.700 Zeilen. Dieser Umfang signalisiert echten Entwicklungsaufwand.

Der Skill ist sowohl manuell über `/ux-designer` aufrufbar als auch automatisch aktiv, wenn UX-relevante Themen in der Konversation auftreten. Diese Breitenwirkung ist ein Designentscheid mit Konsequenzen, auf den wir zurückkommen werden.

## Die 19-Quellen-These: Wer prüft das wirklich?

Die Behauptung lautet: Dieser Skill synthetisiert Designwissen aus 19 autorisierten Quellen. Verglichen mit dem Rest des Ökosystems ist das ein ungewöhnlich expliziter Quellenanspruch. Die meisten Skills zitieren keine Quellen oder erfinden Kategorien ohne Herkunftsnachweis.

Der Unterschied ist real. Ob Nielsen Normans zehn Usability-Heuristiken korrekt in das Skill-Wissensmodell portiert wurden, ist prüfbar. Ob WCAG 2.2 Erfolgskriterien korrekt repräsentiert sind, ist ebenfalls prüfbar, weil die Quellen selbst öffentlich zugänglich und eindeutig definiert sind.

Das ist die entscheidende Lernfrage, die dieser Skill im Unterricht provoziert. Nicht „Welche Quellen werden genannt?", sondern „Sind sie korrekt übersetzt worden?"

<div class="callout">
<div class="callout__title">Quellen nennen ist nicht Quellen anwenden</div>
Ein Skill der „auf Nielsen Norman basiert" kann Nielsens Heuristik Nummer 5, „Error Prevention", korrekt beschreiben, falsch anwenden oder aus dem Kontext herauslösen. Die Quelle legitimiert nicht automatisch die Portierung. Studierende die diesen Skill nutzen sollten explizit aufgefordert werden, einzelne Prinzipien gegen die Originalquellen zu vergleichen: Was sagt die NN/G tatsächlich zu „Visibility of System Status"? Was steht in WCAG 2.2 Success Criterion 1.3.1 „Info and Relationships"? Die Abweichungen, falls vorhanden, sind der eigentliche Lernstoff.
</div>

## Das Transparenzproblem: Wenn „comprehensive" keine Grenze kennt

Der Skill beschreibt sich selbst als „comprehensive UX/UI design guidance". Er löst automatisch aus, sobald UX-Themen in einem Gespräch auftreten. Das sind zwei Signale, die zusammen ein Muster ergeben: Es gibt keine kommunizierte Grenze dessen, was der Skill können soll.

Das ist methodisch problematisch. Ein Skill kann kein WCAG-Compliance-Audit durchführen wie ein automatisiertes Accessibility-Prüfwerkzeug. Er kann Contrast-Ratios nicht messen. Er kann Screen-Reader-Kompatibilität nicht testen. Er kann Baymard-Institut-Erkenntnisse zu E-Commerce-Formularen aktivieren, aber er kann nicht prüfen, ob ein spezifisches Checkout-Formular Baymards Empfehlungen tatsächlich erfüllt.

Diese Unterscheidung verläuft zwischen „informiertes Analysieren mit einem Framework" und „normkonforme Prüfung nach einem Standard". Sie wird im Repository nach aktuellem Recherchestand nicht explizit kommuniziert. Ein Skill der ohne Einschränkungshinweis als „comprehensive" gilt und automatisch für jedes UX-Thema aktiviert wird, erzeugt eine stille Überversprechung.

## Umfang als Signal, aber nicht als Garant

24 Referenzdateien mit rund 10.700 Zeilen sind kein Zufall. Das ist ernsthafte Arbeit. Verglichen mit Skills die in 50 Zeilen „vollständiges UX-Wissen" versprechen, signalisiert dieser Umfang eine andere Qualitätsambition.

Das Problem: Umfang ersetzt keine Verifizierbarkeit. Soweit recherchierbar gibt es keine öffentlich dokumentierten Testfälle, keine Before/After-Beispiele, keine Vergleiche zwischen Skill-Output und Expertenurteil. Wie gut der Skill tatsächlich arbeitet, lässt sich nur durch eigenständige Prüfung herausfinden: Jemand muss die 24 Referenzdateien mit den Originalquellen vergleichen und Skill-Outputs gegen Expertenanalysen stellen.

Das ist kein unüberwindbares Problem, sondern eine Einladung zu einer produktiven Übungsaufgabe. Aber als Grundlage für einen unkritischen Produktionseinsatz reicht Umfang alleine nicht.

## Wartbarkeit: Einzelne Person, unbekannte Aktivität

Der Skill wird von Szilard Hajba unter dem GitHub-Namen szilu gepflegt. Es handelt sich um einen Einzelmaintainer, typisch für Community-Skills in diesem Ökosystem. Problematischer als der Einzelmaintainer-Status selbst ist das Fehlen öffentlicher Signale: keine nachweisbare Community-Diskussion, keine Aktivitätshinweise auf X/Twitter, keine Issues-Diskussionen im öffentlichen Recherchezugang. Ob der Skill aktiv weiterentwickelt oder bei Versionsänderungen der Quellstandards aktualisiert wird, ist unklar. WCAG 3.0 ist bereits in Vorbereitung.

Die Lizenz konnte bei dieser Evaluation nicht bestätigt werden. Das ist ein praktischer Aspekt der vor einem Lehreinsatz geklärt werden sollte.

## Empfehlung für den Unterrichtseinsatz

`szilu/ux-designer-skill` eignet sich gut als Prüfgegenstand, nicht als unkritisches Werkzeug.

Der Skill ist ideal für eine Lehrsequenz rund um die Frage: „Was bedeutet es, auf Autoritätsquellen zu verweisen?" Studierende können konkret arbeiten. Sie wählen eine der 19 Quellen aus, zum Beispiel Nielsens Heuristik 1 „Visibility of System Status", lesen die Originalquelle, aktivieren dann den Skill und vergleichen die Outputs. Stimmen die Definitionen überein? Wird der Kontext korrekt abgebildet? Fehlen Nuancen?

Diese Übung macht aus der abstrakten Kritik „Quellen nennen ist nicht Quellen anwenden" eine erfahrbare Erkenntnis. Und sie trainiert gleichzeitig den kritischen Umgang mit Skill-Dokumentation, der im professionellen Designalltag zunehmend relevant wird.

Das Urteil ist **vorsicht**: Der Skill ist nicht wertlos, aber er fordert aktive Prüfung ein. Wer ihn ohne Quellenvergleich im Produktionseinsatz nutzt, verlässt sich auf ein Versprechen, dessen Einlösung er selbst nicht verifiziert hat.
