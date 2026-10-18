---
layout: post
title: "interface-design: Craft-Philosophie mit dateibasiertem Gedächtnis — starkes Handwerk, schwache Quellenarbeit"
date: 2026-05-04
category: Skill-Evaluation
skill_reviewed: "Dammyjay93/interface-design"
verdict: vertrauen
reading_time: 8
last_audited: "04. Mai 2026"
superseded_by: /2026/06/08/interface-design/

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "Die Practitioner-Prinzipien sind stark, aber ohne Quellenangaben. Die Inspirationen bleiben implizit und nicht verifizierbar."
  transparenz: 4
  transparenz_note: "Der Scope ist klar abgegrenzt. Die KI-Warnung ist ehrlich. Der 'Memory'-Begriff im README ist leicht problematisch gerahmt."
  validierbarkeit: 3
  validierbarkeit_note: "Vor/Nachher-Vergleiche und vier eingebaute Selbst-Checks sind vorhanden. Externe Tests oder Screenshots fehlen."
  wartbarkeit: 4
  wartbarkeit_note: "MIT-Lizenz, aktiver Release-Zyklus (Feb 2026) und eigene Domain sprechen für das Projekt. Dahinter steht eine Einzelperson ohne Team-Redundanz."

tags:
  - interface-design
  - craft
  - design-tokens
  - memory
  - consistency
  - stateless-ki
  - system-md
---

<div class="callout">
<div class="callout__title">Überholt: es gibt eine neuere Evaluation dieses Skills</div>
Diese Fassung vom 4. Mai 2026 ist der historische Stand. Am 8. Juni wurde der Skill erneut geprüft. Die methodische Fundierung wurde von 3 auf 2 korrigiert. Das Urteil wechselt dadurch von <code>vertrauen</code> auf <code>vorsicht</code>. Einen neuen Befund gab es nicht. Der Grund war eine falsche Anwendung des eigenen Bewertungsrahmens. Der Wert 3 setzt vorhandene, wenn auch lückenhafte Quellen voraus. Dieser Skill nennt keine. Maßgeblich ist das <a href="{{ '/2026/06/08/interface-design/' | relative_url }}">Re-Audit vom 8. Juni 2026</a>.
</div>

