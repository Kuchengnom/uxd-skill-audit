---
layout: post
title: "accessibility-agents: Die Prüfungen sichern die Form ab, die Fehler sitzen im Inhalt"
date: 2026-10-15
category: Skill-Evaluation
skill_reviewed: "Community-Access/accessibility-agents"
verdict: vertrauen
reading_time: 10
last_audited: "15. Oktober 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "Die Kriterienliste von WCAG 2.2 liegt als maschinenlesbare Datei vor und stimmt mit dem Standard überein, und ein Test weist erfundene Kriterien zurück; im Kontrast-Spezialisten stehen aber eine falsche Definition von großem Text und sechs falsch gerechnete Tailwind-Verhältnisse, obwohl andere Dateien desselben Repositories die richtigen Werte nennen."
  transparenz: 4
  transparenz_note: "Roadmap, Konformitätsdossier und Audit-Bericht benennen eigene Vorbehalte, Abweichungen und ungeprüfte Behauptungen mit seltener Offenheit; die Quellenpolitik wirbt dagegen weiter mit einer wöchentlichen Prüfung, deren Workflow mit Version 7.0.0 entfernt wurde."
  validierbarkeit: 4
  validierbarkeit_note: "Fünfzehn Prüfschritte, ein Fixture mit 49 eingebauten Fehlern ohne Lösungskommentare und ein veröffentlichter Erstaudit samt Fehlerbericht sind mehr Prüfapparat als in jedem anderen Kandidaten der Serie, aber das Fixture stammt vom Projekt selbst und die Testsuite ließ in den Versionen 7.0.1 und 7.0.2 ausnahmslos defekte Werkzeuge passieren."
  wartbarkeit: 4
  wartbarkeit_note: "MIT-Lizenz, zwei namentlich benannte Hauptautoren, Changelog nach Keep a Changelog, Versionsnummern nach SemVer und ein Fehlerbericht, der binnen Tagen behoben wurde; dagegen steht ein Repository von acht Monaten Alter, das am 21. September 843 Dateien auf einmal entfernt hat."

tags:
  - barrierefreiheit
  - wcag
  - multi-agent
  - kontrast
  - selbst-audit
  - skill-evaluation
---

Wenn ein Skill-Projekt seine eigenen Fehler veröffentlicht, ist das in dieser Serie bereits eine Nachricht. `Community-Access/accessibility-agents` geht weiter: Im Repository liegt ein Bericht über einen ersten echten Audit, in dem steht, dass die zentrale Funktion, das Zusammenführen von Befunden, bei 141 Befunden exakt null zusammengeführt hat. Das Changelog dokumentiert, dass in den Versionen 7.0.1 und 7.0.2 alle 39 mitgelieferten Prüfwerkzeuge beim Aufruf einen Fehler zurückgaben, während die Qualitätstests grün blieben. Und die Roadmap beginnt mit einem Abschnitt, der "Review of 7.0, with the reservations stated" heißt.

Das ist ungewöhnlich und verdient Anerkennung. Es macht den Fall aber auch zu einem guten Prüfstein, denn wer so offen misst, lässt sich fair überprüfen. Dieser Post macht das an dem, was im Repository tatsächlich steht, nicht an dem, was Verzeichnisse oder frühere README-Fassungen darüber berichten.

Eine Vorbemerkung zum Gegenstand, weil sie selbst eine Lektion enthält: Das Projekt ist nicht mehr das, was ältere Beschreibungen zeigen. Fassungen des READMEs, die in Verzeichnissen und Zwischenspeichern kursieren, nennen "79" oder "80" Agenten, an anderer Stelle "59" oder "elf Spezialisten". Seit dem 21. September 2026, Version 7.0.0, besteht das Paket aus 108 Skills: sechs Einstiegspunkte, die 102 weitere Spezialisten, Hilfs- und Referenz-Skills nach Namen aufrufen. Der Umbau hat 843 Dateien aus mehreren Client-Verzeichnissen entfernt und den Kontext, den das Paket vor der ersten Nutzeranfrage belegt, laut Commit-Nachricht von 15.924 auf 1.136 Token gesenkt. Alles Folgende bezieht sich auf diesen Stand, geprüft an einer lokalen Kopie des Repositories (Version 7.0.3, 23. September).

## Was dieses Projekt anders macht

Die meisten Skills dieser Serie behaupten eine Methode. Dieses Projekt dokumentiert, wie es seine Behauptungen prüft, und bewertet dabei auch sich selbst kritisch.

