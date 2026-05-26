---
layout: post
title: "design-mastery-claude-code: Saul Bass als Methode — was Autorität durch Assoziation kann und nicht kann"
date: 2026-05-25
category: Skill-Evaluation
skill_reviewed: "HermeticOrmus/design-mastery-claude-code"
verdict: vorsicht
reading_time: 9
last_audited: "25. Mai 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "Zitate und Designer-Auswahl sind legitim; die operativen 'Apply His Lesson'-Workflows sind jedoch kreative Extrapolationen des Autors, keine dokumentierte Methodik der Designer selbst."
  transparenz: 2
  transparenz_note: "Keine Kommunikation der epistemischen Grundgrenze: Ein LLM kann Beschreibungen historischer Designphilosophien abrufen, aber keine visuelle Urteilskraft replizieren."
  validierbarkeit: 2
  validierbarkeit_note: "Versprochene Referenzdateien existieren, ihr Inhalt ist ungeprüft; keine Before/After-Outputs, keine Vergleiche mit fachkundiger menschlicher Anwendung der Prinzipien."
  wartbarkeit: 3
  wartbarkeit_note: "Autor identifizierbar (Diego Bodart, ormus.solutions), MIT-Lizenz vorhanden, nur 2 Commits, 2 GitHub-Stars, null externe Beiträge — strukturell fragile Einzelperson-Pflege."

tags:
  - autorschaft
  - historiographie
  - epistemologie
  - name-dropping
  - prompt-engineering
  - designgeschichte
  - lehrbeispiel
---

`HermeticOrmus/design-mastery-claude-code` ist das letzte Repository in unserer Evaluation der HermeticOrmus-Projekte — und das konzeptuell interessanteste. Wo `LibreUIUX-Claude-Code` durch schiere Masse auffiel, stellt dieses Repository eine substanziellere Frage: Kann man die visuelle Intelligenz historischer Designmeister als Prompt operationalisieren? Und was bedeutet es für ein Sprachmodell, „von Saul Bass zu lernen"?

Das Repository ist klein und fokussiert: drei Agenten, drei Commands, vier Skills. Die Auswahl der behandelten Designer — Saul Bass, Massimo Vignelli, Dieter Rams, Paula Scher, Josef Müller-Brockmann, David Carson, Paul Rand — ist kanonisch und vertretbar. Die Zitate sind überwiegend authentisch. Und dennoch enthält der Ansatz eine epistemische Lücke, die im Unterricht sorgfältig diskutiert werden sollte.

## Was das Repository enthält

Der Kern des Projekts ist der `design-masters`-Skill. Für jeden der sieben Designer liefert er: eine Kurzbiografie, zentrale Zitate, Signatur-Techniken, ausgewählte Werke und — das ist der kritische Teil — einen „Apply His/Her Lesson"-Abschnitt, der eine schrittweise Arbeitsanleitung formuliert.

Für Saul Bass lautet diese Anleitung:

> 1. Identify the core concept  
> 2. Find a visual metaphor  
> 3. Reduce to essential geometry  
> 4. Test if meaning survives reduction  
> 5. Add nothing more

Für Dieter Rams gibt es den „Rams Test" — drei Fragen, die man an jedes Designelement stellen soll, bevor man es beibehält. Für Massimo Vignelli eine Übung mit zwei Schriftarten, drei Farben und vier Abstandswerten.

Die Struktur ist pädagogisch nachvollziehbar. Wer Studierenden oder Entwicklern ohne Designhintergrund einen Einstieg in die Gedankenwelt kanonischer Designerinnen und Designer geben will, findet hier eine kompakte, gut lesbare Zusammenstellung.

## Was an den Quellen stimmt — und was extrapoliert ist

Bevor man den Skill inhaltlich bewertet, lohnt ein Blick auf die Trennlinie zwischen Dokumentation und Interpretation.

Die Kurzformel von Saul Bass — „Symbolize and summarize" — ist historisch gut belegt. Sie findet sich in Archivmaterialien des Rochester Institute of Technology und ist in der AIGA-Dokumentation zitiert. Das Zitat „Design is thinking made visual", das dem Skill als Leitmotiv dient, wird Bass zugeschrieben und erscheint in mehreren Designarchiven — seine genaue Herkunft ist in der Fachliteratur jedoch gelegentlich umstritten.

Dieter Rams' zehn Prinzipien sind aus seiner Arbeit für Braun ab Ende der 1970er-Jahre dokumentiert und vollständig verifizierbar; der Skill gibt sie korrekt wieder.

Der Vignelli Canon bezieht sich auf Massimo Vignellis kostenlos verfügbares gleichnamiges Dokument (2007 / 2010). Die zwölf Punkte im Skill — „Semantics, Syntactics, Pragmatics, Discipline, Appropriateness..." — entsprechen aber nicht direkt dem Aufbau des Canon-Dokuments. Sie sind eine freie Destillation, keine direkte Portierung.

Das eigentliche Problem liegt bei den operativen Workflows. Saul Bass hat nie eine fünfschrittigen Algorithmus zur geometrischen Reduktion formuliert. Der Skill-Autor hat aus Bass' Philosophie eine Arbeitsanleitung destilliert — das ist eine legitime pädagogische Entscheidung, aber es ist eine Entscheidung des Autors, nicht von Bass. Dieser Unterschied wird im Skill nirgends markiert.

