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
  methodische_fundierung_note: "Die Anti-Slop-Regeln sind konkret und beobachtungsbasiert (4/8px-Raster, oklch()-Paletten), Der zentrale Anspruch 'reverse-engineered aus Anthropics echtem System-Prompt' bleibt aber unbelegt und unverifizierbar."
  transparenz: 4
  transparenz_note: "Der Abschnitt 'Model calibration' benennt explizit, für welche Modellgeneration der Prompt kalibriert ist. Er nennt auch, wo der Prompt auf älteren oder anderen Modellen versagen kann. Das ist ungewöhnlich ehrlich für dieses Genre."
  validierbarkeit: 2
  validierbarkeit_note: "Einzelne Regeln sind selbst-prüfbar (Farbwerte, Spacing-Werte). Es gibt aber keine Vorher/Nachher-Beispiele, keine Testsuite und keinerlei Beleg für die Leak-Behauptung selbst."
  wartbarkeit: 3
  wartbarkeit_note: "Identifizierbarer Einzelentwickler mit MIT-Lizenz und einer nachweisbaren Aktualisierung für neue Modelle. Es gibt aber nur sechs Commits insgesamt. Der Issue-Tracker ist für externe Nutzer gesperrt, trotz gegenteiliger Einladung im README."

tags:
  - reverse-engineering
  - systemprompt
  - ai-slop
  - transparenz
  - skill-evaluation
---

Die meisten Skills in dieser Serie behaupten, aus anerkannten Quellen zu schöpfen. Genannt werden Nielsen, WCAG, Kahneman und Refactoring UI. `Trystan-SA/claude-design-system-prompt` behauptet etwas anderes. Es sei, so das README wörtlich, der „reverse-engineered system prompt of Claude Design from Anthropic". Gemeint ist der tatsächliche interne Prompt, mit dem Claude.ai sein Design-Tool steuert. Er wurde aus dem Modellverhalten zurückgewonnen und aufgeschrieben. Binnen weniger Wochen kamen daraus 1.900 Stars und 238 Forks. Ein Twitter-Thread von Jason Zhou zerlegte die „geleakte Architektur" Punkt für Punkt.

Das Repository positioniert sich ausdrücklich modellunabhängig. Der Prompt soll in Claude, GPT, Gemini oder lokale Modelle passen. Das macht ihn zu einem Grenzfall für diese Rubrik. Die Quellenfrage fehlt hier nicht. Eine andere Autoritätsbehauptung ersetzt sie. Es heißt nicht „das steht bei WCAG", sondern „das ist, was Anthropic wirklich einsetzt".

## Was drinsteckt

Das Repository liefert zwei Varianten, eine für Claude Code und Claude.ai und eine für OpenAI Codex. Jede bringt einen 20-Kapitel-System-Prompt und 14 aufrufbare Skills mit. Die Skills sind in drei Gruppen geordnet. Produktion umfasst `wireframe`, `make-a-prototype` und `generate-variations`. System umfasst `design-system-extract` und `component-extract`. Review umfasst `accessibility-audit`, `ai-slop-check`, `hierarchy-rhythm-review` und `polish-pass`.

Kern des Ganzen ist der `ai-slop-check`. Er ist ein Katalog von neun Mustern, die „generisches KI-Design" verraten sollen. Dazu zählen Regenbogen-Gradients und dekorative Emoji. Auch die Kombination aus `border-radius: 12px` und `border-left: 4px solid` als Standard-Card gehört dazu. Hinzu kommen reines `#FFFFFF`-auf-`#000000` und Off-Grid-Spacing-Werte wie `padding: 7px 15px`. Jede Regel folgt demselben Muster. Erst kommt der Standardfall, dann das Erkennungsmerkmal, dann die Korrektur. Handwerklich ist das sauber gemacht. Der Katalog ist konkret genug, um ihn als Checkliste gegen ein bestehendes Interface abzuarbeiten. Viele Skills dieser Serie liefern das bislang nicht.

## Die Leak-Behauptung: prüfbar ist sie nicht

<div class="callout">
<div class="callout__title">Autorität durch unverifizierbare Herkunft</div>
Der gesamte Wert des Skills hängt an einer einzigen Prämisse. Es soll sich tatsächlich um Anthropics internen System-Prompt handeln und nicht um eine plausible Nachbildung. Niemand außer Anthropic kann das bestätigen oder widerlegen. Anthropic selbst hat den Prompt nie veröffentlicht oder bestätigt. Der Twitter-Diskurs um den Fund behandelt die Herkunft weitgehend als gegeben. Er spricht von „Claude Design's leaked system prompt". Nirgends wird eine Methodik offengelegt, wie das „Reverse Engineering" überhaupt funktionierte. Strukturell ist das dasselbe Problem wie bei `jiji262/claude-design-skill`. Es fiel dort schon auf und wurde im Juni unter dem Titel „Wenn ein extrahierter System-Prompt zur Methodik wird" evaluiert. Hier tritt es nur mit größerer Reichweite auf. Dazu kommt eine ausdrücklichere Echtheitsbehauptung im Titel selbst.
</div>

