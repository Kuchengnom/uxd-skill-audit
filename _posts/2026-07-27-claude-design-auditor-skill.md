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
  methodische_fundierung_note: "Die WCAG-Erfolgskriterien sind namentlich und korrekt zitiert (SC 1.4.3, 2.1.1, 1.1.1, 2.4.1). Die Nielsen-Heuristiken sind sauber abgegrenzt. Die 22 Dark Patterns, die Verhaltensprinzipien und die gesamte Typografie- und Rasterebene kommen aber ohne Primärquelle aus."
  transparenz: 4
  transparenz_note: "Der Skill koppelt Konfidenzstufen an das tatsächliche Prüfverhalten. Bei reiner Textbeschreibung verweigert er ausdrücklich jede Punktzahl. Die Regulatorik-Prüfungen deklariert er als UI-Signalebene und nicht als Rechtsgutachten. Nur die Gesamtnote selbst tritt ohne Unsicherheitsangabe auf."
  validierbarkeit: 2
  validierbarkeit_note: "Es gibt weder Testfälle noch Referenzausgaben noch einen Vergleichskorpus. Das einzige durchgerechnete Beispiel im README widerspricht der eigenen Punkteformel um acht Punkte."
  wartbarkeit: 4
  wartbarkeit_note: "MIT-Lizenz, 21 Releases, 84 Commits und ein detailliert geführtes Changelog bis Mai 2026. Getragen wird das Projekt aber von einer einzelnen Person ohne erkennbare Nachfolgeplanung."

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

Die bisher evaluierten Skills dieser Reihe wollten Claude beim *Entwerfen* helfen. `claude-design-auditor-skill` von Ashutos1997 dreht die Richtung um. Er soll fertige Entwürfe *prüfen*. Eingabe kann eine Figma-Datei über MCP sein, HTML/CSS/React/Vue-Code, ein Screenshot, eine URL oder ein Wireframe. Heraus kommt ein Prüfbericht mit einer Gesamtnote von 100. Dazu gibt es drei Teilnoten für Accessibility, Ethics und Usability und Befunde in vier Schweregraden.

Interessant ist der Fall, weil Prüfen andere epistemische Ansprüche stellt als Entwerfen. Ein Entwurfsskill mit schlechten Vorschlägen produziert schlechte Entwürfe. Das sieht man. Ein Prüfskill, der falsch prüft, produziert eine Zahl, die wie ein Messergebnis aussieht. Eine Angabe wie 62/100 wirkt auf zwei Stellen genau. Zahlen werden geglaubt.

## Was der Skill nachweislich richtig macht

Beginnen wir mit dem, was in dieser Reihe selten vorkommt. Die Quellenarbeit ist überprüfbar.

An konkrete WCAG-Erfolgskriterien ist die Blocker-Stufe gebunden, und zwar an die richtigen. Kontrast unter 4,5:1 wird gegen SC 1.4.3 gemeldet. Ein tastaturunerreichbares Element geht gegen SC 2.1.1, fehlender Alternativtext gegen SC 1.1.1 und ein fehlender Sprunglink gegen SC 2.4.1. Das lässt sich Kriterium für Kriterium gegen die W3C-Empfehlung prüfen. Es stimmt. Wer die Reihe mitgelesen hat, weiß, wie ungewöhnlich das ist. Die Mehrzahl der bisher untersuchten Skills nennt „WCAG" als Etikett und schreibt nie eine SC-Nummer.

Ähnlich sauber ist der Umgang mit den Nielsen-Heuristiken. Kategorie 19 behandelt nicht alle zehn. Die Referenzdatei `heuristics.md` erklärt ausdrücklich, dass H4, H5, H8 und H9 ausgeschlossen sind. Sie begründet das so, dass diese inhaltlich schon in anderen Kategorien geprüft werden. Ein Skill, der von zehn Heuristiken sechs behandelt und das offen deklariert, ist methodisch ehrlicher als einer, der alle zehn behauptet und keine sauber portiert.

## Konfidenz, die tatsächlich etwas verändert

Der bemerkenswerteste Abschnitt trägt die Überschrift „Set Confidence Level" samt Zusatz „and act on it". Er beginnt mit dem Satz, Konfidenz sei nicht bloß ein Etikett. Ernst gemeint ist das.

Bei Figma-Zugriff oder Quellcode gilt hohe Konfidenz. Es gibt volle Punktabzüge, und exakte Werte werden zitiert. Bei einem Screenshot sinkt die Konfidenz auf mittel. Daraufhin ändert sich das Verhalten. Punktabzüge für alles, was exakte Werte voraussetzt, werden halbiert. Die Kategorie „Design Tokens" wird komplett übersprungen. Hex-Werte dürfen nicht mehr genannt werden. Blocker werden auf Critical herabgestuft, sofern die Verletzung visuell nicht eindeutig ist. Bei einer bloßen Textbeschreibung verweigert der Skill die Bewertung: „Never assign a score on description alone."

