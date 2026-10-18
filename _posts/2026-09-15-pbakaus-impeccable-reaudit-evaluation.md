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
  methodische_fundierung_note: "Nielsen-Heuristiken (0–4-Skala) und WCAG-Kontrastwerte (4,5:1 / 7:1) werden korrekt wiedergegeben. Im Skill-Text selbst fehlt weiterhin jede Fußnote und Quellenangabe. Korrektheit ja, Nachvollziehbarkeit nein."
  transparenz: 4
  transparenz_note: "Neu ist ein expliziter Warnhinweis, dass ein sauberer Detektor-Lauf „Evidenz, nicht Beweis" für visuelle oder Zugänglichkeitsqualität ist. Dazu kommen dokumentierte Sicherheitshinweise zu Hooks und Live-Mode-Skriptausführung."
  validierbarkeit: 4
  validierbarkeit_note: "61 deterministische Regeln laufen als eigenständige CLI ohne LLM und ohne API-Key. Es gibt JSON-Output und CI-taugliche Exit-Codes. Das ist ausführbare Prüfbarkeit statt Prosa-Checkliste. Ein Abgleich mit menschlicher Expertenbewertung existiert nicht."
  wartbarkeit: 5
  wartbarkeit_note: "Von 10.000 auf 63.337 Sterne und 251.415 Installs. Dazu kommen Apache-2.0-Lizenz, VS-Code-Marketplace-Extension eines Drittanbieters, npm-Paket, GitHub Discussions und Unterstützung für 16 Agent-Harnesses. Sieben Monate anhaltendes, sichtbares Wachstum statt einer Drei-Wochen-Welle."

tags:
  - re-audit
  - design-frontend
  - deterministic-detection
  - wachstum
  - skill-evaluation
---

Im Februar hatten wir `pbakaus/impeccable` mit „Vertrauen, aber nicht Solide" bewertet. Dazu gehörte die ausdrückliche Einschränkung. Drei Wochen Erfolgsgeschichte beweisen noch keine Wartbarkeit. Quellenangaben fehlten ebenfalls. Sieben Monate später ist der Skill nicht mehr derselbe. Das verlangt einen Re-Audit. Eine Korrektur des alten Posts wäre falsch. Die Methodik dieses Blogs behandelt Bewertungen als Momentaufnahmen. Diese hier verdient einen eigenen Eintrag.

## Was sich strukturell verändert hat

Im Februar bestand der Skill aus sieben Referenzdateien und 20 Slash-Commands. Version 4.0.4 liefert heute 35 Referenz-Playbooks und vier Subagenten-Prompts. Dazu kommen native Varianten für iOS und Android. Ein eigenes `doctor`-Kommando erkennt Drift zwischen Projektartefakten und Skill-Version. Ein Hook lässt nach jeder UI-Dateiänderung automatisch einen Detektor laufen. Das ist keine graduelle Erweiterung. Es ist eine andere Kategorie von Software. Der Skill ist ein kompiliertes Engine-Binary mit Launcher-Skripten. Er wird über 16 Agent-Umgebungen verteilt, von Claude Code bis Grok Build. Eine VS-Code-Marketplace-Extension eines Drittanbieters kommt hinzu, `renaissance-geek.impeccable`. Dazu kommt ein npm-Paket.

## Der wichtigste Fund: ein echter Detektor statt einer Checkliste

Das ist der Kern der Höherstufung. Die CLI `npx impeccable detect` führt 61 deterministische Regeln aus. Sie braucht kein LLM und keinen API-Key. Die Engine ist kompiliert. Sie erkennt konkrete Anti-Pattern wie seitliche Farbstreifen an Karten, Lila-Blau-Verläufe, Bounce-Easing und zu kleine Touch-Targets. JSON-Output für CI-Pipelines und definierte Exit-Codes gehören dazu. 0 heißt sauber, 2 Befunde, 1 Scan-Fehler. Im Februar kritisierten wir explizit: „Ohne Testfälle lässt sich der Skill nicht objektiv überprüfen." Für den LLM-gestützten Teil stimmt das weiterhin. Für den Detektor-Teil stimmt es nicht mehr. Er ist ausführbarer, reproduzierbarer Code. Man kann ihn in eine Pipeline einbauen. Sein Output lässt sich versionieren.

