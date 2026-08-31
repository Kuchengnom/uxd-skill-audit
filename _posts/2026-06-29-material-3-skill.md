---
layout: post
title: "material-3-skill: Wenn Methodentransparenz zum Maßstab wird"
date: 2026-06-29
category: Skill-Evaluation
skill_reviewed: "hamen/material-3-skill"
verdict: solide
reading_time: 11
last_audited: "29. Juni 2026"

skill_scores:
  methodische_fundierung: 4
  methodische_fundierung_note: "Direkt auf Googles offizieller MD3-Spezifikation aufgebaut, live gescrapt via Chrome-Automatisierung — aber KI-cross-validiert-KI-Ansatz bringt strukturelle Zirkuläre mit."
  transparenz: 5
  transparenz_note: "Vorbildliche Offenlegung der gesamten Entstehungsmethodik, explizite Warnungen vor möglicher Drift, ehrliche Plattform-Coverage-Matrix."
  validierbarkeit: 4
  validierbarkeit_note: "10-Kategorie-Audit-Modus, reale Produktionsfehler dokumentiert, agentskills.io-Validator bestanden — kein automatisiertes Test-Artefakt im Repository."
  wartbarkeit: 4
  wartbarkeit_note: "Identifizierbarer Maintainer mit verifizierbarem Track Record (1,4 Mio. Downloads), MIT-Lizenz, aktiv bis Google I/O 2026, aber Einzelperson ohne Team."

tags:
  - material-design
  - google
  - design-system
  - transparenz
  - methodentransparenz
  - jetpack-compose
  - skill-evaluation
---

In dieser Serie läuft immer wieder derselbe Befund auf: Skills, die Quellenarbeit vorgeben statt sie zu leisten. Die Autoritäten werden benannt, Nielsen, WCAG, Apple HIG, aber die Brücke zwischen Quelle und Skillinhalt bleibt unsichtbar. `hamen/material-3-skill` ist in dieser Hinsicht ein Ausnahmefall. Der Skill wurde von Ivan Morgillo aufgebaut, einem bekannten Android-Entwickler, und zwar transparent, methodisch nachvollziehbar und auf einer der am besten dokumentierten Design-Spezifikationen überhaupt: Googles Material Design 3.

Was macht dieser Skill anders? Und wo bleibt trotz allem eine echte Grenze?

## Was der Skill ist und beansprucht

Der Skill richtet sich an Entwicklerteams, die mit Jetpack Compose, Flutter oder `@material/web` arbeiten und die Material Design 3-Spezifikation korrekt umsetzen wollen. Er besteht aus einer zentralen `SKILL.md` und sechs Referenzdateien: Farbsystem mit über 29 Farbrollen, Komponentenkatalog mit über 30 Komponenten, Theming und Dynamic Color, Typografie und Formen, Navigationsmuster, Layout und Breakpoints.

Der Anspruch ist konkret und prüfbar. In vier slash-Commands soll der Skill MD3-konforme Komponenten generieren, Themes aus Seed-Farben ableiten, responsive App-Shells bauen und bestehenden Code gegen die Spezifikation auditieren. Das ist kein vage gehaltener „Best Practices"-Skill, sondern eine Implementierungshilfe für ein reales, veröffentlichtes Design-System.

## Methodentransparenz als Ausnahmefall

Was an diesem Skill sofort auffällt, ist die Offenheit über die Entstehung. Das README beschreibt den gesamten Prozess. Live-Scraping von m3.material.io via Chrome-Browser-Automatisierung, weil die Seite eine JavaScript-gerenderte Single-Page-App ist und `curl` nur einen leeren HTML-Shell zurückgibt. Danach Kreuzabgleich mit dem Trainingskorpus dreier Frontier-Modelle, nämlich Claude Code, GPT-5.5 und Gemini 3.1 Pro. Zuletzt die Destillation in strukturierte Markdown-Lookup-Tabellen.

<div class="callout">
<div class="callout__title">Transparenz als Designentscheidung</div>
Ivan Morgillo schreibt im README explizit: „This skill represents a best-effort distillation of Material Design 3 as of early 2025. If Google updates the spec, this skill may drift." Das ist ungewöhnlich. Die meisten Skills, die in dieser Serie untersucht wurden, kommunizieren ihre Grenzen entweder gar nicht oder in so allgemeinen Formulierungen, dass sie praktisch wertlos sind. Hier steht ein Ablaufdatum direkt im Dokument. Für Lehrkontexte ist das ein Lehrbeispiel: Qualitätsbewusstsein zeigt sich nicht nur in dem, was ein Skill enthält, sondern auch in dem, was er über sich selbst sagt.
</div>

