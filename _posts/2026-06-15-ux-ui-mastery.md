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

Manche Repositories lassen sich durch ihren README-Einstieg sofort einordnen. `phazurlabs/ux-ui-mastery` beginnt mit der Zeile: *"The most comprehensive UX/UI design intelligence ever built for an AI coding assistant."* Dieser Superlativ steht nicht in einer Abschnittsüberschrift. Er ist die erste Prämisse des gesamten Projekts. Alles, was folgt, soll ihn belegen.

Was folgt, ist in der Tat beeindruckend groß. In Zahlen sind es 19 Skills, 55 Referenzdateien, 10 Slash-Commands, 87 Dateien und 310.000 Wörter. Im Ökosystem der Claude-Design-Skills ist das konkurrenzlos. Genau deshalb lohnt sich der genaue Blick. Der Skill treibt eine der grundlegendsten Fragen des Felds auf die Spitze. Ab wann ist mehr nicht mehr besser?

## Der Zählerstand zählt, nur nicht so wie das Projekt es meint

Der README-Text präsentiert Metriken wie ein Dashboard. Er nennt 25+ Laws of UX, 50+ kognitive Biases, 40+ Produktionskomponenten, 18+ Fallstudien und 30+ haptische Muster. Jede Zahl übertrifft die der Konkurrenz. Das implizite Argument lautet: Umfang beweist Qualität.

Ein anderer Zählerstand steht nirgends im README: **2 Stars. 1 Fork. 4 Commits. 0 Issues. 0 Pull Requests. 0 Releases.**

Seit dem initialen Upload ist das Repository praktisch unverändert. Es gibt keine öffentliche Diskussion und keinen Community-Post. In den einschlägigen Aggregatoren wie awesome-claude-skills, claudeskills.info oder claudemarketplaces.com taucht es nicht auf. Phazurlabs hat ein Plugin für die Community gebaut. Die Community hat es abgelehnt.

Eine Kleinigkeit ist das nicht. Gut gemachte Skills sammeln im Ökosystem innerhalb von Wochen Tausende Stars. `pbakaus/impeccable` kam in drei Wochen auf 10.000. `Dammyjay93/interface-design` kam auf rund 4.600. Bei 2 Stars ist die Stille ein Signal. Schlecht muss der Inhalt deshalb nicht sein. Es hat aber niemand die Installation testen wollen. Das sagt viel.

## Die Quellenarbeit: Real, aber unüberprüfbar

Im Abschnitt „Research Sources" listet das Repository eine beeindruckende Bibliographie auf. Genannt sind Daniel Kahneman mit Peak-End Rule und System 1/2, John Sweller mit der Cognitive Load Theory und Jakob Nielsen mit seinen Heuristiken. Dazu kommen WCAG 2.2 und WCAG 3.0 vom April 2026. Es folgen arXiv-Papiere von der ACM CHI 2025, W3C Design Tokens vom Oktober 2025, Apple WWDC 2025 und Google I/O 2025.

Die Quellen sind echt. Wer die arXiv-IDs nachschlägt, findet tatsächlich Papiere. Wer die WCAG-Version prüft, findet den korrekten Stand. Erfunden ist die Bibliographie nicht.

Das Problem liegt eine Ebene tiefer. **Werden diese Quellen korrekt in Designprinzipien übersetzt?** Bei einem Skill auf Basis von Claude-generiertem Inhalt lässt sich das nicht prüfen. Hier beginnt das zentrale Problem.

<div class="callout">
<div class="callout__title">Das Selbstreferenz-Problem</div>

Der letzte Satz des README lautet: <em>"Built with obsessive attention to detail by Design Tribe Republic. Powered by Claude Opus 4.6."</em>

Claude hat dieses Plugin also geschrieben. Wer es installiert, lehrt Claude etwas, das Claude selbst formuliert hat. Böswillig ist das nicht. Es ist aber ein epistemisches Problem. Das Plugin kommuniziert es nirgends. Das wiegt schwer.

Angenommen, ein Skill behauptet, Kahneman korrekt zu portieren. Die einzige Quelle dieser Portierung ist Claudes Training auf Kahneman-Texten. Dann prüft das Plugin keine externe Expertise gegen Claudes Wissenslücken. Es verstärkt, was Claude ohnehin denkt. Tief kalibrierte Fehler werden dadurch stabiler und nicht korrekter. Beispiele sind falsch vereinfachte Heuristiken und aus dem Kontext gerissene Biaseffekte.

Methodisch sinnvoll wäre eine Alternative. Ein Domain-Experte vergleicht Claudes Portierung einer Quelle mit der Originalquelle und dokumentiert die Abweichungen. Aufwendig ist das. Nur so wird „korrekte Portierung" operationalisierbar.
</div>

