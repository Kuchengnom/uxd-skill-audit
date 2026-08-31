---
layout: post
title: "ux-ui-mastery: Wenn 310.000 Wörter keinen einzigen Nutzer überzeugen"
date: 2026-06-15
category: Skill-Evaluation
skill_reviewed: "phazurlabs/ux-ui-mastery"
verdict: ablehnen
reading_time: 11
last_audited: "15. Juni 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "Quellen (Kahneman, Sweller, Nielsen, WCAG 2.2, arXiv) sind real und namentlich korrekt; die Portierungsqualität bleibt unprüfbar, weil der gesamte Inhalt von Claude Opus 4.6 generiert wurde."
  transparenz: 2
  transparenz_note: "Superlative ohne Einschränkungen ('definitive', 'most comprehensive ever built'); 'Powered by Claude Opus 4.6' steht im letzten Satz des README, nicht im Einleitungsparagraphen."
  validierbarkeit: 1
  validierbarkeit_note: "2 Stars, 4 Commits, 0 Issues, 0 Pull Requests seit dem initialen Upload — keine Community-Erprobung nachweisbar, keine Beispiel-Outputs, kein Testframework."
  wartbarkeit: 1
  wartbarkeit_note: "Anonyme Organisation 'Design Tribe Republic', keine Releases, keine Aktivität nach dem initialen Push; MIT-Lizenz vorhanden, aber ohne aktive Entwicklung praktisch wertlos."

tags:
  - quantität-vs-qualität
  - selbstreferenz
  - ki-generierter-inhalt
  - marketing-sprache
  - keine-community-adoption
  - ablehnen-beispiel
  - epistemisches-problem
  - phazurlabs
---

Manche Repositories lassen sich durch ihren README-Einstieg sofort einordnen. `phazurlabs/ux-ui-mastery` beginnt mit der Zeile: *"The most comprehensive UX/UI design intelligence ever built for an AI coding assistant."* Dieser Superlativ ist nicht die Überschrift eines Abschnitts, sondern die erste Prämisse des gesamten Projekts. Alles, was folgt, soll ihn belegen.

Was folgt, ist in der Tat beeindruckend groß: 19 Skills, 55 Referenzdateien, 10 Slash-Commands, 87 Dateien, 310.000 Wörter. Das sind Zahlen, die im Ökosystem der Claude-Design-Skills konkurrenzlos sind. Und genau deshalb lohnt es sich, diesen Skill genau anzusehen. Er treibt eine der grundlegendsten Fragen des gesamten Felds auf die Spitze: Ab wann ist mehr nicht mehr besser?

## Der Zählerstand zählt, nur nicht so wie das Projekt es meint

Der README-Text präsentiert Metriken wie ein Dashboard: 25+ Laws of UX, 50+ kognitive Biases, 40+ Produktionskomponenten, 18+ Fallstudien, 30+ haptische Muster. Jede Zahl ist größer als die der Konkurrenz. Das ist das implizite Argument: Umfang beweist Qualität.

Demgegenüber steht ein anderer Zählerstand, der nirgendwo im README steht: **2 Stars. 1 Fork. 4 Commits. 0 Issues. 0 Pull Requests. 0 Releases.**

Das Repository ist seit dem initialen Upload praktisch unverändert. Es gibt keine einzige öffentliche Diskussion, keinen Community-Post, keinen Verweis in den einschlägigen Aggregatoren wie awesome-claude-skills, claudeskills.info oder claudemarketplaces.com. Phazurlabs hat ein Plugin für die Community gebaut, und die Community hat es nicht genommen.

Das ist keine Kleinigkeit. In einem Ökosystem, in dem gut gemachte Skills innerhalb von Wochen Tausende Stars bekommen, ist Stille bei 2 Stars ein Signal. `pbakaus/impeccable` kam in drei Wochen auf 10.000, `Dammyjay93/interface-design` auf rund 4.600. Es bedeutet nicht zwangsläufig, dass der Inhalt schlecht ist. Es bedeutet, dass niemand bereit war, die Installation zu testen.

## Die Quellenarbeit: Real, aber unüberprüfbar

Im Abschnitt „Research Sources" listet das Repository eine beeindruckende Bibliographie auf: Daniel Kahneman mit Peak-End Rule und System 1/2, John Sweller mit der Cognitive Load Theory, Jakob Nielsen mit seinen Heuristiken, WCAG 2.2 und WCAG 3.0 vom April 2026, arXiv-Papiere von der ACM CHI 2025, W3C Design Tokens vom Oktober 2025, Apple WWDC 2025 und Google I/O 2025.

Das sind echte Quellen. Wer die arXiv-IDs nachschlägt, findet tatsächlich Papiere. Wer die WCAG-Version prüft, findet den korrekten Stand. Die Bibliographie ist keine Erfindung.

Das Problem liegt eine Ebene tiefer: **Werden diese Quellen korrekt in Designprinzipien übersetzt?** Das ist bei einem Skill, der auf Claude-generiertem Inhalt basiert, nicht überprüfbar. Hier beginnt das zentrale epistemische Problem dieses Projekts.

<div class="callout">
<div class="callout__title">Das Selbstreferenz-Problem</div>

Der letzte Satz des README lautet: <em>"Built with obsessive attention to detail by Design Tribe Republic. Powered by Claude Opus 4.6."</em>

Das bedeutet: Claude hat dieses Plugin geschrieben. Installiert man es, lehrt man Claude etwas, das Claude selbst formuliert hat. Das ist kein böswilliger Trick, aber es ist ein epistemisches Problem, das nirgendwo im Plugin kommuniziert wird.

