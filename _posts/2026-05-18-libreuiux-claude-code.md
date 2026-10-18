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
  methodische_fundierung_note: "Die einzige methodische Quelle ist ein Karpathy-Tweet über LLM-Agenten. UX-Literatur, Designprinzipien und eine nachvollziehbare Fachbasis fehlen."
  transparenz: 2
  transparenz_note: "Die Titelzeile nennt 67 Agenten, das README 152. Das TypeScript-Badge steht bei einer Shell/Python-Codebasis. Grenzen werden nicht kommuniziert."
  validierbarkeit: 2
  validierbarkeit_note: "Die Entwicklerzitate sind namenlos. Die Case-Study-Links sind intern und ohne Screenshots. Versprechen wie 'Perfect. First try. Every time.' sind nicht reproduzierbar."
  wartbarkeit: 3
  wartbarkeit_note: "Der Autor ist identifizierbar (Diego Bodart). Die MIT-Lizenz ist vorhanden. Der letzte Commit stammt vom April 2026. Dahinter steht aber eine Einzelperson mit 5 GitHub-Followern und null externen Beiträgen."

tags:
  - scope-inflation
  - quantität-vs-qualität
  - methodische-leerstelle
  - prompt-engineering
  - designsysteme
  - transparenz
  - lehrbeispiel
---

`HermeticOrmus/LibreUIUX-Claude-Code` positioniert sich als „Complete UI/UX system for Claude Code". Zahlen sollen das belegen: 152 Agenten, 70 Plugins, 76 Commands, 74 Skills. Damit zählt das Repository zu den umfangreichsten öffentlich verfügbaren Claude-Skill-Paketen überhaupt. Schon das macht es für eine Evaluation interessant. Größe ist kein Qualitätsmerkmal. Hier ist das besonders offensichtlich.

Dieses Repository ist der angekündigte Lehrfall für einen Fehlschluss, dem wir in dieser Serie immer wieder begegnen. Es ist der Glaube, dass mehr Inhalt tiefere Qualität bedeutet.

## Was das Repository verspricht

Die Einleitung des README beginnt mit einem Andrej-Karpathy-Zitat aus Dezember 2025. Er beschreibt darin die neue Vokabular-Schicht der KI-gestützten Entwicklung: „agents, subagents, prompts, contexts, memory, modes, permissions, tools, plugins, skills, hooks, MCP." LibreUIUX liefere die UI/UX-Infrastruktur für dieses neue Paradigma. So liest es HermeticOrmus alias Diego Bodart von Ormus Solutions.

Der Rahmen ist ehrgeizig. Er hat einen bestimmten Effekt. Ein Prompt-Paket erscheint als Teil einer historischen Verschiebung in der Softwareentwicklung. Wer das Repository ablehnt, lehnt damit gleichsam Karpathys Vision ab. Rhetorisch ist diese Rahmung geschickt. Methodisch ist sie leer.

## Der Inhalt: Was tatsächlich enthalten ist

Ein Blick auf die Plugin-Liste zeigt das eigentliche Problem. Unter den 70 Plugins bilden angeblich alle ein „Complete UI/UX system". Darunter:

- `arm-cortex-microcontrollers`: Embedded Systems
- `blockchain-web3`: Smart Contracts, DeFi
- `quantitative-trading`: Algorithmisches Trading
- `julia-development`: Programmiersprache Julia
- `kubernetes-operations`: Kubernetes-Management
- `jvm-languages`: Java, Kotlin, Scala

Mit Kubernetes-Operationen und Handelsalgorithmen ist es kein UI/UX-System. Es ist eine Sammlung von Prompts aus verschiedenen Quellen. Vermarktet wird sie unter einem UI/UX-Label.

Der designspezifische Kern ist das Plugin `design-mastery`. Es ist nicht falsch. Das README erklärt die zentrale Einsicht klar. Claude antwortet besser auf präzise Designsprache als auf vage Ästhetik. „Change shadow-md to shadow-xl" funktioniert, „make it pop" nicht. Das ist eine reale und nützliche Beobachtung über das Verhalten von Sprachmodellen bei Design-Prompts.

Ein Design-Framework ist diese Einsicht trotzdem nicht. Sie ist Prompt-Engineering-Hygiene.

