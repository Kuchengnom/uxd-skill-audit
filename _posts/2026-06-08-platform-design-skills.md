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
  methodische_fundierung_note: "Apple HIG (2025) als PDF im Repository, Material Design 3 und WCAG 2.2 mit Direktlinks, drei HCI-Publikationen mit verifizierbaren URLs zu archive.org und PMC — methodisch das Sorgfaeltigste im bisher evaluierten Oekosystem"
  transparenz: 4
  transparenz_note: "Plattformspezifische 'Use when'-Definitionen kommunizieren Scope klar; keine explizite Warnung vor LLM-Grenzen bei formaler Compliance-Pruefung; anonymer Maintainer ohne verifizierbaren Hintergrund"
  validierbarkeit: 4
  validierbarkeit_note: "92 Commits, CHANGELOG.md, PR-Guidelines fordern Before/After-Beispiele; individuelle rules/-Dateien je Plattform ermoeglichen gezielte Pruefung — aber kein automatisiertes Testframework"
  wartbarkeit: 3
  wartbarkeit_note: "MIT-Lizenz, 354 Stars, 20 Forks, aktive Entwicklung mit durchdachten PR-Richtlinien — aber anonymer Einzelmaintainer 'ehmo' ohne veroeffentlichte Identitaet oder Community-Backup"

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

In der Bewertungsgeschichte dieses Blogs gab es bisher immer dasselbe methodische Kernproblem: Skills, die Prinzipien benennen, ohne zu erklären woher sie kommen. `ehmo/platform-design-skills` ist das erste Repository in dieser Evaluationsreihe das dieses Problem systematisch loest. Die Frage, die bleibt, ist eine andere: Was bedeutet es, alle richtigen Quellen zu haben — und wie weit traegt das?

354 GitHub-Stars, 20 Forks, 92 Commits — und im Stammverzeichnis liegt `Apple_HIG.pdf`. Das ist kein Zufall. Das ist eine methodische Aussage.

## Was das Repository verspricht

Der Skill umfasst heute 450+ Regeln (das README hat zwar sowohl "300+" als auch "450+" stehen, was auf aktive Erweiterung hinweist) fuer acht Apple-Plattformen (iOS, iPadOS, macOS, watchOS, visionOS, tvOS), Android und Web. Jede Plattform hat eine eigene Verzeichnisstruktur mit `SKILL.md`, `metadata.json`, `AGENTS.md` und einem `rules/`-Ordner mit Einzeldateien. Ziel ist nicht Allgemein-Design — sondern plattformspezifische Compliance mit publizierten Herstellerrichtlinien.

Fuer iOS bedeutet das: Apple Human Interface Guidelines. Fuer Android: Material Design 3. Fuer Web: WCAG 2.2 plus MDN Web Docs. Die Quellen sind nicht versteckt — sie stehen im README mit URLs, die direkt auf die offiziellen Dokumentationen verweisen.

## Die Quellen — und was sie methodisch bedeuten

Drei Kategorien von Quellen werden unterschieden, was fuer sich genommen schon ungewoehnlich ist:

Erstens die normativen Plattformquellen: Apple HIG (2025), Material Design 3, WCAG 2.2, MDN. Das sind keine Meinungen — das sind offizielle Spezifikationen mit Versionsbezeichnung und konkreten Anforderungen.

Zweitens die HCI-Forschungsliteratur als sekundaere Referenzen: Card, Moran und Newell, *The Psychology of Human-Computer Interaction* (1983) — verlinkt auf archive.org. Newell und Card, *Prospects for Psychological Science in HCI* — verlinkt als PDF der Carnegie Mellon Universitaetsbibliothek. Jastrzembski und Charness (2007) ueber das Model Human Processor bei aelteren Nutzern — verlinkt auf PubMed Central.

Der README-Text macht den epistemischen Status dieser Quellen klar: "These are secondary references used to sharpen guidance around recognition over recall, visible waiting states, and input effort. They do not override Apple HIG, Material, or WCAG." Das ist eine in der Fachliteratur uebliche Unterscheidung zwischen normativen Quellen (was soll gelten) und erklaerenden Quellen (warum gilt es). Diese Hierarchie explizit zu benennen ist in einem Skill-Repository aussergewoehnlich.

Drittens liegt die Apple HIG als zusammengefasstes PDF im Repository selbst. Das bedeutet: Wer die Portierungsqualitaet pruefen moechte, muss nicht erst die Quelle suchen.

## Die Portierungsfrage

<div class="callout">
<div class="callout__title">Die entscheidende Luecke</div>
Gute Quellen garantieren keine korrekte Portierung. Die Apple Human Interface Guidelines 2025 sind ein umfangreiches, kontinuierlich aktualisiertes Dokument mit hunderten Seiten. Material Design 3 hat sich seit dem Erscheinen von Material Design 2 erheblich veraendert. WCAG 2.2 baut auf WCAG 2.1 auf und einfuehrt neue Erfolgskriterien. Das repository behauptet 450+ Regeln aus diesen Quellen destilliert zu haben. Ob jede dieser Regeln korrekt portiert wurde — ob "Navigation Bar unter iOS" tatsaechlich dem entspricht was Apple 2025 spezifiziert — laesst sich nur durch systematischen Quellvergleich pruefen. Diese Arbeit kann im Rahmen einer Evaluation nicht vollstaendig geleistet werden. Sie ist aber die einzige Arbeit, die methodische Fundierung vollstaendig verrifizierbar macht.
</div>