Das Beispiel ist der Erstaudit vom 21. September. Das Verzeichnis `example/` enthält eine Shop-Seite mit 49 absichtlich eingebauten Barrierefreiheitsfehlern, jeder mit einem `ISSUE`-Kommentar markiert; ich habe 49 solcher Markierungen in `index.html` und `styles.css` gezählt, die Angabe stimmt. Der Bericht hält ausdrücklich fest, dass die Kommentare vor dem Audit entfernt wurden, weil sonst gemessen würde, ob ein Spezialist einen Kommentar lesen kann, und das Skript `audit-fixture.mjs` erledigt das samt Zeilenzuordnung. Genau an dieser Stelle ist die frühere Evaluation von `wcag-audit-claude-skill` in dieser Serie gescheitert: Dort stand die Musterlösung als HTML-Kommentar in den Testseiten, und ob sie vor dem Lauf entfernt wurde, blieb offen. Hier ist das Problem erkannt und behoben, und das ist der wichtigste Unterschied zwischen beiden Projekten.

Das Ergebnis liest sich nüchtern. Neun Spezialisten liefen parallel, alle neun Ausgaben bestanden die Schema-Prüfung, die Trefferquote lag bei 49 von 49. Der Bewertungsalgorithmus selbst meldete zunächst 86 Prozent und sieben Fehlstellen, die alle gefunden worden waren, weil Zeilennummern gegen die falsche Datei verglichen wurden. Auch nach der Korrektur meldet er nur 45 von 49; vier wurden von Hand bestätigt. Der Bericht nennt das ausdrücklich "a sanity check, not a measurement to defend".

Der Abschnitt "What is still not proven" endet mit einem Satz, den man jedem Skill-Autor wünschen würde: Ein Fixture sei eine Seite, die jemand kaputt gebaut hat, ihre Fehler seien die, die der Autor sich ausgedacht habe, und der nächste Audit solle von jemandem gefahren werden, der die Antwort nicht kennt. Die Roadmap führt das als offenen Punkt 2.1a.

## Der Standard als Datenstruktur

Methodisch ist die zweite Stärke die Art, wie WCAG 2.2 im Projekt vorkommt. Die Datei `wcag22-criteria.json` listet alle Erfolgskriterien mit Nummer, Name und Stufe. Ich habe nachgezählt: 86 Einträge, 31 auf Stufe A, 24 auf AA, 31 auf AAA. Das entspricht dem Standard, und es ist genau die Zählung, an der der frühere WCAG-Skill der Serie gescheitert ist.

Dazu kommt ein Test, `test-findings-contract.mjs`, der jeden Befund gegen diese Liste prüft. Er weist drei Dinge zurück: eine Nummer, die es in WCAG 2.2 nicht gibt, eine Stufe, die nicht zum Kriterium passt, und das in 2.2 gestrichene Kriterium 4.1.1 Parsing. Ich habe ihn ausgeführt: 12 Beispiele, 88 Prüfungen, alle bestanden. Das Pflichtfeld `wcag` im Befundschema bedeutet, dass kein Spezialist einen Befund ohne Kriterium melden kann, höchstens mit dem ausdrücklichen Vermerk `n/a`. Für Studierende ist das ein anschauliches Muster: Ein Standard wird nicht zitiert, sondern als Prüfgrundlage maschinenlesbar eingebaut.

<div class="callout">
<div class="callout__title">Die Prüfungen sichern die Form ab, die Fehler sitzen im Inhalt</div>
Die Qualitätsprüfungen dieses Projekts sind ernsthaft und trotzdem blind für eine bestimmte Art von Fehler. Der Kontrakt-Test kann nur feststellen, ob ein Befund ein existierendes Kriterium mit der richtigen Stufe nennt. Er kann nicht feststellen, ob der Spezialist, der den Befund erzeugt hat, die Kriterien richtig versteht. Das Projekt belegt dieses Muster selbst zweimal. Erstens hat der Selbsttest des Zusammenführens nur zwei Beispiel-Ausgaben verwendet, die zufällig dieselbe Regelkennung trugen; erst der echte Audit zeigte, dass von 141 Befunden keiner zusammengeführt wurde, und ein Div, das als Button benutzt wird, erschien achtmal im Bericht. Zweitens blieb die Testsuite des MCP-Servers grün, obwohl in den Versionen 7.0.1 und 7.0.2 jeder einzelne der 39 Werkzeugaufrufe mit einem Validierungsfehler endete. Das Changelog formuliert es so: Der Server habe gestartet, den Handshake erledigt und alle 39 Werkzeuge korrekt aufgelistet, "which is why it looked healthy". Die Tests riefen die Handler-Funktionen direkt auf und lasen die Werkzeugliste, aber kein Ergebnis lief je durch die Ausgabeprüfung des SDK. Beide Fehler wurden gefunden und behoben, und beide Berichte sind vorbildlich ehrlich. Der Rückschluss für die Bewertung ist trotzdem unbequem: Was die Prüfungen nicht abdecken, ist ungeprüft, und die inhaltliche Richtigkeit von 57 Spezialisten-Texten gehört dazu. Die Roadmap räumt das selbst ein: Die Spezialisten seien mechanisch aufgeteilt worden, die ersten 6 KiB blieben im Skill, der Rest ging in Referenzdateien, und "that is the largest remaining quality gap".
</div>

