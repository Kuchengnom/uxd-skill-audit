---
layout: post
title: "impeccable im Re-Audit: Aus einem Drei-Wochen-Hype wurde eine Werkzeugkette mit einem echten Detektor"
date: 2026-09-15
category: Skill-Evaluation
skill_reviewed: "pbakaus/impeccable"
verdict: solide
reading_time: 10
last_audited: "15. September 2026"
supersedes: /2026/02/28/pbakaus-impeccable-evaluation/

skill_scores:
  methodische_fundierung: 4
  methodische_fundierung_note: "Nielsen-Heuristiken (0–4-Skala) und WCAG-Kontrastwerte (4,5:1 / 7:1) werden korrekt wiedergegeben, aber weiterhin ohne eine einzige Fußnote oder Quellenangabe im Skill-Text selbst — Korrektheit ja, Nachvollziehbarkeit nein."
  transparenz: 4
  transparenz_note: "Neu: ein expliziter Warnhinweis, dass ein sauberer Detektor-Lauf „Evidenz, nicht Beweis" für visuelle oder Zugänglichkeitsqualität ist, dazu dokumentierte Sicherheitshinweise zu Hooks und Live-Mode-Skriptausführung."
  validierbarkeit: 4
  validierbarkeit_note: "61 deterministische Regeln laufen als eigenständige CLI ohne LLM und ohne API-Key, mit JSON-Output und CI-tauglichen Exit-Codes — das ist ausführbare Prüfbarkeit statt Prosa-Checkliste, auch wenn kein Abgleich mit menschlicher Expertenbewertung existiert."
  wartbarkeit: 5
  wartbarkeit_note: "Von 10.000 auf 63.337 Sterne und 251.415 Installs, Apache-2.0-Lizenz, VS-Code-Marketplace-Extension eines Drittanbieters, npm-Paket, GitHub Discussions, Unterstützung für 16 Agent-Harnesses — sieben Monate anhaltendes, sichtbares Wachstum statt einer Drei-Wochen-Welle."

tags:
  - re-audit
  - design-frontend
  - deterministic-detection
  - wachstum
  - skill-evaluation
---

Im Februar hatten wir `pbakaus/impeccable` mit „Vertrauen, aber nicht Solide" bewertet — mit der ausdrücklichen Einschränkung, dass drei Wochen Erfolgsgeschichte noch keine Wartbarkeit beweisen und dass Quellenangaben fehlen. Sieben Monate später ist der Skill nicht mehr derselbe. Zeit für einen Re-Audit, nicht für eine Korrektur des alten Posts — die Methodik dieses Blogs behandelt Bewertungen als Momentaufnahmen, und diese hier verdient einen eigenen Eintrag.

## Was sich strukturell verändert hat

Im Februar bestand der Skill aus sieben Referenzdateien und 20 Slash-Commands. Die aktuelle Version 4.0.4 liefert 35 Referenz-Playbooks, vier Subagenten-Prompts, native Varianten für iOS und Android, ein eigenes `doctor`-Kommando zur Drift-Erkennung zwischen Projektartefakten und Skill-Version, und einen Hook, der nach jeder UI-Dateiänderung automatisch einen Detektor laufen lässt. Das ist keine graduelle Erweiterung, das ist eine andere Kategorie von Software geworden: ein kompiliertes Engine-Binary mit Launcher-Skripten, verteilt über 16 Agent-Umgebungen von Claude Code bis Grok Build, zusätzlich eine VS-Code-Marketplace-Extension eines Drittanbieters (`renaissance-geek.impeccable`) und ein npm-Paket.

## Der wichtigste Fund: ein echter Detektor statt einer Checkliste

Das ist der Kern der Höherstufung. Die CLI `npx impeccable detect` führt 61 deterministische Regeln aus — ohne LLM, ohne API-Key, als kompilierte Engine. Sie erkennt konkrete Anti-Pattern wie seitliche Farbstreifen an Karten, Lila-Blau-Verläufe, Bounce-Easing und zu kleine Touch-Targets, liefert JSON-Output für CI-Pipelines und definierte Exit-Codes (0 = sauber, 2 = Befunde, 1 = Scan-Fehler). Im Februar kritisierten wir explizit: „Ohne Testfälle lässt sich der Skill nicht objektiv überprüfen." Das stimmt für den LLM-gestützten Teil weiterhin, aber für den Detektor-Teil nicht mehr — das ist ausführbarer, reproduzierbarer Code, den man in eine Pipeline einbauen und dessen Output man versionieren kann.