Das ist kein Vorwurf an den Autor. Es ist die strukturelle Grenze jeder Portierung, unabhaengig von der Sorgfalt mit der sie erstellt wurde. Ein Skill der Apple HIG korrekt zitiert aber eine Regel falsch destilliert ist methodisch problematischer als ein Skill der gar keine Quellen angibt — weil er impliziert, der Nutzer muesse nicht mehr pruefen.

Fuer den Unterrichtseinsatz ist das der zentrale Lernmoment: Eine Quellenangabe schiebt die Verantwortung zur Pruefung nicht weg. Sie benennt lediglich wo die Pruefung beginnen muss.

## Scope-Klarheit als pädagogisches Modell

Fuer jede der acht Plattformen gibt es im README eine "Use when"-Sektion. Diese ist ungewoehnlich praezise. Fuer iOS heisst es: "Use when: Building SwiftUI or UIKit interfaces for iPhone / Reviewing iOS app code for HIG compliance / Choosing between iOS navigation patterns / Implementing accessibility, Dark Mode, Dynamic Type." Das sind keine Marketing-Formulierungen — das sind Einsatzbedingungen die helfen, den Skill nicht falsch einzusetzen.

Die explizite Trennung von iOS und iPadOS (separate Skills) zeigt, dass der Autor zwischen Plattformen unterscheidet, die viele Skills zusammenfassen. iOS und iPadOS teilen eine Codebase, aber unterschiedliche Interaktionsparadigmen, Multitasking-Modelle und Eingabemodalitaeten. Diese Unterscheidung in der Skill-Architektur abzubilden ist eine methodische Entscheidung mit Substanz.

Die Inklusion von visionOS — Apple Vision Pro — ist zeitgemaess. Die HIG fuer visionOS ist eine der am staerksten von traditionellen mobilen Paradigmen abweichenden Plattformspezifikationen. Einen Skill dafuer anzubieten ist ein Zeichen dafuer, dass der Autor die Plattform-Dokumentation tatsaechlich verfolgt.

## Wartbarkeit und das Anonymitaetsproblem

354 Stars und 20 Forks zeigen echte Community-Resonanz. Die 92 Commits belegen aktive Entwicklung. Die PR-Guidelines sind durchdacht: Fokus auf einen Themenbereich pro PR, Anforderung von Before/After-Beispielen in der PR-Beschreibung, spezifische Pruefkriterien fuer Portierungsaenderungen.

Und doch: Der Autor ist "ehmo". Kein verifizierbarer Nachname, kein LinkedIn, kein Twitter, keine Referenz auf professionelle Taetigkeit. Das GitHub-Profil selbst listet keine weiteren Repositories, keine Beschreibung, keine Organisationszugehoerigkeit. Das ist kein Fehler — aber es ist eine Einschraenkung. Fuer Institutionen die Skill-Qualitaet gegenueber Stakeholdern begruenden muessen, ist "MIT-lizenzierter GitHub-Account ohne Impressum" kein ausreichendes Vertrauen-Signal.

Gleichzeitig zeigt die tatsaechliche Struktur des Repositories — die PR-Richtlinien, die Quellenunterscheidung, die Changelog-Pflege — eine Arbeitsdisziplin die auf professionellen Hintergrund hindeutet. Der anonyme Maintainer hat offensichtlich Erfahrung mit Dokumentationsprojekten und Versionierung. Die Frage der Identitaet bleibt offen, aendert aber an der evaluierbaren Qualitaet des Inhalts wenig.

## Was das Repository von fast allem anderen unterscheidet

Um die Einordnung klar zu machen: Bisher wurde in dieser Evaluationsreihe kein einziges Repository gefunden das HCI-Forschungsliteratur mit Direktlinks auf Originalquellen zitiert. Kein einziges hat eine Quelldatei (hier: Apple_HIG.pdf) physisch ins Repository aufgenommen. Kein einziges hat zwischen normativen und sekundaeren Quellen explizit unterschieden.

Das sind keine kleinen Unterschiede. Das sind strukturelle Qualitaetsmerkmale die zeigen, dass der Autor die Grenze zwischen "gut klingendem Prinzip" und "verifizierbarer Anforderung" kennt und respektiert.

Im Vergleich zum zuletzt evaluierten `szilu/ux-designer-skill` — der 19 Quellen behauptet aber keine davon direkt verlinkt — ist der methodische Abstand erheblich.

## Empfehlung fuer den Unterrichtseinsatz

`ehmo/platform-design-skills` eignet sich als positives Gegenbeispiel zu den meisten anderen Skills in dieser Evaluationsreihe. Der Einsatz empfiehlt sich in zwei Kontexten:

Erstens als Modell fuer "wie Quellenarbeit im Skill-Kontext aussehen sollte". Die Quellenstruktur, die Hierarchie normativer vs. sekundaerer Referenzen, die physische Beigabe der Apple HIG als PDF — das alles kann als Benchmark fuer eigene Skill-Entwicklung dienen.

Zweitens als Einstieg in die Portierungsfrage: Zwei oder drei Regeln aus dem iOS-Skill auwaehlen, die entsprechenden Abschnitte in der Apple HIG aufschlagen, und vergleichen. Das ist eine ueberschaubare Uebung die zeigt, wie viel Interpretationsraum zwischen "Quelle vorhanden" und "korrekt portiert" noch bleibt.

Der Skill verdient das Urteil `vertrauen` — methodisch das Sorgfaeltigste was dieses Oekosystem bisher hervorgebracht hat, mit dem einzigen echten Vorbehalt eines anonymen Einzelmaintainers. Wer plattformspezifische Designguide-Compliance in Claude Code einsetzen will, hat hier den bisher besten verfuegbaren Ausgangspunkt.
