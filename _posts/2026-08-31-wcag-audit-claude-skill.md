---
layout: post
title: "wcag-audit-claude-skill: Der erste Skill mit echter Evaluation — und einer Prüfungsordnung, die er selbst geschrieben hat"
date: 2026-08-31
category: Skill-Evaluation
skill_reviewed: "CFLW-AI/wcag-audit-claude-skill"
verdict: vorsicht
reading_time: 9
last_audited: "31. August 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "WCAG 2.2 ist die am besten prüfbare Grundlage, die ein Skill in diesem Ökosystem wählen kann, und die Kontrastberechnung läuft programmatisch statt geschätzt — aber die im README genannte Zahl von 28 AA-Erfolgskriterien stimmt mit keiner Zählung des Standards überein, weder mit den 24 Kriterien der Stufe AA noch mit den 55 Kriterien, die eine AA-Konformität tatsächlich verlangt."
  transparenz: 4
  transparenz_note: "Ein eigener Abschnitt benennt ausdrücklich, dass statische Codeanalyse weder Tastaturbedienung noch Screenreader-Verhalten noch JavaScript-getriebene Zustandswechsel prüfen kann, und verlangt ergänzende manuelle Tests — das ist die klarste Grenzkommunikation der bisherigen Serie, verschweigt aber die Herkunft der eigenen Prüfzahlen."
  validierbarkeit: 3
  validierbarkeit_note: "Zehn Testseiten, ein Bewertungsskript, strukturierte Ergebnisse und ein öffentlicher Report sind mehr Prüfapparat als alle bisher evaluierten Skills zusammen — nur stammen Prüfling, Prüfungsaufgaben und Bewertungsmaßstab von derselben Hand, und die Musterlösung liegt als HTML-Kommentar in genau der Datei, die der Skill einliest."
  wartbarkeit: 2
  wartbarkeit_note: "MIT-Lizenz und saubere Repository-Struktur stehen gegen vier Commits, sechs Sterne, null Watcher, keine Repository-Beschreibung, keine Releases und eine Organisation ohne Profil, hinter der keine namentlich greifbare Person steht."

tags:
  - wcag
  - barrierefreiheit
  - evaluation
  - zirkelschluss
  - kontrastberechnung
  - skill-evaluation
---

Diese Serie hat bislang vor allem ein Muster dokumentiert: Skills, die behaupten, eine Methode zu haben, und keine Möglichkeit anbieten, das zu überprüfen. Kein Testfall, kein Referenzoutput, kein Before/After. Die Dimension "Validierbarkeit" war in den meisten bisherigen Evaluationen die schwächste, oft mit einer 1 oder 2.

`CFLW-AI/wcag-audit-claude-skill` bricht mit diesem Muster. Das Repository enthält ein Verzeichnis `evals/` mit zehn eigens gebauten Testseiten, ein automatisiertes Bewertungsskript `grade_all.py`, strukturierte Ergebnisse in `grading_results.json` und einen als GitHub Page veröffentlichten Auswertungsbericht. Das README führt eine Ergebnistabelle: 56 von 56 bekannten Fehlern erkannt, null falsch-negative, null falsch-positive Treffer, 28 von 28 Erfolgskriterien abgedeckt. Das ist mehr Prüfapparat als in allen bisher hier evaluierten Projekten zusammen.

Genau deshalb lohnt dieser Skill eine genaue Betrachtung. Nicht weil er schlecht wäre — er gehört handwerklich zum Besseren, was das Ökosystem hervorgebracht hat — sondern weil er die interessantere Frage stellt: Was ist eine Evaluation wert, die der Prüfling selbst entworfen hat?

## Die beste denkbare Grundlage

Zunächst das Positive, und es ist erheblich. Wer einen Design-Skill auf WCAG 2.2 aufbaut, wählt die einzige Grundlage im gesamten UX-Feld, die vollständig normiert, öffentlich dokumentiert und im Wortlaut nachprüfbar ist. Nielsens Heuristiken sind Faustregeln. Rams' Prinzipien sind eine Haltung. Ein Erfolgskriterium der W3C ist ein Satz mit einer definierten Prüfbedingung. Der Unterschied ist für einen Skill fundamental: Bei WCAG lässt sich objektiv feststellen, ob eine Regel korrekt portiert wurde.

