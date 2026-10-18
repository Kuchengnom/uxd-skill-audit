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
  methodische_fundierung_note: "WCAG 2.2 ist die am besten prüfbare Grundlage, die ein Skill in diesem Ökosystem wählen kann. Die Kontrastberechnung läuft programmatisch statt geschätzt. Die im README genannte Zahl von 28 AA-Erfolgskriterien stimmt aber mit keiner Zählung des Standards überein. Der Standard hat 24 Kriterien der Stufe AA. Eine AA-Konformität verlangt 55 Kriterien."
  transparenz: 4
  transparenz_note: "Ein eigener Abschnitt benennt ausdrücklich, dass statische Codeanalyse weder Tastaturbedienung noch Screenreader-Verhalten noch JavaScript-getriebene Zustandswechsel prüfen kann. Er verlangt ergänzende manuelle Tests. Das ist die klarste Grenzkommunikation der bisherigen Serie. Die Herkunft der eigenen Prüfzahlen verschweigt der Skill aber."
  validierbarkeit: 3
  validierbarkeit_note: "Zehn Testseiten, ein Bewertungsskript, strukturierte Ergebnisse und ein öffentlicher Report sind mehr Prüfapparat als alle bisher evaluierten Skills zusammen. Prüfling, Prüfungsaufgaben und Bewertungsmaßstab stammen aber von derselben Hand. Die Musterlösung liegt als HTML-Kommentar in genau der Datei, die der Skill einliest."
  wartbarkeit: 2
  wartbarkeit_note: "MIT-Lizenz und saubere Repository-Struktur stehen gegen vier Commits, sechs Sterne, null Watcher, keine Repository-Beschreibung und keine Releases. Die Organisation hat kein Profil. Eine namentlich greifbare Person steht nicht dahinter."

tags:
  - wcag
  - barrierefreiheit
  - evaluation
  - zirkelschluss
  - kontrastberechnung
  - skill-evaluation
---

Diese Serie hat bislang vor allem ein Muster dokumentiert. Skills behaupten, eine Methode zu haben, und bieten keine Möglichkeit an, das zu überprüfen. Es gibt keinen Testfall, kein Referenzoutput und kein Before/After. „Validierbarkeit" war in den meisten bisherigen Evaluationen die schwächste Dimension. Oft stand dort eine 1 oder 2.

`CFLW-AI/wcag-audit-claude-skill` bricht mit diesem Muster. Das Repository enthält ein Verzeichnis `evals/` mit zehn eigens gebauten Testseiten. Dazu kommen ein automatisiertes Bewertungsskript `grade_all.py`, strukturierte Ergebnisse in `grading_results.json` und ein als GitHub Page veröffentlichter Auswertungsbericht. Das README führt eine Ergebnistabelle. Sie meldet 56 von 56 bekannten Fehlern erkannt, null falsch-negative, null falsch-positive Treffer und 28 von 28 Erfolgskriterien abgedeckt. Das ist mehr Prüfapparat als in allen bisher hier evaluierten Projekten zusammen.

Genau deshalb lohnt dieser Skill eine genaue Betrachtung. Er ist nicht schlecht. Handwerklich gehört er zum Besseren, was das Ökosystem hervorgebracht hat. Er stellt aber die interessantere Frage. Was ist eine Evaluation wert, die der Prüfling selbst entworfen hat?

## Die beste denkbare Grundlage

Zunächst das Positive, und es ist erheblich. Ein Design-Skill auf WCAG 2.2 steht auf der einzigen Grundlage im UX-Feld, die vollständig normiert ist. Sie ist öffentlich dokumentiert und im Wortlaut nachprüfbar. Nielsens Heuristiken sind Faustregeln. Rams' Prinzipien sind eine Haltung. Ein Erfolgskriterium der W3C ist ein Satz mit einer definierten Prüfbedingung. Für einen Skill ist der Unterschied fundamental. Bei WCAG lässt sich objektiv feststellen, ob eine Regel korrekt portiert wurde.