## Transparenz als Leerstelle

Ein Plugin, das „the most comprehensive UX/UI design intelligence ever built" verspricht, trägt eine besondere Verantwortung zur Einschränkungskommunikation. Je umfangreicher die Versprechen sind, desto schwerer wiegen Fehleinschätzungen. Das gilt hier.

`ux-ui-mastery` kommuniziert sehr viel Können. Eine Grenze kommuniziert es nicht.

Einen Abschnitt „When not to use this" gibt es nicht. Eine Warnung fehlt, dass die WCAG-Compliance-Prüfung durch ein LLM keine formale Accessibility-Prüfung ersetzt. Ebenso fehlt der Hinweis, dass „Fitts's Law predicts a 23% improvement" eine grobe Modellschätzung ist und keine empirische Messung. In der Skill-Domain „Agentic AI" ist Claudes eigene Architektur Designgegenstand. Die offensichtliche Befangenheit benennt sie nicht.

Besonders auffällig ist das Schweigen zu Grenzen. Als Methodenquelle nennt der Skill explizit den „Liz Lerman Critical Response Process". In der Originalform ist das ein strukturiertes Feedback-Verfahren. Es unterscheidet explizit zwischen dem, was ein Werk zeigt, und dem, was es nicht zeigt. Das Plugin lehrt diese Methode und wendet sie nicht auf sich selbst an. Es demonstriert genau den Fehler, vor dem die Methode schützen soll. Der Widerspruch ist offensichtlich.

## 310.000 Wörter als Anti-Pattern

Die Kennzahl „310K+ words" begegnet einem im README dreimal. Sie ist das stärkste Argument des Projekts. Zugleich verrät sie ein grundlegendes Missverständnis.

Sprachmodelle produzieren Text. Mehr Text kostet nichts. Offen ist, ob 310.000 Wörter nützlich sind. Beantworten kann das nur die Nutzung. Die Community ist ausgeblieben. Das ist die Antwort.

Die Designtheorie, auf die sich das Plugin beruft, hat einen Namen für dieses Phänomen. Wird Quantität als Qualitätsproxy verwendet, heißt es Feature Overflow. In der Information Architecture heißt es Category Pollution. Ein System, das alles kategorisiert, kategorisiert nichts. Ihre Unterscheidungskraft verlieren die Kategorien. Ein Plugin mit 19 Skill-Domains, 55 Referenzdateien und 87 Dateien hat dasselbe Problem. Es steckt in der eigenen Architektur.

Im Abschnitt „How It Works" erklärt das Plugin das Problem selbst. Es nennt „progressive disclosure — the same cognitive principle it teaches." Progressive Disclosure heißt, dass Nutzende nur sehen, was sie in diesem Moment brauchen. 87 Dateien und 310.000 Wörter sind das Gegenteil. Das Kompendium präsentiert alles gleichzeitig.

## Der Vergleich mit dem Feld

`ehmo/platform-design-skills` bekam in dieser Reihe das Urteil „vertrauen". 354 Stars hat der Skill, 92 Commits, ein CHANGELOG und PR-Guidelines. Die Apple HIG liegt als PDF direkt im Repository. Sein Inhalt ist weniger umfangreich. Die Qualitätssicherung ist nachvollziehbar. `mastepanoski/claude-skills` kombiniert Nielsen, WCAG und Don Norman. Das sind drei Frameworks, die sich gegenseitig überprüfen lassen.

`ux-ui-mastery` ist nach eigener Angabe größer als beide zusammen. Es hat weniger Nutzer als jeder andere Skill, den dieser Blog evaluiert hat.

## Empfehlung für den Unterrichtseinsatz

Als primäre Lehrressource für UX-Methodik eignet sich dieses Repository nicht. Es ist weder hinreichend validiert noch ausreichend transparent über seine Grenzen.

Ausgezeichnet eignet es sich als Diskussionsgegenstand für zwei Lehrthemen.

Erstens der Unterschied zwischen Quellennennung und Quellenkompetenz. Real ist die Bibliographie. Unüberprüfbar ist die Portierung. Dieses Problem müssen Studierende bei jeder Quelle erkennen. Hier tritt es in einer Form auf, die sich zeigen lässt. Das taugt als Beispiel.

Zweitens das Selbstreferenz-Problem bei KI-generierten Wissenssystemen. Claude beschreibt, wie man Designheuristiken korrekt anwendet. Dieses Destillat wird als Plugin in Claude zurückinstalliert. Was genau lernt Claude dann? Rhetorisch ist die Frage nicht. Im Feld ist es eine offene Forschungsfrage.

310.000 Wörter können beide Diskussionen anstoßen. Als zuverlässige Designressource für die tägliche Praxis taugt das Plugin derzeit nicht.
