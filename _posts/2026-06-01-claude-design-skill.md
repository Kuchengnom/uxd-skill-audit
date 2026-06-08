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
  methodische_fundierung_note: "Reale Designschulen (Swiss Editorial, Brutalism) korrekt referenziert, aber die Basis ist ein extrahierter System-Prompt — kein zitierbares Methodenwissen."
  transparenz: 4
  transparenz_note: "Klare Scope-Abgrenzung (nur HTML-Artefakte, kein Figma), ehrliche Lizenzaussage zur Anthropic-Provenienz."
  validierbarkeit: 4
  validierbarkeit_note: "Drei browseröffnbare Demo-HTML-Dateien und eine test-prompts.json mit sechs getaggten Szenarien — ungewöhnlich solide für einen Community-Skill."
  wartbarkeit: 2
  wartbarkeit_note: "Zwei Commits gesamt, keine Releases, pseudonymer Einzelmaintainer ohne verifizierbaren Design-Background."

tags:
  - html-artefakte
  - system-prompt
  - provenienz
  - anti-slop
  - validierbarkeit
---

## Was ist dieser Skill — und warum ist die Herkunftsfrage so interessant?

`jiji262/claude-design-skill` positioniert sich als portabler Skill, der Claude in einen Experten für HTML-basierte Designartefakte verwandelt: Pitch-Decks, Landing Pages, interaktive Prototypen, Animationen. Das klingt nach vielen anderen Skills im Ökosystem. Was diesen Skill heraushebt, ist ein Satz in der Beschreibung: *„Adapted from Claude.ai's internal Design system prompt."*

Diese Behauptung ist der Dreh- und Angelpunkt der gesamten Evaluation — denn sie verspricht etwas Fundamentales: dass die Anweisungen in diesem Skill nicht aus dem Kopf des Autors stammen, sondern aus Anthropics eigenem Produktionssystem. Das ist entweder eine außergewöhnliche Grundlage oder ein epistemisches Problem — je nachdem, was man unter „Methodik" versteht.

## Die Herkunft des System-Prompts: Was „adapted from internal" bedeutet

Der Skill enthält eine Datei namens `Claude-Design-Sys-Prompt.txt`. Diese Datei taucht auch in `elder-plinius/CL4R1T4S` auf — einem Repository, das sich dem Sammeln und Veröffentlichen von extrahierten Anthropic-System-Prompts widmet. Mit anderen Worten: Die methodische Basis dieses Skills ist kein veröffentlichtes UX-Framework, kein akademisches Paper, kein Styleguide — sondern der Versuch, Anthropics interne Betriebsanweisungen für Claude Design zu rekonstruieren und portierbar zu machen.

Das ist keine Abwertung, sondern eine Präzisierung. Was hier destilliert wurde, ist echtes Designwissen — Anthropic hat für das Claude-Design-Produkt tatsächlich konkrete Regeln entwickelt: gegen Gradient-Orbs-als-KI-Metapher, gegen CSS-Silhouetten als Produktfotos, für das Einholen realer Brand Assets vor dem ersten Pixel. Dieses Wissen ist empirisch wertvoll. Aber es ist nicht zitierfähig, nicht versioniert, und nicht durch externe Experten validiert. Es ist eine Momentaufnahme eines kommerziellen System-Prompts.

<div class="callout">
<div class="callout__title">Kernproblem: Provenienz ≠ Methodik</div>
„Adapted from Anthropic's internal Design system prompt" ist eine ehrliche Aussage — aber sie beschreibt eine Quelle, keine Methodik. Ein extrahierter System-Prompt ist nicht dasselbe wie Norman & Draper (1986), Nielsen (1994) oder Tidwell (2010). Er kann richtig liegen, er kann irren, er kann veralten — und keines dieser Szenarien lässt sich von außen überprüfen. Studierende sollten verstehen, dass „von Anthropic stammend" keine unabhängige Validierung ersetzt, sondern nur eine andere Form von Autorität durch Assoziation darstellt.
</div>

## Was der Skill inhaltlich liefert

Jenseits der Provenienzfrage lohnt ein genauer Blick auf die Struktur. Der Skill ist architektonisch sauber aufgebaut:

