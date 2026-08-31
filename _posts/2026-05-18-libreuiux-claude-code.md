---
layout: post
title: "LibreUIUX-Claude-Code: Quantität als Qualitätssignal — ein Trugschluss in 152 Akten"
date: 2026-05-18
category: Skill-Evaluation
skill_reviewed: "HermeticOrmus/LibreUIUX-Claude-Code"
verdict: ablehnen
reading_time: 10
last_audited: "18. Mai 2026"

skill_scores:
  methodische_fundierung: 2
  methodische_fundierung_note: "Die einzige methodische Quelle ist ein Karpathy-Tweet über LLM-Agenten — keine UX-Literatur, keine Designprinzipien, keine nachvollziehbare Fachbasis."
  transparenz: 2
  transparenz_note: "Interne Widersprüche zwischen Titelzeile (67 Agenten) und README (152 Agenten), falsches TypeScript-Badge bei einer Shell/Python-Codebasis, keine Kommunikation von Grenzen."
  validierbarkeit: 2
  validierbarkeit_note: "Namenlose Entwicklerzitate, interne Case-Study-Links ohne Screenshots, nicht reproduzierbare Versprechen ('Perfect. First try. Every time.')."
  wartbarkeit: 3
  wartbarkeit_note: "Autor identifizierbar (Diego Bodart), MIT-Lizenz vorhanden, letzter Commit April 2026 — aber Einzelperson, 5 GitHub-Follower, null externe Beiträge."

tags:
  - scope-inflation
  - quantität-vs-qualität
  - methodische-leerstelle
  - prompt-engineering
  - designsysteme
  - transparenz
  - lehrbeispiel
---

`HermeticOrmus/LibreUIUX-Claude-Code` positioniert sich als „Complete UI/UX system for Claude Code" und belegt diese Behauptung mit Zahlen: 152 Agenten, 70 Plugins, 76 Commands, 74 Skills. Das Repository zählt damit zu den umfangreichsten öffentlich verfügbaren Claude-Skill-Paketen überhaupt. Allein dieser Umstand macht es für eine Evaluation interessant. Nicht weil Größe ein Qualitätsmerkmal wäre, sondern weil sie es so offensichtlich nicht ist.

Dieses Repository ist der angekündigte Lehrfall für den Fehlschluss, dem wir in dieser Serie immer wieder begegnen: dass mehr Inhalt tiefere Qualität bedeutet.

## Was das Repository verspricht

Die Einleitung des README beginnt mit einem Andrej-Karpathy-Zitat aus Dezember 2025, in dem er die neue Vokabular-Schicht der KI-gestützten Entwicklung beschreibt: „agents, subagents, prompts, contexts, memory, modes, permissions, tools, plugins, skills, hooks, MCP." LibreUIUX, so die Lesart von HermeticOrmus alias Diego Bodart von Ormus Solutions, liefere die UI/UX-Infrastruktur für dieses neue Paradigma.

Das ist ein ehrgeiziger Rahmen. Und er hat einen bestimmten Effekt: Er positioniert ein Prompt-Paket als Teil einer historischen Verschiebung in der Softwareentwicklung. Wer das Repository ablehnt, lehnt damit gleichsam Karpathys Vision ab. Diese Rahmung ist rhetorisch geschickt, aber methodisch leer.

## Der Inhalt: Was tatsächlich enthalten ist

Ein Blick auf die Plugin-Liste zeigt das eigentliche Problem. Unter den 70 Plugins, die angeblich ein „Complete UI/UX system" bilden, finden sich:

- `arm-cortex-microcontrollers`: Embedded Systems
- `blockchain-web3`: Smart Contracts, DeFi
- `quantitative-trading`: Algorithmisches Trading
- `julia-development`: Programmiersprache Julia
- `kubernetes-operations`: Kubernetes-Management
- `jvm-languages`: Java, Kotlin, Scala

Ein UI/UX-System, das Kubernetes-Operationen und algorithmischen Handel enthält, ist kein UI/UX-System. Es ist eine Sammlung von Prompts, die aus verschiedenen Quellen zusammengetragen und unter einem UI/UX-Label vermarktet wurde.

Der eigentliche designspezifische Kern ist das Plugin `design-mastery`, und der ist nicht falsch. Das README erklärt die zentrale Einsicht klar: Claude antwortet besser auf präzise Designsprache als auf vage Ästhetik. „Change shadow-md to shadow-xl" funktioniert, „make it pop" nicht. Das ist eine reale und nützliche Beobachtung über das Verhalten von Sprachmodellen bei Design-Prompts.

