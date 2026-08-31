---
layout: post
title: "claude-design-auditor-skill: Eine Punktzahl, die Genauigkeit verspricht, wo geschätzt wird"
date: 2026-07-27
category: Skill-Evaluation
skill_reviewed: "Ashutos1997/claude-design-auditor-skill"
verdict: vorsicht
reading_time: 11
last_audited: "27. Juli 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "Die WCAG-Erfolgskriterien sind namentlich und korrekt zitiert (SC 1.4.3, 2.1.1, 1.1.1, 2.4.1) und die Nielsen-Heuristiken sauber abgegrenzt, doch die 22 Dark Patterns, die Verhaltensprinzipien und die gesamte Typografie- und Rasterebene kommen ohne Primärquelle aus."
  transparenz: 4
  transparenz_note: "Der Skill koppelt Konfidenzstufen an das tatsächliche Prüfverhalten, verweigert bei reiner Textbeschreibung ausdrücklich jede Punktzahl und deklariert die Regulatorik-Prüfungen als UI-Signalebene statt als Rechtsgutachten — nur die Gesamtnote selbst tritt ohne Unsicherheitsangabe auf."
  validierbarkeit: 2
  validierbarkeit_note: "Es gibt weder Testfälle noch Referenzausgaben noch einen Vergleichskorpus; das einzige durchgerechnete Beispiel im README widerspricht der eigenen Punkteformel um acht Punkte."
  wartbarkeit: 4
  wartbarkeit_note: "MIT-Lizenz, 21 Releases, 84 Commits und ein detailliert geführtes Changelog bis Mai 2026 — getragen aber von einer einzelnen Person ohne erkennbare Nachfolgeplanung."

tags:
  - design-audit
  - wcag
  - accessibility
  - dark-patterns
  - nielsen-heuristiken
  - scoring
  - validierbarkeit
  - skill-evaluation
---

Die bisher evaluierten Skills dieser Reihe wollten Claude beim *Entwerfen* helfen. `claude-design-auditor-skill` von Ashutos1997 dreht die Richtung um: Er soll fertige Entwürfe *prüfen*. Eingabe kann eine Figma-Datei über MCP sein, HTML/CSS/React/Vue-Code, ein Screenshot, eine URL oder ein Wireframe. Heraus kommt ein Prüfbericht mit einer Gesamtnote von 100, drei Teilnoten für Accessibility, Ethics und Usability, und Befunden in vier Schweregraden.

Das ist ein interessanter Fall, weil Prüfen andere epistemische Ansprüche stellt als Entwerfen. Ein Entwurfsskill, der schlechte Vorschläge macht, produziert schlechte Entwürfe. Das sieht man. Ein Prüfskill, der falsch prüft, produziert eine Zahl, die aussieht wie ein Messergebnis. Und Zahlen werden geglaubt.

## Was der Skill nachweislich richtig macht

Beginnen wir mit dem, was in dieser Reihe selten vorkommt: überprüfbare Quellenarbeit.

Die Blocker-Stufe des Skills ist an konkrete WCAG-Erfolgskriterien gebunden, und zwar an die richtigen. Kontrast unter 4,5:1 wird gegen SC 1.4.3 gemeldet, ein tastaturunerreichbares Element gegen SC 2.1.1, fehlender Alternativtext gegen SC 1.1.1, ein fehlender Sprunglink gegen SC 2.4.1. Das lässt sich Kriterium für Kriterium gegen die W3C-Empfehlung prüfen, und es stimmt. Wer die Reihe mitgelesen hat, weiß, wie ungewöhnlich das ist. Die Mehrzahl der bisher untersuchten Skills nennt „WCAG" als Etikett, ohne je eine SC-Nummer zu schreiben.

Ähnlich sauber ist der Umgang mit den Nielsen-Heuristiken. Kategorie 19 behandelt nicht alle zehn, sondern erklärt in der Referenzdatei `heuristics.md` ausdrücklich, dass H4, H5, H8 und H9 ausgeschlossen sind, und begründet das damit, dass sie inhaltlich bereits in anderen Kategorien geprüft werden. Eine Skill-Datei, die von zehn Heuristiken sechs behandelt und das offen deklariert, ist methodisch ehrlicher als eine, die alle zehn behauptet und keine sauber portiert.

## Konfidenz, die tatsächlich etwas verändert

Der bemerkenswerteste Abschnitt trägt die Überschrift „Set Confidence Level — and act on it" und beginnt mit dem Satz, Konfidenz sei nicht bloß ein Etikett. Der Skill macht das ernst:

Bei Figma-Zugriff oder Quellcode gilt hohe Konfidenz, volle Punktabzüge, exakte Werte werden zitiert. Bei einem Screenshot sinkt die Konfidenz auf mittel, und daraufhin ändert sich das Verhalten: Punktabzüge für alles, was exakte Werte voraussetzt, werden halbiert, die Kategorie „Design Tokens" wird komplett übersprungen, Hex-Werte dürfen nicht mehr genannt werden, und Blocker werden auf Critical herabgestuft, sofern die Verletzung visuell nicht eindeutig ist. Bei einer bloßen Textbeschreibung verweigert der Skill die Bewertung: „Never assign a score on description alone."

