---
layout: post
title: "claude-design-system-prompt: Ein angeblich geleakter Prompt, den niemand verifizieren kann — und der trotzdem funktioniert"
date: 2026-08-10
category: Skill-Evaluation
skill_reviewed: "Trystan-SA/claude-design-system-prompt"
verdict: vertrauen
reading_time: 8
last_audited: "10. August 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "Die Anti-Slop-Regeln sind konkret und beobachtungsbasiert (4/8px-Raster, oklch()-Paletten), aber der zentrale Anspruch 'reverse-engineered aus Anthropics echtem System-Prompt' bleibt unbelegt und unverifizierbar."
  transparenz: 4
  transparenz_note: "Der Abschnitt 'Model calibration' benennt explizit, für welche Modellgeneration der Prompt kalibriert ist und wo er auf älteren oder anderen Modellen versagen kann — ungewöhnlich ehrlich für dieses Genre."
  validierbarkeit: 2
  validierbarkeit_note: "Einzelne Regeln sind selbst-prüfbar (Farbwerte, Spacing-Werte), aber es gibt keine Vorher/Nachher-Beispiele, keine Testsuite und keinerlei Beleg für die Leak-Behauptung selbst."
  wartbarkeit: 3
  wartbarkeit_note: "Identifizierbarer Einzelentwickler mit MIT-Lizenz und einer nachweisbaren Aktualisierung für neue Modelle, aber nur sechs Commits insgesamt und ein für externe Nutzer gesperrter Issue-Tracker trotz gegenteiliger Einladung im README."

tags:
  - reverse-engineering
  - systemprompt
  - ai-slop
  - transparenz
  - skill-evaluation
---

Die meisten Skills in dieser Serie behaupten, aus anerkannten Quellen zu schöpfen: Nielsen, WCAG, Kahneman, Refactoring UI. `Trystan-SA/claude-design-system-prompt` behauptet etwas anderes. Es sei, so das README wörtlich, der „reverse-engineered system prompt of Claude Design from Anthropic". Gemeint ist der tatsächliche interne Prompt, mit dem Claude.ai sein Design-Tool steuert, aus dem Modellverhalten zurückgewonnen und aufgeschrieben. Binnen weniger Wochen kamen daraus 1.900 Stars und 238 Forks. Ein Twitter-Thread von Jason Zhou zerlegte die „geleakte Architektur" Punkt für Punkt. Das Repository positioniert sich dabei ausdrücklich modellunabhängig: Der Prompt soll in Claude, GPT, Gemini oder lokale Modelle passen. Das macht ihn zu einem Grenzfall für diese Rubrik. Die Quellenfrage fehlt hier nicht, sie ist nur durch eine andere Autoritätsbehauptung ersetzt: nicht „das steht bei WCAG", sondern „das ist, was Anthropic wirklich einsetzt".

## Was drinsteckt

Das Repository liefert zwei Varianten, eine für Claude Code und Claude.ai, eine für OpenAI Codex. Jede bringt einen 20-Kapitel-System-Prompt und 14 aufrufbare Skills mit, geordnet in drei Gruppen: Produktion mit `wireframe`, `make-a-prototype` und `generate-variations`, System mit `design-system-extract` und `component-extract`, Review mit `accessibility-audit`, `ai-slop-check`, `hierarchy-rhythm-review` und `polish-pass`. Kern des Ganzen ist der `ai-slop-check`: ein Katalog von neun Mustern, die „generisches KI-Design" verraten sollen. Dazu zählen Regenbogen-Gradients, dekorative Emoji, die Kombination aus `border-radius: 12px` und `border-left: 4px solid` als Standard-Card, reines `#FFFFFF`-auf-`#000000` und Off-Grid-Spacing-Werte wie `padding: 7px 15px`. Jede Regel folgt demselben Muster: erst der Standardfall, dann das Erkennungsmerkmal, dann die Korrektur. Das ist handwerklich sauber gemacht. Der Katalog ist konkret genug, dass man ihn tatsächlich als Checkliste gegen ein bestehendes Interface abarbeiten kann. Das liefern viele Skills dieser Serie bislang nicht.

## Die Leak-Behauptung: prüfbar ist sie nicht