Die Plattform-Coverage-Matrix im Begleitblog ist ebenfalls bemerkenswert ehrlich. Compose ist der primäre Unterstützungskanal. Flutter läuft mit Einschränkungen. `@material/web` wird explizit als „in maintenance mode" markiert, denn Google hat die offizielle Web-Komponenten-Bibliothek zurückgezogen und pflegt sie nicht mehr aktiv. Statt diesen Sachverhalt zu verschweigen oder zu glätten, macht der Skill ihn zum Bestandteil der Nutzungshinweise.

## Das KI-cross-validiert-KI-Problem

Trotz aller Transparenz enthält die Methodenbeschreibung eine strukturelle Spannung, die im Unterricht thematisiert werden sollte. Morgillo beschreibt, wie Claude Code als primärer Autor fungierte und GPT-5.5 sowie Gemini 3.1 Pro als unabhängige Reviewer. Artefakte wurden mit einem „Find what's wrong here"-Prompt an die anderen Modelle übergeben. Unstimmigkeiten wurden als Signal für vertiefte Recherche in der MD3-Spezifikation genutzt.

Das klingt rigoros. Und es ist besser als reine Einzelmodell-Arbeit. Aber es löst das Grundproblem nicht auf, es verteilt es. Alle drei Modelle haben dieselbe Klasse von Wissenslücken, nämlich Zeitschnitte und Trainingsdatenabdeckung, nur an leicht unterschiedlichen Stellen. Wenn ein Modell eine Compose-API-Änderung aus Q4 2025 nicht kennt, ist es wahrscheinlich dass ein anderes sie ebenfalls nicht kennt. Der Kreuzabgleich unter Peers fängt systematische Lücken nur dann ab, wenn die Peers tatsächlich unterschiedliche Abdeckungszonen haben. Dafür liefert der Skill keine Garantie.

Das relativiert den Validierungsanspruch, negiert ihn aber nicht. Das Live-Scraping von m3.material.io als dritte, externe Wahrheitsquelle, die unabhängig von Trainingsdaten ist, stabilisiert das System erheblich. Wer diesen Skill im Unterricht einsetzt, sollte diese Konstruktion erklären: KI-cross-Validierung ist sinnvoll, aber keine hinreichende Qualitätskontrolle ohne externe Grundlage.

## Prüfbare Basis: Material Design 3

Einer der stärksten Vorzüge dieses Skills ist die Quelle selbst. Material Design 3 ist nicht „das Erfahrungswissen von 20 Jahren Frontend-Entwicklung" und auch kein „bewährtes Wissen aus der Praxis". Hinter solchen Formulierungen stand in dieser Serie häufig nichts Greifbares. MD3 ist eine vollständig publizierte, versionierte Spezifikation von Google, mit Token-Werten, Typenmaßstäben und Komponentenbeschreibungen, die sich im direkten Vergleich mit den Skillinhalten prüfen lassen.

Das bedeutet: Wenn der Skill behauptet, dass `colorScheme.primary` für die Hauptfarbe eines Buttons verwendet werden soll, lässt sich das auf m3.material.io nachschlagen. Wenn die Typografie-Lookup-Tabellen Token-Namen wie `displayLarge` oder `bodyMedium` enthalten, existieren diese Token in der offiziellen Spezifikation und können verifiziert werden. Diese Art von Nachvollziehbarkeit fehlt bei generalistischen UX-Skills grundlegend.

Gleichzeitig bringt dieser Vorzug eine eigene Herausforderung mit: MD3 ist ein bewegliches Ziel. Google I/O 2026 hat neue Änderungen mitgebracht, darunter das 8dp-Spacing-System, Watch- und XR-Formfaktoren sowie Expressive-Listen und -Menüs. Morgillo hat das README entsprechend aktualisiert, aber die Tiefe dieser Abdeckung variiert je nach Plattform. Watch und XR sind im aktuellen Skill nach eigener Aussage noch flach behandelt.

## Der Audit-Modus: Selbstreferenz mit Lernwert

