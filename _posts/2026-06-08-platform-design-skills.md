---
layout: post
title: "platform-design-skills: Wenn Quellenarbeit wirklich ernst gemeint ist — und was dann noch fehlt"
date: 2026-06-08
category: Skill-Evaluation
skill_reviewed: "ehmo/platform-design-skills"
verdict: vertrauen
reading_time: 12
last_audited: "8. Juni 2026"

skill_scores:
  methodische_fundierung: 5
  methodische_fundierung_note: "Apple HIG (2025) als PDF im Repository, Material Design 3 und WCAG 2.2 mit Direktlinks, drei HCI-Publikationen mit verifizierbaren URLs zu archive.org und PMC — methodisch das Sorgfältigste im bisher evaluierten Ökosystem"
  transparenz: 4
  transparenz_note: "Plattformspezifische 'Use when'-Definitionen kommunizieren Scope klar; keine explizite Warnung vor LLM-Grenzen bei formaler Compliance-Prüfung; anonymer Maintainer ohne verifizierbaren Hintergrund"
  validierbarkeit: 4
  validierbarkeit_note: "92 Commits, CHANGELOG.md, PR-Guidelines fordern Before/After-Beispiele; individuelle rules/-Dateien je Plattform ermöglichen gezielte Prüfung — aber kein automatisiertes Testframework"
  wartbarkeit: 3
  wartbarkeit_note: "MIT-Lizenz, 354 Stars, 20 Forks, aktive Entwicklung mit durchdachten PR-Richtlinien — aber anonymer Einzelmaintainer 'ehmo' ohne veröffentlichte Identität oder Community-Backup"

tags:
  - apple-hig
  - material-design-3
  - wcag-2-2
  - plattform-guidelines
  - quellenarbeit
  - portierungsfrage
  - positives-beispiel
  - anonymer-maintainer
  - vertrauen-beispiel
---

In der Bewertungsgeschichte dieses Blogs kehrte ein methodisches Kernproblem immer wieder. Skills nannten Prinzipien und erklärten nicht, woher sie stammen. `ehmo/platform-design-skills` ist das erste Repository dieser Reihe, das dieses Problem systematisch löst. Offen bleibt eine andere Frage. Was bedeutet es, alle richtigen Quellen zu haben, und wie weit trägt das?

354 GitHub-Stars, 20 Forks, 92 Commits. Im Stammverzeichnis liegt auch `Apple_HIG.pdf`. Zufall ist das nicht. Es ist eine methodische Aussage.

## Was das Repository verspricht

Über 450 Regeln für acht Apple-Plattformen umfasst der Skill heute. Dazu kommen Android und Web. Abgedeckt sind iOS, iPadOS, macOS, watchOS, visionOS und tvOS. Das README nennt an einer Stelle „300+" und an anderer „450+". Mit dem Projekt wächst also die Zahl. Jede Plattform hat eine eigene Verzeichnisstruktur mit `SKILL.md`, `metadata.json`, `AGENTS.md` und einem `rules/`-Ordner mit Einzeldateien. Allgemein-Design ist nicht das Ziel. Gemeint ist plattformspezifische Compliance mit publizierten Herstellerrichtlinien.

Für iOS gelten die Apple Human Interface Guidelines. Für Android gilt Material Design 3. Für Web gelten WCAG 2.2 und MDN Web Docs. Die Quellen stehen mit URLs im README. Alle Links führen direkt zu den offiziellen Dokumentationen.

## Die Quellen, und was sie methodisch bedeuten

Der Skill trennt drei Kategorien von Quellen. Schon das ist ungewöhnlich.

Erstens die normativen Plattformquellen. Dazu zählen die Apple HIG in der Fassung von 2025, Material Design 3, WCAG 2.2 und MDN. Meinungen sind das nicht. Es sind offizielle Spezifikationen mit Versionsbezeichnung und konkreten Anforderungen. Das zählt.

Zweitens die HCI-Forschungsliteratur als sekundäre Referenz. Card, Moran und Newell schrieben 1983 *The Psychology of Human-Computer Interaction*. Verlinkt ist archive.org. Newell und Card verfassten *Prospects for Psychological Science in HCI*. Das PDF stammt aus der Universitätsbibliothek der Carnegie Mellon. Jastrzembski und Charness untersuchten 2007 das Model Human Processor bei älteren Nutzern. Verlinkt ist PubMed Central.

Der README-Text klärt den epistemischen Status dieser Quellen: „These are secondary references used to sharpen guidance around recognition over recall, visible waiting states, and input effort. They do not override Apple HIG, Material, or WCAG." Die Fachliteratur kennt diese Unterscheidung. Normative Quellen legen fest, was gelten soll. Erklärende Quellen begründen, warum es gilt. In einem Skill-Repository ist es außergewöhnlich, diese Hierarchie offen zu benennen. Das ist selten.

Drittens liegt die Apple HIG als zusammengefasstes PDF im Repository selbst. Wer die Portierungsqualität prüfen will, muss die Quelle nicht erst suchen. Kurz ist der Weg zur Prüfung.

## Die Portierungsfrage

<div class="callout">
<div class="callout__title">Die entscheidende Lücke</div>
Gute Quellen garantieren keine korrekte Portierung. Die Apple Human Interface Guidelines 2025 sind ein umfangreiches Dokument mit hunderten Seiten. Apple aktualisiert es laufend. Material Design 3 unterscheidet sich erheblich von Material Design 2. WCAG 2.2 baut auf WCAG 2.1 auf und führt neue Erfolgskriterien ein. Das Repository behauptet, über 450 Regeln aus diesen Quellen destilliert zu haben. Ob jede Regel korrekt portiert wurde, lässt sich nur durch systematischen Quellvergleich prüfen. Entspricht „Navigation Bar unter iOS" wirklich dem, was Apple 2025 spezifiziert? Eine Evaluation kann diese Arbeit nicht vollständig leisten. Sie ist trotzdem die einzige, die methodische Fundierung vollständig verifizierbar macht.
</div>