Zweitens, und das ist der eigentliche Fortschritt: Der Skill rät Kontrastverhältnisse nicht, er rechnet sie. Phase 3 der beschriebenen Methodik ruft ein Python-Skript `contrast_checker.py` auf, das die relative Leuchtdichte nach der WCAG-Formel berechnet. Das ist der richtige Umgang mit der Arbeitsteilung zwischen Sprachmodell und Werkzeug. Ein Sprachmodell, das aus zwei Hexwerten ein Kontrastverhältnis schätzen soll, produziert plausibel klingende Zahlen, die falsch sind — und Barrierefreiheitsprüfung ist eine Domäne, in der eine plausibel klingende falsche Zahl schlimmer ist als gar keine, weil sie zu einem Prüfbericht wird, auf den sich jemand verlässt. Dass hier gerechnet statt geschätzt wird, ist die wichtigste einzelne Entwurfsentscheidung des Projekts.

Drittens der Abschnitt "Limitations". Er sagt in klaren Worten, dass es sich um statische Codeanalyse handelt, dass tatsächliche Tastaturnavigation, Screenreader-Verhalten und JavaScript-getriebene Zustandsänderungen nicht geprüft werden können, und dass für eine vollständige Konformitätsaussage manuelle Tests mit assistiven Technologien hinzukommen müssen. Nach zwei Dutzend evaluierten Skills, von denen die meisten keinen einzigen Satz darüber verlieren, was sie nicht können, ist das bemerkenswert. Es ist auch fachlich exakt die richtige Grenze: Ein großer Teil der WCAG-Kriterien ist ohne Interaktion schlicht nicht entscheidbar.

## Die Zahl 28 gibt es im Standard nicht

Und hier beginnt das Problem. Das README spricht durchgängig von "allen 28 WCAG 2.2 AA-Erfolgskriterien" und meldet eine Abdeckung von 28/28.

WCAG 2.2 enthält 86 Erfolgskriterien: 31 auf Stufe A, 24 auf Stufe AA, 31 auf Stufe AAA. Wer "Stufe AA" im engen Sinn meint, also nur die AA-Kriterien selbst, kommt auf 24. Wer AA-Konformität meint — und das ist das, was ein Auditbericht üblicherweise aussagt, denn Konformität auf Stufe AA setzt die Erfüllung aller A- und aller AA-Kriterien voraus — kommt auf 55. Die Zahl 28 entspricht keiner dieser beiden Zählungen.

Das ist kein Tippfehler in einer Nebenangabe. Es ist der Nenner, auf den sich die zentrale Leistungsaussage des Projekts bezieht. "28/28" liest sich als vollständige Abdeckung, und formal stimmt das auch — nur eben Abdeckung eines Kriterienkatalogs, den das Projekt selbst zusammengestellt hat, nicht des normativen Standards. Wenn tatsächlich 28 Kriterien geprüft werden, fehlen zur AA-Konformität rund 27 weitere, darunter der gesamte nicht abgedeckte Teil der Stufe A. Ein Bericht, der auf dieser Basis "WCAG 2.2 AA" im Titel führt, sagt mehr aus, als er geprüft hat.

Für Studierende ist das die übertragbare Lektion dieses Falls, und sie ist unbequemer als die üblichen: Eine Prozentangabe ist nur so gut wie ihr Nenner. "100 % erkannt" beantwortet nicht die Frage, wie viel überhaupt gesucht wurde. Bei jeder Leistungszahl in einem Skill-README lautet die erste Rückfrage nicht "wie hoch?", sondern "wovon?".

