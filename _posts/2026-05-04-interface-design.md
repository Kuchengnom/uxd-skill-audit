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
  methodische_fundierung_note: "Starke Practitioner-Prinzipien ohne Quellenangaben — Inspirationen bleiben implizit, nicht verifizierbar."
  transparenz: 4
  transparenz_note: "Klare Scope-Abgrenzung und ehrliche KI-Warnung, leichtes Framing-Problem beim 'Memory'-Begriff im README."
  validierbarkeit: 3
  validierbarkeit_note: "Vor/Nachher-Vergleiche und vier eingebaute Selbst-Checks vorhanden, aber keine externen Tests oder Screenshots."
  wartbarkeit: 4
  wartbarkeit_note: "MIT-Lizenz, aktiver Release-Zyklus (Feb 2026), eigene Domain — Einzelperson ohne Team-Redundanz."

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
Diese Fassung vom 4. Mai 2026 ist der historische Stand. Am 8. Juni wurde der Skill erneut geprüft und dabei die methodische Fundierung von 3 auf 2 korrigiert, wodurch das Urteil von <code>vertrauen</code> auf <code>vorsicht</code> wechselt. Grund war kein neuer Befund, sondern eine falsche Anwendung des eigenen Bewertungsrahmens. Der Wert 3 setzt vorhandene, wenn auch lückenhafte Quellen voraus, und dieser Skill nennt keine. Maßgeblich ist das <a href="{{ '/2026/06/08/interface-design/' | relative_url }}">Re-Audit vom 8. Juni 2026</a>.
</div>