<div class="callout">
<div class="callout__title">Der Autor warnt selbst vor Überinterpretation des eigenen Tools</div>
Im README steht wörtlich: „A clean detector run is evidence, not proof of visual or accessibility quality: it does not replace inspecting the rendered experience across relevant viewports." Das ist genau die Art von Grenzkommunikation, die wir im Februar vermisst haben — und die wir in fast keinem anderen bisher evaluierten Skill in dieser Direktheit gefunden haben.
</div>

## Was sich nicht verbessert hat

Die Nielsen-Heuristiken tauchen jetzt mit einer vollständigen 0–4-Bewertungsskala pro Heuristik auf, inklusive konkreter Prüfkriterien — methodisch ordentlich gemacht, korrekt zehn statt fünf oder sieben Heuristiken, mit sinnvollen Abstufungen. Die WCAG-Kontrastwerte (4,5:1 für AA, 7:1 für AAA) sind ebenfalls korrekt. Aber: Keine dieser beiden anerkannten Methoden wird im Skill-Text selbst mit einer Quelle versehen. Kein „Nielsen, 1994", kein Link zu nngroup.com oder zur WCAG-Spezifikation, keine Fußnote. Der Skill wendet die Methoden korrekt an, ohne zu sagen, woher sie stammen. Das ist ein anderer Fehler als im Februar (damals war unklar, ob überhaupt korrekt portiert wurde — jetzt ist klar: korrekt portiert, aber weiterhin unbelegt), aber es ist derselbe Dimensionsabzug.

## Das Marketing-Problem ist gelöst

Im Februar kritisierten wir den Pitch „das was Anthropics `frontend-design` hätte sein sollen" als Marketing statt Substanz. Die aktuelle Selbstdarstellung im README liest sich anders: „Anthropic's frontend-design was the first widely-used design skill for Claude. Impeccable started from there." Das ist Anerkennung der Herkunft statt Abgrenzung durch Angriff. Ob diese Änderung bewusst redaktionell war oder sich einfach mit wachsendem Selbstbewusstsein ergeben hat, lässt sich von außen nicht feststellen — das Ergebnis zählt für die Bewertung.

## Wartbarkeit: von Hoffnung zu Beleg

Im Februar war die Wartbarkeits-Note (4/5) mit einem Vorbehalt versehen: „Es ist noch sehr neu, gerade einmal drei Wochen. Wie lange hält die Maintenance?" Diese Frage ist jetzt beantwortet. Sieben Monate anhaltendes Wachstum auf 63.337 Sterne und eine Viertelmillion Installs, eine Apache-2.0-Lizenz, ein aktives npm-Paket, GitHub Discussions, und — als stärkstes Signal — ein Drittanbieter, der eine eigene VS-Code-Extension um den Skill herum baut. Das ist keine virale Welle mehr, das ist ein Ökosystem, das sich um das Projekt bildet.

## Das Urteil: Solide, mit einer bleibenden Lücke

`impeccable` erreicht jetzt in allen vier Dimensionen mindestens 4 von 5 — die Voraussetzung für „Solide" nach unserem Rahmen. Die Höherstufung ist in drei von vier Dimensionen begründet: Transparenz durch explizite Grenzkommunikation, Validierbarkeit durch einen echten deterministischen Detektor, Wartbarkeit durch sieben Monate belegtes statt behauptetes Wachstum. Die methodische Fundierung bleibt bei 4, nicht bei 5, weil die zugrundeliegenden Methoden zwar korrekt angewendet, aber nie mit ihrer Quelle benannt werden.

**Für den Unterrichtseinsatz:** Dieser Fall eignet sich besser als der Februar-Post für eine Lehrveranstaltung über Skill-Evolution statt Skill-Momentaufnahmen. Die Aufgabenstellung: Studierende vergleichen die Februar- und September-Version desselben Skills und identifizieren, welche der vier Dimensionen sich durch echte strukturelle Arbeit verbessert haben (Validierbarkeit, Transparenz) und welche sich nur durch externe Faktoren verbessert haben, die der Skill selbst nicht kontrolliert (Wartbarkeit durch Marktreaktion). Die Lektion: Wachstum ist kein Ersatz für Quellenarbeit, aber es ist auch kein Zufall — und beides muss getrennt bewertet werden.
