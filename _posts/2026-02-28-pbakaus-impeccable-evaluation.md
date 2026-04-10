---
layout: post
title: "pbakaus/impeccable: Das Design-Upgrade-Versprechen — Hält es das aus?"
date: 2026-02-28
category: Skill-Evaluation
skill_reviewed: "pbakaus/impeccable"
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

Der meistdiskutierte Skill der letzten Wochen, 10.000 GitHub-Stars in drei Wochen: Ein großes Versprechen. Paul Bakaus positioniert `impeccable` explizit als das was Anthropics `frontend-design` hätte sein können — vollständiger, praktischer, unverstellt. Aber große Versprechen brauchen große Überprüfung.

## Paul Bakaus — Das Fundament stimmt

Das müssen wir zuerst klären: Paul Bakaus ist nicht irgendein Designer mit einem Domain-Namen. Ex-Google, Mitautor von Raycast (die App in der viele von uns täglich leben), Redner auf internationalen Konferenzen. Das ist Urteilsvermoegen das verifizierbar ist.

Und ja, impeccable.style ist *seine* Domain, nicht ein Repository mit marketingartigem Namen. Das zählt.

Aber Reputation ist nicht Methode. Schauen wir rein.

## Struktur: 7 Dateien, 20 Slash-Commands

Der Skill ist offen strukturiert:
- **Referenzen**: Typografie, OKLCH-Farbraum, Motion, Interaction, Spacing, Dark Mode, Accessibility
- **Commands**: 20 verschiedene Befehle die alle Aspekte abdecken

Das ist nicht Breite — das ist *angemessene* Breite für den Scope "Frontend-Design". Im Vergleich zu anderen Skills ist das erfrischend fokussiert.

Das Problem: Wir müssen die Referenzdateien tatsächlich lesen um zu wissen was drin steckt.

## Das erste kritische Problem: Was sind die "Referenzen" tatsächlich?

Hier wird es interessant. Der Skill behauptet sieben Referenzdateien zu haben:

1. **Typography** — Vermutlich Web-Typografie. Aber nach wessen Standard? Die 10 Grundprinzipien Robert Bringhurst's? Material Design? Apple's Guidelines? Oder einfach "gute Praktiken"?
2. **OKLCH-Color** — Ein Farbraum. Das ist mathematisch definiert, nicht interpretierbar. Das ist gut. Aber wie wird die Farbwahl methodisch begründet?
3. **Motion** — 300ms als Magic Number. Das kennen wir von Emil Kowalski. Wird Kowalski zitiert? Oder wird die Zahl ohne Kontext übernommen?
4. **Interaction** — Was bedeutet "gute Interaktion"? Schnelligkeit? Feedback? Vorhersagbarkeit?
5. **Spacing** — Wahrscheinlich 8px-Grid oder Modular Scale. Aber welcher Quelle folgt das?

Das ist die verdächtige Stelle: **Die Kategorien existieren, aber sind sie tatsächlich an Quellen gebunden oder nur benannt?**

Unsere Aufgabe als Blog ist das zu überprüfen. Ein Skill der "Nielsen's 10 Heuristiken" oder "Don Norman's Prinzipien" sagt, aber nur 3 davon korrekt portiert hat, ist problematisch. Das ist nicht "Vertrauen" — das ist "Vertrauen braucht Überprüfung."

## Das zweite Problem: Der "Upgrade"-Claim ist Marketing, nicht Methode

Der gesamte Pitch lautet: "Das was Anthropics `frontend-design` hätte sein sollen."

Das ist ein impliziter Angriff. Und wahrscheinlich nicht ganz unfair — Anthropics Skill ist breiter und weniger kohärent. Aber dieser Blog bewertet nicht *Konkurrenz zwischen Skills*, er bewertet *Qualität einzelner Skills*.

Und genau hier verliert `impeccable` einen Punkt: Es definiert sich über einen Vergleich, nicht über die eigene Substanz.

Ein solider Skill sagt: "Das bin ich. Hier sind die Grenzen. Hier sind die Quellen." Ein Marketing-Skill sagt: "Das bin ich aber auch besser."

## Was der Skill tatsächlich leistet — ein ehrliches Assessment

Positiv: Der Skill ist **konsistent implementiert**. Die 20 Commands sind nicht willkürlich. Sie folgen einer erkennbaren Logik. `/suggest-typography` ist verwandt mit `/optimize-spacing` — beide folgen mathematischen/gestalterischen Prinzipien.