Das ist die durchdachteste Behandlung von Eingabequalität, die mir in diesem Ökosystem bisher begegnet ist. Sie erkennt an, dass ein Screenshot schlicht weniger Information enthält als eine Figma-Datei, und übersetzt das in konkrete Verhaltensregeln statt in eine Fußnote.

Genauso ehrlich ist die Regulatorik-Ebene. Die sechs Compliance-Prüfungen in Kategorie 18, also Cookie-Banner, Abo-Offenlegung, Datenschutzhinweis am Erhebungspunkt, Widerrufsrecht, Altersverifikation und Barrierefreiheits-Rechtslage, tragen jeweils den ausdrücklichen Vorbehalt, dies sei eine UI-Signalebene und kein Rechtsgutachten. Genau diese Unterscheidung fehlt sonst überall dort, wo Skills mit GDPR-Vokabular hantieren.

## Und dann die Zahl

Jetzt zum Kern. Der Skill dokumentiert seit v1.2.11 eine explizite Formel:

`100 − (Blocker × 12) − (Critical × 8) − (Warning × 4) − (Tip × 1)`

Sie soll das Ergebnis reproduzierbar machen. Das README zeigt dazu ein Beispiel, einen Checkout-Flow mit drei Frames, und rechnet vor:

`100 − (1 × 🚫 12) − (2 × 🔴 8) − (4 × 🟡 4) − (2 × 🟢 1) = 62/100`

Rechnet man nach: 12 + 16 + 16 + 2 = 46. Und 100 − 46 = 54. Nicht 62. Acht Punkte Differenz, im einzigen vollständig durchgerechneten Beispiel der gesamten Dokumentation, in jenem Beispiel also das die Reproduzierbarkeit der Formel demonstrieren soll.

Erschwerend kommt hinzu, dass die Notation selbst mehrdeutig ist. `(1 × 🚫 12)` lässt offen, ob „1" die Anzahl und „12" der Abzug ist oder umgekehrt. Unter der dokumentierten Formel gilt die erste Lesart. Aber ein Beispiel, dessen Schreibweise man erst gegen die Formel disambiguieren muss, erklärt nichts.

<div class="callout">
<div class="callout__title">Determinismus in der Formel, Schätzung in den Zahlen</div>
Die Formel ist deterministisch. Was in sie eingesetzt wird, ist es nicht. Ob eine Abstandsabweichung als 🟡 Warnung oder als 🔴 Critical gilt, ob zwei Befunde denselben Ursprung haben und zusammengefasst gehören, ob eine CTA-Hierarchie manipulativ oder nur ungeschickt ist: all das entscheidet das Modell bei jedem Durchlauf neu. Die Formel legt nur fest, wie diese Urteile addiert werden. Das Ergebnis ist eine Ganzzahl auf einer 100er-Skala, die aussieht wie eine Messung und tatsächlich eine gewichtete Zusammenfassung wiederholt getroffener Ermessensentscheidungen ist. Der Skill zeigt die Formel in jedem Bericht. Das schafft Nachvollziehbarkeit der Addition, nicht der Summanden. Zwei Läufe über dieselbe Datei können 54 und 71 ergeben, und beide Berichte werden ihre Rechnung sauber ausweisen. Genau hier verschiebt sich das Versprechen: Nicht die Note ist das Problem, sondern die zwei Stellen Sicherheit, die sie suggeriert.
</div>

Verschärft wird das dadurch, dass drei verschiedene Skalen nebeneinander laufen. Die Gesamtnote arbeitet mit −12/−8/−4/−1, der Ethics Score mit −15/−7/0. Das Changelog v1.2.12 vermerkt, es sei ein Hinweis ergänzt worden, dass die Ethics-Formel „distinct from standard formula" sei. Der Vorbehalt ist da. Aber zwei Zahlen mit derselben Optik, derselben Skala und unterschiedlicher Berechnungsgrundlage stehen im Bericht nebeneinander und laden zum Vergleich ein.

## Was das Changelog über die Substanz verrät

Das Changelog ist ungewöhnlich detailliert geführt, und gerade deshalb aufschlussreich.

Version v1.2.11 listet unter „Bug fixes": *category count „17" → „19" throughout* und *Cat 18/19 numbering corrected*. Das heißt: Der Skill hat in einer veröffentlichten Version an mehreren Stellen eine falsche Anzahl eigener Kategorien angegeben und Kategorien vertauscht. Die Zählung der Dark Patterns wandert parallel dazu: v1.2.4 spricht von 20 Mustern in 5 Gruppen, v1.2.12 korrigiert auf 22, der aktuelle README-Text nennt sechs Gruppen und formuliert „and 17 more" nach acht aufgezählten Beispielen, was 25 ergäbe. Für einen Skill, dessen Kernversprechen Systematik ist, ist die eigene Systematik erstaunlich beweglich.