<div class="callout">
<div class="callout__title">Die zentrale epistemische Frage: Was lernt Claude von einem verstorbenen Grafiker?</div>
Ein Sprachmodell kann Beschreibungen von Saul Bass' Werk und Philosophie abrufen, zusammenfassen und in neue Kontexte übertragen — weil diese Beschreibungen in seinen Trainingsdaten enthalten sind. Was es nicht kann: die verkörperte visuelle Urteilskraft replizieren, die Bass nach jahrzehntelanger Praxis als Filmplakat-Gestalter entwickelt hatte. Der Skill formuliert als Ziel, Claude solle „Saul Bass's simplification principles" anwenden. Aber Vereinfachung war bei Bass kein Algorithmus — sie war das Ergebnis von visuellem Urteilsvermögen, das sich in einem spezifischen Medium (Siebdruck, Kinoformat, begrenztes Farbregister) über Jahrzehnte ausgebildet hatte. Diesen Unterschied kommuniziert der Skill nicht.
</div>

## Das Problem der verdeckten Autorschaft

Im Skill gibt es eine Eigenheit, die im Unterricht diskutiert werden sollte: Wenn der Autor eine Arbeitsanleitung formuliert und sie in einem Abschnitt namens „Apply His Lesson" unterbringt, entsteht beim Lesenden der Eindruck, diese Anleitung stamme von Bass selbst oder sei eng an dessen eigene Methodenbeschreibungen angelehnt.

Das ist Autorschaft durch Assoziation. Das Prinzip ist verbreitet — und nicht per se unehrlich. Pädagogische Aufbereitung bedeutet immer Interpretation. Das Problem entsteht, wenn die Grenze zwischen Dokument und Interpretation unsichtbar wird.

Ein gegenläufiges Beispiel: Vignellis „The Vignelli Canon" ist frei verfügbar. Wer ihn liest, liest Vignelli. Der `design-masters`-Skill ist eine Zusammenfassung einer Zusammenfassung von Vignellis Denken — ohne explizite Rückverlinkung auf das Originaldokument. Studierende, die dem Skill folgen, haben das Gefühl, eine Primärquelle konsultiert zu haben. Das Gegenteil ist der Fall.

## Was der Skill gut macht

Es wäre unfair, das Repository als bloßes Name-Dropping abzuwerten. Einige Entscheidungen sind durchdacht.

Die Warnungen bei David Carson sind ein Positivbeispiel: Der Skill markiert explizit, für welche Kontexte seine Anti-Design-Prinzipien geeignet sind (kreative Portfolios, Marketing, das Aufmerksamkeit braucht) und für welche nicht (Navigation, Rechtstexte, Marken mit Konformitätserfordernissen). Das ist eine der wenigen Stellen im Skill, an der Grenzen aktiv kommuniziert werden — und es zeigt, dass der Ansatz prinzipiell zu sinnvoller Transparenz fähig ist.

Die Vergleichstabelle am Ende des `design-masters`-Skills — wer ist für welchen Kontext am nützlichsten? — ist ebenfalls brauchbar. Sie gibt Nutzenden einen Einstiegspunkt in kontextualisierte Auswahl statt universeller Anwendung.

Die Auswahl der sieben Designer ist vertretbar: Bass, Vignelli, Rams, Scher, Müller-Brockmann, Carson, Rand decken unterschiedliche Epochen, Medien und Philosophien ab. Wer die Reihe im Unterricht durcharbeiten würde, hätte tatsächlich einen Überblick über wesentliche Strömungen des 20. Jahrhunderts in der visuellen Kommunikation.

## Wartbarkeit: Wieder dasselbe Muster

`design-mastery-claude-code` zeigt denselben Wartungskontext wie das LibreUIUX-Repository: Diego Bodart ist identifizierbar, die MIT-Lizenz ist vorhanden, der letzte Commit ist nicht älter als einige Monate. Aber mit zwei Commits, zwei GitHub-Stars, null Forks und null externen Beiträgen hat das Repository keine Community, die methodische Fehler korrigieren würde.

Das ist bei diesem spezifischen Repository ein weniger kritisches Problem als bei LibreUIUX — der Inhalt ist kompakter, die Fehleranfälligkeit geringer. Aber die strukturelle Fragilität bleibt: Was heute als „Saul Bass' Lesson" beschrieben ist, kann morgen inhaltlich falsch sein, ohne dass es jemand meldet.

## Empfehlung für den Unterrichtseinsatz

`design-mastery-claude-code` ist für den Designunterricht unter zwei verschiedenen Vorzeichen nutzbar.

Als Designgeschichts-Einstieg mit Vorbehalt ist der Skill tatsächlich verwendbar — wenn Lehrende explizit kommunizieren, dass die „Apply"-Abschnitte Autorenkonstruktionen sind, nicht dokumentierte Methodik der Designer selbst. Mit dieser Rahmung kann der Skill als Sprungbrett dienen, von dem aus Studierende in die Primärquellen einsteigen: Vignellis Canon, Rams' Braun-Designdokumentation, Bass' eigene Interviews und Werkanalysen.

Als Analysegegenstand ist das Repository wertvoller: Es illustriert präzise die Frage, die in der KI-gestützten Designpraxis nicht oft genug gestellt wird — was bedeutet es, wenn ein Werkzeug behauptet, Weisheit historischer Designerinnen und Designer zu vermitteln? Welche Autorschaft entsteht, wenn eine Anleitung im Namen einer verstorbenen Person formuliert wird? Und was genau kann ein Sprachmodell aus einer solchen Anleitung tatsächlich extrahieren?

Die ehrliche Antwort auf die letzte Frage: Konsistenz in der Beschreibungssprache, präzisere Terminologie, eine Struktur für Designentscheidungen. Was ein Sprachmodell nicht kann, ist das visuelle Urteilsvermögen, das Saul Bass brauchte, um zu wissen, wann eine Vereinfachung zu weit gegangen ist. Diesen Unterschied zu kennen, ist die eigentliche Designkompetenz — und der Skill, so nützlich er in Teilen ist, macht ihn unsichtbar.