Eine durchdachtere Behandlung von Eingabequalität ist mir in diesem Ökosystem bisher nicht begegnet. Der Skill erkennt an, dass ein Screenshot weniger Information enthält als eine Figma-Datei. Er übersetzt das in konkrete Verhaltensregeln statt in eine Fußnote.

Genauso ehrlich ist die Regulatorik-Ebene. Kategorie 18 hat sechs Compliance-Prüfungen. Sie betreffen Cookie-Banner, Abo-Offenlegung, Datenschutzhinweis am Erhebungspunkt, Widerrufsrecht, Altersverifikation und Barrierefreiheits-Rechtslage. Jede trägt den ausdrücklichen Vorbehalt, dies sei eine UI-Signalebene und kein Rechtsgutachten. Genau diese Unterscheidung fehlt sonst überall dort, wo Skills mit GDPR-Vokabular hantieren.

## Und dann die Zahl

Jetzt zum Kern. Seit v1.2.11 dokumentiert der Skill eine explizite Formel.

`100 − (Blocker × 12) − (Critical × 8) − (Warning × 4) − (Tip × 1)`

Sie soll das Ergebnis reproduzierbar machen. Das README zeigt dazu ein Beispiel mit einem Checkout-Flow aus drei Frames. Es rechnet vor:

`100 − (1 × 🚫 12) − (2 × 🔴 8) − (4 × 🟡 4) − (2 × 🟢 1) = 62/100`

Die Abzüge summieren sich auf 46. Es sind 12 + 16 + 16 + 2. Dann ist 100 − 46 = 54. Nicht 62. Acht Punkte Differenz sind das. Sie stehen im einzigen vollständig durchgerechneten Beispiel der gesamten Dokumentation. Dieses Beispiel soll die Reproduzierbarkeit der Formel demonstrieren.

Erschwerend kommt hinzu, dass die Notation mehrdeutig ist. `(1 × 🚫 12)` lässt offen, ob „1" die Anzahl und „12" der Abzug ist oder umgekehrt. Unter der dokumentierten Formel gilt die erste Lesart. Ein Beispiel, dessen Schreibweise man erst gegen die Formel auflösen muss, erklärt aber nichts.

<div class="callout">
<div class="callout__title">Determinismus in der Formel, Schätzung in den Zahlen</div>
Die Formel ist deterministisch. Was in sie eingesetzt wird, ist es nicht. Ob eine Abstandsabweichung als 🟡 Warnung oder als 🔴 Critical gilt, entscheidet das Modell bei jedem Durchlauf neu. Dasselbe gilt für die Frage, ob zwei Befunde denselben Ursprung haben und zusammengehören. Auch ob eine CTA-Hierarchie manipulativ oder nur ungeschickt ist, entscheidet das Modell neu. Die Formel legt nur fest, wie diese Urteile addiert werden. Das Ergebnis ist eine Ganzzahl auf einer 100er-Skala. Sie sieht aus wie eine Messung. Tatsächlich ist sie eine gewichtete Zusammenfassung wiederholt getroffener Ermessensentscheidungen. In jedem Bericht steht die Formel. Nachvollziehbar wird so die Addition und nicht der Summand. Zwei Läufe über dieselbe Datei können 54 und 71 ergeben. Beide Berichte weisen ihre Rechnung sauber aus. Hier verschiebt sich das Versprechen. Nicht die Note ist das Problem, sondern die zwei Stellen Sicherheit, die sie suggeriert.
</div>

Verschärft wird das durch drei verschiedene Skalen, die nebeneinander laufen. Die Gesamtnote arbeitet mit −12/−8/−4/−1. Beim Ethics Score gilt −15/−7/0. Das Changelog v1.2.12 vermerkt einen ergänzten Hinweis, dass die Ethics-Formel „distinct from standard formula" sei. Der Vorbehalt ist da. Trotzdem stehen zwei Zahlen mit derselben Optik und derselben Skala im Bericht nebeneinander. Ihre Berechnungsgrundlage ist verschieden. Sie laden zum Vergleich ein.

## Was das Changelog über die Substanz verrät

Das Changelog ist ungewöhnlich detailliert geführt. Gerade deshalb ist es aufschlussreich.

Version v1.2.11 listet unter „Bug fixes" *category count „17" → „19" throughout* und *Cat 18/19 numbering corrected*. Der Skill hat in einer veröffentlichten Version an mehreren Stellen eine falsche Anzahl eigener Kategorien angegeben. Dazu hat er Kategorien vertauscht. Parallel wandert die Zählung der Dark Patterns. Version v1.2.4 spricht von 20 Mustern in 5 Gruppen. Version v1.2.12 korrigiert auf 22. Der aktuelle README-Text nennt sechs Gruppen und formuliert „and 17 more" nach acht aufgezählten Beispielen. Zusammen wären das 25. Für einen Skill, dessen Kernversprechen Systematik ist, ist die eigene Systematik erstaunlich beweglich.

