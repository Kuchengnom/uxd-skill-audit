---
layout: post
title: "pbakaus/impeccable: Das Design-Upgrade-Versprechen — Hält es das aus?"
date: 2026-02-28
category: Skill-Evaluation
skill_reviewed: "pbakaus/impeccable"
lang: de
lang_url: "/en/2026/02/28/pbakaus-impeccable-evaluation/"
verdict: vertrauen
reading_time: 11
last_audited: "28. Februar 2026"

skill_scores:
  methodische_fundierung: 4
  methodische_fundierung_note: "Referenzdateien haben Quellen, aber Portierung teilweise oberflächlich"
  transparenz: 3
  transparenz_note: "Marketing-Rhetorik 'Upgrade' verschleiert wo Kompromisse liegen"
  validierbarkeit: 3
  validierbarkeit_note: "20 Slash-Commands sind dokumentiert, aber kein Vergleich zu Baseline"
  wartbarkeit: 4
  wartbarkeit_note: "Aktiver Autor mit Google/Raycast-Background; eigene Domain; GitHub aktiv"

tags:
  - design-frontend
  - upgrade-fallacy
  - kritisches-beispiel
  - skill-evaluation
---

Der meistdiskutierte Skill der letzten Wochen, 10.000 GitHub-Stars in drei Wochen: Ein großes Versprechen. Paul Bakaus positioniert `impeccable` explizit als das was Anthropics `frontend-design` hätte sein können: vollständiger, praktischer, unverstellt. Aber große Versprechen brauchen große Überprüfung.

## Paul Bakaus: Das Fundament stimmt

Das müssen wir zuerst klären: Paul Bakaus ist nicht irgendein Designer mit einem Domain-Namen. Ex-Google, Mitautor von Raycast, jener App in der viele von uns täglich leben, Redner auf internationalen Konferenzen. Das ist Urteilsvermoegen das verifizierbar ist.

Und ja, impeccable.style ist *seine* Domain, nicht ein Repository mit marketingartigem Namen. Das zählt.

Aber Reputation ist nicht Methode. Schauen wir rein.

## Struktur: 7 Dateien, 20 Slash-Commands

Der Skill ist offen strukturiert: sieben Referenzdateien zu Typografie, OKLCH-Farbraum, Motion, Interaction, Spacing, Dark Mode und Accessibility, dazu 20 Slash-Commands die alle Aspekte abdecken. Das ist nicht Breite um der Breite willen. Das ist angemessener Scope für „Frontend-Design". Im Vergleich zu anderen Skills ist das erfrischend fokussiert.

Das Problem: Wir müssen die Referenzdateien tatsächlich lesen um zu wissen was drin steckt.

## Das erste kritische Problem: Was sind die "Referenzen" tatsächlich?

Hier wird es interessant. Der Skill behauptet sieben Referenzdateien zu haben:

1. **Typography**: Vermutlich Web-Typografie. Aber nach wessen Standard? Die 10 Grundprinzipien Robert Bringhurst's? Material Design? Apple's Guidelines? Oder einfach „gute Praktiken"?
2. **OKLCH-Color**: Ein Farbraum. Das ist mathematisch definiert, nicht interpretierbar. Das ist gut. Aber wie wird die Farbwahl methodisch begründet?
3. **Motion**: 300ms als Magic Number. Das kennen wir von Emil Kowalski. Wird Kowalski zitiert? Oder wird die Zahl ohne Kontext übernommen?
4. **Interaction**: Was bedeutet „gute Interaktion"? Schnelligkeit? Feedback? Vorhersagbarkeit?
5. **Spacing**: Wahrscheinlich 8px-Grid oder Modular Scale. Aber welcher Quelle folgt das?

Das ist die verdächtige Stelle: **Die Kategorien existieren, aber sind sie tatsächlich an Quellen gebunden oder nur benannt?**

Unsere Aufgabe als Blog ist das zu überprüfen. Ein Skill der „Nielsen's 10 Heuristiken" oder „Don Norman's Prinzipien" sagt, aber nur 3 davon korrekt portiert hat, ist problematisch. Das ist nicht „Vertrauen". Das ist „Vertrauen braucht Überprüfung".

## Das zweite Problem: Der "Upgrade"-Claim ist Marketing, nicht Methode

Der gesamte Pitch lautet: "Das was Anthropics `frontend-design` hätte sein sollen."

