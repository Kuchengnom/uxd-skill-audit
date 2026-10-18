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
  methodische_fundierung_note: "Das Format stammt aus einer echten, verlinkten Spezifikation (Google Stitch DESIGN.md) und wird korrekt umgesetzt. Wie die 73 Dateien aus den Websites extrahiert wurden, dokumentiert das Projekt nirgends."
  transparenz: 4
  transparenz_note: "Jede Datei enthält eine eigene 'Known Gaps'-Sektion. Sie benennt Lizenzgrenzen bei Schriften, fehlende Animationsdaten und die Trennung von Marketing- und Produktoberfläche. Verschwiegen bleibt allein die Barrierefreiheit."
  validierbarkeit: 4
  validierbarkeit_note: "Zu jeder Datei liefert das Projekt preview.html und preview-dark.html. Die Referenz ist eine öffentlich zugängliche Website. Nachprüfbarer geht es kaum. Automatisierte Tests fehlen aber."
  wartbarkeit: 3
  wartbarkeit_note: "Firma als Träger, MIT-Lizenz und laufende Commits sprechen für das Projekt. Dagegen stehen 300 offene Issues und inhaltliche Fehlermeldungen, die seit zwei Monaten unbeantwortet sind. Der Issue-Tracker ist gesperrt. Das README fordert trotzdem zum Issue-Öffnen auf."

tags:
  - design-md
  - google-stitch
  - design-tokens
  - barrierefreiheit
  - deskriptiv-normativ
  - skill-evaluation
---

`VoltAgent/awesome-design-md` hat 103.000 Sterne und 11.800 Forks. Es ist das mit Abstand größte Projekt, das diese Serie bisher untersucht hat. Es ist größer als alle bislang evaluierten Skills zusammen. Zugleich liefert es als erstes keinen Skill im engeren Sinne. Es liefert ein Dateiformat. Es sind 73 DESIGN.md-Dateien. Jede beschreibt die visuelle Sprache einer real existierenden Website. Dazu zählen Stripe, Linear, Notion, Apple, Ferrari, Nike und Vodafone. Eine Samstagsreihe rekonstruiert Dell aus 1996 und Nintendo.com aus 2001. Die Nutzung ist trivial. Man kopiert die Datei ins Projektverzeichnis und sagt dem Agenten "baue mir eine Seite, die so aussieht". Fertig.

Das Format ist keine Erfindung des Projekts. DESIGN.md ist eine offene Spezifikation von Google Stitch. Sie definiert neun Abschnitte, von "Visual Theme & Atmosphere" über Farbrollen, Typografie und Komponenten bis zu "Do's and Don'ts" und einem Agent-Prompt-Guide. Das README verlinkt die Spezifikation. Die Abschnittsstruktur der Dateien folgt ihr nachvollziehbar. Eigene Erweiterungen kennzeichnet das Projekt als solche. Für diese Serie ist das ungewohnt. Die Quelle muss man hier nicht suchen. Sie steht in der zweiten Zeile.

## Was in einer Datei tatsächlich steht

Ich habe die Claude-Datei vollständig gelesen. Sie ist die einzige im Bestand, deren Vorlage ich gegen die Beschreibung prüfen kann. Die Datei enthält 25 benannte Farbtoken mit Hex-Wert und Funktionszuweisung. Dazu kommen eine vierzehnstufige Typografietabelle mit Größe, Gewicht, Zeilenhöhe und Laufweite sowie 29 Komponentendefinitionen inklusive Zuständen. Die Spacing-Skala hat eine 4px-Basiseinheit. Breakpoints kommen mit konkreten Umbruchregeln. Durchgehend stehen Token-Referenzen statt Inline-Hexwerten, etwa `{colors.primary}` und `{typography.display-xl}`. Das ist handwerklich deutlich sorgfältiger als vieles, was in dieser Serie unter dem Etikett "Design-Intelligenz" schon durchgegangen ist.

Bemerkenswert ist der Abschnitt "Known Gaps" am Ende jeder Datei. Er hält ausdrücklich fest, dass Copernicus und StyreneB lizenzierte Anthropic-Schriften sind. Als Webfonts sind sie nicht verfügbar. Animations- und Übergangszeiten wurden nicht erfasst. Formularfehlerzustände fehlen. Ohne Anmeldeprozess waren sie nicht beobachtbar. Der wichtigste Satz des ganzen Dokuments kommt danach. Die tatsächliche Produktoberfläche von claude.ai ist ausdrücklich *nicht* Gegenstand. Beschrieben ist nur die Marketing-Oberfläche. Wer eine Chat-Anwendung baut und die Claude-DESIGN.md einsetzt, erhält also die Formensprache einer Landingpage. Eine Produktsprache erhält er nicht. Dass das Projekt diesen Unterschied selbst benennt, ist die stärkste Einzelleistung im Bestand. Die Dateien tragen im Kopf zudem ein `version: alpha`.