Aber diese Einsicht ist kein Design-Framework. Sie ist Prompt-Engineering-Hygiene.

<div class="callout">
<div class="callout__title">Das Kernproblem: Quantität simuliert Qualität</div>
152 Agenten, die ARM-Microcontroller, Kubernetes-Cluster und algorithmisches Trading abdecken, können kein kohärentes UI/UX-System bilden. Die Breite ist kein Feature, sie ist das Problem. In einem Repository dieser Größe kann kein einzelner Maintainer sicherstellen, dass die Inhalte methodisch korrekt, aktuell und konsistent sind. Was entsteht, ist nicht ein „Complete UI/UX system", sondern eine Textwüste, in der nützliche Teile unter dem Gewicht irrelevanter Inhalte begraben werden. Für Studierende ist das die wichtigste Beobachtung: Viele Dateien, viele Begriffe und eine selbstbewusste Einleitung erzeugen das Gefühl von Substanz, ohne sie einzulösen.
</div>

## Interne Widersprüche als Warnsignal

Bevor man inhaltlich evaluiert, sollte man die interne Konsistenz eines Repositories prüfen. LibreUIUX besteht diesen Test nicht.

**Widerspruch 1, die Agentenzahl:** Der GitHub-Titel lautet „67 specialized agents". Der README-Body nennt durchgängig „152 agents". Die Shields-Badges zeigen ebenfalls 152. Eine dieser Zahlen ist falsch, und welche lässt sich aus dem README allein nicht klären. Das ist kein Tippfehler. Es ist eine Inkongruenz zwischen Marketing-Metadaten und Dokumentationstext, die zeigt, dass das Repository nicht intern abgestimmt wurde.

**Widerspruch 2, das Technologie-Badge:** Das README trägt ein TypeScript-Badge mit dem blauen TypeScript-Logo. Die tatsächliche Sprachverteilung laut GitHub liegt bei 78,1 % Shell und 21,9 % Python, ohne jedes TypeScript. Das Badge ist entweder manuell gesetzt ohne Abgleich mit dem tatsächlichen Code, oder es wurde aus einem anderen Kontext kopiert.

**Widerspruch 3, „Complete UI/UX system":** Ein System, das vollständig ist, muss eine erkennbare Grenze haben. LibreUIUX hat keine, es schließt fortlaufend neue Domänen ein. „Komplett" bedeutet hier: alles, was der Autor bisher hinzugefügt hat.

Diese drei Widersprüche sind kein Zufall. Sie zeigen ein Muster: Das Repository wurde schnell aufgebaut und nicht systematisch gepflegt.

## Was fehlt: UX-Methodologie

Das README zitiert Karpathy und verweist auf Shadcn, Tailwind, Material Design 3 und Apples Human Interface Guidelines. Keine dieser Referenzen erscheint als methodische Grundlage in den Skill-Dateien selbst. Material Design und HIG werden im resources-Verzeichnis als Leselinks aufgeführt, nicht als integrierte Prinzipien.

Zum Vergleich: `mastepanoski/claude-skills`, im April 2026 evaluiert, portiert Nielsen-Heuristiken, WCAG und Don Normans Prinzipien explizit in ausführbare Skill-Instruktionen. Dort lässt sich nachvollziehen, welche Heuristik eine Empfehlung begründet. Bei LibreUIUX ist die methodische Quelle die persönliche Feldbeobachtung des Autors: „I spent two weeks fighting this." Das ist ein Erfahrungsbericht, kein Design-Framework.

Die Nennung von Karpathy erfüllt dabei eine ähnliche Funktion wie Name-Dropping in anderen Repositories. Sie verleiht dem Inhalt die Autorität einer anerkannten Persönlichkeit, ohne deren Erkenntnisse inhaltlich zu portieren. Karpathy hat etwas über LLM-Agenten im Allgemeinen gesagt. Das begründet keine spezifische Methodologie für UI/UX-Design.

## Die Validierbarkeit: Unprüfbare Versprechen

Das README enthält zwei Arten von Validierungsversuch, die beide ins Leere führen.

Die „Real Developer Experiences", zwei Zitate frustrierter Entwickler, sind namenlos, datumlos und quellenlos. Sie könnten aus Foren stammen, aus dem Gedächtnis des Autors, oder selbst verfasst sein. Es gibt keine Möglichkeit, das zu prüfen.