`Dammyjay93/interface-design` hat sich seit seinem Start als `claude-design-skill` zu einem der meistgenutzten Claude-Code-Plugins im Designbereich entwickelt: knapp 4.600 GitHub-Stars und 316 Forks nach dem Stand vom Mai 2026. Hinter dem Projekt steht Oyindamola Akinleye, eine Designerin mit eigenem Website-Auftritt unter [interface-design.dev](https://interface-design.dev) und nachweisbarem Practitioner-Hintergrund. Der Skill verspricht drei Dinge gleichzeitig: Handwerk, Gedächtnis und Konsistenz. Er richtet sich an Dashboards, Admin-Panels, Apps und Tools, ausdrücklich nicht an Marketing-Seiten.

Das ist ein präzise formulierter Anspruch. Diese Evaluation prüft, wie viel davon hält.

## Das eigentliche Problem, das der Skill adressiert

Wer regelmäßig UI-Prototypen mit Claude baut, kennt das Phänomen: Button-Höhen variieren sitzungsübergreifend zwischen 36px, 38px und 40px, Abstände folgen keinem erkennbaren Raster, Farbtokens werden spontan erfunden. Die SKILL.md benennt das präzise: *„You will generate generic output. Your training has seen thousands of dashboards. The patterns are strong."*

Dieser Satz ist ungewöhnlich ehrlich für ein Skill-Dokument. Die meisten Skills bauen auf der Fiktion auf, dass Instruktionen das KI-Verhalten zuverlässig kontrollieren. Hier steht das Gegenteil: Defaults sind real, stark und werden durch Prozess allein nicht überwunden. *„Process alone doesn't guarantee craft. You have to catch yourself."*

Das ist eine methodisch saubere Ausgangsposition: Selbstkritik als eingebetteter Skill-Bestandteil.

## Die Philosophie: Manifest oder Methodik?

Das Herzstück der SKILL.md ist eine Designphilosophie, die in drei Kernaussagen kulminiert:

Erstens **Intent First**. Vor dem ersten Codezeichen müssen drei Fragen beantwortet werden. Wer ist dieser Mensch konkret? Was muss er erledigen, als Verb formuliert und nicht als Feature? Wie soll es sich anfühlen, spezifisch und nicht als „clean and modern"?

Zweitens **Product Domain Exploration**. Bevor eine visuelle Richtung vorgeschlagen wird, müssen Domain-Konzepte, eine Farbwelt aus dem realen Produktkontext, eine Signatur-Element-Idee und drei explizite Defaults benannt werden, die bewusst abgelehnt werden.

Drittens **The Mandate**. Der Skill fordert, das eigene Output vor der Präsentation mit vier Checks zu prüfen. Der Swap-Test fragt, ob jemand den Unterschied überhaupt merken würde. Der Squint-Test prüft, ob Hierarchie auch verschwommen erkennbar bleibt. Der Signature-Test verlangt fünf konkret benennbare Elemente. Der Token-Test fragt, ob die CSS-Variablen nach einem erkennbaren Produkt klingen.

Diese Checks sind vernünftig und deckungsgleich mit etablierten UX-Prüfverfahren. Das Problem: Sie werden nirgends zitiert. Der Squint-Test ist seit Jahrzehnten in der visuellen Kommunikation bekannt. Die Idee, Designentscheidungen auf Intent zurückzuführen, ist zentral in Don Normans Theorie menschenzentrierter Gestaltung. Tokens als Designentscheidungen zu begreifen und nicht nur als Implementierungsdetail ist ein Gedanke, der seit Brad Frosts Atomic-Design-Konzept und Salesforce Lightning diskutiert wird.

Nichts davon wird erwähnt. Die Prinzipien wirken wie destillierte Praxiserfahrung einer einzelnen Designerin. Das ist valide, aber für Lernende eine Falle. Sie können nicht überprüfen, woher das Wissen stammt, wie breit es konsentiert ist und wo seine Grenzen liegen.

## Das Gedächtnis-Problem

<div class="callout"><div class="callout__title">Kernkritik: „Memory" ist eine Datei, kein Gedächtnis</div>

Das prominenteste Feature des Skills heißt Memory, und der README verspricht: „The system remembers across sessions." Diese Formulierung ist technisch ungenau und kann bei Studierenden falsche Erwartungen erzeugen.

Was tatsächlich passiert: Der Skill schreibt Designentscheidungen in eine lokale Datei namens `.interface-design/system.md`. Beim Start der nächsten Sitzung liest Claude diese Datei und wendet die dort festgehaltenen Werte an. Es gibt kein Gedächtnis. Es gibt eine Datei, die gelesen wird.

Das hat konkrete Konsequenzen. Fehlt die Datei, etwa im falschen Verzeichnis, in einem neuen Repository oder auf einem anderen Rechner, gibt es keine Kontinuität. Wenn mehrere Projekte dieselbe Datei versehentlich teilen, entsteht unbeabsichtigte Konsistenz über Projektgrenzen hinweg. Wenn die Datei manuell verändert wird, ändert sich das „Gedächtnis" sofort und vollständig.

Das ist kein technischer Fehler, sondern eine elegante, einfache Lösung für ein echtes Problem. Aber die Kommunikation als „Memory" ist eine anthropomorphe Vereinfachung, die das Modell falsch beschreibt. Für den Unterrichtseinsatz ist genau dieser Punkt wertvoll: Er zeigt, wie technisch korrekte Mechanismen durch irreführende Frames kommuniziert werden können.

</div>

Zur Verteidigung des Skills: Die SKILL.md selbst ist transparenter als das README. Dort wird der Mechanismus als Dateilade-Prozess beschrieben, nicht als Gedächtnis. Das Framing-Problem ist im Marketing-Text stärker ausgeprägt als im eigentlichen Skill-Dokument.

## Was der Skill gut macht: Explizite Grenzen

Seltener als das Memory-Versprechen, aber genauso wichtig: Der Skill zieht explizite Grenzen.

*„Not for: Landing pages, marketing sites, campaigns. Redirect those to `/frontend-design`."*

Das ist methodisch wichtig. Ein Skill, der sich selbst einen Einsatzbereich verweigert, signalisiert Selbstreflexion. Die Community-Reaktion auf Claude Design generell zeigt, dass das Scope-Problem real ist. Kritisiert werden stereotype Outputs mit immer gleichen serif-Fonts und Card-Layouts. `interface-design` löst das nicht vollständig, aber es benennt es.

Ebenso positiv: Die SKILL.md warnt aktiv vor dem AI-Default-Problem. *„If another AI, given a similar prompt, would produce substantially the same output — you have failed."* Das ist eine seltene Formulierung. Sie zwingt dazu, Einzigartigkeit als Qualitätsmerkmal zu begreifen, nicht als Bonus.

## Validierbarkeit: Checks ohne externe Referenz

Der Skill liefert konkrete Vorher-Nachher-Vergleiche, etwa den quantitativen Kontrast zwischen „Button heights drift 36px, 38px, 40px" und „Button: 36px, documented". Dazu kommen Referenz-Systemdateien für die zwei Richtungen Precision und Warmth sowie die vier eingebauten Selbst-Checks.

Was fehlt: Vergleichende UI-Screenshots, externe Validierung durch Nutzertests, oder ein Verweis auf Studien zu Design-Konsistenz und Nutzerwahrnehmung. Die Vor/Nachher-Beispiele im README sind Texte über Design, nicht Design selbst. Für eine didaktische Nutzung wäre ein Screenshot-Paar erheblich überzeugender als Pixelwert-Listen: ein generisches Dashboard neben einem system.md-gesteuerten.

## Wartung und Kontext

Version `v2026.2.8` wurde im Februar 2026 veröffentlicht und hat die SKILL.md vollständig selbsttragend gemacht, indem alle Referenzinhalte inline statt in externen Dateien liegen. Das ist ein technisch sauberer Schritt: Der Skill funktioniert jetzt ohne Abhängigkeit von einer Verzeichnisstruktur, die der Nutzer vielleicht nicht kennt.

Die MIT-Lizenz ist vorhanden. Die eigene Domain ist gepflegt. Oyindamola Akinleye ist als Einzelperson aktiv, ohne erkennbares Team dahinter. Issue #13, in dem Plugin-Commands nicht im Claude-Code-Menü laden, war zum Zeitpunkt dieser Evaluation noch offen. Das ist ein gängiges Integrationsproblem im Plugin-Ökosystem, das nicht spezifisch auf Skill-Qualität hinweist.

## Empfehlung für den Unterrichtseinsatz

`interface-design` eignet sich gut als Lehrobjekt für zwei verschiedene Diskussionen.

**Erste Diskussion, was ein guter Workflow-Skill leisten kann:** Die Intent-First-Methodik und die vier Craft-Checks bieten echtes didaktisches Material. Studierende können den Squint-Test, den Swap-Test und den Token-Test an eigenen Outputs anwenden, unabhängig davon ob sie den Skill installieren. Das Prinzip „Defaults benennen bevor sie passieren" ist übertragbar auf jeden Designprozess.

**Zweite Diskussion, wie technische Mechanismen kommuniziert werden:** Das Memory-Framing ist ein Paradebeispiel dafür, wie eine einfache Dateioperation als kognitive Fähigkeit vermarktet wird. Lehrende können diesen Skill nutzen um zu zeigen: Der Mechanismus ist korrekt und nützlich. Die Beschreibung des Mechanismus ist irreführend. Beides kann gleichzeitig wahr sein.

Für den Einsatz im Studio-Kontext gilt: Der Skill funktioniert gut, wenn die Studierenden verstehen, dass die `system.md`-Datei das eigentliche Werkzeug ist und kein lernfähiges System. Wer das versteht, kann den Skill produktiv einsetzen. Wer es nicht versteht, wird frustriert sein, wenn das „Gedächtnis" beim nächsten Rechner fehlt.

Urteil: **Vertrauen**, mit klarem Unterricht darüber, was hinter dem Memory-Versprechen steckt.
