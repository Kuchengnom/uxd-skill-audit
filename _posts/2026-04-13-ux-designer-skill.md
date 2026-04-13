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

Das Versprechen klingt vertrauenerweckend: ein Claude-Skill der Designwissen aus 19 anerkannten Autoritaetsquellen synthetisiert. Nielsen Norman Group, WCAG 2.2, Material Design, Apple HIG, Laws of UX, Google PAIR, Microsoft HAX Toolkit, Baymard Institute, The A11y Project, web.dev — das ist keine beliebige Zusammenstellung. Das sind die Institutionen und Publikationen auf die sich professionelle UX-Arbeit tagtaeglich stuetzt.

`szilu/ux-designer-skill` ist damit eines der ambitioniertesten Quellenversprechen im Claude-Skill-Oekosystem. Es ist auch ein lehrreiches Beispiel dafuer, warum Quellen nennen und Quellen korrekt anwenden zwei verschiedene Dinge sind.

## Was das Repository anbietet

Der Skill ist als umfassende UX-Designberatung positioniert: Claude soll damit Interfaces und Komponenten nach korrekten Patterns gestalten und bestehenden Code auf UX-Probleme pruefen koennen. Technisch besteht das Repository aus einer zentralen SKILL.md (297 Zeilen) und 24 Referenzdateien mit insgesamt rund 10.700 Zeilen — ein Umfang der echten Entwicklungsaufwand signalisiert.

Der Skill ist sowohl manuell aufrufbar (`/ux-designer`) als auch automatisch aktiv, wenn UX-relevante Themen in der Konversation auftreten. Diese Breitenwirkung ist ein Designentscheid mit Konsequenzen, auf den wir zurueckkommen werden.

## Die 19-Quellen-These: Wer prueft das wirklich?

Die Behauptung lautet: Dieser Skill synthetisiert Designwissen aus 19 autorisierten Quellen. Das ist — verglichen mit dem Rest des Oekosystems — ein ungewoehnlich expliziter Quellenanspruch. Die meisten Skills zitieren keine Quellen oder erfinden Kategorien ohne Herkunftsnachweis.

Der Unterschied ist real. Ob Nielsen Normans zehn Usability-Heuristiken korrekt in das Skill-Wissensmodell portiert wurden, ist pruefbar. Ob WCAG 2.2 Erfolgskriterien korrekt repraesentiert sind, ist pruefbar — weil die Quellen selbst oeffentlich zugaenglich und eindeutig definiert sind.

Das ist die entscheidende Lernfrage, die dieser Skill im Unterricht provoziert: Nicht "Welche Quellen werden genannt?" sondern "Sind sie korrekt uebersetzt worden?"

<div class="callout">
<div class="callout__title">Quellen nennen ist nicht Quellen anwenden</div>
Ein Skill der "auf Nielsen Norman basiert" kann Nielsens Heuristik Nummer 5 — "Error Prevention" — korrekt beschreiben, falsch anwenden oder aus dem Kontext herausloesen. Die Quelle legitimiert nicht automatisch die Portierung. Studierende die diesen Skill nutzen sollten explizit aufgefordert werden, einzelne Prinzipien gegen die Originalquellen zu vergleichen: Was sagt die NN/G tatsaechlich zu "Visibility of System Status"? Was steht in WCAG 2.2 Success Criterion 1.3.1 "Info and Relationships"? Die Abweichungen — falls vorhanden — sind der eigentliche Lernstoff.
</div>

## Das Transparenzproblem: Wenn "comprehensive" keine Grenze kennt

Der Skill beschreibt sich selbst als "comprehensive UX/UI design guidance". Er loest automatisch aus, sobald UX-Themen in einem Gespraech auftreten. Das sind zwei Signale, die zusammen ein Muster ergeben: Es gibt keine kommunizierte Grenze dessen, was der Skill koennen soll.