Die verlinkten Case Studies zu SaaS Dashboard und E-commerce Product Page führen zu internen Repository-Dateien, die keine Screenshots, keine messbaren Outcomes und keine Before/After-Vergleiche enthalten. Was als Evidenz präsentiert wird, ist Dokumentation ohne Vergleichswert.

Besonders auffällig ist die Formulierung im „Field Notes"-Abschnitt: „Perfect. First try. Every time." Kein Prompt-System liefert perfekte Ergebnisse auf Anhieb bei jedem Versuch. Diese Formulierung ist als motivierender Ton gemeint, aber sie macht eine Aussage über Reproduzierbarkeit, die nicht stimmt und nicht stimmen kann.

## Was der Autor richtig macht

Es wäre unfair, das Repository ausschließlich als Problem darzustellen. Die zentrale praktische Einsicht ist real und lehrreich: Sprachmodelle brauchen spezifische, tokenbasierte Beschreibungen statt ästhetischer Adjektive. Die Analogie „Koordinaten statt Wegbeschreibung" trifft etwas Wesentliches über die Natur von Prompt-Engineering.

Das VOICE_GUIDE.md und die CONTRIBUTING.md zeigen, dass der Autor über Codekultur nachgedacht hat. Die MIT-Lizenz ist klar, die Installationsanleitung ist nachvollziehbar strukturiert, und das Repository wurde zuletzt im April 2026 aktualisiert. Es ist nicht verlassen.

Die Empfehlung, Design-Tokens und Tailwind-Klassen präzise zu benennen statt vage Ästhetik zu beschreiben, ist für Entwickler ohne Design-Vokabular ein sinnvoller praktischer Einstieg.

## Wartbarkeit: Identifizierbarer Autor, strukturell fragil

Diego Bodart ist unter dem Pseudonym HermeticOrmus identifizierbar und verlinkt auf ormus.solutions. Er hat mehrere thematisch ähnliche Repositories veröffentlicht: `claude-code-for-ceos`, `LibreMobileDev-Claude-Code`, `claude-code-guide`, `design-mastery-claude-code`. Das Muster ist erkennbar: ein einzelner Autor, der in kurzer Zeit viele thematisch ähnliche Repositories anlegt.

Zum Zeitpunkt dieser Evaluation hat der Autor 5 GitHub-Follower. Das Repository hat 22 Stars, 2 Forks, null offene Issues und null Pull Requests. Es gibt keine externe Community, die Fehler meldet oder Inhalte verbessert. Was immer in den Skill-Dateien methodisch falsch ist, bleibt falsch. Es gibt keine Korrekturroutine.

Das ist das eigentliche Wartbarkeitsproblem. Nicht ob der Autor erreichbar ist, sondern ob das System klein genug ist, um von einer Einzelperson sinnvoll gepflegt zu werden. 152 Agenten in 70 Plugins können nicht mit 21 Commits und null externen Beiträgern substanziell gewartet werden.

## Empfehlung für den Unterrichtseinsatz

LibreUIUX-Claude-Code ist kein brauchbarer Designkurs-Skill. Als Analysegegenstand hat es jedoch echten Lehrwert.

Im Unterricht lassen sich an diesem Repository drei grundlegende kritische Fragen einüben:

**1. Konsistenzprüfung vor Inhaltsanalyse.** Wenn ein Repository in den ersten zwei Bildschirmen zwei verschiedene Zahlen für dieselbe Eigenschaft nennt, was sagt das über die interne Qualitätssicherung? Wie viel Vertrauen setzt man dann in die Inhalte?

**2. Der Scope-Inflation-Test.** Was muss ein Skill-Paket enthalten, damit es als „Complete UI/UX system" gilt? Und was schließt ein vollständiges UI/UX-System aus? Diese Fragen lassen sich an der Plugin-Liste konkret diskutieren.

**3. Die Quelle hinter dem Versprechen.** Was unterscheidet einen Skill, der sagt „sei spezifisch mit Tailwind-Klassen", von einem Skill, der erklärt warum Spezifität bei Sprachmodellen funktioniert und für welche Designprobleme sie nicht ausreicht?

Das Repository zeigt, wie ein Prompt-Paket aussieht, das Infrastruktur-Rhetorik mit Design-Vokabular kombiniert, ohne beides einzulösen. Das zu erkennen ist eine Kompetenz, die Design-Praktikerinnen und -Studierenden im KI-Zeitalter nützlicher ist als jeder einzelne Skill im Paket.
