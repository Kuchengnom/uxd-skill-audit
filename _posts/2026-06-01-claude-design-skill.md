---
layout: post
title: "claude-design-skill: Wenn ein extrahierter System-Prompt zur Methodik wird"
date: 2026-06-01
category: Skill-Evaluation
skill_reviewed: "jiji262/claude-design-skill"
verdict: vorsicht
reading_time: 8
last_audited: "01. Juni 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "Reale Designschulen (Swiss Editorial, Brutalism) korrekt referenziert. Die Basis ist aber ein extrahierter System-Prompt und kein zitierbares Methodenwissen."
  transparenz: 4
  transparenz_note: "Klare Scope-Abgrenzung (nur HTML-Artefakte, kein Figma), ehrliche Lizenzaussage zur Anthropic-Provenienz."
  validierbarkeit: 4
  validierbarkeit_note: "Drei browseröffnbare Demo-HTML-Dateien und eine test-prompts.json mit sechs getaggten Szenarien. Das ist ungewöhnlich solide für einen Community-Skill."
  wartbarkeit: 2
  wartbarkeit_note: "Zwei Commits gesamt, keine Releases, pseudonymer Einzelmaintainer ohne verifizierbaren Design-Background."

tags:
  - html-artefakte
  - system-prompt
  - provenienz
  - anti-slop
  - validierbarkeit
---

## Was ist dieser Skill, und warum ist die Herkunftsfrage so interessant?

`jiji262/claude-design-skill` positioniert sich als portabler Skill. Er soll Claude in einen Experten für HTML-basierte Designartefakte verwandeln. Dazu zählen Pitch-Decks, Landing Pages, interaktive Prototypen und Animationen. Nach vielen anderen Skills im Ökosystem klingt das. Heraus hebt diesen Skill ein Satz in der Beschreibung: *„Adapted from Claude.ai's internal Design system prompt."*

Diese Behauptung ist der Dreh- und Angelpunkt der gesamten Evaluation. Sie verspricht etwas Fundamentales. Die Anweisungen sollen nicht aus dem Kopf des Autors stammen. Sie sollen aus Anthropics eigenem Produktionssystem kommen. Das ist entweder eine außergewöhnliche Grundlage oder ein epistemisches Problem. Es hängt davon ab, was man unter „Methodik" versteht. Schmal ist das Repository selbst. Es hat zwei Commits und neun Referenzdateien.

## Die Herkunft des System-Prompts: Was „adapted from internal" bedeutet

Der Skill enthält eine Datei namens `Claude-Design-Sys-Prompt.txt`. Diese Datei taucht auch in `elder-plinius/CL4R1T4S` auf. Dort werden extrahierte Anthropic-System-Prompts gesammelt und veröffentlicht. Die methodische Basis dieses Skills ist also kein veröffentlichtes UX-Framework. Sie ist auch kein akademisches Paper und kein Styleguide. Sie ist der Versuch, Anthropics interne Betriebsanweisungen für Claude Design zu rekonstruieren und portierbar zu machen. Mehr Basis gibt es nicht.

Eine Abwertung ist das nicht, sondern eine Präzisierung. Hier wurde echtes Designwissen destilliert. Anthropic hat für das Claude-Design-Produkt tatsächlich konkrete Regeln entwickelt. Sie richten sich gegen Gradient-Orbs als KI-Metapher und gegen CSS-Silhouetten als Produktfotos. Sie fordern, reale Brand Assets vor dem ersten Pixel einzuholen. Dieses Wissen ist empirisch wertvoll. Es ist aber nicht zitierfähig und nicht versioniert. Externe Experten haben es nicht validiert. Es ist eine Momentaufnahme eines kommerziellen System-Prompts.

<div class="callout">
<div class="callout__title">Kernproblem: Provenienz ≠ Methodik</div>
„Adapted from Anthropic's internal Design system prompt" ist eine ehrliche Aussage. Sie beschreibt eine Quelle und keine Methodik. Ein extrahierter System-Prompt ist nicht dasselbe wie Norman und Draper 1986, Nielsen 1994 oder Tidwell 2010. Er kann richtig liegen. Er kann irren. Er kann veralten. Keines dieser Szenarien lässt sich von außen überprüfen. Studierende sollten verstehen, dass „von Anthropic stammend" keine unabhängige Validierung ersetzt. Es ist nur eine andere Form von Autorität durch Assoziation.
</div>

## Was der Skill inhaltlich liefert

Jenseits der Provenienzfrage lohnt ein genauer Blick auf die Struktur. Architektonisch ist der Skill sauber aufgebaut.