Eine der originellsten Funktionen ist der 10-Kategorie-MD3-Compliance-Audit. Der Skill analysiert Compose-Code oder eine URL und gibt einen Score in zehn Kategorien aus: Farbtokens, Typografie, Formen, Elevation, Komponenten, Layout, Navigation, Motion, Accessibility und Theming. Jeder Abzug enthält eine Referenz auf die spezifische MD3-Dokumentationsseite, die die Regel definiert.

Morgillo dokumentiert vier echte Produktionsfehler, die der Audit in seiner App „Kindle Gratis" mit 1,4 Millionen Downloads gefunden hat: `Random.nextInt()` innerhalb einer Composable-Funktion, `Color.Black`-Text auf variablem Hintergrund, veraltete `DisposableEffect`-Verwendung für Lifecycle-Beobachtung und ein fehlendes `modifier`-Parameter-Layout. Das sind reale, spezifische Fehler mit Before-After-Codebeispielen, nicht abstrakte Kategorien.

Zwei Einschränkungen bleiben. Erstens ist der Audit selbstreferenziell, denn er prüft Code gegen dieselben Regeln nach denen er generiert wurde. Was innerhalb des Systems konsistent ist, muss nicht zwingend korrekt gegenüber der Spezifikation sein. Zweitens gibt es im Repository kein automatisiertes Test-Artefakt, also keine CI-Pipeline die den Skill gegen bekannte Referenzbeispiele testet. Der „agentskills.io"-Validator-Nachweis im Blogpost ist ein formales Signal, gibt aber keinen Aufschluss über inhaltliche Korrektheit.

## Wartbarkeit: Einzelperson mit sichtbarem Rückhalt

Ivan Morgillo ist kein anonymer Account. Er ist auf X als `@hamen` präsent, hat einen aktiven YouTube-Kanal, LinkedIn-Profil, und eine verifizierbare Produktionserfahrung als Android-Entwickler. Das Repository hat MIT-Lizenz, eine `CONTRIBUTING.md`, und wurde im Juni 2026 aktiv mit I/O-2026-Material aktualisiert. Mit `compose_skill` existiert bereits ein Companion-Skill. Das deutet auf Systemdenken hin, nicht auf ein Einzelprojekt.

Die Kehrseite: Es ist ein Einzel-Maintainer-Projekt. Sechs Commits in der Geschichte, ein offenes Issue. Der Roadmap-Abschnitt nennt eine GitHub Action für PR-Kommentare und tiefere Flutter-Abdeckung, aber das sind noch Versprechen, keine abgelieferten Features. Für ein Lehrprojekt, das über ein Semester läuft, ist das Risiko gering. Für Produktionseinsatz über mehrere Jahre sollte die Organisationsfähigkeit des Projekts evaluiert werden.

## Empfehlung für den Unterrichtseinsatz

Dieser Skill eignet sich für zwei verschiedene Lehrszenarien besonders gut.

Das erste ist die **methodische Analyse**: Studierende vergleichen ausgewählte Token-Werte aus dem Skill mit den korrespondierenden Einträgen auf m3.material.io. Ein Token, eine Komponente, ein Breakpoint. Stimmt der Wert? Stammt er aus der aktuellen Spezifikation? Was würde sich ändern, wenn Google in der nächsten I/O-Ausgabe eine Aktualisierung vornimmt? Das Ziel ist nicht, den Skill zu demontieren, sondern zu verstehen, was es bedeutet, wenn eine KI-Ressource auf einer externen, nachprüfbaren Quelle aufbaut.

Das zweite ist die **Transparenz-Kontrastanalyse**: die Gegenüberstellung mit einem Skill der Quellen nennt ohne sie zu belegen, etwa `ceorkm/mobile-app-ui-design` aus dieser Serie. Warum ist es ein Unterschied, ob ein Skill sagt „basierend auf MD3" und dann die genauen Token-Werte samt Quellenlink tabellarisch auflistet, oder ob er „Peak-End-Rule" schreibt ohne einen einzigen Namen oder Link? Diese Kontrastübung macht den Unterschied zwischen Quellenbehauptung und Quellenarbeit für Lernende greifbar.

Für den produktiven Einsatz im Compose-Kontext: empfehlenswert, mit dem Hinweis, die Plattformabdeckungs-Matrix im README vor dem Einsatz zu lesen. Flutter-Teams sollten die Teilabdeckung kennen. Web-Teams sollten wissen, dass `@material/web` als Plattform eingeschränkt ist.