Der zweite aufschlussreiche Eintrag steht in v1.2.7. Nach Berichten, dass Drittanbieter-Agenten statt des Berichts eine freie UX-Kritik ausgaben, wurden zwei Hinweise eingefügt: `⚠️ OUTPUT FORMAT IS MANDATORY — DO NOT DEVIATE` und `⚠️ MANDATORY — ALL AGENTS — NO EXCEPTIONS`. Das ist eine ehrliche Reaktion auf ein reales Problem, aber es ist eine Prompt-Reaktion auf ein strukturelles Problem. Ein Format, das nur durch Großbuchstaben gehalten wird, ist kein erzwungenes Format. Für den Unterricht ist das ein gutes Anschauungsstück: Wo ein Skill anfängt zu schreien, liegt meist die Stelle, an der ihm die Durchsetzungsmittel fehlen.

## Was fehlt: jede Form von Prüfung des Prüfers

Der Skill misst andere. Ihn selbst misst nichts.

Es gibt keine Testfälle. Es gibt keine Referenzausgaben, gegen die man einen Lauf halten könnte. Es gibt keinen Korpus mit bekannten Fehlern, an dem sich Trefferquote und Fehlalarmrate bestimmen ließen. Es gibt keinen Vergleich mit einem menschlichen Audit derselben Oberfläche. Es gibt kein ausführbares Skript, anders als etwa bei `plugin87/ux-ui-agent-skills`, wo Kontrastwerte tatsächlich berechnet und in CI erzwungen werden. Hier bleibt jede Prüfung eine Modellaussage über einen Prompt.

Das einzige Belegstück ist das Beispiel im README. Und das rechnet sich selbst falsch.

Damit steht die Frage im Raum, die jeder Prüfskill beantworten müsste und dieser nicht beantwortet: Wie oft meldet er einen Kontrastverstoß, der keiner ist? Wie oft übersieht er einen? Ohne diese Zahlen ist die Gesamtnote von 100 eine Angabe ohne Bezugsgröße.

## Bewertung und Empfehlung für den Unterricht

Das Urteil lautet **vorsicht** — wegen der Validierbarkeit, nicht wegen der Substanz. Inhaltlich gehört dieser Skill zum oberen Drittel des Ökosystems: korrekte SC-Nummern, sauber abgegrenzte Heuristiken, verhaltenswirksame Konfidenzstufen, ein ehrlicher Rechtsvorbehalt, MIT-Lizenz, 21 Releases mit gepflegtem Changelog bis Mai 2026. Was fehlt, ist jeder Nachweis, dass das Ergebnis stimmt.

Für den Unterricht schlage ich eine zweiteilige Übung vor.

**Teil 1 — Reproduzierbarkeit prüfen.** Studierende lassen denselben Entwurf dreimal in getrennten Sitzungen auditieren und protokollieren die drei Gesamtnoten sowie die Zahl der Befunde je Schweregrad. Die Streuung ist das eigentliche Lernergebnis. Anschließend rechnen sie das README-Beispiel selbst nach und finden die Acht-Punkte-Lücke.

**Teil 2 — Trennschärfe prüfen.** Die Klasse teilt die Befunde eines Berichts in zwei Stapel: mechanisch entscheidbare wie Kontrastverhältnis, fehlendes `<label>` oder Abstand außerhalb des 8er-Rasters und interpretationsbedürftige wie Manipulationsvorwurf, Tonalität der Microcopy und Hierarchie der Handlungsaufforderung). Der erste Stapel lässt sich extern verifizieren, etwa mit einem Kontrastrechner. Der zweite nicht. Beide gehen mit demselben Gewicht in dieselbe Zahl ein, und das ist der Punkt, an dem die Diskussion beginnen sollte.

Als Werkzeug ist der Design Auditor brauchbar: Wer ihn als strukturierte Checkliste verwendet, die Aufmerksamkeit auf Bereiche lenkt, die man sonst überspringt, bekommt echten Wert. Als Qualitätsnachweis taugt er nicht. Man schreibt „62/100" nicht in eine Abgabe, ohne die zugrunde liegenden Befunde einzeln geprüft zu haben.

---

*Geprüft am 27. Juli 2026 gegen den Stand v1.2.13, dessen Release vom 17. Mai 2026 datiert, 57 Stars, 12 Forks, 84 Commits, MIT-Lizenz. Die Referenzdateien im Verzeichnis `references/`, darunter `ethics.md` und `heuristics.md`, waren zum Prüfzeitpunkt nicht direkt abrufbar; Aussagen dazu stützen sich auf README und Changelog des Repositorys sowie auf die Haupt-`SKILL.md`.*
