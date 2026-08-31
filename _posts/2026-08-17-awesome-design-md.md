---
layout: post
title: "awesome-design-md: 103.000 Sterne für eine Beschreibung, die sich wie eine Vorschrift liest"
date: 2026-08-17
category: Skill-Evaluation
skill_reviewed: "VoltAgent/awesome-design-md"
verdict: vertrauen
reading_time: 9
last_audited: "17. August 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "Das Format stammt aus einer echten, verlinkten Spezifikation (Google Stitch DESIGN.md) und wird korrekt umgesetzt, aber wie die 73 Dateien aus den Websites extrahiert wurden, dokumentiert das Projekt nirgends."
  transparenz: 4
  transparenz_note: "Jede Datei enthält eine eigene 'Known Gaps'-Sektion, die Lizenzgrenzen bei Schriften, fehlende Animationsdaten und die Trennung von Marketing- und Produktoberfläche benennt — verschwiegen bleibt allein die Barrierefreiheit."
  validierbarkeit: 4
  validierbarkeit_note: "Zu jeder Datei liefert das Projekt preview.html und preview-dark.html, und die Referenz ist eine öffentlich zugängliche Website — nachprüfbarer geht es kaum, auch wenn automatisierte Tests fehlen."
  wartbarkeit: 3
  wartbarkeit_note: "Firma als Träger, MIT-Lizenz und laufende Commits, aber 300 offene Issues, inhaltliche Fehlermeldungen seit zwei Monaten unbeantwortet und ein gesperrter Issue-Tracker, obwohl das README zum Issue-Öffnen auffordert."

tags:
  - design-md
  - google-stitch
  - design-tokens
  - barrierefreiheit
  - deskriptiv-normativ
  - skill-evaluation
---

Mit 103.000 Sternen und 11.800 Forks ist `VoltAgent/awesome-design-md` das mit Abstand größte Projekt, das in dieser Serie bisher untersucht wurde, größer als alle bislang evaluierten Skills zusammen. Es ist auch das erste, das keinen Skill im engeren Sinne liefert, sondern ein Dateiformat: 73 DESIGN.md-Dateien, jede eine Beschreibung der visuellen Sprache einer real existierenden Website. Stripe, Linear, Notion, Apple, Ferrari, Nike, Vodafone, dazu eine Samstagsreihe mit Rekonstruktionen von Dell aus 1996 und Nintendo.com aus 2001. Die Nutzung ist trivial: Datei ins Projektverzeichnis kopieren, dem Agenten sagen "baue mir eine Seite, die so aussieht", fertig.

Das Format selbst ist keine Erfindung des Projekts. DESIGN.md ist eine offene Spezifikation von Google Stitch mit neun definierten Abschnitten von "Visual Theme & Atmosphere" über Farbrollen, Typografie und Komponenten bis zu "Do's and Don'ts" und einem Agent-Prompt-Guide. Die Spezifikation ist im README verlinkt, die Abschnittsstruktur der Dateien folgt ihr nachvollziehbar, und das Projekt kennzeichnet seine eigenen Erweiterungen als solche. Für diese Serie ist das ungewohnt: Hier muss man die Quelle nicht suchen, sie steht in der zweiten Zeile.

## Was in einer Datei tatsächlich steht

Ich habe die Claude-Datei vollständig gelesen, weil sie die einzige im Bestand ist, deren Vorlage ich gegen die Beschreibung prüfen kann. Sie enthält 25 benannte Farbtoken mit Hex-Wert und Funktionszuweisung, eine vierzehnstufige Typografietabelle mit Größe, Gewicht, Zeilenhöhe und Laufweite, 29 Komponentendefinitionen inklusive Zuständen, eine Spacing-Skala mit 4px-Basiseinheit, Breakpoints mit konkreten Umbruchregeln, dazu durchgehende Token-Referenzen statt Inline-Hexwerten wie `{colors.primary}`, `{typography.display-xl}`). Das ist handwerklich deutlich sorgfältiger als das, was in dieser Serie unter dem Etikett "Design-Intelligenz" schon durchgegangen ist.

Bemerkenswert ist der Abschnitt "Known Gaps" am Ende jeder Datei. Dort steht ausdrücklich, dass Copernicus und StyreneB lizenzierte Anthropic-Schriften sind und nicht als Webfonts verfügbar; dass Animations- und Übergangszeiten nicht erfasst wurden; dass Formularfehlerzustände fehlen, weil sie ohne Anmeldeprozess nicht beobachtbar waren. Und, das ist der wichtigste Satz des ganzen Dokuments, dass die tatsächliche Produktoberfläche von claude.ai ausdrücklich *nicht* Gegenstand des Dokuments ist, sondern nur die Marketing-Oberfläche. Wer eine Chat-Anwendung baut und die Claude-DESIGN.md einsetzt, erhält also die Formensprache einer Landingpage, nicht die eines Produkts. Dass das Projekt diesen Unterschied selbst benennt, statt ihn zu verwischen, ist die stärkste Einzelleistung im Bestand. Die Dateien tragen im Kopf zudem ein `version: alpha`.