<div class="callout">
<div class="callout__title">Der Autor warnt selbst vor Überinterpretation des eigenen Tools.</div>
Im README steht wörtlich: „A clean detector run is evidence, not proof of visual or accessibility quality: it does not replace inspecting the rendered experience across relevant viewports". Das ist genau die Art von Grenzkommunikation, die wir im Februar vermisst haben. In fast keinem anderen bisher evaluierten Skill haben wir sie in dieser Direktheit gefunden.
</div>

## Was sich nicht verbessert hat

Die Nielsen-Heuristiken tauchen jetzt mit einer vollständigen 0–4-Bewertungsskala pro Heuristik auf. Konkrete Prüfkriterien sind inklusive. Methodisch ist das ordentlich gemacht. Es sind korrekt zehn Heuristiken, nicht fünf oder sieben, mit sinnvollen Abstufungen. Auch die WCAG-Kontrastwerte stimmen. Es sind 4,5:1 für AA und 7:1 für AAA. Keine dieser beiden anerkannten Methoden versieht der Skill-Text selbst mit einer Quelle. Es gibt kein „Nielsen, 1994", keinen Link zu nngroup.com oder zur WCAG-Spezifikation und keine Fußnote. Der Skill wendet die Methoden korrekt an. Woher sie stammen, sagt er nicht. Das ist ein anderer Fehler als im Februar. Damals war unklar, ob überhaupt korrekt portiert wurde. Jetzt ist klar, dass korrekt portiert wurde, aber weiterhin unbelegt. Der Dimensionsabzug bleibt derselbe.

## Das Marketing-Problem ist gelöst

Im Februar kritisierten wir den Pitch „das was Anthropics `frontend-design` hätte sein sollen" als Marketing statt Substanz. Die aktuelle Selbstdarstellung im README liest sich anders. Dort steht: „Anthropic's frontend-design was the first widely-used design skill for Claude. Impeccable started from there." Das ist Anerkennung der Herkunft statt Abgrenzung durch Angriff. Ob diese Änderung bewusst redaktionell war oder sich mit wachsendem Selbstbewusstsein ergeben hat, lässt sich von außen nicht feststellen. Für die Bewertung zählt das Ergebnis.

## Wartbarkeit: von Hoffnung zu Beleg

Im Februar stand die Wartbarkeits-Note 4/5 unter einem Vorbehalt. Er lautete: „Es ist noch sehr neu, gerade einmal drei Wochen. Wie lange hält die Maintenance?" Diese Frage ist jetzt beantwortet. Das Wachstum hält sieben Monate an und liegt bei 63.337 Sternen und einer Viertelmillion Installs. Dazu kommen eine Apache-2.0-Lizenz, ein aktives npm-Paket und GitHub Discussions. Als stärkstes Signal baut ein Drittanbieter eine eigene VS-Code-Extension um den Skill herum. Das ist keine virale Welle mehr. Es ist ein Ökosystem, das sich um das Projekt bildet.

## Das Urteil: Solide, mit einer bleibenden Lücke

`impeccable` erreicht jetzt in allen vier Dimensionen mindestens 4 von 5. Damit ist die Voraussetzung für „Solide" nach unserem Rahmen erfüllt. Die Höherstufung ist in drei von vier Dimensionen begründet. Transparenz gewinnt durch explizite Grenzkommunikation. Validierbarkeit gewinnt durch einen echten deterministischen Detektor. Wartbarkeit gewinnt durch sieben Monate belegtes statt behauptetes Wachstum. Die methodische Fundierung bleibt bei 4 und steigt nicht auf 5. Zugrundeliegende Methoden sind zwar korrekt angewendet. Nie werden sie aber mit ihrer Quelle benannt.

**Für den Unterrichtseinsatz:** Dieser Fall eignet sich besser als der Februar-Post für eine Lehrveranstaltung über Skill-Evolution statt Skill-Momentaufnahmen. Studierende vergleichen die Februar- und September-Version desselben Skills. Sie identifizieren die Dimensionen, die sich durch echte strukturelle Arbeit verbessert haben. Das sind Validierbarkeit und Transparenz. Die Wartbarkeit hat sich nur durch einen externen Faktor verbessert, die Marktreaktion. Der Skill kontrolliert ihn nicht selbst. Wachstum ist kein Ersatz für Quellenarbeit. Zufall ist es aber auch nicht. Beides muss getrennt bewertet werden.