Ein zweiter aufschlussreicher Eintrag steht in v1.2.7. Drittanbieter-Agenten gaben statt des Berichts eine freie UX-Kritik aus. Daraufhin wurden zwei Hinweise eingefügt, nämlich `⚠️ OUTPUT FORMAT IS MANDATORY — DO NOT DEVIATE` und `⚠️ MANDATORY — ALL AGENTS — NO EXCEPTIONS`. Das ist eine ehrliche Reaktion auf ein reales Problem. Es bleibt eine Prompt-Reaktion auf ein strukturelles Problem. Ein Format, das nur durch Großbuchstaben gehalten wird, ist kein erzwungenes Format. Für den Unterricht ist das ein gutes Anschauungsstück. Wo ein Skill anfängt zu schreien, fehlen ihm meist die Durchsetzungsmittel.

## Was fehlt: jede Form von Prüfung des Prüfers

Andere misst der Skill. Ihn selbst misst nichts.

Es gibt keine Testfälle. Es gibt keine Referenzausgaben, gegen die man einen Lauf halten könnte. Es gibt keinen Korpus mit bekannten Fehlern, an dem sich Trefferquote und Fehlalarmrate bestimmen ließen. Es gibt keinen Vergleich mit einem menschlichen Audit derselben Oberfläche. Ein ausführbares Skript fehlt ebenfalls. Bei `plugin87/ux-ui-agent-skills` werden Kontrastwerte tatsächlich berechnet und in CI erzwungen. Hier bleibt jede Prüfung eine Modellaussage über einen Prompt.

Das einzige Belegstück ist das Beispiel im README. Und das rechnet sich selbst falsch.

Damit steht die Frage im Raum, die jeder Prüfskill beantworten müsste. Dieser beantwortet sie nicht. Wie oft meldet er einen Kontrastverstoß, der keiner ist? Wie oft übersieht er einen? Ohne diese Zahlen ist die Gesamtnote von 100 eine Angabe ohne Bezugsgröße.

## Bewertung und Empfehlung für den Unterricht

Das Urteil lautet **vorsicht**. Grund ist die Validierbarkeit und nicht die Substanz. Inhaltlich gehört dieser Skill zum oberen Drittel des Ökosystems. Er hat korrekte SC-Nummern, sauber abgegrenzte Heuristiken und verhaltenswirksame Konfidenzstufen. Der Rechtsvorbehalt ist ehrlich. Dazu kommen MIT-Lizenz und 21 Releases mit gepflegtem Changelog bis Mai 2026. Es fehlt jeder Nachweis, dass das Ergebnis stimmt.

Für den Unterricht schlage ich eine zweiteilige Übung vor.

**Teil 1: Reproduzierbarkeit prüfen.** Studierende lassen denselben Entwurf dreimal in getrennten Sitzungen auditieren. Sie protokollieren die drei Gesamtnoten und die Zahl der Befunde je Schweregrad. Die Streuung ist das eigentliche Lernergebnis. Anschließend rechnen sie das README-Beispiel selbst nach und finden die Acht-Punkte-Lücke.

**Teil 2: Trennschärfe prüfen.** Die Klasse teilt die Befunde eines Berichts in zwei Stapel. Stapel eins enthält mechanisch Entscheidbares wie Kontrastverhältnis, fehlendes `<label>` oder Abstand außerhalb des 8er-Rasters. Stapel zwei enthält Interpretationsbedürftiges wie Manipulationsvorwurf, Tonalität der Microcopy und Hierarchie der Handlungsaufforderung. Der erste Stapel lässt sich extern verifizieren, etwa mit einem Kontrastrechner. Der zweite nicht. Beide gehen mit demselben Gewicht in dieselbe Zahl ein. Dort sollte die Diskussion beginnen.

Als Werkzeug ist der Design Auditor brauchbar. Wer ihn als strukturierte Checkliste verwendet, bekommt echten Wert. Sie lenkt die Aufmerksamkeit auf Bereiche, die man sonst überspringt. Als Qualitätsnachweis taugt er nicht. Man schreibt „62/100" nicht in eine Abgabe, ohne die zugrunde liegenden Befunde einzeln geprüft zu haben.

---

*Geprüft am 27. Juli 2026 gegen den Stand v1.2.13, dessen Release vom 17. Mai 2026 datiert, 57 Stars, 12 Forks, 84 Commits, MIT-Lizenz. Die Referenzdateien im Verzeichnis `references/`, darunter `ethics.md` und `heuristics.md`, waren zum Prüfzeitpunkt nicht direkt abrufbar. Aussagen dazu stützen sich auf README und Changelog des Repositorys sowie auf die Haupt-`SKILL.md`.*
