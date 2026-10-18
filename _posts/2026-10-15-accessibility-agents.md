---
layout: post
title: "accessibility-agents: Die Prüfungen sichern die Form ab, die Fehler sitzen im Inhalt"
date: 2026-10-15
category: Skill-Evaluation
skill_reviewed: "Community-Access/accessibility-agents"
verdict: vertrauen
reading_time: 9
last_audited: "15. Oktober 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "Die Kriterienliste von WCAG 2.2 liegt maschinenlesbar vor und stimmt mit dem Standard überein. Ein Test weist erfundene Kriterien zurück. Im Kontrast-Spezialisten stehen aber eine falsche Definition von großem Text und sechs falsch gerechnete Tailwind-Verhältnisse."
  transparenz: 4
  transparenz_note: "Roadmap, Konformitätsdossier und Audit-Bericht benennen eigene Vorbehalte mit seltener Offenheit. Die Quellenpolitik wirbt dagegen weiter mit einer wöchentlichen Prüfung. Deren Workflow wurde mit Version 7.0.0 entfernt."
  validierbarkeit: 4
  validierbarkeit_note: "Fünfzehn Prüfschritte, ein Fixture mit 49 Fehlern ohne Lösungskommentare und ein veröffentlichter Erstaudit sind mehr Prüfapparat als bei jedem anderen Kandidaten der Serie. Das Fixture stammt aber vom Projekt selbst. Die Testsuite ließ in den Versionen 7.0.1 und 7.0.2 ausnahmslos defekte Werkzeuge passieren."
  wartbarkeit: 4
  wartbarkeit_note: "MIT-Lizenz, zwei namentlich benannte Hauptautoren, Changelog und SemVer sprechen für das Projekt. Ein Fehlerbericht wurde binnen Tagen behoben. Dagegen stehen acht Monate Alter und ein Umbau, der am 21. September 843 Dateien auf einmal entfernt hat."

tags:
  - barrierefreiheit
  - wcag
  - multi-agent
  - kontrast
  - selbst-audit
  - skill-evaluation
---

Ein Projekt, das seine eigenen Fehler veröffentlicht, ist in dieser Serie schon eine Nachricht. `Community-Access/accessibility-agents` geht weiter. Im Repository liegt ein Bericht über einen ersten echten Audit. Darin steht, dass die zentrale Funktion bei 141 Befunden exakt null zusammengeführt hat. Laut Changelog lieferten in den Versionen 7.0.1 und 7.0.2 alle 39 Prüfwerkzeuge beim Aufruf einen Fehler. Trotzdem blieben die Tests grün. Am Anfang der Roadmap steht ein Abschnitt namens "Review of 7.0, with the reservations stated".

Das verdient Anerkennung. Es macht den Fall auch zum Prüfstein. Wer so offen misst, lässt sich fair überprüfen. Ich stütze mich auf das, was im Repository steht. Verzeichnisse und alte README-Fassungen zählen nicht.

Der Gegenstand hat sich geändert, und das ist selbst eine Lektion. Das Projekt ist nicht mehr das, was ältere Beschreibungen zeigen. Alte README-Fassungen nennen 79 oder 80 Agenten, an anderer Stelle 59 oder elf Spezialisten. Seit dem 21. September 2026, Version 7.0.0, besteht das Paket aus 108 Skills. Sechs davon sind Einstiegspunkte. Sie rufen 102 weitere Spezialisten, Hilfs- und Referenz-Skills nach Namen auf. Zugleich verschwanden 843 Dateien aus mehreren Client-Verzeichnissen. Laut Commit-Nachricht sank der Kontext vor der ersten Nutzeranfrage von 15.924 auf 1.136 Token. Das ist ein Vierzehntel. Alles Folgende bezieht sich auf diesen Stand. Ich habe eine lokale Kopie der Version 7.0.3 vom 23. September geprüft.

## Was dieses Projekt anders macht

Die meisten Skills dieser Serie behaupten eine Methode. Dieses Projekt dokumentiert, wie es seine Behauptungen prüft. Es bewertet sich dabei selbst kritisch.

Das Beispiel ist der Erstaudit vom 21. September. Das Verzeichnis `example/` enthält eine Shop-Seite mit 49 eingebauten Fehlern. Jeder trägt einen `ISSUE`-Kommentar. Ich habe 49 solcher Markierungen in `index.html` und `styles.css` gezählt. Die Angabe stimmt.