Wenn ein Skill behauptet, Kahneman korrekt zu portieren, und die einzige Quelle dieser Portierung Claudes Training auf Kahneman-Texten ist, dann prüft das Plugin keine externe Expertise gegen Claudes Wissenslücken. Es verstärkt, was Claude ohnehin schon denkt. Tiefkalibrierte Fehler werden dadurch stabiler, nicht korrekter: falsch vereinfachte Heuristiken, aus dem Kontext gerissene Biaseffekte.

Die methodisch sinnvolle Alternative: ein Domain-Experte vergleicht Claudes Portierung einer Quelle mit der Originalquelle und dokumentiert Abweichungen. Das ist aufwendig, aber das Einzige, was „korrekte Portierung" operationalisierbar macht.
</div>

## Transparenz als Leerstelle

Ein Plugin, das „the most comprehensive UX/UI design intelligence ever built" verspricht, trägt eine besondere Verantwortung zur Einschränkungskommunikation. Denn je umfangreicher die Versprechen, desto schwerwiegender sind Fehleinschätzungen.

Was `ux-ui-mastery` kommuniziert: sehr viel Können. Was es nicht kommuniziert: irgendeine Grenze.

Es gibt keinen Abschnitt „When not to use this". Es gibt keine Warnung, dass WCAG-Compliance-Prüfung durch einen LLM keine formale Accessibility-Prüfung ersetzt. Es gibt keinen Hinweis, dass „Fitts's Law predicts a 23% improvement" eine grobe Modellschätzung ist und keine empirische Messung. Die Skill-Domain „Agentic AI" behandelt Claudes eigene Architektur als Designgegenstand, ohne die offensichtliche Befangenheit zu benennen.

Das Schweigen zu Grenzen ist in diesem Skill besonders auffällig, weil er explizit den „Liz Lerman Critical Response Process" als Methodenquelle nennt. Der Critical Response Process ist in seiner Originalform ein strukturiertes Feedback-Verfahren, das explizit unterscheidet zwischen dem, was ein Werk zeigt, und dem, was es nicht zeigt. Ein Plugin, das diese Methode lehrt, ohne sie auf sich selbst anzuwenden, demonstriert genau den Fehler, vor dem die Methode schützen soll.

## 310.000 Wörter als Anti-Pattern

Die Kennzahl „310K+ words" begegnet einem im README dreimal. Sie ist das stärkste Argument des Projekts und zugleich das aufschlussreichste Signal für ein grundlegendes Missverständnis.

Sprachmodelle produzieren Text. Mehr Text zu produzieren kostet nichts. Die Frage ist nicht, ob 310.000 Wörter generiert werden können, sondern ob 310.000 Wörter nützlich sind. Das ist eine Frage, die nur durch Nutzung beantwortet werden kann. Die Community hat diese Antwort gegeben, indem sie ausgeblieben ist.

In der Designtheorie, auf die sich das Plugin beruft, gibt es einen Namen für das Phänomen, wenn Quantität als Qualitätsproxy verwendet wird: Feature Overflow, und auf der Ebene der Information Architecture Category Pollution. Ein System, das alles kategorisiert, kategorisiert nichts, weil die Kategorien ihre Unterscheidungskraft verlieren. Ein Plugin mit 19 Skill-Domains, 55 Referenzdateien und 87 Dateien hat dasselbe Problem auf der Ebene seiner eigenen Architektur.

Das Plugin beschreibt im Abschnitt „How It Works" selbst, warum das ein Problem ist: „progressive disclosure — the same cognitive principle it teaches." Progressive Disclosure bedeutet, dass Nutzende nur das sehen, was sie in diesem Moment brauchen. 87 Dateien und 310.000 Wörter sind das Gegenteil davon. Das ist ein Kompendium, das alles gleichzeitig präsentiert.

## Der Vergleich mit dem Feld

`ehmo/platform-design-skills`, in dieser Reihe mit dem Urteil „vertrauen" bewertet, hat 354 Stars, 92 Commits, ein CHANGELOG, PR-Guidelines und Apple HIG als PDF direkt im Repository. Der Inhalt ist weniger umfangreich, aber die Qualitätssicherung ist nachvollziehbar. `mastepanoski/claude-skills` kombiniert Nielsen, WCAG und Don Norman, also drei Frameworks die sich gegenseitig überprüfen lassen.

`ux-ui-mastery` ist nach eigener Angabe größer als beide zusammen. Es hat weniger Nutzer als jeder andere in diesem Blog evaluierte Skill.

## Empfehlung für den Unterrichtseinsatz

Dieses Repository eignet sich nicht als primäre Lehrressource für UX-Methodik. Es ist weder hinreichend validiert noch ausreichend transparent über seine Grenzen.

Es eignet sich ausgezeichnet als Diskussionsgegenstand für zwei spezifische Lehrthemen:

Erstens: Der Unterschied zwischen Quellennennung und Quellenkompetenz. Die Bibliographie ist real. Die Portierung ist unüberprüfbar. Das ist genau das Problem, das Studierende beim kritischen Umgang mit jeder Quelle erkennen müssen, und hier tritt es in einer Form auf die sich zeigen lässt.

Zweitens: Das Selbstreferenz-Problem bei KI-generierten Wissenssystemen. Wenn Claude beschreibt, wie man Designheuristiken korrekt anwenden soll, und dieses Destillat als Plugin in Claude zurückinstalliert wird, was genau lernt Claude dann? Das ist keine rhetorische Frage. Es ist eine offene Forschungsfrage, die im Feld noch unbeantwortet ist.

310.000 Wörter können einen Ausgangspunkt für beide Diskussionen bilden. Als zuverlässige Designressource für die tägliche Praxis ist dieses Plugin derzeit nicht geeignet.
