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

In dieser Serie läuft immer wieder derselbe Befund auf. Skills geben Quellenarbeit vor und leisten sie nicht. Benannt werden die Autoritäten, etwa Nielsen, WCAG und Apple HIG. Die Brücke zwischen Quelle und Skillinhalt bleibt unsichtbar. `hamen/material-3-skill` ist in dieser Hinsicht ein Ausnahmefall. Ivan Morgillo, ein bekannter Android-Entwickler, hat den Skill aufgebaut. Er tat es transparent und methodisch nachvollziehbar. Als Grundlage dient eine der am besten dokumentierten Design-Spezifikationen überhaupt. Es ist Googles Material Design 3.

Was macht diesen Skill anders? Und wo bleibt trotz allem eine echte Grenze?

## Was der Skill ist und beansprucht

Entwicklerteams sind die Zielgruppe. Sie arbeiten mit Jetpack Compose, Flutter oder `@material/web` und wollen die Material Design 3-Spezifikation korrekt umsetzen. Er besteht aus einer zentralen `SKILL.md` und sechs Referenzdateien. Die Dateien behandeln das Farbsystem mit über 29 Farbrollen, den Komponentenkatalog mit über 30 Komponenten, Theming und Dynamic Color, Typografie und Formen, Navigationsmuster sowie Layout und Breakpoints.

Konkret und prüfbar ist der Anspruch. Vier slash-Commands sollen MD3-konforme Komponenten generieren, Themes aus Seed-Farben ableiten, responsive App-Shells bauen und bestehenden Code gegen die Spezifikation auditieren. Ein vage gehaltener „Best Practices"-Skill ist das nicht. Es ist eine Implementierungshilfe für ein reales, veröffentlichtes Design-System. Das ist konkret.

## Methodentransparenz als Ausnahmefall

Sofort fällt die Offenheit über die Entstehung auf. Das README beschreibt den gesamten Prozess. Am Anfang steht Live-Scraping von m3.material.io via Chrome-Browser-Automatisierung. Es handelt sich um eine JavaScript-gerenderte Single-Page-App. `curl` gibt nur eine leere HTML-Shell zurück. Danach folgt der Kreuzabgleich mit dem Trainingskorpus dreier Frontier-Modelle, nämlich Claude Code, GPT-5.5 und Gemini 3.1 Pro. Zuletzt wird alles in strukturierte Markdown-Lookup-Tabellen destilliert.

<div class="callout">
<div class="callout__title">Transparenz als Designentscheidung</div>
Ivan Morgillo schreibt im README explizit: „This skill represents a best-effort distillation of Material Design 3 as of early 2025. If Google updates the spec, this skill may drift." Das ist ungewöhnlich. Ihre Grenzen kommunizieren die meisten Skills dieser Serie gar nicht. Oder sie tun es in so allgemeinen Formulierungen, dass sie praktisch wertlos sind. Hier steht ein Ablaufdatum direkt im Dokument. Für Lehrkontexte ist das ein Lehrbeispiel. Qualitätsbewusstsein zeigt sich nicht nur in dem, was ein Skill enthält. Es zeigt sich auch in dem, was er über sich selbst sagt. Dieser Skill sagt viel.
</div>

Die Plattform-Coverage-Matrix im Begleitblog ist ebenfalls bemerkenswert ehrlich. Compose ist der primäre Unterstützungskanal. Flutter läuft mit Einschränkungen. `@material/web` markiert der Skill explizit als „in maintenance mode". Google hat die offizielle Web-Komponenten-Bibliothek zurückgezogen und pflegt sie nicht mehr aktiv. Der Skill verschweigt oder glättet diesen Sachverhalt nicht. Er macht ihn zum Bestandteil der Nutzungshinweise.

## Das KI-cross-validiert-KI-Problem