Neun Referenzdateien decken Fact Verification, Brand-Asset-Protokoll, Design-Direktionen, Anti-Slop-Regeln, Output-Formate, React/Babel-Pinning und Verifikationschecklisten ab. Das ist mehr strukturelle Disziplin als die meisten Community-Skills aufweisen. Der Skill benennt nicht nur Kategorien — er gibt konkrete Entscheidungsregeln. Das Anti-Slop-Kapitel zum Beispiel listet explizite Verbote: keine Gradient-Orbs für KI, keine CSS-Silhouetten als Produktfotos, keine aggressiven Verläufe. Diese Regeln sind aus echten Mustern destilliert und damit direkt lehrbar.

Die Referenz auf zehn Designphilosophien aus fünf Schulen (Swiss Editorial, Kenya Hara Minimalism, Brutalist Web u.a.) ist inhaltlich solide. Diese Schulen sind real und historisch verankert. Ein Advisor Mode, der bei vagen Briefings drei differenzierte Richtungen vorschlägt, ist methodisch durchdacht — auch wenn die didaktische Aufbereitung fehlt.

## Die Stärke des Skills: Testinfrastruktur

Was diesen Skill von der großen Masse der Community-Skills unterscheidet, ist die `test-prompts.json` — sechs realistische Szenarien, jeweils getaggt mit den Guardrails, die sie triggern sollen. Dazu kommen drei browseröffnbare Demo-HTML-Dateien: ein Pitch-Deck im Swiss-Editorial-Stil, ein Design-Canvas mit vier Hero-Varianten aus verschiedenen Schulen, ein interaktiver iOS-Prototyp mit Live-State.

Das ist ein für dieses Ökosystem seltenes Maß an Nachvollziehbarkeit. Man muss keinem Abstract vertrauen — man kann öffnen, klicken, prüfen. Für den Unterricht ist das ein erheblicher Vorteil: Es gibt konkrete Referenzoutputs, die zeigen, was der Skill produzieren soll, und gegen die neue Outputs geprüft werden können.

## Was fehlt: Wartbarkeit und methodischer Rahmen

Zwei Commits. Keine Releases. Kein Changelog. Der Maintainer jiji262 ist ein chinesischer Entwickler, bekannt für Tools wie einen Douyin-Downloader und eine Claude-Code-Quellcode-Analyse. Design-Background ist nicht verifizierbar. Das Repository dankt der Community linux.do — einem chinesischsprachigen Tech-Forum — für die Inspiration.

Das bedeutet nicht, dass der Inhalt schlecht ist. Aber es bedeutet: Wenn Anthropic seinen System-Prompt für Claude Design ändert (was bei einem aktiv entwickelten Produkt wahrscheinlich ist), veraltet dieser Skill ohne erkennbaren Mechanismus für Updates. Die Abhängigkeit von einem extrahierten, inoffiziellen Source macht Wartung strukturell schwierig — der Maintainer hat keinen privilegierten Zugang zur Quelle.

Der UX-methodische Rahmen ist ebenfalls dünn. Es gibt keine Referenz auf Norman, Nielsen, WCAG oder irgendein anerkanntes Evaluationsframework. Die Qualität der Outputs hängt ausschließlich davon ab, wie gut Anthropics ursprüngliche interne Regeln waren — und diese sind für den Benutzer nicht verifizierbar.

## Empfehlung für den Unterrichtseinsatz

Dieser Skill eignet sich gut als Beispiel für zwei Unterrichtsgespräche. Erstens: Was bedeutet Provenienz? „Von Anthropic stammend" klingt wie ein Qualitätsmerkmal — aber extrahierte System-Prompts sind weder peer-reviewed noch stabil. Die Frage „Woher weiß das der Skill?" führt zu einer produktiven Diskussion über den Unterschied zwischen Autorität durch Assoziation und Autorität durch Verifikation.

Zweitens: Was macht eine gute Testinfrastruktur aus? Die `test-prompts.json` und die drei Demos sind ein positives Beispiel für Nachvollziehbarkeit. Studierende können an diesem Skill üben, was es bedeutet, einen Skill nicht nur zu lesen, sondern zu prüfen.

Für produktiven Einsatz gilt: Die Anti-Slop-Regeln und Output-Format-Playbooks sind direkt verwendbar. Der Skill gibt nützliche, konkrete Heuristiken für HTML-Artefakte. Wer ihn einsetzt, sollte sich aber bewusst sein, dass er keine UX-Methodik im akademischen Sinne liefert — sondern destilliertes Produktionswissen aus einem kommerziellen KI-System.