<div class="callout">
<div class="callout__title">Das Kernproblem: Quantität simuliert Qualität</div>
152 Agenten für ARM-Microcontroller, Kubernetes-Cluster und algorithmisches Trading bilden kein kohärentes UI/UX-System. Die Breite ist kein Feature. Sie ist das Problem. In einem Repository dieser Größe kann kein einzelner Maintainer die Inhalte sichern. Methodische Korrektheit, Aktualität und Konsistenz bleiben offen. Es entsteht kein „Complete UI/UX system". Es entsteht eine Textwüste. Nützliche Teile liegen darin unter dem Gewicht irrelevanter Inhalte begraben. Für Studierende ist das die wichtigste Beobachtung. Viele Dateien, viele Begriffe und eine selbstbewusste Einleitung erzeugen das Gefühl von Substanz. Eingelöst wird sie nicht.
</div>

## Interne Widersprüche als Warnsignal

Vor der inhaltlichen Evaluation sollte man die interne Konsistenz eines Repositories prüfen. LibreUIUX besteht diesen Test nicht.

**Widerspruch 1, die Agentenzahl.** Der GitHub-Titel lautet „67 specialized agents". Der README-Body nennt durchgängig „152 agents". Die Shields-Badges zeigen ebenfalls 152. Eine dieser Zahlen ist falsch. Welche, lässt sich aus dem README allein nicht klären. Ein Tippfehler ist das nicht. Es ist eine Inkongruenz zwischen Marketing-Metadaten und Dokumentationstext. Sie zeigt, dass das Repository nicht intern abgestimmt wurde.

**Widerspruch 2, das Technologie-Badge.** Das README trägt ein TypeScript-Badge mit dem blauen TypeScript-Logo. Die Sprachverteilung laut GitHub liegt bei 78,1 % Shell und 21,9 % Python. TypeScript kommt nicht vor. Das Badge wurde entweder manuell gesetzt, ohne Abgleich mit dem Code. Oder es wurde aus einem anderen Kontext kopiert.

**Widerspruch 3, „Complete UI/UX system".** Ein vollständiges System braucht eine erkennbare Grenze. LibreUIUX hat keine. Es schließt fortlaufend neue Domänen ein. „Komplett" bedeutet hier: alles, was der Autor bisher hinzugefügt hat.

Diese drei Widersprüche sind kein Zufall. Sie zeigen ein Muster. Das Repository wurde schnell aufgebaut und nicht systematisch gepflegt.

## Was fehlt: UX-Methodologie

Das README zitiert Karpathy und verweist auf Shadcn, Tailwind, Material Design 3 und Apples Human Interface Guidelines. Keine dieser Referenzen erscheint als methodische Grundlage in den Skill-Dateien selbst. Material Design und HIG stehen im resources-Verzeichnis als Leselinks. Als integrierte Prinzipien tauchen sie nicht auf.

Zum Vergleich dient `mastepanoski/claude-skills`, im April 2026 evaluiert. Dieses Paket portiert Nielsen-Heuristiken, WCAG und Don Normans Prinzipien explizit in ausführbare Skill-Instruktionen. Dort lässt sich jede Empfehlung auf ihre Heuristik zurückführen. Bei LibreUIUX ist die methodische Quelle die persönliche Feldbeobachtung des Autors: „I spent two weeks fighting this." Das ist ein Erfahrungsbericht und kein Design-Framework.

Die Nennung von Karpathy erfüllt eine ähnliche Funktion wie Name-Dropping in anderen Repositories. Sie verleiht dem Inhalt die Autorität einer anerkannten Persönlichkeit. Deren Erkenntnisse werden inhaltlich nicht portiert. Karpathy hat etwas über LLM-Agenten im Allgemeinen gesagt. Eine spezifische Methodologie für UI/UX-Design begründet das nicht.

## Die Validierbarkeit: Unprüfbare Versprechen

Das README enthält zwei Arten von Validierungsversuch. Beide führen ins Leere.

Die „Real Developer Experiences" bestehen aus zwei Zitaten frustrierter Entwickler. Sie sind namenlos, datumlos und quellenlos. Sie könnten aus Foren stammen oder aus dem Gedächtnis des Autors. Sie könnten auch selbst verfasst sein. Prüfen lässt sich das nicht.