Trotz aller Transparenz enthält die Methodenbeschreibung eine strukturelle Spannung. Im Unterricht sollte sie Thema sein. Morgillo beschreibt, wie Claude Code als primärer Autor fungierte. GPT-5.5 und Gemini 3.1 Pro dienten als unabhängige Reviewer. Die Artefakte gingen mit einem „Find what's wrong here"-Prompt an die anderen Modelle. Unstimmigkeiten galten als Signal für vertiefte Recherche in der MD3-Spezifikation. Das hilft.

Rigoros klingt das. Es ist auch besser als reine Einzelmodell-Arbeit. Aufgelöst wird das Grundproblem damit nicht. Es verteilt es nur. Alle drei Modelle haben dieselbe Klasse von Wissenslücken, nämlich Zeitschnitte und Trainingsdatenabdeckung, nur an leicht unterschiedlichen Stellen. Ein Modell kennt eine Compose-API-Änderung aus Q4 2025 nicht. Dann kennt wahrscheinlich ein anderes sie ebenfalls nicht. Der Kreuzabgleich unter Peers fängt systematische Lücken nur ab, wenn die Peers unterschiedliche Abdeckungszonen haben. Dafür gibt der Skill keine Garantie.

Das relativiert den Validierungsanspruch und negiert ihn nicht. Das Live-Scraping von m3.material.io ist eine dritte, externe Wahrheitsquelle und unabhängig von Trainingsdaten. Es stabilisiert das System erheblich. Wer den Skill im Unterricht einsetzt, sollte diese Konstruktion erklären. KI-cross-Validierung ist sinnvoll. Ohne externe Grundlage reicht sie als Qualitätskontrolle nicht. Das ist der Punkt.

## Prüfbare Basis: Material Design 3

Einer der stärksten Vorzüge ist die Quelle selbst. Material Design 3 ist nicht „das Erfahrungswissen von 20 Jahren Frontend-Entwicklung". Es ist auch kein „bewährtes Wissen aus der Praxis". Hinter solchen Formulierungen stand in dieser Serie häufig nichts Greifbares. MD3 ist eine vollständig publizierte, versionierte Spezifikation von Google. Token-Werte, Typenmaßstäbe und Komponentenbeschreibungen lassen sich im direkten Vergleich mit den Skillinhalten prüfen.

Laut Skill gilt `colorScheme.primary` für die Hauptfarbe eines Buttons. Das lässt sich auf m3.material.io nachschlagen. Die Typografie-Lookup-Tabellen enthalten Token-Namen wie `displayLarge` oder `bodyMedium`. Diese Token existieren in der offiziellen Spezifikation und können verifiziert werden. Bei generalistischen UX-Skills fehlt diese Nachvollziehbarkeit grundlegend.

Eine eigene Herausforderung bringt der Vorzug mit. MD3 ist ein bewegliches Ziel. Google I/O 2026 hat neue Änderungen gebracht. Dazu gehören das 8dp-Spacing-System, Watch- und XR-Formfaktoren sowie Expressive-Listen und -Menüs. Morgillo hat das README entsprechend aktualisiert. Je nach Plattform variiert aber die Tiefe der Abdeckung. Watch und XR behandelt der Skill nach eigener Aussage noch flach. Er sagt das offen.

## Der Audit-Modus: Selbstreferenz mit Lernwert

Zu den originellsten Funktionen zählt der 10-Kategorie-MD3-Compliance-Audit. Der Skill analysiert Compose-Code oder eine URL. Er gibt einen Score in zehn Kategorien aus. Die Kategorien sind Farbtokens, Typografie, Formen, Elevation, Komponenten, Layout, Navigation, Motion, Accessibility und Theming. Jeder Abzug enthält eine Referenz auf die MD3-Dokumentationsseite, die die Regel definiert.

