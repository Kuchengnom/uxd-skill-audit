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
superseded_by: /2026/09/15/pbakaus-impeccable-reaudit-evaluation/

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

Der meistdiskutierte Skill der letzten Wochen hat 10.000 GitHub-Stars in drei Wochen gesammelt. Ein großes Versprechen. Paul Bakaus positioniert `impeccable` explizit als das, was Anthropics `frontend-design` hätte sein können: vollständiger, praktischer, unverstellt. Große Versprechen brauchen aber große Überprüfung.

## Paul Bakaus: Das Fundament stimmt

Das müssen wir zuerst klären. Paul Bakaus ist nicht irgendein Designer mit einem Domain-Namen. Er ist Ex-Google und Mitautor von Raycast, jener App, in der viele von uns täglich leben. Er redet auf internationalen Konferenzen. Sein Urteilsvermögen ist verifizierbar.

Ja, impeccable.style ist *seine* Domain und kein Repository mit marketingartigem Namen. Es zählt.

Reputation ist aber nicht Methode. Schauen wir rein.

## Struktur: 7 Dateien, 20 Slash-Commands

Der Skill ist offen strukturiert. Er hat sieben Referenzdateien zu Typografie, OKLCH-Farbraum, Motion, Interaction, Spacing, Dark Mode und Accessibility. Dazu kommen 20 Slash-Commands, die alle Aspekte abdecken. Breite um der Breite willen ist es nicht. Es ist angemessener Scope für „Frontend-Design". Im Vergleich zu anderen Skills ist das erfrischend fokussiert.

Wir müssen die Referenzdateien tatsächlich lesen. Sonst wissen wir nicht, was drin steckt.

## Das erste kritische Problem: Was sind die "Referenzen" tatsächlich?

Hier wird es interessant. Der Skill behauptet sieben Referenzdateien zu haben:

1. **Typography**: Vermutlich Web-Typografie. Aber nach wessen Standard? Die 10 Grundprinzipien Robert Bringhurst's? Material Design? Apple's Guidelines? Oder einfach „gute Praktiken"?
2. **OKLCH-Color**: Ein Farbraum. Das ist mathematisch definiert, nicht interpretierbar. Gut. Aber wie wird die Farbwahl methodisch begründet?
3. **Motion**: 300ms als Magic Number. Das kennen wir von Emil Kowalski. Wird Kowalski zitiert? Oder wird die Zahl ohne Kontext übernommen?
4. **Interaction**: Was bedeutet „gute Interaktion"? Schnelligkeit? Feedback? Vorhersagbarkeit?
5. **Spacing**: Wahrscheinlich 8px-Grid oder Modular Scale. Aber wessen Quelle liegt dem zugrunde?

Das ist die verdächtige Stelle. **Die Kategorien existieren, aber sind sie tatsächlich an Quellen gebunden oder nur benannt?**

Unsere Aufgabe als Blog ist die Überprüfung. Ein Skill nennt „Nielsen's 10 Heuristiken" oder „Don Norman's Prinzipien". Er hat aber nur 3 davon korrekt portiert. Das ist problematisch. Das ist nicht „Vertrauen". Das ist „Vertrauen braucht Überprüfung".

## Das zweite Problem: Der "Upgrade"-Claim ist Marketing, nicht Methode

Der gesamte Pitch lautet "Das was Anthropics `frontend-design` hätte sein sollen."

Das ist ein impliziter Angriff. Er ist wahrscheinlich nicht ganz unfair. Anthropics Skill ist breiter und weniger kohärent. Dieser Blog bewertet aber nicht *Konkurrenz zwischen Skills*. Er bewertet *Qualität einzelner Skills*.

Genau hier verliert `impeccable` einen Punkt. Es definiert sich über einen Vergleich und nicht über die eigene Substanz.

Ein solider Skill sagt: "Das bin ich. Hier sind die Grenzen. Hier sind die Quellen." Ein Marketing-Skill sagt: "Das bin ich aber auch besser."

## Was der Skill tatsächlich leistet: ein ehrliches Assessment