Das ist methodisch problematisch. Ein Skill kann kein WCAG-Compliance-Audit durchfuehren wie ein automatisiertes Accessibility-Pruefwerkzeug. Er kann Contrast-Ratios nicht messen. Er kann Screen-Reader-Kompatibilitaet nicht testen. Er kann Baymard-Institut-Erkenntnisse zu E-Commerce-Formularen aktivieren — aber er kann nicht pruefen, ob ein spezifisches Checkout-Formular Baymards Empfehlungen tatsaechlich erfuellt.

Diese Unterscheidung — zwischen "informiertes Analysieren mit einem Framework" und "normkonforme Pruefung nach einem Standard" — wird im Repository nach aktuellem Recherchestand nicht explizit kommuniziert. Ein Skill der ohne Einschraenkungshinweis als "comprehensive" gilt und automatisch fuer jedes UX-Thema aktiviert wird, erzeugt eine stille Ueberversprechung.

## Umfang als Signal — aber nicht als Garant

24 Referenzdateien mit ~10.700 Zeilen sind kein Zufall. Das ist ernsthafte Arbeit. Verglichen mit Skills die in 50 Zeilen "vollstaendiges UX-Wissen" versprechen, signalisiert dieser Umfang eine andere Qualitaetsambition.

Das Problem: Umfang ersetzt keine Verifizierbarkeit. Es gibt — soweit recherchierbar — keine oeffentlich dokumentierten Testfaelle, keine Before/After-Beispiele, keine Vergleiche zwischen Skill-Output und Expertenurteil. Wie gut der Skill tatsaechlich arbeitet, laesst sich nur durch eigenstaendige Pruefung herausfinden: Jemand muss die 24 Referenzdateien mit den Originalquellen vergleichen und Skill-Outputs gegen Expertenanalysen stellen.

Das ist kein unueberwindbares Problem — es ist eine Einladung zu einer produktiven Uebungsaufgabe. Aber als Grundlage fuer einen unkritischen Produktionseinsatz reicht Umfang alleine nicht.

## Wartbarkeit: Einzelne Person, unbekannte Aktivitaet

Der Skill wird von Szilard Hajba (GitHub: szilu) gepflegt. Es handelt sich um einen Einzelmaintainer — typisch fuer Community-Skills in diesem Oekosystem. Problematischer als der Einzelmaintainer-Status selbst ist das Fehlen oeffentlicher Signale: keine nachweisbare Community-Diskussion, keine Aktivitaetshinweise auf X/Twitter, keine Issues-Diskussionen im oeffentlichen Recherchezugang. Ob der Skill aktiv weiterentwickelt oder bei Versionsaenderungen der Quellstandards (WCAG 3.0 ist in Vorbereitung) aktualisiert wird, ist unklar.

Die Lizenz konnte bei dieser Evaluation nicht bestaetigt werden — ein praktischer Aspekt der vor einem Lehreinsatz geklaert werden sollte.

## Empfehlung fuer den Unterrichtseinsatz

`szilu/ux-designer-skill` eignet sich gut als Pruefgegenstand, nicht als unkritisches Werkzeug.

Der Skill ist ideal fuer eine Lehrsequenz rund um die Frage: "Was bedeutet es, auf Autoritaetsquellen zu verweisen?" Studierende koennen konkret arbeiten: Sie waehlen eine der 19 Quellen aus (zum Beispiel Nielsens Heuristik 1 "Visibility of System Status"), lesen die Originalquelle, aktivieren dann den Skill und vergleichen die Outputs. Stimmen die Definitionen ueberein? Wird der Kontext korrekt abgebildet? Fehlen Nuancen?

Diese Uebung macht eine abstrakte Kritik — "Quellen nennen ist nicht Quellen anwenden" — zu einer erfahrbaren Erkenntnis. Und sie trainiert gleichzeitig den kritischen Umgang mit Skill-Dokumentation, der im professionellen Designalltag zunehmend relevant wird.

Das Urteil ist **vorsicht**: Der Skill ist nicht wertlos, aber er fordert aktive Pruefung ein. Wer ihn ohne Quellenvergleich im Produktionseinsatz nutzt, verlaesst sich auf ein Versprechen, dessen Einloesung er selbst nicht verifiziert hat.