<div class="callout">
<div class="callout__title">Der Prüfling hat die Klausur selbst geschrieben — und die Lösung steht im Aufgabenblatt</div>
Die Evaluationsergebnisse sind auffällig perfekt: 56 von 56 Fehlern gefunden, null übersehen, null Fehlalarme. In der Messtechnik ist ein perfektes Ergebnis kein Qualitätssignal, sondern ein Anlass, das Messverfahren zu prüfen. Hier fallen drei Rollen zusammen, die in jeder ernsthaften Evaluation getrennt gehören: Wer den Skill geschrieben hat, hat auch die zehn Testseiten entworfen, auch die Musterlösung festgelegt und auch das Bewertungsskript programmiert. Ein Prüfling, der seine eigene Klausur stellt, besteht sie zuverlässig. Gravierender ist ein technisches Detail, das im README beiläufig steht: Die Musterlösung — welche Fehler auf welcher Seite absichtlich eingebaut wurden — liegt als HTML-Kommentar in den Testseiten selbst. Der Skill liest diese Seiten im Quelltext ein. Die Antworten stehen damit potenziell in genau der Eingabe, die bewertet wird. Ob das Auswertungsskript die Kommentare vor dem Durchlauf entfernt, ist die entscheidende Frage der gesamten Evaluation — und das Repository beantwortet sie nirgends. Solange sie offen ist, misst die Tabelle möglicherweise nicht die Prüfkompetenz des Skills, sondern seine Lesefähigkeit. Bezeichnend ist auch, wie der Befund zu Testseite 07 gerahmt wird: Die Seite sollte fehlerfrei sein, der Skill fand dort echte Kontrastfehler, und das README verbucht das als Beleg für Gründlichkeit. Man kann es auch anders lesen — als Beweis, dass die Musterlösung falsch war. Wenn die Referenz an einer nachweislich geprüften Stelle danebenlag, ist die Angabe "null Fehlalarme, manuell verifiziert" von derselben Partei bestätigt worden, die sich zuvor geirrt hat.
</div>

## Wer steht dahinter?

Die Wartbarkeit ist die schwächste Dimension. Das Repository hat vier Commits, sechs Sterne, einen Fork und null Watcher. Es trägt keine Beschreibung, keine Topics, keine Releases. Die Organisation `CFLW-AI` hat kein öffentliches Profil, hinter dem eine namentlich greifbare Person oder Institution stünde. Eine Suche in den einschlägigen Communities — Reddit, Hacker News, X — ergab keine einzige Erwähnung. Immerhin liegt eine MIT-Lizenz vor, was in dieser Serie keineswegs selbstverständlich ist.

Das ist bei einem Werkzeug für Barrierefreiheitsprüfung nicht nebensächlich. WCAG-Prüfberichte haben in vielen Kontexten rechtliche Relevanz; in der EU knüpfen der European Accessibility Act und die Umsetzungen der Web-Richtlinie unmittelbar daran an. Ein Werkzeug, das solche Berichte erzeugt, braucht eine identifizierbare verantwortliche Stelle und eine Pflegezusage, die über vier Commits hinausgeht. Der Standard selbst entwickelt sich weiter — schon der Übergang von 2.1 auf 2.2 hat neun Kriterien hinzugefügt und eines gestrichen. Ein nicht gepflegter Prüfskill veraltet nicht langsam, sondern mit der nächsten Version schlagartig.

## Empfehlung für den Unterricht

Für die Lehre ist dieser Skill wertvoller als die meisten bisher evaluierten — allerdings nicht als Werkzeug, sondern als Lehrmaterial über Evaluation.

Als Prüfinstrument sollte er nicht eingesetzt werden, wo ein Ergebnis nach außen geht. Für den Einstieg in ein Projekt, um offensichtliche Kontrastprobleme programmatisch statt geschätzt zu finden, ist er dagegen brauchbar — dieser eine Teilbereich ist der methodisch belastbarste, weil er auf einer Formel und nicht auf einem Modellurteil beruht. Wichtig ist, jeden erzeugten Bericht als Rohmaterial und nicht als Konformitätsaussage zu behandeln, und die im Repository selbst genannte Grenze ernst zu nehmen: Ohne Tastatur- und Screenreader-Test ist keine AA-Aussage möglich.

Der eigentliche Unterrichtswert liegt woanders. Man kann an diesem Repository innerhalb einer Sitzung drei Dinge zeigen, für die es sonst kein so sauberes Beispiel gibt. Erstens die Nenner-Frage: Studierende sollen die Zahl 28 selbst gegen den Standard prüfen und feststellen, dass sie dort nicht vorkommt. Zweitens die Rollentrennung in Evaluationen: Warum ist ein 100-Prozent-Ergebnis ein Warnsignal, und welche drei Rollen müssten getrennt sein, damit es keines wäre? Drittens, und das ist die fairste Übung: Dieses Projekt hat als einziges der Serie überhaupt eine Evaluation vorgelegt und macht sich damit angreifbar. Die Skills ohne Testsuite entziehen sich derselben Kritik nur, weil sie gar nichts behaupten, was man nachprüfen könnte. Wer transparent misst, wird kritisierbar; wer schweigt, bleibt unangreifbar. Dass unsere Bewertungslogik diese Asymmetrie nicht vollständig auflöst, gehört zur ehrlichen Einordnung dieses Urteils dazu.
