---
layout: post
title: "interface-design: Craft-Philosophie mit dateibasiertem Gedächtnis — starkes Handwerk, schwache Quellenarbeit"
date: 2026-05-04
category: Skill-Evaluation
skill_reviewed: "Dammyjay93/interface-design"
verdict: vertrauen
reading_time: 8
last_audited: "04. Mai 2026"

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

`Dammyjay93/interface-design` hat sich seit seinem Start als `claude-design-skill` zu einem der meistgenutzten Claude-Code-Plugins im Designbereich entwickelt: knapp 4.600 GitHub-Stars und 316 Forks (Stand Mai 2026). Hinter dem Projekt steht Oyindamola Akinleye, eine Designerin mit eigenem Website-Auftritt unter [interface-design.dev](https://interface-design.dev) und nachweisbarem Practitioner-Hintergrund. Der Skill verspricht drei Dinge gleichzeitig: **Handwerk** (Craft), **Gedächtnis** (Memory) und **Konsistenz** (Consistency) — für Dashboards, Admin-Panels, Apps und Tools, ausdrücklich nicht für Marketing-Seiten.

Das ist ein präzise formulierter Anspruch. Diese Evaluation prüft, wie viel davon hält.

## Das eigentliche Problem, das der Skill adressiert

Wer regelmäßig UI-Prototypen mit Claude baut, kennt das Phänomen: Button-Höhen variieren sitzungsübergreifend zwischen 36px, 38px und 40px, Abstände folgen keinem erkennbaren Raster, Farbtokens werden spontan erfunden. Die SKILL.md benennt das präzise: *"You will generate generic output. Your training has seen thousands of dashboards. The patterns are strong."*

Dieser Satz ist ungewöhnlich ehrlich für ein Skill-Dokument. Die meisten Skills bauen auf der Fiktion auf, dass Instruktionen das KI-Verhalten zuverlässig kontrollieren. Hier steht das Gegenteil: Defaults sind real, stark und werden durch Prozess allein nicht überwunden. *"Process alone doesn't guarantee craft. You have to catch yourself."*

Das ist eine methodisch saubere Ausgangsposition — Selbstkritik als eingebetteter Skill-Bestandteil.

## Die Philosophie: Manifest oder Methodik?

Das Herzstück der SKILL.md ist eine Designphilosophie, die in drei Kernaussagen kulminiert:

Erstens: **Intent First** — Vor dem ersten Codezeichen müssen drei Fragen beantwortet werden: Wer ist dieser Mensch konkret? Was muss er erledigen (Verb, nicht Feature)? Wie soll es sich anfühlen (spezifisch, nicht "clean and modern")?

Zweitens: **Product Domain Exploration** — Bevor eine visuelle Richtung vorgeschlagen wird, müssen Domain-Konzepte, eine Farbwelt aus dem realen Produktkontext, eine Signatur-Element-Idee und drei explizite Defaults benannt werden, die bewusst abgelehnt werden.

Drittens: **The Mandate** — Der Skill fordert, das eigene Output vor der Präsentation mit vier Checks zu prüfen: Swap-Test (würde niemand den Unterschied merken?), Squint-Test (ist Hierarchie auch verschwommen erkennbar?), Signature-Test (lassen sich fünf konkrete Elemente benennen?), Token-Test (klingen die CSS-Variablen wie ein erkennbares Produkt?).

Diese Checks sind vernünftig und deckungsgleich mit etablierten UX-Prüfverfahren. Das Problem: Sie werden nirgends zitiert. Der Squint-Test ist seit Jahrzehnten in der visuellen Kommunikation bekannt. Die Idee, Designentscheidungen auf Intent zurückzuführen, ist zentral in Don Normans Theorie menschenzentrierter Gestaltung. Tokens als Designentscheidungen (nicht nur Implementierungsdetail) ist ein Gedanke der seit Brad Frosts Atomic-Design-Konzept und Salesforce Lightning diskutiert wird.

Nichts davon wird erwähnt. Die Prinzipien wirken wie destillierte Praxiserfahrung einer einzelnen Designerin — was valide ist, aber für Lernende eine Falle: Sie können nicht überprüfen, woher das Wissen stammt, wie breit es konsentiert ist und wo seine Grenzen liegen.

## Das Gedächtnis-Problem

<div class="callout"><div class="callout__title">Kernkritik: "Memory" ist eine Datei, kein Gedächtnis</div>

Das prominenteste Feature des Skills heißt Memory, und der README verspricht: "The system remembers across sessions." Diese Formulierung ist technisch ungenau und kann bei Studierenden falsche Erwartungen erzeugen.

Was tatsächlich passiert: Der Skill schreibt Designentscheidungen in eine lokale Datei namens `.interface-design/system.md`. Beim Start der nächsten Sitzung liest Claude diese Datei und wendet die dort festgehaltenen Werte an. Es gibt kein Gedächtnis — es gibt eine Datei, die gelesen wird.

Das hat konkrete Konsequenzen: Wenn die Datei fehlt (falsches Verzeichnis, neues Repository, anderer Rechner), gibt es keine Kontinuität. Wenn mehrere Projekte dieselbe Datei versehentlich teilen, entsteht unbeabsichtigte Konsistenz über Projektgrenzen hinweg. Wenn die Datei manuell verändert wird, ändert sich das "Gedächtnis" sofort und vollständig.

Das ist kein technischer Fehler — es ist eine elegante, einfache Lösung für ein echtes Problem. Aber die Kommunikation als "Memory" ist eine anthropomorphe Vereinfachung, die das Modell falsch beschreibt. Für den Unterrichtseinsatz ist genau dieser Punkt wertvoll: Er zeigt, wie technisch korrekte Mechanismen durch irreführende Frames kommuniziert werden können.

</div>

Zur Verteidigung des Skills: Die SKILL.md selbst ist transparenter als das README. Dort wird der Mechanismus als Dateilade-Prozess beschrieben, nicht als Gedächtnis. Das Framing-Problem ist im Marketing-Text stärker ausgeprägt als im eigentlichen Skill-Dokument.

## Was der Skill gut macht: Explizite Grenzen

Seltener als das Memory-Versprechen, aber genauso wichtig: Der Skill zieht explizite Grenzen.

*"Not for: Landing pages, marketing sites, campaigns. Redirect those to `/frontend-design`."*

Das ist methodisch wichtig. Ein Skill, der sich selbst einen Einsatzbereich verweigert, signalisiert Selbstreflexion. Die Community-Reaktion auf Claude Design generell — Kritik an stereotypen Outputs mit immer gleichen serif-Fonts und Card-Layouts — zeigt, dass das Scope-Problem real ist. `interface-design` löst es nicht vollständig, aber es benennt ihn.

Ebenso positiv: Die SKILL.md warnt aktiv vor dem AI-Default-Problem: *"If another AI, given a similar prompt, would produce substantially the same output — you have failed."* Das ist eine seltene Formulierung. Sie zwingt dazu, Einzigartigkeit als Qualitätsmerkmal zu begreifen, nicht als Bonus.

## Validierbarkeit: Checks ohne externe Referenz

Der Skill liefert konkrete Vorher-Nachher-Vergleiche (quantitativ: "Button heights drift 36px, 38px, 40px" vs. "Button: 36px, documented"), Referenz-Systemdateien für zwei Richtungen (Precision und Warmth) und die vier eingebauten Selbst-Checks.

Was fehlt: Vergleichende UI-Screenshots, externe Validierung durch Nutzertests, oder ein Verweis auf Studien zu Design-Konsistenz und Nutzerwahrnehmung. Die Vor/Nachher-Beispiele im README sind Texte über Design, nicht Design selbst. Für eine didaktische Nutzung wäre ein Screenshot-Paar — generisches Dashboard vs. system.md-gesteuertes Dashboard — erheblich überzeugender als Pixelwert-Listen.

## Wartung und Kontext

Version `v2026.2.8` wurde im Februar 2026 veröffentlicht und hat die SKILL.md vollständig selbsttragend gemacht (alle Referenzinhalte inline statt in externen Dateien). Das ist ein technisch sauberer Schritt: Der Skill funktioniert jetzt ohne Abhängigkeit von einer Verzeichnisstruktur, die der Nutzer vielleicht nicht kennt.

Die MIT-Lizenz ist vorhanden. Die eigene Domain ist gepflegt. Oyindamola Akinleye ist als Einzelperson aktiv, ohne erkennbares Team dahinter. Issue #13 (Plugin-Commands laden nicht im Claude-Code-Menü) war zum Zeitpunkt dieser Evaluation noch offen — ein gängiges Integrationsproblem im Plugin-Ökosystem, das nicht spezifisch auf Skill-Qualität hinweist.

## Empfehlung für den Unterrichtseinsatz

`interface-design` eignet sich gut als Lehrobjekt für zwei verschiedene Diskussionen.

**Erste Diskussion — Was ein guter Workflow-Skill leisten kann:** Die Intent-First-Methodik und die vier Craft-Checks bieten echtes didaktisches Material. Studierende können den Squint-Test, den Swap-Test und den Token-Test an eigenen Outputs anwenden — unabhängig davon, ob sie den Skill installieren. Das Prinzip "Defaults benennen bevor sie passieren" ist übertragbar auf jeden Designprozess.

**Zweite Diskussion — Wie technische Mechanismen kommuniziert werden:** Das Memory-Framing ist ein Paradebeispiel dafür, wie eine einfache Dateioperationen als kognitive Fähigkeit vermarktet wird. Lehrende können diesen Skill nutzen um zu zeigen: Der Mechanismus ist korrekt und nützlich. Die Beschreibung des Mechanismus ist irreführend. Beides kann gleichzeitig wahr sein.

Für den Einsatz im Studio-Kontext gilt: Der Skill funktioniert gut, wenn die Studierenden verstehen, dass die `system.md`-Datei das eigentliche Werkzeug ist — nicht ein lernfähiges System. Wer das versteht, kann den Skill produktiv einsetzen. Wer es nicht versteht, wird frustriert sein, wenn das "Gedächtnis" beim nächsten Rechner fehlt.

Urteil: **Vertrauen** — mit klarem Unterricht darüber, was hinter dem Memory-Versprechen steckt.