Der eigentliche Fortschritt kommt zweitens. Der Skill rät Kontrastverhältnisse nicht. Er rechnet sie. Phase 3 der beschriebenen Methodik ruft ein Python-Skript `contrast_checker.py` auf. Es berechnet die relative Leuchtdichte nach der WCAG-Formel. Das ist der richtige Umgang mit der Arbeitsteilung zwischen Sprachmodell und Werkzeug. Ein Sprachmodell soll aus zwei Hexwerten ein Kontrastverhältnis schätzen. Es produziert plausibel klingende Zahlen, die falsch sind. In der Barrierefreiheitsprüfung ist eine plausibel klingende falsche Zahl schlimmer als gar keine. Sie wird zu einem Prüfbericht, auf den sich jemand verlässt. Dass hier gerechnet statt geschätzt wird, ist die wichtigste Entwurfsentscheidung.

Drittens kommt der Abschnitt „Limitations". Er sagt in klaren Worten, dass es sich um statische Codeanalyse handelt. Tastaturnavigation, Screenreader-Verhalten und JavaScript-getriebene Zustandsänderungen kann sie nicht prüfen. Für eine vollständige Konformitätsaussage müssen manuelle Tests mit assistiven Technologien hinzukommen. Zwei Dutzend Skills wurden bislang evaluiert. Die meisten verlieren keinen einzigen Satz darüber, was sie nicht können. Dieser Abschnitt ist bemerkenswert. Er markiert auch fachlich exakt die richtige Grenze. Ein großer Teil der WCAG-Kriterien ist ohne Interaktion schlicht nicht entscheidbar.

## Die Zahl 28 gibt es im Standard nicht

Und hier beginnt das Problem. Das README spricht durchgängig von „allen 28 WCAG 2.2 AA-Erfolgskriterien". Es meldet eine Abdeckung von 28/28.

WCAG 2.2 enthält 86 Erfolgskriterien. 31 liegen auf Stufe A, 24 auf Stufe AA und 31 auf Stufe AAA. Zählt man „Stufe AA" im engen Sinn, also nur die AA-Kriterien selbst, kommt man auf 24. Meint man AA-Konformität, kommt man auf 55. Das ist, was ein Auditbericht üblicherweise aussagt. Konformität auf Stufe AA setzt die Erfüllung aller A- und aller AA-Kriterien voraus. Die Zahl 28 entspricht keiner dieser beiden Zählungen.

Das ist kein Tippfehler in einer Nebenangabe. Es ist der Nenner der zentralen Leistungsaussage des Projekts. „28/28" liest sich als vollständige Abdeckung. Formal stimmt das auch. Gemeint ist aber die Abdeckung eines Kriterienkatalogs, den das Projekt selbst zusammengestellt hat. Der normative Standard ist es nicht. Werden tatsächlich 28 Kriterien geprüft, fehlen zur AA-Konformität rund 27 weitere. Darunter liegt der gesamte nicht abgedeckte Teil der Stufe A. Ein Bericht führt „WCAG 2.2 AA" im Titel. Auf dieser Basis sagt er mehr aus, als er geprüft hat.

Für Studierende ist das die übertragbare Lektion dieses Falls. Sie ist unbequemer als die üblichen. Eine Prozentangabe ist nur so gut wie ihr Nenner. „100 % erkannt" beantwortet nicht die Frage, wie viel überhaupt gesucht wurde. Bei jeder Leistungszahl in einem Skill-README lautet die erste Rückfrage nicht „wie hoch?". Sie lautet „wovon?".

<div class="callout">
<div class="callout__title">Der Prüfling hat die Klausur selbst geschrieben, und die Lösung steht im Aufgabenblatt</div>
Die Evaluationsergebnisse sind auffällig perfekt. 56 von 56 Fehlern wurden gefunden, null übersehen, null Fehlalarme. In der Messtechnik ist ein perfektes Ergebnis kein Qualitätssignal. Es ist ein Anlass, das Messverfahren zu prüfen. Hier fallen drei Rollen zusammen, die in jeder ernsthaften Evaluation getrennt gehören. Wer den Skill geschrieben hat, hat auch die zehn Testseiten entworfen. Er hat die Musterlösung festgelegt und das Bewertungsskript programmiert. Ein Prüfling, der seine eigene Klausur stellt, besteht sie zuverlässig. Gravierender ist ein technisches Detail, das im README beiläufig steht. Die Musterlösung liegt als HTML-Kommentar in den Testseiten selbst. Sie nennt die Fehler, die je Seite absichtlich eingebaut wurden. Der Skill liest diese Seiten im Quelltext ein. Die Antworten stehen damit potenziell in genau der Eingabe, die bewertet wird. Ob das Auswertungsskript die Kommentare vor dem Durchlauf entfernt, ist die entscheidende Frage der gesamten Evaluation. Das Repository beantwortet sie nirgends. Solange sie offen ist, misst die Tabelle möglicherweise nicht die Prüfkompetenz des Skills. Sie misst seine Lesefähigkeit. Bezeichnend ist auch, wie der Befund zu Testseite 07 gerahmt wird. Die Seite sollte fehlerfrei sein. Der Skill fand dort echte Kontrastfehler. Das README verbucht das als Beleg für Gründlichkeit. Man kann es auch anders lesen, nämlich als Beweis, dass die Musterlösung falsch war. Die Referenz lag an einer nachweislich geprüften Stelle daneben. Die Angabe „null Fehlalarme, manuell verifiziert" stammt von derselben Partei. Sie hat sich zuvor geirrt.
</div>