Laut Bericht wurden die Kommentare vor dem Audit entfernt. Sonst misst der Test, ob ein Spezialist einen Kommentar lesen kann. Das Skript `audit-fixture.mjs` erledigt das samt Zeilenzuordnung. An genau dieser Stelle ist `wcag-audit-claude-skill` gescheitert. Dort stand die Musterlösung als HTML-Kommentar in den Testseiten. Ob sie vor dem Lauf entfernt wurde, blieb offen. Hier ist das Problem erkannt und behoben. Das ist der wichtigste Unterschied zwischen beiden Projekten.

Das Ergebnis liest sich nüchtern. Neun Spezialisten liefen parallel. Alle neun Ausgaben bestanden die Schema-Prüfung. Die Trefferquote lag bei 49 von 49. Zunächst meldete der Bewertungsalgorithmus 86 Prozent und sieben Fehlstellen. Alle sieben waren gefunden worden. Er hatte Zeilennummern gegen die falsche Datei verglichen. Nach der Korrektur meldet er 45 von 49. Vier wurden von Hand bestätigt. Als "a sanity check, not a measurement to defend" bezeichnet der Bericht das.

Der Abschnitt "What is still not proven" endet mit einem Gedanken, den man jedem Skill-Autor wünscht. Ein Fixture ist eine Seite, die jemand kaputt gebaut hat. Ihre Fehler sind die, die sich der Autor ausgedacht hat. Den nächsten Audit soll jemand fahren, der die Antwort nicht kennt. Die Roadmap führt das als offenen Punkt 2.1a.

## Der Standard als Datenstruktur

Die zweite Stärke liegt darin, wie WCAG 2.2 im Projekt vorkommt. Die Datei `wcag22-criteria.json` listet alle Erfolgskriterien mit Nummer, Name und Stufe. Ich habe nachgezählt. Es sind 86 Einträge, 31 auf Stufe A, 24 auf AA und 31 auf AAA. So steht es im Standard. An genau dieser Zählung ist der frühere WCAG-Skill der Serie gescheitert.

Der Test `test-findings-contract.mjs` prüft jeden Befund gegen diese Liste. Er weist drei Dinge zurück. Eine Nummer, die es in WCAG 2.2 nicht gibt. Eine Stufe, die nicht zum Kriterium passt. Und das gestrichene Kriterium 4.1.1 Parsing. Ich habe ihn ausgeführt. Er prüfte 12 Beispiele mit 88 Aussagen, alle bestanden. Im Befundschema erzwingt das Pflichtfeld `wcag` ein Kriterium. Höchstens der Vermerk `n/a` ist erlaubt. Ein Standard wird hier nicht zitiert. Er wird maschinenlesbar eingebaut.

<div class="callout">
<div class="callout__title">Die Prüfungen sichern die Form ab, die Fehler sitzen im Inhalt</div>
Die Qualitätsprüfungen dieses Projekts sind ernsthaft. Für eine Art von Fehler sind sie trotzdem blind. Ob ein Befund ein existierendes Kriterium mit der richtigen Stufe nennt, stellt der Kontrakt-Test fest. Ob der Spezialist das Kriterium richtig versteht, prüft er nicht.

Das Projekt belegt dieses Muster selbst zweimal. Beim Selbsttest des Zusammenführens dienten zwei Beispiel-Ausgaben als Eingabe. Sie trugen zufällig dieselbe Regelkennung. Erst der echte Audit zeigte das Gegenteil. Von 141 Befunden wurde keiner zusammengeführt. Ein Div, das als Button dient, stand achtmal im Bericht. Es ist, als zeigte man denselben Falschparker achtmal an. Verlangt wurden 141 Reparaturen. Nötig waren etwa 60.

Der zweite Fall ist der MCP-Server. In den Versionen 7.0.1 und 7.0.2 endete jeder der 39 Werkzeugaufrufe mit einem Validierungsfehler. Trotzdem blieb die Testsuite grün. Im Changelog steht es so: Der Server startete, erledigte den Handshake und listete alle 39 Werkzeuge korrekt auf, "which is why it looked healthy". Sie riefen Handler-Funktionen direkt auf und lasen die Werkzeugliste. Kein Ergebnis lief je durch die Ausgabeprüfung des SDK.