Die verlinkten Case Studies zu SaaS Dashboard und E-commerce Product Page führen zu internen Repository-Dateien. Diese enthalten keine Screenshots, keine messbaren Outcomes und keine Before/After-Vergleiche. Als Evidenz wird Dokumentation ohne Vergleichswert präsentiert.

Besonders auffällig ist die Formulierung im „Field Notes"-Abschnitt: „Perfect. First try. Every time." Kein Prompt-System liefert bei jedem Versuch auf Anhieb perfekte Ergebnisse. Der Satz ist als motivierender Ton gemeint. Er macht aber eine Aussage über Reproduzierbarkeit, die nicht stimmt und nicht stimmen kann.

## Was der Autor richtig macht

Es wäre unfair, das Repository ausschließlich als Problem darzustellen. Die zentrale praktische Einsicht ist real und lehrreich. Sprachmodelle brauchen spezifische, tokenbasierte Beschreibungen statt ästhetischer Adjektive. Die Analogie „Koordinaten statt Wegbeschreibung" trifft etwas Wesentliches über die Natur von Prompt-Engineering.

VOICE_GUIDE.md und CONTRIBUTING.md zeigen, dass der Autor über Codekultur nachgedacht hat. Die MIT-Lizenz ist klar. Die Installationsanleitung ist nachvollziehbar strukturiert. Das Repository wurde zuletzt im April 2026 aktualisiert. Verlassen ist es nicht.

Design-Tokens und Tailwind-Klassen präzise zu benennen, ist die Empfehlung des Autors. Für Entwickler ohne Design-Vokabular ist das ein sinnvoller praktischer Einstieg.

## Wartbarkeit: Identifizierbarer Autor, strukturell fragil

Diego Bodart ist unter dem Pseudonym HermeticOrmus identifizierbar und verlinkt auf ormus.solutions. Er hat mehrere thematisch ähnliche Repositories veröffentlicht: `claude-code-for-ceos`, `LibreMobileDev-Claude-Code`, `claude-code-guide`, `design-mastery-claude-code`. Das Muster ist erkennbar. Ein einzelner Autor legt in kurzer Zeit viele ähnliche Repositories an.

Zum Zeitpunkt dieser Evaluation hat der Autor 5 GitHub-Follower. Das Repository hat 22 Stars, 2 Forks, null offene Issues und null Pull Requests. Eine externe Community, die Fehler meldet oder Inhalte verbessert, gibt es nicht. Was in den Skill-Dateien methodisch falsch ist, bleibt falsch. Eine Korrekturroutine fehlt.

Das ist das eigentliche Wartbarkeitsproblem. Es geht nicht darum, ob der Autor erreichbar ist. Entscheidend ist, ob das System klein genug bleibt für die Pflege durch eine Einzelperson. 152 Agenten in 70 Plugins lassen sich mit 21 Commits und null externen Beiträgern nicht substanziell warten.

## Empfehlung für den Unterrichtseinsatz

LibreUIUX-Claude-Code ist kein brauchbarer Designkurs-Skill. Als Analysegegenstand hat es jedoch echten Lehrwert.

Im Unterricht lassen sich an diesem Repository drei grundlegende kritische Fragen einüben.

**1. Konsistenzprüfung vor Inhaltsanalyse.** Ein Repository nennt in den ersten zwei Bildschirmen zwei verschiedene Zahlen für dieselbe Eigenschaft. Was sagt das über die interne Qualitätssicherung? Wie viel Vertrauen setzt man dann in die Inhalte?

**2. Der Scope-Inflation-Test.** Was muss ein Skill-Paket enthalten, damit es als „Complete UI/UX system" gilt? Und was schließt ein vollständiges UI/UX-System aus? Diese Fragen lassen sich an der Plugin-Liste konkret diskutieren.

**3. Die Quelle hinter dem Versprechen.** Ein Skill sagt „sei spezifisch mit Tailwind-Klassen". Ein anderer erklärt, warum Spezifität bei Sprachmodellen funktioniert und wo sie bei Designproblemen nicht ausreicht. Worin liegt der Unterschied?

Das Repository zeigt ein Prompt-Paket, das Infrastruktur-Rhetorik mit Design-Vokabular kombiniert. Beides löst es nicht ein. Das zu erkennen, ist eine Kompetenz. Für Design-Praktikerinnen und -Studierende im KI-Zeitalter ist sie nützlicher als jeder einzelne Skill im Paket.