Das ist kein Vorwurf an den Autor. Jede Portierung stößt an diese strukturelle Grenze, so sorgfältig sie auch entstanden ist. Ein Skill zitiert die Apple HIG korrekt und destilliert eine Regel falsch. Das ist methodisch problematischer als ein Skill ohne jede Quellenangabe. Er suggeriert dem Nutzer, dass er nicht mehr prüfen muss. Das ist trügerisch.

Für den Unterrichtseinsatz ist das der zentrale Lernmoment. Eine Quellenangabe nimmt die Verantwortung zur Prüfung nicht ab. Sie zeigt nur, wo die Prüfung beginnt.

## Scope-Klarheit als pädagogisches Modell

Für jede der acht Plattformen gibt es im README eine „Use when"-Sektion. Sie ist ungewöhnlich präzise. Für iOS heißt es zuerst „Use when: Building SwiftUI or UIKit interfaces for iPhone". Es folgen „Reviewing iOS app code for HIG compliance", „Choosing between iOS navigation patterns" und „Implementing accessibility, Dark Mode, Dynamic Type". Das sind keine Marketing-Formulierungen. Es sind Einsatzbedingungen. Sie helfen, den Skill nicht falsch einzusetzen.

Der Autor trennt iOS und iPadOS in zwei Skills. Viele Skills fassen beide zusammen. Beide Plattformen teilen eine Codebase. Ihre Interaktionsparadigmen, Multitasking-Modelle und Eingabemodalitäten unterscheiden sich aber. Diese Unterscheidung in der Skill-Architektur abzubilden ist eine methodische Entscheidung mit Substanz.

Auch visionOS für die Apple Vision Pro ist zeitgemäß. Die HIG für visionOS weicht stärker von traditionellen mobilen Paradigmen ab als fast jede andere Plattformspezifikation. Ein Skill dafür zeigt, dass der Autor die Plattform-Dokumentation tatsächlich verfolgt. Er liest mit.

## Wartbarkeit und das Anonymitätsproblem

354 Stars und 20 Forks zeigen echte Community-Resonanz. Die 92 Commits belegen aktive Entwicklung. Die PR-Guidelines sind durchdacht. Jeder PR behandelt einen Themenbereich. Die PR-Beschreibung braucht Before/After-Beispiele. Für Portierungsänderungen gelten eigene Prüfkriterien.

Und doch bleibt der Autor „ehmo". Es gibt keinen verifizierbaren Nachnamen, kein LinkedIn, kein Twitter und keine Referenz auf professionelle Tätigkeit. Im GitHub-Profil stehen keine weiteren Repositories, keine Beschreibung und keine Organisationszugehörigkeit. Fehler ist das keiner. Es ist eine Einschränkung. Institutionen müssen die Skill-Qualität gegenüber Stakeholdern begründen. Für sie ist „MIT-lizenzierter GitHub-Account ohne Impressum" kein ausreichendes Vertrauenssignal. Das reicht nicht.

Eine Arbeitsdisziplin zeigt zugleich die Struktur des Repositories. Sie deutet auf einen professionellen Hintergrund hin. Belegt ist das durch die PR-Richtlinien, die Quellenunterscheidung und die Changelog-Pflege. Der anonyme Maintainer kennt offensichtlich Dokumentationsprojekte und Versionierung. Offen bleibt die Frage der Identität. An der evaluierbaren Qualität des Inhalts ändert sie wenig.

## Was das Repository von fast allem anderen unterscheidet

Zur Einordnung drei Beobachtungen. Bisher zitierte in dieser Evaluationsreihe kein Repository HCI-Forschungsliteratur mit Direktlinks auf Originalquellen. Keines nahm eine Quelldatei physisch auf, wie hier die Apple_HIG.pdf. Keines unterschied explizit zwischen normativen und sekundären Quellen.

Klein sind diese Unterschiede nicht. Es sind strukturelle Qualitätsmerkmale. Der Autor kennt die Grenze zwischen „gut klingendem Prinzip" und „verifizierbarer Anforderung". Er respektiert sie.

Zuletzt evaluiert wurde `szilu/ux-designer-skill`. Der Skill behauptet 19 Quellen und verlinkt keine davon direkt. Erheblich ist der methodische Abstand.

## Empfehlung für den Unterrichtseinsatz

`ehmo/platform-design-skills` eignet sich als positives Gegenbeispiel zu den meisten anderen Skills dieser Reihe. Ich empfehle den Einsatz in zwei Kontexten.

Erstens als Modell für Quellenarbeit im Skill-Kontext. Die Quellenstruktur, die Hierarchie normativer und sekundärer Referenzen und die physische Beigabe der Apple HIG als PDF taugen als Benchmark für eigene Skill-Entwicklung.

Zweitens als Einstieg in die Portierungsfrage. Man wählt zwei oder drei Regeln aus dem iOS-Skill. Man schlägt die entsprechenden Abschnitte in der Apple HIG auf und vergleicht. Überschaubar ist die Übung. Sie zeigt, wie viel Interpretationsraum zwischen „Quelle vorhanden" und „korrekt portiert" bleibt.

Der Skill verdient das Urteil `vertrauen`. Methodisch ist er das Sorgfältigste, was dieses Ökosystem bisher hervorgebracht hat. Den einzigen echten Vorbehalt liefert der anonyme Einzelmaintainer. Wer plattformspezifische Designguide-Compliance in Claude Code einsetzen will, findet hier den besten verfügbaren Ausgangspunkt. Besser geht es derzeit nicht.