Beide Fehler wurden gefunden und behoben. Beide Berichte sind vorbildlich ehrlich. Für die Bewertung bleibt ein unbequemer Schluss. Was die Prüfungen nicht abdecken, ist ungeprüft. Dazu gehört die inhaltliche Richtigkeit von 57 Spezialisten-Texten. Selbst die Roadmap räumt das ein. Mechanisch wurden die Spezialisten aufgeteilt. Im Skill blieben die ersten 6 KiB, der Rest ging in Referenzdateien. Als "the largest remaining quality gap" bezeichnet sie das.
</div>

## Was in den Spezialisten steht

Als Stichprobe habe ich `contrast-master` gelesen. Kontrast ist der Bereich, in dem sich Zahlen exakt nachrechnen lassen. Die Stichprobe ist klein, denn sie umfasst einen von 57 Spezialisten. Das Ergebnis ist gemischt.

Positiv ist die Formel. Der Skill enthält die korrekte WCAG-Formel für relative Leuchtdichte als Python-Code. Er empfiehlt, Werte zu berechnen statt zu schätzen. Es ist dieselbe Entwurfsentscheidung, die bei `wcag-audit-claude-skill` als beste galt.

Zwei Dinge sind problematisch. Erstens die Definition von großem Text. Im Skill heißt es "18px+ or 14px+ bold". WCAG meint 18 Punkt oder 14 Punkt fett. Umgerechnet sind das rund 24 und 18,66 CSS-Pixel. Ein Fließtext mit 20 Pixeln wäre nach dem Skill großer Text mit der Grenze 3:1. Nach dem Standard braucht er 4,5:1. Der Fehler widerspricht dem Projekt selbst. Die Referenzdatei `complete-wcag-2-2-aa-success-criteria-reference.md` im Skill `wcag-guide` nennt die richtigen Punktwerte. Die Tabelle in `kb-design-system` auch. Ein Abgleich zwischen den Dateien findet offenbar nicht statt.

Zweitens die Tailwind-Tabelle. Er listet Kontrastverhältnisse für Grautöne. Ich habe sie nachgerechnet. Als Grundlage dienten die Formel aus demselben Dokument und die Hexwerte, die der Skill selbst nennt.

| Kombination | Angabe im Skill | Nachgerechnet |
|---|---|---|
| gray-400 auf Weiß | 2,85:1 | 2,54:1 |
| gray-500 auf Weiß | 4,64:1 | 4,83:1 |
| gray-300 auf Weiß | 1,74:1 | 1,47:1 |
| gray-500 auf gray-900 | 3,41:1 | 3,67:1 |
| gray-400 auf gray-900 | 5,51:1 | 6,99:1 |
| gray-600 auf gray-900 | 2,11:1 | 2,35:1 |

Alle sechs Zahlen weichen ab. Alle sechs Urteile stimmen. Klein ist der praktische Schaden, denn der Skill fordert ausdrücklich "Always verify". Trotzdem stehen dort Zahlen im Ton eines Messergebnisses, die nicht gemessen sind. Man kennt das Muster von Sprachmodellen. Sie liefern plausible Zahlen ohne Rechenschritt.

Ein Rest betrifft das Kriterium, das der eigene Test ablehnt. 4.1.1 Parsing steht in `kb-help-url-reference` als Zuordnung für `duplicate-id`. Es steht auch in einer Referenzdatei des Web-Wizards. Als Befund würde der Kontrakt-Test es zurückweisen. `wcag-guide` erklärt, warum es entfällt. Geprüft wird die Ausgabe. Das Material dahinter bleibt ungeprüft.

## Das Versprechen, das den Umbau nicht überlebt hat

Die Quellenpolitik wirkt auf dem Papier wie ein Schmuckstück. Sie hat einen sechsstufigen Autoritätsrang von Normen über Herstellerdokumentation bis zu Gesetzen. Sie hat die Regel "No Source, No Claim". Sie hat eine Registerdatei mit 20 Quellen. Sie verspricht auch einen wöchentlichen GitHub-Actions-Workflow. Er soll die Quellen auf Änderungen prüfen und bei Abweichungen Issues eröffnen. Dieselbe Zusage stand in der älteren README-Fassung.

