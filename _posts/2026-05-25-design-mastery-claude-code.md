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
  methodische_fundierung_note: "Zitate und Designer-Auswahl sind legitim. Die operativen 'Apply His Lesson'-Workflows sind jedoch kreative Extrapolationen des Autors und keine dokumentierte Methodik der Designer selbst."
  transparenz: 2
  transparenz_note: "Keine Kommunikation der epistemischen Grundgrenze: Ein LLM kann Beschreibungen historischer Designphilosophien abrufen, aber keine visuelle Urteilskraft replizieren."
  validierbarkeit: 2
  validierbarkeit_note: "Versprochene Referenzdateien existieren, ihr Inhalt ist ungeprüft. Es gibt keine Before/After-Outputs und keine Vergleiche mit fachkundiger menschlicher Anwendung der Prinzipien."
  wartbarkeit: 3
  wartbarkeit_note: "Autor identifizierbar (Diego Bodart, ormus.solutions), MIT-Lizenz vorhanden. Nur 2 Commits, 2 GitHub-Stars, null externe Beiträge. Die Pflege hängt strukturell an einer Einzelperson und ist fragil."

tags:
  - autorschaft
  - historiographie
  - epistemologie
  - name-dropping
  - prompt-engineering
  - designgeschichte
  - lehrbeispiel
---

`HermeticOrmus/design-mastery-claude-code` ist das letzte Repository der HermeticOrmus-Reihe. Es ist auch das konzeptuell interessanteste. `LibreUIUX-Claude-Code` fiel durch schiere Masse auf. Dieses Repository stellt eine substanziellere Frage. Es fragt, ob sich die visuelle Intelligenz historischer Designmeister als Prompt operationalisieren lässt. Es fragt auch, was es für ein Sprachmodell bedeutet, „von Saul Bass zu lernen".

Das Repository ist klein und fokussiert. Es enthält drei Agenten, drei Commands und vier Skills. Die Auswahl der Designer ist kanonisch und vertretbar. Sie umfasst Saul Bass, Massimo Vignelli, Dieter Rams, Paula Scher, Josef Müller-Brockmann, David Carson und Paul Rand. Auch die Zitate sind überwiegend authentisch. Der Ansatz enthält dennoch eine epistemische Lücke. Im Unterricht verdient sie eine sorgfältige Diskussion.

## Was das Repository enthält

Der Kern des Projekts ist der `design-masters`-Skill. Für jeden der sieben Designer liefert er eine Kurzbiografie, zentrale Zitate, Signatur-Techniken und ausgewählte Werke. Dazu kommt der kritische Teil. Ein „Apply His/Her Lesson"-Abschnitt formuliert eine schrittweise Arbeitsanleitung.

Für Saul Bass lautet diese Anleitung:

> 1. Identify the core concept  
> 2. Find a visual metaphor  
> 3. Reduce to essential geometry  
> 4. Test if meaning survives reduction  
> 5. Add nothing more

Für Dieter Rams gibt es den „Rams Test". Er stellt drei Fragen an jedes Designelement. Erst danach bleibt es erhalten. Für Massimo Vignelli gibt es eine Übung mit zwei Schriftarten, drei Farben und vier Abstandswerten.

Die Struktur ist pädagogisch nachvollziehbar. Studierende oder Entwickler ohne Designhintergrund finden hier einen Einstieg in die Gedankenwelt kanonischer Designerinnen und Designer. Kompakt und gut lesbar ist sie auch.

## Was an den Quellen stimmt, und was extrapoliert ist

Vor der inhaltlichen Bewertung lohnt ein Blick auf die Trennlinie zwischen Dokumentation und Interpretation.

Die Kurzformel von Saul Bass, „Symbolize and summarize", ist historisch gut belegt. Sie findet sich in Archivmaterialien des Rochester Institute of Technology. Auch die AIGA-Dokumentation zitiert sie. Das Zitat „Design is thinking made visual" dient dem Skill als Leitmotiv. Es wird Bass zugeschrieben und erscheint in mehreren Designarchiven. Seine genaue Herkunft ist in der Fachliteratur gelegentlich umstritten.

Dieter Rams' zehn Prinzipien sind aus seiner Arbeit für Braun ab Ende der 1970er-Jahre dokumentiert. Sie sind vollständig verifizierbar. Er gibt sie korrekt wieder.

Der Vignelli Canon bezieht sich auf Massimo Vignellis kostenlos verfügbares gleichnamiges Dokument von 2007 und 2010. Die zwölf Punkte im Skill entsprechen nicht direkt dem Aufbau des Canon-Dokuments. Dazu zählen „Semantics, Syntactics, Pragmatics, Discipline, Appropriateness" und weitere. Er bietet eine freie Destillation. Eine direkte Portierung ist er nicht.

Das eigentliche Problem liegt bei den operativen Workflows. Saul Bass hat nie einen fünfschrittigen Algorithmus zur geometrischen Reduktion formuliert. Bass' Philosophie hat der Skill-Autor zu einer Arbeitsanleitung destilliert. Pädagogisch ist das eine legitime Entscheidung. Es ist aber die Entscheidung des Autors und nicht die von Bass. Im Skill ist dieser Unterschied nirgends markiert.