`Dammyjay93/interface-design` startete als `claude-design-skill`. Heute zählt es zu den meistgenutzten Claude-Code-Plugins im Designbereich. Im Mai 2026 hat es knapp 4.600 GitHub-Stars und 316 Forks. Hinter dem Projekt steht Oyindamola Akinleye. Sie ist Designerin mit nachweisbarem Practitioner-Hintergrund und einem eigenen Auftritt unter [interface-design.dev](https://interface-design.dev). Der Skill verspricht drei Dinge gleichzeitig: Handwerk, Gedächtnis und Konsistenz. Er richtet sich an Dashboards, Admin-Panels, Apps und Tools. Marketing-Seiten schließt er ausdrücklich aus.

Präzise formuliert ist dieser Anspruch. Diese Evaluation prüft, wie viel davon hält.

## Das eigentliche Problem, das der Skill adressiert

Wer regelmäßig UI-Prototypen mit Claude baut, kennt das Phänomen. Button-Höhen variieren sitzungsübergreifend zwischen 36px, 38px und 40px. Abstände folgen keinem erkennbaren Raster. Farbtokens werden spontan erfunden. Die SKILL.md benennt das präzise: *„You will generate generic output. Your training has seen thousands of dashboards. The patterns are strong."*

Dieser Satz ist ungewöhnlich ehrlich für ein Skill-Dokument. Die meisten Skills bauen auf der Fiktion auf, dass Instruktionen das KI-Verhalten zuverlässig kontrollieren. Hier steht das Gegenteil. Defaults sind real und stark. Prozess allein überwindet sie nicht. *„Process alone doesn't guarantee craft. You have to catch yourself."*

Die Ausgangsposition ist methodisch sauber. Selbstkritik ist ein eingebetteter Bestandteil des Skills.

## Die Philosophie: Manifest oder Methodik?

Das Herzstück der SKILL.md ist eine Designphilosophie mit drei Kernaussagen.

Erstens **Intent First**. Vor dem ersten Codezeichen müssen drei Fragen beantwortet werden. Wer ist dieser Mensch konkret? Was muss er erledigen, als Verb formuliert und nicht als Feature? Wie soll es sich anfühlen, spezifisch und nicht als „clean and modern"?

Zweitens **Product Domain Exploration**. Vor jeder visuellen Richtung müssen vier Dinge benannt sein. Das sind Domain-Konzepte, eine Farbwelt aus dem realen Produktkontext und eine Signatur-Element-Idee. Dazu kommen drei explizite Defaults, die bewusst abgelehnt werden.

Drittens **The Mandate**. Der Skill fordert vier Checks vor der Präsentation des eigenen Outputs. Der Swap-Test fragt, ob jemand den Unterschied überhaupt merken würde. Der Squint-Test prüft, ob die Hierarchie auch verschwommen erkennbar bleibt. Der Signature-Test verlangt fünf konkret benennbare Elemente. Der Token-Test fragt, ob die CSS-Variablen nach einem erkennbaren Produkt klingen.

Diese Checks sind vernünftig. Sie decken sich mit etablierten UX-Prüfverfahren. Zitiert werden sie nirgends. Der Squint-Test ist seit Jahrzehnten in der visuellen Kommunikation bekannt. Die Rückführung von Designentscheidungen auf Intent ist zentral in Don Normans Theorie menschenzentrierter Gestaltung. Tokens als Designentscheidungen zu begreifen, ist ein Gedanke aus der Diskussion um Brad Frosts Atomic-Design-Konzept und Salesforce Lightning. Er betrifft mehr als ein Implementierungsdetail.

Nichts davon wird erwähnt. Die Prinzipien wirken wie destillierte Praxiserfahrung einer einzelnen Designerin. Valide ist das. Für Lernende ist es trotzdem eine Falle. Sie können nicht überprüfen, woher das Wissen stammt. Sie sehen nicht, wie breit es konsentiert ist. Auch seine Grenzen bleiben unsichtbar.

## Das Gedächtnis-Problem

<div class="callout"><div class="callout__title">Kernkritik: „Memory" ist eine Datei, kein Gedächtnis</div>

Das prominenteste Feature des Skills heißt Memory. Das README verspricht: „The system remembers across sessions." Diese Formulierung ist technisch ungenau. Bei Studierenden erzeugt sie falsche Erwartungen.

Tatsächlich schreibt der Skill Designentscheidungen in eine lokale Datei namens `.interface-design/system.md`. Beim Start der nächsten Sitzung liest Claude diese Datei. Die dort festgehaltenen Werte wendet Claude an. Es gibt kein Gedächtnis. Es gibt eine Datei, die gelesen wird.

Das hat konkrete Konsequenzen. Fehlt die Datei, gibt es keine Kontinuität. Das passiert im falschen Verzeichnis, in einem neuen Repository oder auf einem anderen Rechner. Teilen mehrere Projekte versehentlich dieselbe Datei, entsteht unbeabsichtigte Konsistenz über Projektgrenzen hinweg. Wird die Datei manuell verändert, ändert sich das „Gedächtnis" sofort und vollständig.

Technisch ist das kein Fehler. Es ist eine elegante, einfache Lösung für ein echtes Problem. Die Kommunikation als „Memory" ist dagegen eine anthropomorphe Vereinfachung. Sie beschreibt das Modell falsch. Für den Unterricht ist genau dieser Punkt wertvoll. Er zeigt, wie technisch korrekte Mechanismen durch irreführende Frames kommuniziert werden.

</div>

Zur Verteidigung des Skills: Die SKILL.md selbst ist transparenter als das README. Dort steht der Mechanismus als Dateilade-Prozess und nicht als Gedächtnis. Das Framing-Problem sitzt im Marketing-Text. Das eigentliche Skill-Dokument ist weniger betroffen.

## Was der Skill gut macht: Explizite Grenzen

Seltener als das Memory-Versprechen, aber genauso wichtig: Der Skill zieht explizite Grenzen.

*„Not for: Landing pages, marketing sites, campaigns. Redirect those to `/frontend-design`."*

Methodisch wichtig ist das. Ein Skill, der sich selbst einen Einsatzbereich verweigert, signalisiert Selbstreflexion. Die Community-Reaktion auf Claude Design zeigt, dass das Scope-Problem real ist. Kritisiert werden stereotype Outputs mit immer gleichen serif-Fonts und Card-Layouts. `interface-design` löst das nicht vollständig. Es benennt das Problem aber.

Positiv ist auch die aktive Warnung vor dem AI-Default-Problem. *„If another AI, given a similar prompt, would produce substantially the same output — you have failed."* Selten ist eine solche Formulierung. Sie macht Einzigartigkeit zum Qualitätsmerkmal und nicht zum Bonus.

## Validierbarkeit: Checks ohne externe Referenz

Der Skill liefert konkrete Vorher-Nachher-Vergleiche. Ein Beispiel ist der quantitative Kontrast zwischen „Button heights drift 36px, 38px, 40px" und „Button: 36px, documented". Dazu kommen Referenz-Systemdateien für die zwei Richtungen Precision und Warmth. Die vier eingebauten Selbst-Checks gehören ebenfalls dazu.

Es fehlen vergleichende UI-Screenshots. Es fehlt auch externe Validierung durch Nutzertests und ein Verweis auf Studien zu Design-Konsistenz und Nutzerwahrnehmung. Die Vor/Nachher-Beispiele im README sind Texte über Design und nicht Design selbst. Für die Lehre wäre ein Screenshot-Paar erheblich überzeugender als Pixelwert-Listen. Gemeint ist ein generisches Dashboard neben einem system.md-gesteuerten.

## Wartung und Kontext

Version `v2026.2.8` erschien im Februar 2026. Sie hat die SKILL.md vollständig selbsttragend gemacht. Alle Referenzinhalte liegen jetzt inline und nicht mehr in externen Dateien. Technisch ist das ein sauberer Schritt. Der Skill funktioniert ohne Abhängigkeit von einer Verzeichnisstruktur, die der Nutzer vielleicht nicht kennt.

Die MIT-Lizenz ist vorhanden. Die eigene Domain ist gepflegt. Oyindamola Akinleye ist als Einzelperson aktiv. Ein Team dahinter ist nicht erkennbar. Issue #13 war zum Zeitpunkt dieser Evaluation noch offen. Darin laden Plugin-Commands nicht im Claude-Code-Menü. Das ist ein gängiges Integrationsproblem im Plugin-Ökosystem. Auf die Skill-Qualität deutet es nicht.

## Empfehlung für den Unterrichtseinsatz

`interface-design` eignet sich gut als Lehrobjekt für zwei verschiedene Diskussionen.

**Erste Diskussion, was ein guter Workflow-Skill leisten kann:** Die Intent-First-Methodik und die vier Craft-Checks bieten echtes didaktisches Material. Studierende wenden Squint-Test, Swap-Test und Token-Test an eigenen Outputs an. Dafür müssen sie den Skill nicht installieren. Das Prinzip „Defaults benennen bevor sie passieren" lässt sich auf jeden Designprozess übertragen.

**Zweite Diskussion, wie technische Mechanismen kommuniziert werden:** Das Memory-Framing ist ein Paradebeispiel. Eine einfache Dateioperation wird als kognitive Fähigkeit vermarktet. Lehrende zeigen daran, dass der Mechanismus korrekt und nützlich ist. Die Beschreibung des Mechanismus ist irreführend. Beides ist gleichzeitig wahr.

Im Studio-Kontext gilt eine Bedingung. Die Studierenden müssen verstehen, dass die `system.md`-Datei das eigentliche Werkzeug ist. Ein lernfähiges System ist sie nicht. Wer das versteht, setzt den Skill produktiv ein. Wer es nicht versteht, wird frustriert sein. Beim nächsten Rechner fehlt das „Gedächtnis".

Urteil: **Vertrauen**, mit klarem Unterricht darüber, was hinter dem Memory-Versprechen steckt.