## Der Bruch: aus Beobachtung wird Anweisung

Die Sektion "Do's and Don'ts" ist der Ort, an dem das Format seine eigene Natur überschreibt. Dort steht nicht "die Website verwendet Cremeweiß", sondern: "Verwende niemals kühle Grautöne oder reines Weiß. Creme ist die Marke." Nicht "Displaygrößen erscheinen in Gewicht 400", sondern: "Negative Laufweite bei Displaygrößen ist nicht verhandelbar." Der Iteration Guide verschärft weiter: "Die Trennung ist unaufbrechbar." Das ist die Grammatik eines internen Markenhandbuchs, nur dass niemand sie geschrieben hat, der über die Marke entscheiden darf. Eine Beobachtung ("so sieht claude.com aus") wird zur Regel ("so muss es sein"), ohne dass irgendwo die Frage gestellt wird, ob die beobachtete Entscheidung gut ist.

Genau hier wird es überprüfbar. Ich habe die dokumentierten Farbpaare durchgerechnet:

| Paar | Kontrast | WCAG AA (Text) |
| --- | --- | --- |
| `on-primary` #ffffff auf `primary` #cc785c, Label des Primärbuttons, 14px | 3,28 : 1 | durchgefallen |
| `primary` #cc785c auf `canvas` #faf9f5 — Textlink in Body-Größe | 3,11 : 1 | durchgefallen |
| `muted-soft` #8e8b82 auf `canvas` — Bildunterschriften, Kleingedrucktes | 3,23 : 1 | durchgefallen |
| `accent-amber` #e8a55a auf `canvas` — Kategorie-Badges | 2,00 : 1 | durchgefallen |
| `ink` #141413 auf `canvas` — Überschriften und Fließtext | 17,50 : 1 | bestanden |

Das Fundament der Datei ist tragfähig: Fließtext und Überschriften liegen weit über der Anforderung. Aber die Beschriftung des Primärbuttons, die Textlinkfarbe und alle Badge-Töne verfehlen die 4,5:1 für Text in Standardgröße. Das ist keine Nachlässigkeit von VoltAgent, sondern die getreue Abbildung einer real existierenden Website. Die Extraktion funktioniert also genau wie versprochen. Das Problem entsteht erst durch die Umetikettierung: Sobald diese Werte in einer Tabelle mit Rollenzuweisungen und einem "nicht verhandelbar" daneben stehen, sehen ein Agent und eine Studentin ein geprüftes System, wo eine Momentaufnahme vorliegt.

<div class="callout">
<div class="callout__title">Extraktion vererbt Mängel und tarnt sie als System</div>
Dass die Barrierefreiheit ungeprüft bleibt, ist dem Projekt nicht entgangen. Es geht damit nur selektiv um. Der Abschnitt "Touch Targets" der Claude-Datei notiert zum runden Icon-Button ausdrücklich: "genau 36 × 36 — leicht unter WCAG 44, aber visuell zentriert." Die Norm ist also bekannt und wird zitiert. Die Abweichung wird dennoch nicht als Defekt markiert, sondern mit einer ästhetischen Begründung weitergegeben. Bei den Kontrastwerten fehlt jeder Hinweis. Ein Format, das WCAG in einem Absatz zitiert und in fünf Farbtoken ignoriert, ist nicht barrierefreiheitsunkundig, sondern barrierefreiheitsselektiv. Für den Unterricht ist das der zentrale Befund: Eine Extraktion erbt die Fehler ihrer Quelle, aber sie erbt nicht deren Kontext. Anthropic hat diese Werte in Kenntnis der eigenen Gestaltungsprioritäten gewählt. Wer sie kopiert, übernimmt die Entscheidung ohne die Entscheidungsgrundlage.
</div>

## Wie die Dateien entstanden sind, sagt niemand