## Der Bruch: aus Beobachtung wird Anweisung

Die Sektion "Do's and Don'ts" ist der Ort, an dem das Format seine eigene Natur überschreibt. Dort steht nicht "die Website verwendet Cremeweiß". Dort steht: "Verwende niemals kühle Grautöne oder reines Weiß. Creme ist die Marke." Dort steht nicht "Displaygrößen erscheinen in Gewicht 400". Dort steht: "Negative Laufweite bei Displaygrößen ist nicht verhandelbar." Der Iteration Guide verschärft weiter: "Die Trennung ist unaufbrechbar." Das ist die Grammatik eines internen Markenhandbuchs. Geschrieben hat sie niemand, der über die Marke entscheiden darf. Eine Beobachtung ("so sieht claude.com aus") wird zur Regel ("so muss es sein"). Ob die beobachtete Entscheidung gut ist, fragt niemand.

Genau hier wird es überprüfbar. Ich habe die dokumentierten Farbpaare durchgerechnet:

| Paar | Kontrast | WCAG AA (Text) |
| --- | --- | --- |
| `on-primary` #ffffff auf `primary` #cc785c, Label des Primärbuttons, 14px | 3,28 : 1 | durchgefallen |
| `primary` #cc785c auf `canvas` #faf9f5, Textlink in Body-Größe | 3,11 : 1 | durchgefallen |
| `muted-soft` #8e8b82 auf `canvas`, Bildunterschriften und Kleingedrucktes | 3,23 : 1 | durchgefallen |
| `accent-amber` #e8a55a auf `canvas`, Kategorie-Badges | 2,00 : 1 | durchgefallen |
| `ink` #141413 auf `canvas`, Überschriften und Fließtext | 17,50 : 1 | bestanden |

Das Fundament der Datei ist tragfähig. Fließtext und Überschriften liegen weit über der Anforderung. Die Beschriftung des Primärbuttons, die Textlinkfarbe und alle Badge-Töne verfehlen dagegen die 4,5:1 für Text in Standardgröße. Das ist keine Nachlässigkeit von VoltAgent. Es ist die getreue Abbildung einer real existierenden Website. Damit funktioniert die Extraktion genau wie versprochen. Das Problem entsteht erst durch die Umetikettierung. Die Werte stehen dann in einer Tabelle mit Rollenzuweisungen und einem "nicht verhandelbar" daneben. Ein Agent und eine Studentin sehen ein geprüftes System. Tatsächlich ist es eine Momentaufnahme.

<div class="callout">
<div class="callout__title">Extraktion vererbt Mängel und tarnt sie als System</div>
Dem Projekt ist die ungeprüfte Barrierefreiheit nicht entgangen. Es geht damit nur selektiv um. Der Abschnitt "Touch Targets" der Claude-Datei notiert zum runden Icon-Button ausdrücklich: "genau 36 × 36 — leicht unter WCAG 44, aber visuell zentriert." Die Norm ist also bekannt und wird zitiert. Als Defekt markiert die Datei die Abweichung trotzdem nicht. Sie reicht sie mit einer ästhetischen Begründung weiter. Bei den Kontrastwerten fehlt jeder Hinweis. Ein Format, das WCAG in einem Absatz zitiert und in fünf Farbtoken ignoriert, ist nicht barrierefreiheitsunkundig. Es ist barrierefreiheitsselektiv. Für den Unterricht ist das der zentrale Befund. Eine Extraktion erbt die Fehler ihrer Quelle. Deren Kontext erbt sie nicht. Anthropic hat diese Werte in Kenntnis der eigenen Gestaltungsprioritäten gewählt. Wer sie kopiert, übernimmt die Entscheidung ohne die Entscheidungsgrundlage. Zurück bleibt der Kontext.
</div>

## Wie die Dateien entstanden sind, sagt niemand

Die zweite Lücke betrifft die Methode. Das Projekt beschreibt seine Dateien als "aus öffentlich sichtbaren CSS-Werten extrahiert". Es liefert aber kein Skript, keinen Extraktionszeitpunkt, keine Herkunftsangabe pro Datei und keinen Prüfschritt. Ein Teil des Inhalts kann so gar nicht entstanden sein. Rollenzuweisungen wie "wird sparsam auf sekundären Produktoberflächen verwendet" sind Interpretation. Wertungen wie "Markenspannung entsteht aus der Creme-Koralle-Paarung" sind es auch. Das gilt ebenso für die Empfehlung von Cormorant Garamond als nächstliegender Open-Source-Ersatz. Ausgelesen wurde das alles nicht. Ein Satz in den Known Gaps verrät die Arbeitsweise: "Der statische Screenshot erfasst die Animations-Chrome nicht vollständig." Gearbeitet wurde also offenbar mit Screenshots und Modellanalyse. Das ist legitim. Es ist aber eine andere Tätigkeit als CSS auslesen. Die Differenz spricht das Projekt nicht aus. Dazu kommt das Verfallsdatum. Websites werden umgebaut. Ohne Stand-Datum lässt sich bei keiner der 73 Dateien feststellen, ob sie noch die Realität beschreibt. Ein Stand-Datum fehlt bei allen.