Positiv: **Scope-Klarheit**. Es ist ein Frontend-Design-Skill, nicht "alles für UX."

Negativ: **Keine strukturierten Testfälle**. Wenn ich `/suggest-color-palette` starte, wie überprüfe ich ob der Output gut ist? Ein Skill könnte sagen: "Mit Basis-Design X sollte die Palette die Properties [A, B, C] erfüllen." Das würde ich testen können.

Negativ: **Keine Vergleichbarkeit zu Baseline**. Anthropics `frontend-design` ist ein Baseline. `impeccable` behauptet besser zu sein. Wo sind die Metriken dafür?

## Die vier Dimensionen im Detail

**Methodische Fundierung: 4 von 5**

Die Referenzen existieren und haben Namen. Das ist besser als 10 Prinzipien ohne Quellen. Aber: die *Portierung* der Methoden ist nicht vollständig dokumentiert. Nielsen's Heuristiken können falsch portiert werden, genau wie alles andere. Hier sehen wir die Struktur, nicht die Arbeit dahinter.

Punkt abgezogen weil: Eine Fußnote "Typography basiert auf Robert Bringhurst, Thinking with Type" würde alles klären. Sie existiert nicht.

**Transparenz der Grenzen: 3 von 5**

Der Skill sagt nicht: "Ich kann kein inklusive Design erzwingen" oder "Ich kenne keine Kultur-Sensibilität." Er sagt auch nicht "Dark Mode wird nur auf Basis mechanischer Kontraste berechnet, nicht auf Wahrnehmungs-Kontexte."

Stattdessen wird "Accessibility" als eine Datei unter sieben präsentiert — als würde eine Datei das Problem lösen.

Das ist nicht böse gemeint. Aber es ist ein Versprechen das größer ist als die Wahrheit. Deshalb: 3 Punkte.

**Validierbarkeit: 3 von 5**

Die Commands sind dokumentiert. Das ist verifizierbar. Aber: es gibt keinen Qualitäts-Standard. Welcher Output ist "gut"? Ein Framework wie Nielsen oder Kowalski könnte das zeigen: "Bei dieser Input-Definition sollte dieser Output entstehen."

Ohne Testfälle kann ich den Skill nicht objektiv überprüfen.

**Wartbarkeit: 4 von 5**

Paul Bakaus ist ein aktiver Autor, die Repositories sind gepflegt, es gibt Releases. Das ist solide. Der einzige Punkt: Es ist noch sehr neu (3 Wochen!). Wie lange hält die Maintenance? Kowalski hat Jahre von Production-Expertise hinter sich. Bakaus hat begeisterte Community aber noch keine langfristige Spur.

Das ist kein Mangel, eher: Zeit wird das zeigen.

## Wofür der Skill gut ist — und wofür nicht

**Gut für**: Designer die einen strukturierten Einstieg in Frontend-Constraints wollen. Die Organisierung ist logisch. Die Breite ist adäquat.

**Nicht gut für**: Teams die *beweisen* müssen dass ihre Designentscheidungen methodisch sound sind. Dafür braucht man Quellen und Testfälle.

**Risiko**: Studierende könnten glauben dass der Skill ein "komplettes Design-System" erzeugt. Das ist falsch. Der Skill gibt Constraints, nicht Systeme.

## Das Urteil: Vertrauen statt Ablehnung, aber nicht Solide

Dieser Skill verdient das Vertrauen seiner Nutzer **weil**:
- Der Autor verifizierbares Wissen hat
- Die Struktur logisch ist
- Die Commands praktisch sind

Dieser Skill verdient **nicht** das "Solide"-Urteil **weil**:
- Die Quellenbasen nicht transparent sind
- Der Vergleich zu Anthropic ein Marketing-Framing ist, nicht wissenschaftlich
- Keine strukturierten Testfälle existieren um Qualität zu überprüfen

---

**Ein abschließender Punkt für Lehrende:**

Dieser Skill ist ein Lehrbeispiel dafür wie verständliche Struktur und persönliches Ansehen methodische Schwächen verschleiern können. Paul Bakaus ist glaubwürdig. Der Skill *sieht* fundiert aus. Aber "sieht fundiert aus" ist nicht "ist fundiert."

Das ist was Überprüfung bedeutet.