## Wer steht dahinter?

Die Wartbarkeit ist die schwächste Dimension. Das Repository hat vier Commits, sechs Sterne, einen Fork und null Watcher. Es trägt keine Beschreibung, keine Topics, keine Releases. Die Organisation `CFLW-AI` hat kein öffentliches Profil. Eine namentlich greifbare Person oder Institution steht nicht dahinter. Eine Suche in den einschlägigen Communities Reddit, Hacker News und X ergab keine einzige Erwähnung. Immerhin liegt eine MIT-Lizenz vor. In dieser Serie ist das keineswegs selbstverständlich.

Das ist bei einem Werkzeug für Barrierefreiheitsprüfung nicht nebensächlich. WCAG-Prüfberichte haben in vielen Kontexten rechtliche Relevanz. In der EU knüpfen der European Accessibility Act und die Umsetzungen der Web-Richtlinie unmittelbar daran an. Ein Werkzeug, das solche Berichte erzeugt, braucht eine identifizierbare verantwortliche Stelle. Es braucht eine Pflegezusage, die über vier Commits hinausgeht. Der Standard selbst entwickelt sich weiter. Schon der Übergang von 2.1 auf 2.2 hat neun Kriterien hinzugefügt und eines gestrichen. Ein nicht gepflegter Prüfskill veraltet nicht langsam. Er veraltet mit der nächsten Version schlagartig.

## Empfehlung für den Unterricht

Für die Lehre ist dieser Skill wertvoller als die meisten bisher evaluierten. Das gilt allerdings nicht für den Werkzeugeinsatz. Er taugt als Lehrmaterial über Evaluation.

Als Prüfinstrument sollte er nicht eingesetzt werden, wo ein Ergebnis nach außen geht. Für den Einstieg in ein Projekt ist er dagegen brauchbar. Er findet offensichtliche Kontrastprobleme programmatisch statt geschätzt. Dieser eine Teilbereich ist der methodisch belastbarste. Er beruht auf einer Formel und nicht auf einem Modellurteil. Jeden erzeugten Bericht sollte man als Rohmaterial behandeln und nicht als Konformitätsaussage. Die im Repository selbst genannte Grenze gilt es ernst zu nehmen. Ohne Tastatur- und Screenreader-Test ist keine AA-Aussage möglich.

Der eigentliche Unterrichtswert liegt woanders. An diesem Repository lassen sich innerhalb einer Sitzung drei Dinge zeigen. Dafür gibt es sonst kein so sauberes Beispiel. Erstens die Nenner-Frage. Studierende prüfen die Zahl 28 selbst gegen den Standard und stellen fest, dass sie dort nicht vorkommt. Zweitens die Rollentrennung in Evaluationen. Warum ist ein 100-Prozent-Ergebnis ein Warnsignal? Und wie müssten die drei Rollen getrennt sein, damit es keines wäre? Drittens die fairste Übung. Dieses Projekt hat als einziges der Serie überhaupt eine Evaluation vorgelegt und macht sich damit angreifbar. Skills ohne Testsuite entziehen sich derselben Kritik. Sie behaupten gar nichts, was man nachprüfen könnte. Wer transparent misst, wird kritisierbar. Wer schweigt, bleibt unangreifbar. Unsere Bewertungslogik löst diese Asymmetrie nicht vollständig auf. Das gehört zur ehrlichen Einordnung dieses Urteils.