## Was in den Spezialisten steht

Ich habe als Stichprobe den Kontrast-Spezialisten `contrast-master` gelesen, weil Kontrast der Bereich ist, in dem sich Zahlen exakt nachrechnen lassen. Die Stichprobe ist klein, ein Skill von 57 Spezialisten, und das Ergebnis ist gemischt.

Positiv: Der Skill enthält die korrekte WCAG-Formel für relative Leuchtdichte als Python-Code und verweist darauf, Werte zu berechnen statt zu schätzen. Das ist dieselbe Entwurfsentscheidung, die schon bei `wcag-audit-claude-skill` als beste des Projekts galt.

Problematisch sind zwei Dinge. Erstens definiert der Skill großen Text als "18px+ or 14px+ bold". WCAG definiert ihn als 18 Punkt oder 14 Punkt fett, also rund 24 beziehungsweise 18,66 CSS-Pixel. Ein Fließtext von 20 Pixeln wäre nach dem Skill großer Text mit der Grenze 3:1, nach dem Standard braucht er 4,5:1. Der Fehler widerspricht dem Projekt selbst: Die Referenzdatei `complete-wcag-2-2-aa-success-criteria-reference.md` im Skill `wcag-guide` und die Tabelle in `kb-design-system` nennen die korrekten Punktwerte. Ein Abgleich zwischen beiden Dateien findet offenbar nicht statt.

Zweitens listet der Skill Kontrastverhältnisse für Tailwind-Grautöne auf. Ich habe sie mit der Formel nachgerechnet, die der Skill im selben Dokument abbildet, auf den Hexwerten, die er selbst nennt:

| Kombination | Angabe im Skill | Nachgerechnet |
|---|---|---|
| gray-400 auf Weiß | 2,85:1 | 2,54:1 |
| gray-500 auf Weiß | 4,64:1 | 4,83:1 |
| gray-300 auf Weiß | 1,74:1 | 1,47:1 |
| gray-500 auf gray-900 | 3,41:1 | 3,67:1 |
| gray-400 auf gray-900 | 5,51:1 | 6,99:1 |
| gray-600 auf gray-900 | 2,11:1 | 2,35:1 |

Alle sechs Zahlen weichen ab, alle sechs Urteile "besteht" oder "besteht nicht" stimmen. Der praktische Schaden ist deshalb klein, und der Skill fordert ausdrücklich "Always verify". Aber es sind Zahlen, die im Ton eines Messergebnisses auftreten und nicht gemessen sind. Das Muster kennt man aus Sprachmodell-Ausgaben, und es ist dort entstanden, wo kein Werkzeug dazwischen stand.

Ein weiterer Rest betrifft das Kriterium, das der eigene Test ablehnt: 4.1.1 Parsing taucht in `kb-help-url-reference` als Zuordnung für `duplicate-id` auf und in einer Referenzdatei des Web-Wizards, obwohl der Kontrakt-Test es als Befund zurückweisen würde und `wcag-guide` erklärt, warum es entfernt wurde. Auch hier prüft der Test die Ausgabe, nicht das Referenzmaterial, aus dem die Ausgabe entsteht.

## Das Versprechen, das den Umbau nicht überlebt hat

Die Quellenpolitik des Projekts ist ein Schmuckstück auf dem Papier: ein sechsstufiger Autoritätsrang von Normen über Hersteller-Dokumentation bis zu Gesetzen, eine Regel "No Source, No Claim", eine Registerdatei mit 20 Quellen. Die Politik behauptet außerdem, ein wöchentlicher GitHub-Actions-Workflow prüfe die Quellen auf Änderungen und eröffne bei Abweichungen Issues. Genau diese Zusage stand auch in der älteren README-Fassung.