In der aktuellen Fassung gibt es diesen Workflow nicht mehr. Laut `git log` wurde `source-currency-check.yml` im Commit zu Version 7.0.0 gelöscht. Verlinkt ist er trotzdem weiter. Als Ort des Registers nennt sie `skills/SOURCE_REGISTRY.json`. Dort liegt die Datei nicht. Sie liegt in `docs/standards/source-registry.json`. Als letzter Gesamtabgleich steht der 3. März 2026 im Register. Beim ersten Eintrag, WCAG 2.2, ist das Feld für den Inhaltsabdruck leer.

Die Quellenpflege, die am überzeugendsten wirkte, läuft nach heutigem Stand nicht mehr automatisch. Vermerkt ist das nirgends. Das ist keine Täuschung. Es ist Dokumentationsdrift nach einem sehr großen Umbau. Genau diesen Fehler will ein Projekt für Dokumentationsqualität vermeiden.

## Wartbarkeit

Die Gegenseite ist solide. Die Lizenz ist MIT, Rechteinhaber ist Taylor Arndt. Die Historie umfasst 374 Commits seit dem 20. Februar 2026. Rund 300 stammen von Jeff Bishop und Taylor Arndt. Dazu kommen Dependabot-Commits. Das Changelog folgt dem Format Keep a Changelog, die Versionsnummern folgen SemVer. Den Fehler mit den 39 defekten Werkzeugen meldete jemand als Issue 205. Version 7.0.3 behob ihn am 23. September. Ein neuer Test führt jetzt alle Aufrufe tatsächlich aus. Eine Abhängigkeitsprüfung blockiert hohe Sicherheitswarnungen.

Zwei Einschränkungen bleiben. Die Aktivität kommt in Schüben. Seit dem 1. Juni gab es 14 Commits, vier davon zwischen dem 21. und dem 23. September. Im 7.0.0-Commit steht ein Claude-Modell als Mitautor im Trailer. Prüfschritte und Umbau entstanden also im selben, teilweise KI-gestützten Arbeitsgang. Ein Mangel an sich ist das nicht. Es ist ein Grund, den nächsten Audit von Unbeteiligten fahren zu lassen. Genau das fordert das Projekt selbst.

## Grenzen dieser Evaluation

Ich habe nicht `npm run verify` mit allen fünfzehn Prüfschritten ausgeführt. Ausgeführt habe ich nur den Kontrakt-Test. Einen eigenen Audit gegen eine echte Seite habe ich nicht gefahren. Damit bleiben die 49 von 49 unbestätigt und unwiderlegt. Ausführlich gelesen habe ich einen Spezialisten, den Kontrast-Skill. Dazu kamen README, Roadmap, Changelog, Konformitätsdossier, Quellenpolitik und der Erstaudit-Bericht. Ungetestet blieben die Sperre für ungeprüfte Änderungen und die Live-Gates für Codex und Copilot. Gemini CLI und Antigravity hat das Projekt laut Roadmap selbst nicht live getestet. Ihr Verhalten ist aus der Dokumentation abgeleitet.

## Empfehlung für den Unterricht

Das Urteil "vertrauen" bei einem Durchschnitt von 3,75 heißt: Als Arbeitsmittel taugt das Paket. Seine Ergebnisse sind Rohmaterial und keine Konformitätsaussage. So sagt es das Projekt selbst. Automatische Prüfungen finden nur eine Minderheit der Barrieren. Ein bestandener Wert ist eine Untergrenze. Vor einem Einsatz für Berichte nach außen sollte man den Kontrast-Spezialisten und die Referenzdateien gegen den Standard lesen.

Als Lehrmaterial ist das Repository ergiebiger als fast alles andere in dieser Serie.

Die erste Übung ist Nachrechnen. Studierende prüfen die Tailwind-Tabelle selbst. Sie suchen in `contrast-master` und `wcag-guide` die zwei Definitionen von großem Text. Jede Datei klingt für sich plausibel. Trotzdem widerspricht sich das Projekt.

Die zweite Übung ist Lesen. Studierende nehmen den Erstaudit-Bericht und fragen nach den Fehlern, die ein Fixture grundsätzlich nicht findet. Im letzten Absatz des Berichts steht die Antwort. Sie lässt sich an einem Beispiel prüfen.

Die dritte Übung ist Vergleichen. Studierende legen die README-Fassungen von vor und nach dem 21. September nebeneinander. Dabei zeigt sich, warum man Kennzahlen mit Datum und Version zitiert. Eine im September übernommene Agentenzahl beschrieb ein Projekt von gestern.