Das ist ein impliziter Angriff. Und wahrscheinlich nicht ganz unfair. Anthropics Skill ist breiter und weniger kohärent. Aber dieser Blog bewertet nicht *Konkurrenz zwischen Skills*, er bewertet *Qualität einzelner Skills*.

Und genau hier verliert `impeccable` einen Punkt: Es definiert sich über einen Vergleich, nicht über die eigene Substanz.

Ein solider Skill sagt: "Das bin ich. Hier sind die Grenzen. Hier sind die Quellen." Ein Marketing-Skill sagt: "Das bin ich aber auch besser."

## Was der Skill tatsächlich leistet: ein ehrliches Assessment

Die 20 Commands sind konsistent und folgen einer erkennbaren Logik: `/suggest-typography` und `/optimize-spacing` sind verwandt, beide an mathematischen Gestaltungsprinzipien orientiert. Scope ist klar: Frontend-Design, nicht „alles für UX".

Was fehlt: Wenn ich `/suggest-color-palette` starte, wie überprüfe ich ob der Output gut ist? Ein Skill könnte das zeigen: „Mit Basis-Design X sollte die Palette die Properties [A, B, C] erfüllen." Das wäre testbar. Und wenn `impeccable` besser als Anthropics `frontend-design` sein soll: Wo sind die Metriken dafür?

## Die vier Dimensionen im Detail

### Methodische Fundierung: 4/5

Die Referenzen existieren und haben Namen. Das ist besser als 10 Prinzipien ohne Quellen. Aber die Portierung der Methoden ist nicht vollständig dokumentiert. Nielsen's Heuristiken können falsch portiert werden, genau wie alles andere. Hier sehen wir die Struktur, nicht die Arbeit dahinter. Eine Fußnote "Typography basiert auf Robert Bringhurst, Thinking with Type" würde alles klären. Sie existiert nicht.

### Transparenz der Grenzen: 3/5

Der Skill sagt nicht: "Ich kann kein inklusives Design erzwingen" oder "Dark Mode wird nur auf Basis mechanischer Kontraste berechnet, nicht auf Wahrnehmungs-Kontexte." Stattdessen wird „Accessibility" als eine Datei unter sieben präsentiert, als würde eine Datei das Problem lösen. Das ist nicht böse gemeint. Aber es ist ein Versprechen, das größer ist als die Wahrheit.

### Validierbarkeit: 3/5

Die Commands sind dokumentiert, das ist verifizierbar. Aber es gibt keinen Qualitäts-Standard. Welcher Output ist "gut"? Ein Framework wie Nielsen oder Kowalski könnte das zeigen: "Bei dieser Input-Definition sollte dieser Output entstehen." Ohne Testfälle lässt sich der Skill nicht objektiv überprüfen.

### Wartbarkeit: 4/5

Paul Bakaus ist ein aktiver Autor, die Repositories sind gepflegt, es gibt Releases. Solide. Der einzige Vorbehalt: Es ist noch sehr neu, gerade einmal drei Wochen. Wie lange hält die Maintenance? Kowalski hat Jahre von Production-Expertise hinter sich. Bakaus hat eine begeisterte Community, aber noch keine langfristige Spur. Das ist kein Mangel. Zeit wird das zeigen.

## Wofür der Skill gut ist, und wofür nicht

Für Designer die einen strukturierten Einstieg in Frontend-Constraints wollen, ist der Skill sinnvoll. Die Organisierung ist logisch, die Breite adäquat. Teams die ihre Designentscheidungen methodisch belegen müssen, kommen damit nicht weit. Dafür braucht es Quellen und Testfälle. Und Studierende sollten wissen: Der Skill liefert Constraints, kein vollständiges Design-System.

## Das Urteil: Vertrauen statt Ablehnung, aber nicht Solide

Vertrauen verdient der Skill, weil der Autor überprüfbares Wissen hat, die Struktur stimmt und die Commands in der Praxis funktionieren. Das "Solide" fehlt, weil die Quellenbasen nicht transparent kommuniziert werden, der Anthropic-Vergleich ein Marketing-Framing ist, und keine Testfälle existieren um Qualität zu überprüfen.

---

**Ein abschließender Punkt für Lehrende:**

Dieser Skill ist ein Lehrbeispiel dafür wie verständliche Struktur und persönliches Ansehen methodische Schwächen verschleiern können. Paul Bakaus ist glaubwürdig. Der Skill *sieht* fundiert aus. Aber "sieht fundiert aus" ist nicht "ist fundiert."

Das ist was Überprüfung bedeutet.