<div class="callout">
<div class="callout__title">Autorität durch unverifizierbare Herkunft</div>
Der gesamte Wert des Skills hängt an einer einzigen Prämisse: dass dies tatsächlich Anthropics internes System-Prompt ist und nicht eine plausible Nachbildung. Niemand außer Anthropic kann das bestätigen oder widerlegen. Anthropic selbst hat den Prompt nie veröffentlicht oder bestätigt. Der Twitter-Diskurs um den Fund behandelt die Herkunft weitgehend als gegeben und spricht von „Claude Design's leaked system prompt", ohne dass irgendwo eine Methodik offengelegt wird, wie das „Reverse Engineering" überhaupt funktionierte. Das ist strukturell dasselbe Problem, das bereits bei `jiji262/claude-design-skill` auffiel und im Juni unter dem Titel „Wenn ein extrahierter System-Prompt zur Methodik wird" evaluiert wurde. Hier tritt es nur mit größerer Reichweite auf, und mit einer expliziteren Echtheitsbehauptung im Titel selbst.
</div>

Das bedeutet nicht, dass der Inhalt falsch ist. Die Regeln im `ai-slop-check` sind beobachtbar korrekt. Wer viel KI-generiertes UI gesehen hat, erkennt die beschriebenen Muster wieder. Aber die Behauptung „das ist der echte Anthropic-Prompt" tut methodisch mehr Arbeit, als sie einlösen kann. Ein Skill, der sagt „diese Regeln haben wir aus der Beobachtung von hundert generierten Interfaces destilliert", wäre ehrlicher. Er würde dieselbe praktische Qualität liefern, ohne eine nicht überprüfbare Autoritätsquelle zu beanspruchen.

## Die Ausnahme: eine ungewöhnlich ehrliche Grenzsektion

Was den Skill von den meisten überversprechenden Kandidaten dieser Serie unterscheidet, ist der Abschnitt „Model calibration". Dort steht explizit, dass die Claude-Variante für aktuelle Frontier-Modelle der Fable-5- und Opus-4.7/4.8-Linie kalibriert ist, die Anweisungen wörtlicher befolgen als ältere Generationen. Auf Claude Opus und Sonnet 4.6 und früher sowie auf Nicht-Anthropic-Modellen löst die zurückhaltendere Formulierung möglicherweise nicht mehr aus, was sie auslösen soll. Das ist eine Art von Transparenz, die sonst kaum ein Skill in dieser Serie liefert: eine explizite Aussage darüber, wofür das Werkzeug *nicht* kalibriert ist. Das Grundproblem der Leak-Prämisse widerlegt sie jedoch nicht. Sie macht nur den zweiten, unabhängigen Teil des Skills nachvollziehbar, die Modell-Anpassung.

## Wartbarkeit: sechs Commits, gesperrter Issue-Tracker

Hinter dem Projekt steht mit Trystan Sarrade ein identifizierbarer Fullstack-Entwickler aus Frankreich, kein anonymer Account. Er hat eine sichtbare Historie in anderen Open-Source-Projekten, darunter ein Rust-Prozessmonitor und ein Self-Hosted-Panel für Anthropic Managed Agents. Das Repository ist MIT-lizenziert und lädt im README explizit zu „Issues and PRs" ein, insbesondere zu zusätzlichen Review-Skills, Portierungen für andere Umgebungen und „real-world failure cases". In der Praxis ist der Issue-Tracker für externe Nutzer jedoch gesperrt. Bei sechs Commits seit Erstveröffentlichung gibt es kaum Spuren aktiver Weiterentwicklung. Immerhin belegt die nachweisbare Aktualisierung für neuere Modellgenerationen einen zweiten Bearbeitungszyklus. Für Studierende ist das ein gutes Beispiel dafür, wie man README-Einladung und tatsächliche Repository-Konfiguration gegenprüft, statt sie für bare Münze zu nehmen.

## Empfehlung für den Unterrichtseinsatz

Dieser Skill eignet sich hervorragend als Fallstudie zum Thema Autoritätsbehauptung ohne Verifizierbarkeit, als direkte Gegenüberstellung zu `jiji262/claude-design-skill`. Die Übung: Studierende sollen den `ai-slop-check`-Katalog isoliert von der Leak-Prämisse bewerten und dabei nur fragen, ob die Regel selbst brauchbar ist. Getrennt davon prüfen sie die Herkunftsbehauptung. Lässt sie sich verifizieren? Wer würde davon profitieren, dass man sie glaubt? Praktisch einsetzbar ist der Skill trotzdem. Die Anti-Slop-Regeln und die Model-Calibration-Sektion liefern echten, direkt anwendbaren Wert, unabhängig davon, ob die Ursprungsgeschichte stimmt. Genau das macht ihn lehrreich: Ein Skill kann nützlich und in seiner zentralen Behauptung unbelegt zugleich sein. Wer ihn einsetzt, sollte die „Claude Design"-Etikettierung ablegen und ihn als das behandeln, was verifizierbar ist: eine kompetent zusammengestellte, aber selbst erstellte Anti-Slop- und Review-Checkliste.