Das bedeutet nicht, dass der Inhalt falsch ist. Die Regeln im `ai-slop-check` sind beobachtbar korrekt. Wer viel KI-generiertes UI gesehen hat, erkennt die beschriebenen Muster wieder. Die Behauptung „das ist der echte Anthropic-Prompt" leistet methodisch aber mehr, als sie einlösen kann. Ehrlicher wäre ein Skill, der sagt „diese Regeln haben wir aus der Beobachtung von hundert generierten Interfaces destilliert". Er würde dieselbe praktische Qualität liefern. Eine nicht überprüfbare Autoritätsquelle müsste er nicht beanspruchen.

## Die Ausnahme: eine ungewöhnlich ehrliche Grenzsektion

Von den meisten überversprechenden Kandidaten dieser Serie unterscheidet den Skill der Abschnitt „Model calibration". Dort steht ausdrücklich, dass die Claude-Variante für aktuelle Frontier-Modelle der Fable-5- und Opus-4.7/4.8-Linie kalibriert ist. Diese Modelle befolgen Anweisungen wörtlicher als ältere Generationen. Auf Claude Opus und Sonnet 4.6 und früher löst die zurückhaltendere Formulierung möglicherweise nicht mehr aus, was sie auslösen soll. Auf Nicht-Anthropic-Modellen gilt dasselbe. Eine solche Transparenz liefert kaum ein anderer Skill in dieser Serie. Der Skill sagt ausdrücklich, wofür das Werkzeug *nicht* kalibriert ist. Das Grundproblem der Leak-Prämisse widerlegt der Abschnitt nicht. Er macht nur den zweiten, unabhängigen Teil des Skills nachvollziehbar, die Modell-Anpassung.

## Wartbarkeit: sechs Commits, gesperrter Issue-Tracker

Hinter dem Projekt steht mit Trystan Sarrade ein identifizierbarer Fullstack-Entwickler aus Frankreich. Ein anonymer Account ist es nicht. Er hat eine sichtbare Historie in anderen Open-Source-Projekten, darunter ein Rust-Prozessmonitor und ein Self-Hosted-Panel für Anthropic Managed Agents. Das Repository ist MIT-lizenziert. Das README lädt ausdrücklich zu „Issues and PRs" ein. Gewünscht sind zusätzliche Review-Skills, Portierungen für andere Umgebungen und „real-world failure cases". In der Praxis ist der Issue-Tracker für externe Nutzer jedoch gesperrt. Seit der Erstveröffentlichung gibt es sechs Commits. Spuren aktiver Weiterentwicklung sind kaum zu finden. Immerhin belegt die nachweisbare Aktualisierung für neuere Modellgenerationen einen zweiten Bearbeitungszyklus. Für Studierende ist das ein gutes Beispiel. Man gleicht README-Einladung und tatsächliche Repository-Konfiguration ab und nimmt sie nicht für bare Münze.

## Empfehlung für den Unterrichtseinsatz

Dieser Skill eignet sich hervorragend als Fallstudie zum Thema Autoritätsbehauptung ohne Verifizierbarkeit. Als direkte Gegenüberstellung dient `jiji262/claude-design-skill`. Die Übung läuft in zwei Schritten. Zuerst bewerten Studierende den `ai-slop-check`-Katalog isoliert von der Leak-Prämisse. Sie fragen nur, ob die Regel selbst brauchbar ist. Getrennt davon prüfen sie die Herkunftsbehauptung. Lässt sie sich verifizieren? Wer würde davon profitieren, dass man sie glaubt?

Praktisch einsetzbar ist der Skill trotzdem. Die Anti-Slop-Regeln und die Model-Calibration-Sektion liefern echten, direkt anwendbaren Wert. Ob die Ursprungsgeschichte stimmt, ändert daran nichts. Genau das macht ihn lehrreich. Ein Skill kann nützlich sein und in seiner zentralen Behauptung trotzdem unbelegt. Wer ihn einsetzt, legt die „Claude Design"-Etikettierung ab. Er behandelt den Skill als das, was verifizierbar ist: eine kompetent zusammengestellte, aber selbst erstellte Anti-Slop- und Review-Checkliste.