Morgillo dokumentiert vier echte Produktionsfehler. Der Audit fand sie in seiner App „Kindle Gratis" mit 1,4 Millionen Downloads. Es sind `Random.nextInt()` innerhalb einer Composable-Funktion, `Color.Black`-Text auf variablem Hintergrund, veraltete `DisposableEffect`-Verwendung für Lifecycle-Beobachtung und ein fehlendes `modifier`-Parameter-Layout. Das sind reale, spezifische Fehler mit Before-After-Codebeispielen. Abstrakte Kategorien sind es nicht.

Zwei Einschränkungen bleiben. Erstens ist der Audit selbstreferenziell. Er prüft Code gegen dieselben Regeln, nach denen er generiert wurde. Was im System konsistent ist, muss gegenüber der Spezifikation nicht korrekt sein. Zweitens fehlt im Repository ein automatisiertes Test-Artefakt. Eine CI-Pipeline, die den Skill gegen bekannte Referenzbeispiele testet, gibt es nicht. Der „agentskills.io"-Validator-Nachweis im Blogpost ist ein formales Signal. Über die inhaltliche Korrektheit sagt er nichts.

## Wartbarkeit: Einzelperson mit sichtbarem Rückhalt

Ivan Morgillo ist kein anonymer Account. Er ist auf X als `@hamen` präsent. Er betreibt einen aktiven YouTube-Kanal und hat ein LinkedIn-Profil. Als Android-Entwickler hat er verifizierbare Produktionserfahrung. Das Repository hat eine MIT-Lizenz und eine `CONTRIBUTING.md`. Im Juni 2026 wurde es aktiv mit I/O-2026-Material aktualisiert. Mit `compose_skill` existiert bereits ein Companion-Skill. Das deutet auf Systemdenken hin. Ein Einzelprojekt ist es nicht.

Als Kehrseite bleibt das Einzel-Maintainer-Modell. Sechs Commits zählt die Geschichte, dazu ein offenes Issue. Im Roadmap-Abschnitt stehen eine GitHub Action für PR-Kommentare und tiefere Flutter-Abdeckung. Das sind noch Versprechen und keine abgelieferten Features. Für ein Lehrprojekt über ein Semester ist das Risiko gering. Für Produktionseinsatz über mehrere Jahre sollte man die Organisationsfähigkeit des Projekts evaluieren. Das ist eine andere Frage.

## Empfehlung für den Unterrichtseinsatz

Besonders gut passt der Skill zu zwei Lehrszenarien.

Das erste ist die **methodische Analyse**. Studierende vergleichen ausgewählte Token-Werte aus dem Skill mit den Einträgen auf m3.material.io. Sie wählen ein Token, eine Komponente, einen Breakpoint. Stimmt der Wert? Stammt er aus der aktuellen Spezifikation? Was ändert sich, wenn Google in der nächsten I/O-Ausgabe aktualisiert? Den Skill zu demontieren ist nicht das Ziel. Die Studierenden sollen verstehen, was es heißt, wenn eine KI-Ressource auf einer externen, nachprüfbaren Quelle aufbaut.

Das zweite ist die **Transparenz-Kontrastanalyse**. Man stellt einen Skill gegenüber, der Quellen nennt und nicht belegt. Ein Beispiel ist `ceorkm/mobile-app-ui-design` aus dieser Serie. Warum macht es einen Unterschied, ob ein Skill „basierend auf MD3" sagt und die genauen Token-Werte samt Quellenlink tabellarisch auflistet? Oder ob er „Peak-End-Rule" schreibt, ohne einen Namen oder Link zu nennen? Die Übung macht den Unterschied zwischen Quellenbehauptung und Quellenarbeit für Lernende greifbar.

Für den produktiven Einsatz im Compose-Kontext ist der Skill empfehlenswert. Das README enthält eine Plattformabdeckungs-Matrix. Man sollte sie vor dem Einsatz lesen. Flutter-Teams sollten die Teilabdeckung kennen. Web-Teams sollten wissen, dass `@material/web` als Plattform eingeschränkt ist. Das gehört dazu.