Neun Referenzdateien decken Fact Verification, Brand-Asset-Protokoll, Design-Direktionen, Anti-Slop-Regeln, Output-Formate, React/Babel-Pinning und Verifikationschecklisten ab. Das ist mehr strukturelle Disziplin, als die meisten Community-Skills aufweisen. Kategorien benennt er nicht nur. Er gibt konkrete Entscheidungsregeln. Das Anti-Slop-Kapitel listet zum Beispiel explizite Verbote: keine Gradient-Orbs für KI, keine CSS-Silhouetten als Produktfotos, keine aggressiven Verläufe. Diese Regeln sind aus echten Mustern destilliert. Damit sind sie direkt lehrbar.

Die Referenz auf zehn Designphilosophien aus fünf Schulen ist inhaltlich solide. Darunter sind Swiss Editorial, Kenya Hara Minimalism und Brutalist Web. Es sind reale, historisch verankerte Schulen. Ein Advisor Mode schlägt bei vagen Briefings drei differenzierte Richtungen vor. Methodisch ist das durchdacht. Die didaktische Aufbereitung fehlt allerdings.

## Die Stärke des Skills: Testinfrastruktur

Von der großen Masse der Community-Skills unterscheidet diesen Skill die `test-prompts.json`. Sie enthält sechs realistische Szenarien. Jedes ist mit den Guardrails getaggt, die es triggern soll. Dazu kommen drei browseröffnbare Demo-HTML-Dateien. Gezeigt werden ein Pitch-Deck im Swiss-Editorial-Stil, ein Design-Canvas mit vier Hero-Varianten aus verschiedenen Schulen und ein interaktiver iOS-Prototyp mit Live-State.

Das ist ein für dieses Ökosystem seltenes Maß an Nachvollziehbarkeit. Man muss keinem Abstract vertrauen. Man kann öffnen, klicken, prüfen. Für den Unterricht ist das ein erheblicher Vorteil. Es gibt konkrete Referenzoutputs. Sie zeigen, was der Skill produzieren soll. Neue Outputs lassen sich gegen sie prüfen.

## Was fehlt: Wartbarkeit und methodischer Rahmen

Zwei Commits. Keine Releases. Kein Changelog. Maintainer jiji262 ist ein chinesischer Entwickler. Bekannt ist er für Tools wie einen Douyin-Downloader und eine Claude-Code-Quellcode-Analyse. Design-Background ist nicht verifizierbar. Das Repository dankt der Community linux.do für die Inspiration. Es ist ein chinesischsprachiges Tech-Forum.

Das bedeutet nicht, dass der Inhalt schlecht ist. Es bedeutet aber etwas anderes. Anthropic kann seinen System-Prompt für Claude Design ändern. Bei einem aktiv entwickelten Produkt ist das wahrscheinlich. Dann veraltet dieser Skill ohne erkennbaren Mechanismus für Updates. Die Abhängigkeit von einer extrahierten, inoffiziellen Quelle macht Wartung strukturell schwierig. Privilegierten Zugang zur Quelle hat der Maintainer nicht.

Der UX-methodische Rahmen ist ebenfalls dünn. Es gibt keine Referenz auf Norman, Nielsen, WCAG oder irgendein anerkanntes Evaluationsframework. Die Qualität der Outputs hängt ausschließlich davon ab, wie gut Anthropics ursprüngliche interne Regeln waren. Verifizieren kann der Benutzer sie nicht.

## Empfehlung für den Unterrichtseinsatz

Dieser Skill eignet sich als Beispiel für zwei Unterrichtsgespräche. Erstens geht es um Provenienz. „Von Anthropic stammend" klingt wie ein Qualitätsmerkmal. Extrahierte System-Prompts sind aber weder peer-reviewed noch stabil. Die Frage „Woher weiß das der Skill?" führt zu einer produktiven Diskussion. Sie behandelt den Unterschied zwischen Autorität durch Assoziation und Autorität durch Verifikation.

Zweitens geht es um Testinfrastruktur. Die `test-prompts.json` und die drei Demos sind ein positives Beispiel für Nachvollziehbarkeit. Studierende können an diesem Skill üben, einen Skill nicht nur zu lesen, sondern zu prüfen. Dabei lernen sie, was Prüfen heißt.

Für produktiven Einsatz taugen die Anti-Slop-Regeln und Output-Format-Playbooks direkt. Nützliche, konkrete Heuristiken für HTML-Artefakte gibt der Skill. Eine UX-Methodik im akademischen Sinne liefert er nicht. Er liefert destilliertes Produktionswissen aus einem kommerziellen KI-System. Wer ihn einsetzt, sollte das wissen.