In der aktuellen Fassung gibt es diesen Workflow nicht mehr. `git log` zeigt, dass `source-currency-check.yml` im Commit zu Version 7.0.0 gelöscht wurde. Die Politik verlinkt ihn weiterhin und nennt als Ort des Registers `skills/SOURCE_REGISTRY.json`, wo die Datei nicht liegt; sie liegt in `docs/standards/source-registry.json`. Der letzte Gesamtabgleich im Register trägt das Datum 3. März 2026, und beim ersten Eintrag, WCAG 2.2, ist das Feld für den Inhaltsabdruck leer. Die Quellenpflege, die am überzeugendsten wirkte, wird also nach heutigem Stand nicht mehr automatisch betrieben, ohne dass das irgendwo vermerkt ist. Das ist keine Täuschung, sondern Dokumentationsdrift nach einem sehr großen Umbau, und es ist genau der Fehler, den ein Projekt für Dokumentationsqualität eigentlich vermeiden will.

## Wartbarkeit

Die Gegenseite ist solide. Die Lizenz ist MIT, mit Taylor Arndt als Rechteinhaber. Die Historie umfasst 374 Commits seit dem 20. Februar 2026, davon stammen rund 300 von Jeff Bishop und Taylor Arndt; dazu kommen Dependabot-Commits. Das Changelog folgt dem Keep-a-Changelog-Format, die Versionsnummern folgen SemVer, und der Fehler mit den 39 defekten Werkzeugen wurde als Issue 205 gemeldet und in 7.0.3 am 23. September behoben, mit einem neuen Test, der alle Aufrufe tatsächlich durchführt. Eine Abhängigkeitsprüfung blockiert hohe Sicherheitswarnungen.

Zwei Einschränkungen bleiben. Die Aktivität kommt in Schüben: seit dem 1. Juni 14 Commits, davon vier zwischen dem 21. und dem 23. September. Und der 7.0.0-Commit trägt einen Co-Authored-By-Trailer eines Claude-Modells, die Prüfschritte, die den Umbau absichern, sind also im selben, teilweise KI-gestützten Arbeitsgang entstanden wie der Umbau. Das ist kein Mangel an sich, aber ein Grund, den nächsten Audit, wie das Projekt selbst fordert, von jemand Unbeteiligtem fahren zu lassen.

## Grenzen dieser Evaluation

Ich habe nicht `npm run verify` mit allen fünfzehn Prüfschritten ausgeführt, nur den Kontrakt-Test. Ich habe keinen eigenen Audit gegen eine echte Seite gefahren und deshalb die 49 von 49 weder bestätigt noch widerlegt. Gelesen habe ich ausführlich einen Spezialisten, den Kontrast-Skill, außerdem README, Roadmap, Changelog, Konformitätsdossier, Quellenpolitik und Erstaudit-Bericht. Die Wirksamkeit der Sperre für ungeprüfte Änderungen ("blocks edits") und die Live-Gates für Codex und Copilot habe ich nicht überprüft. Gemini CLI und Antigravity wurden laut Roadmap vom Projekt selbst nicht live getestet, nur aus der Dokumentation abgeleitet.

## Empfehlung für den Unterricht

Das Urteil "vertrauen" bei einem Durchschnitt von 3,75 heißt: Als Arbeitsmittel taugt das Paket, wenn man seine Ergebnisse als Rohmaterial behandelt, nicht als Konformitätsaussage. Das sagt das Projekt selbst, und die Berichte weisen darauf hin, dass automatische Prüfungen nur eine Minderheit der Barrieren finden und ein bestandener Wert eine Untergrenze ist. Vor einem Einsatz für Berichte, die nach außen gehen, sollte man den Kontrast-Spezialisten und die Referenzdateien gegen den Standard lesen.

Als Lehrmaterial ist das Repository ergiebiger als fast alles andere in dieser Serie. Drei Übungen bieten sich an. Erstens: Studierende rechnen die Tailwind-Tabelle selbst nach und suchen in `contrast-master` und `wcag-guide` die zwei verschiedenen Definitionen von großem Text. Das zeigt, dass ein Gesamtprojekt widersprüchlich sein kann, auch wenn jede Datei für sich plausibel klingt. Zweitens: Der Erstaudit-Bericht wird gelesen mit der Frage, welche Fehler ein Fixture grundsätzlich nicht finden kann; der Bericht liefert die Antwort im letzten Absatz, und man kann sie am Beispiel prüfen. Drittens: Der Vergleich der README-Fassungen von vor und nach dem 21. September zeigt, warum man Kennzahlen mit Datum und Version zitiert. Wer im September eine Agentenzahl aus einem Verzeichnis übernommen hat, beschrieb ein Projekt, das es nicht mehr gab.