<div class="callout">
<div class="callout__title">Was Claude von einem verstorbenen Grafiker lernt</div>
Ein Sprachmodell kann Beschreibungen von Saul Bass' Werk und Philosophie abrufen. Es kann sie zusammenfassen und in neue Kontexte übertragen. Diese Beschreibungen stecken in seinen Trainingsdaten. Die verkörperte visuelle Urteilskraft kann es nicht replizieren. Bass entwickelte sie nach jahrzehntelanger Praxis als Filmplakat-Gestalter. Als Ziel nennt der Skill, Claude solle „Saul Bass's simplification principles" anwenden. Vereinfachung war bei Bass jedoch kein Algorithmus. Sie war das Ergebnis von Urteilsvermögen. Dieses hatte sich über Jahrzehnte in Siebdruck, Kinoformat und begrenztem Farbregister ausgebildet. Der Skill kommuniziert diesen Unterschied nicht.
</div>

## Das Problem der verdeckten Autorschaft

Der Skill hat eine Eigenheit, die im Unterricht Diskussion verdient. Eine Arbeitsanleitung formuliert der Autor und bringt sie in einem Abschnitt namens „Apply His Lesson" unter. Beim Lesenden entsteht der Eindruck, die Anleitung stamme von Bass selbst. Oder sie lehne sich eng an dessen Methodenbeschreibungen an.

Das ist Autorschaft durch Assoziation. Verbreitet ist das Prinzip und nicht per se unehrlich. Pädagogische Aufbereitung bedeutet immer Interpretation. Zum Problem wird das erst bei unsichtbarer Grenze zwischen Dokument und Interpretation.

Ein Gegenbeispiel ist „The Vignelli Canon". Er ist frei verfügbar. Wer ihn liest, liest Vignelli. Der `design-masters`-Skill fasst eine Zusammenfassung von Vignellis Denken zusammen. Einen Link auf das Originaldokument gibt es nicht. Studierende, die dem Skill folgen, haben das Gefühl, eine Primärquelle konsultiert zu haben. Das Gegenteil ist der Fall.

## Was der Skill gut macht

Es wäre unfair, das Repository als bloßes Name-Dropping abzuwerten. Einige Entscheidungen sind durchdacht.

Die Warnungen bei David Carson sind ein Positivbeispiel. Explizit markiert der Skill die geeigneten Kontexte für seine Anti-Design-Prinzipien. Geeignet sind kreative Portfolios und Marketing mit Aufmerksamkeitsbedarf. Ungeeignet sind Navigation, Rechtstexte und Marken mit Konformitätserfordernissen. Hier kommuniziert der Skill Grenzen aktiv. Sonst gelingt ihm das selten. Prinzipiell ist der Ansatz also zu sinnvoller Transparenz fähig.

Die Vergleichstabelle am Ende des `design-masters`-Skills ordnet jedem Designer den Kontext zu, in dem er am nützlichsten ist. Auch sie ist brauchbar. Sie gibt Nutzenden einen Einstieg in kontextualisierte Auswahl statt universeller Anwendung.

Die Auswahl der sieben Designer ist vertretbar. Bass, Vignelli, Rams, Scher, Müller-Brockmann, Carson und Rand decken unterschiedliche Epochen, Medien und Philosophien ab. Wer die Reihe im Unterricht durcharbeitet, erhält tatsächlich einen Überblick. Er betrifft wesentliche Strömungen der visuellen Kommunikation im 20. Jahrhundert.

## Wartbarkeit: Wieder dasselbe Muster

`design-mastery-claude-code` zeigt denselben Wartungskontext wie das LibreUIUX-Repository. Diego Bodart ist identifizierbar. Eine MIT-Lizenz ist vorhanden. Älter als einige Monate ist der letzte Commit nicht. Es gibt aber nur zwei Commits, zwei GitHub-Stars, null Forks und null externe Beiträge. Eine Community, die methodische Fehler korrigieren würde, fehlt.

Bei diesem Repository ist das weniger kritisch als bei LibreUIUX. Der Inhalt ist kompakter und weniger fehleranfällig. Die strukturelle Fragilität bleibt. Was heute als „Saul Bass' Lesson" beschrieben ist, kann morgen inhaltlich falsch sein. Niemand würde es melden.

## Empfehlung für den Unterrichtseinsatz

`design-mastery-claude-code` ist für den Designunterricht unter zwei Vorzeichen nutzbar.

Als Designgeschichts-Einstieg mit Vorbehalt ist der Skill verwendbar. Lehrende müssen dazu explizit sagen, dass die „Apply"-Abschnitte Autorenkonstruktionen sind. Sie sind keine dokumentierte Methodik der Designer selbst. Mit dieser Rahmung dient der Skill als Sprungbrett. Von dort aus steigen Studierende in die Primärquellen ein. Dazu zählen Vignellis Canon, Rams' Braun-Designdokumentation sowie Bass' eigene Interviews und Werkanalysen.

Als Analysegegenstand ist das Repository wertvoller. Es illustriert eine Frage, die in der KI-gestützten Designpraxis zu selten gestellt wird. Sie lautet, was es bedeutet, wenn ein Werkzeug behauptet, die Weisheit historischer Designerinnen und Designer zu vermitteln. Eine zweite Frage betrifft die Autorschaft bei Anleitungen im Namen einer verstorbenen Person. Die dritte lautet, was ein Sprachmodell aus einer solchen Anleitung tatsächlich extrahieren kann.

Die ehrliche Antwort auf die letzte Frage ist knapp. Ein Sprachmodell gewinnt Konsistenz in der Beschreibungssprache, präzisere Terminologie und eine Struktur für Designentscheidungen. Visuelles Urteilsvermögen gewinnt es nicht. Bass brauchte es, um zu wissen, wann eine Vereinfachung zu weit gegangen ist. Diesen Unterschied zu kennen ist die eigentliche Designkompetenz. In Teilen ist der Skill nützlich. Diese Kompetenz macht er unsichtbar.