## Träger, Anreize, Rückstau

Hinter dem Projekt steht keine Einzelperson. Träger ist VoltAgent, ein Anbieter eines TypeScript-Agent-Frameworks. Ressourcen und eine MIT-Lizenz folgen daraus. Es bedeutet auch ein Geschäftsmodell. Das README führt zu `getdesign.md`. Dort werden DESIGN.md-Dateien "auf Anfrage, auch privat und exklusiv" angeboten. Sponsoring-Banner und ein eigenes Produkt kommen hinzu. Die Sammlungsliste im README verlinkt inzwischen nicht mehr auf die Dateien im Repository. Sie verlinkt auf die eigene Domain. Das Repository ist damit auch ein Akquisekanal. Man sollte diesen Umstand kennen, wenn man fragt, wem die Weiterentwicklung gehört. Ein Vorwurf ist es nicht.

Der Rückstau ist sichtbar. 300 offene Issues liegen im Tracker, überwiegend Wunschanfragen für weitere Marken. Dazwischen stehen unbearbeitete inhaltliche Fehlermeldungen. Eine fehlende Dark-Mode-Sektion in der Figma-Datei ist seit dem 10. Juli offen. Ein Ordnernamenskonflikt unter macOS ist es seit dem 22. Juni. Wie schon bei `Trystan-SA/claude-design-system-prompt` im letzten Monat findet sich eine Kombination, die man bei Repositories dieser Größe offenbar routinemäßig prüfen muss. Das README bittet darum, vor jedem Pull Request "zuerst ein Issue zu öffnen". Der Tracker meldet "Issue creation is restricted in this repository". Vier Contributors betreuen 73 Dateien und über 11.000 Forks.

Offen bleibt eine Frage, die das Projekt selbst nicht stellt. Was es bedeutet, die visuelle Identität von Nike, Ferrari oder Mastercard als kopierbare Datei bereitzustellen, klärt niemand. Die Lizenz erklärt, man beanspruche kein Eigentum an fremden Identitäten. Das trifft zu. Die eigentliche Frage berührt es nicht. Der beworbene Anwendungsfall ist ja gerade, dass das Ergebnis aussieht wie die Vorlage. Ich bin keine Juristin und kein Jurist. Die Antwort hängt von Jurisdiktion und Einzelfall ab. Studierende sollten aber wissen, dass "MIT-lizenziert" sich auf die Beschreibung bezieht. Das Beschriebene ist nicht gemeint.

## Empfehlung für den Unterrichtseinsatz

Dieses Projekt gehört in den Unterricht. Es taugt als Lesestoff und nicht als Werkzeug. Es ist das beste verfügbare Beispiel für den Unterschied zwischen deskriptiv und normativ. Dieser Unterschied ist an einer einzigen Datei in einer Doppelstunde zeigbar. Eine belastbare Übung sieht so aus. Studierende lassen einen Agenten mit der Claude-DESIGN.md eine Seite bauen. Sie prüfen das Ergebnis mit einem Kontrast-Checker. Dann formulieren sie die "Do's and Don'ts" von Markenkonformitätsregeln in Gestaltungsqualitätsregeln um. Wo sie sich widersprechen, liegt der Lernstoff.

Für die eigene Praxis gilt eine engere Empfehlung. Als Startpunkt für ein Tokenschema ist die Sammlung wertvoll. Das gilt auch als Vokabeltraining für die Beschreibung visueller Systeme und als Vorlage für ein eigenes, selbst verantwortetes DESIGN.md. Die neun Abschnitte sind eine brauchbare Struktur. Die Known-Gaps-Sektion ist ein Muster, das man übernehmen sollte. Als Fertigteil für ein Produkt taugt die Sammlung nicht. Man importiert die Oberflächensprache einer Marketingseite fremder Marken. Die Barrierefreiheit bleibt ungeprüft, ein Stand-Datum fehlt und die Herkunft ist undokumentiert. Wer sie einsetzt, sollte drei Dinge selbst tun, die die Datei nicht tut. Kontraste nachrechnen. Markenmerkmale durch eigene ersetzen. Ein Datum daruntersetzen.