Die zweite Lücke betrifft die Methode. Das Projekt beschreibt seine Dateien als "aus öffentlich sichtbaren CSS-Werten extrahiert", liefert aber kein Skript, keinen Extraktionszeitpunkt, keine Herkunftsangabe pro Datei und keinen Prüfschritt. Und ein Teil des Inhalts kann so gar nicht entstanden sein: Rollenzuweisungen wie "wird sparsam auf sekundären Produktoberflächen verwendet", Wertungen wie "Markenspannung entsteht aus der Creme-Koralle-Paarung" oder die Empfehlung von Cormorant Garamond als nächstliegender Open-Source-Ersatz sind Interpretation, nicht Auslesung. Ein Satz in den Known Gaps verrät die Arbeitsweise: "Der statische Screenshot erfasst die Animations-Chrome nicht vollständig." Gearbeitet wurde also offenbar mit Screenshots und Modellanalyse. Das ist legitim, aber es ist eine andere Tätigkeit als CSS auslesen, und die Differenz wird nicht ausgesprochen. Dazu kommt das Verfallsdatum: Websites werden umgebaut. Ohne Stand-Datum ist bei keiner der 73 Dateien feststellbar, ob sie noch die Realität beschreibt.

## Träger, Anreize, Rückstau

Hinter dem Projekt steht keine Einzelperson, sondern VoltAgent, ein Anbieter eines TypeScript-Agent-Frameworks. Das bedeutet Ressourcen und eine MIT-Lizenz, aber auch ein Geschäftsmodell: Das README führt zu `getdesign.md`, wo DESIGN.md-Dateien "auf Anfrage, auch privat und exklusiv" angeboten werden, dazu Sponsoring-Banner und ein eigenes Produkt. Die Sammlungsliste im README verlinkt inzwischen nicht mehr auf die Dateien im Repository, sondern auf die eigene Domain. Das Repository ist damit auch ein Akquisekanal. Kein Vorwurf, aber ein Umstand, den man bei der Frage "wem gehört die Weiterentwicklung?" kennen sollte.

Der Rückstau ist sichtbar: 300 offene Issues, überwiegend Wunschanfragen für weitere Marken, dazwischen unbearbeitete inhaltliche Fehlermeldungen: eine fehlende Dark-Mode-Sektion in der Figma-Datei seit dem 10. Juli, ein Ordnernamenskonflikt unter macOS seit dem 22. Juni. Und wie schon bei `Trystan-SA/claude-design-system-prompt` im letzten Monat findet sich die Kombination, die man bei Repositories dieser Größe offenbar routinemäßig prüfen muss: Das README bittet darum, vor jedem Pull Request "zuerst ein Issue zu öffnen", während der Tracker meldet "Issue creation is restricted in this repository". Vier Contributors betreuen 73 Dateien und über 11.000 Forks.

Bleibt die Frage, die das Projekt selbst nicht stellt: Was bedeutet es, die visuelle Identität von Nike, Ferrari oder Mastercard als kopierbare Datei bereitzustellen? Die Lizenz erklärt, man beanspruche kein Eigentum an fremden Identitäten. Das trifft zu und berührt die eigentliche Frage nicht, denn der beworbene Anwendungsfall ist ja gerade, dass das Ergebnis aussieht wie die Vorlage. Ich bin keine Juristin und kein Jurist, und die Antwort hängt von Jurisdiktion und Einzelfall ab. Aber Studierende sollten wissen, dass "MIT-lizenziert" sich auf die Beschreibung bezieht, nicht auf das Beschriebene.

## Empfehlung für den Unterrichtseinsatz

Dieses Projekt gehört in den Unterricht — als Lesestoff, nicht als Werkzeug. Es ist das beste verfügbare Beispiel für den Unterschied zwischen deskriptiv und normativ, und dieser Unterschied ist an einer einzigen Datei in einer Doppelstunde zeigbar. Eine belastbare Übung: Studierende lassen einen Agenten mit der Claude-DESIGN.md eine Seite bauen, prüfen das Ergebnis anschließend mit einem Kontrast-Checker und formulieren die "Do's and Don'ts" von Markenkonformitätsregeln in Gestaltungsqualitätsregeln um. Wo sie sich widersprechen, liegt der Lernstoff.

Für die eigene Praxis gilt eine engere Empfehlung. Als Startpunkt für ein Tokenschema, als Vokabeltraining für die Beschreibung visueller Systeme und als Vorlage für ein eigenes, selbst verantwortetes DESIGN.md ist die Sammlung wertvoll. Die neun Abschnitte sind eine brauchbare Struktur, und die Known-Gaps-Sektion ist ein Muster, das man übernehmen sollte. Als Fertigteil für ein Produkt ist sie es nicht: Man importiert die Oberflächensprache einer Marketingseite fremder Marken, ungeprüft in der Barrierefreiheit, ohne Stand-Datum, ohne dokumentierte Herkunft. Wer sie einsetzt, sollte drei Dinge selbst tun, die die Datei nicht tut: Kontraste nachrechnen, Markenmerkmale durch eigene ersetzen und ein Datum daruntersetzen.