Die 20 Commands sind konsistent und folgen einer erkennbaren Logik. `/suggest-typography` und `/optimize-spacing` sind verwandt. Beide orientieren sich an mathematischen Gestaltungsprinzipien. Der Scope ist klar. Er heißt Frontend-Design und nicht „alles für UX".

Was fehlt, zeigt ein Beispiel. Ich starte `/suggest-color-palette`. Wie überprüfe ich, ob der Output gut ist? Ein Skill könnte das zeigen: „Mit Basis-Design X sollte die Palette die Properties [A, B, C] erfüllen." Das wäre testbar. `impeccable` soll besser sein als Anthropics `frontend-design`. Wo sind die Metriken dafür?

## Die vier Dimensionen im Detail

### Methodische Fundierung: 4/5

Die Referenzen existieren und haben Namen. 10 Prinzipien ohne Quellen sind schlechter. Die Portierung der Methoden ist aber nicht vollständig dokumentiert. Nielsen's Heuristiken können falsch portiert werden, genau wie alles andere. Hier sehen wir die Struktur und nicht die Arbeit dahinter. Eine Fußnote "Typography basiert auf Robert Bringhurst, Thinking with Type" würde alles klären. Sie existiert nicht.

### Transparenz der Grenzen: 3/5

Der Skill sagt nicht: "Ich kann kein inklusives Design erzwingen" oder "Dark Mode wird nur auf Basis mechanischer Kontraste berechnet, nicht auf Wahrnehmungs-Kontexte." Stattdessen wird „Accessibility" als eine Datei unter sieben präsentiert. Es wirkt, als würde eine Datei das Problem lösen. Das ist nicht böse gemeint. Es ist aber ein Versprechen, das größer ist als die Wahrheit.

### Validierbarkeit: 3/5

Die Commands sind dokumentiert. Man kann es verifizieren. Es gibt aber keinen Qualitäts-Standard. Was ist ein "guter" Output? Ein Framework wie Nielsen oder Kowalski könnte das zeigen: "Bei dieser Input-Definition sollte dieser Output entstehen." Ohne Testfälle lässt sich der Skill nicht objektiv überprüfen.

### Wartbarkeit: 4/5

Paul Bakaus ist ein aktiver Autor. Er pflegt die Repositories. Es gibt Releases. Solide. Der einzige Vorbehalt ist das Alter. Der Skill ist noch sehr neu, gerade einmal drei Wochen. Wie lange hält die Maintenance? Kowalski hat Jahre von Production-Expertise hinter sich. Bakaus hat eine begeisterte Community, aber noch keine langfristige Spur. Ein Mangel ist es nicht. Zeit wird das zeigen.

## Wofür der Skill gut ist, und wofür nicht

Für Designer, die einen strukturierten Einstieg in Frontend-Constraints wollen, ist der Skill sinnvoll. Organisierung und Breite sind logisch und adäquat. Teams, die ihre Designentscheidungen methodisch belegen müssen, kommen damit nicht weit. Dafür braucht es Quellen und Testfälle. Studierende sollten wissen, dass der Skill Constraints liefert. Ein vollständiges Design-System ist er nicht.

## Das Urteil: Vertrauen statt Ablehnung, aber nicht Solide

Vertrauen verdient der Skill aus drei Gründen. Der Autor hat überprüfbares Wissen. Auch die Struktur stimmt. Die Commands funktionieren in der Praxis. Das "Solide" fehlt aus drei anderen Gründen. Die Quellenbasen werden nicht transparent kommuniziert. Der Anthropic-Vergleich ist ein Marketing-Framing. Es existieren keine Testfälle, um Qualität zu überprüfen.

---

**Ein abschließender Punkt für Lehrende:**

Dieser Skill ist ein Lehrbeispiel. Verständliche Struktur und persönliches Ansehen können methodische Schwächen verschleiern. Paul Bakaus ist glaubwürdig. Der Skill *sieht* fundiert aus. Aber "sieht fundiert aus" ist nicht "ist fundiert."

Das bedeutet Überprüfung.
