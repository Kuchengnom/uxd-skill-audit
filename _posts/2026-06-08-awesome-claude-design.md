---
layout: post
title: "awesome-claude-design: Wenn Marken-Sampling als Designmethodik durchgeht"
date: 2026-06-08
category: Skill-Evaluation
skill_reviewed: "rohitg00/awesome-claude-design"
verdict: vertrauen
reading_time: 9
last_audited: "08. Juni 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "Marken-DNA korrekt und detailgenau portiert, aber die übergeordnete Taxonomie der 9 ästhetischen Familien ist eine Community-Kategorie ohne designtheoretische Grundlage."
  transparenz: 4
  transparenz_note: "Ehrlich über Scope: kuratierter Stil-Katalog, kein Methodenbuch. Anti-Slop-Kit benennt Claudes Schwächen explizit — ungewöhnlich selbstkritisch."
  validierbarkeit: 3
  validierbarkeit_note: "Showcase mit Screenshots vorhanden, aber keine formalen Tests oder systematische Vergleiche gegen die referenzierten Marken."
  wartbarkeit: 3
  wartbarkeit_note: "Aktiver, verifizierbarer Maintainer (Rohit Ghumare, Google Developer Expert), aber Einzelperson; das DESIGN.md-Format selbst ist erst zwei Monate alt."

tags:
  - design-md
  - stil-katalog
  - marken-sampling
  - anti-slop
  - claude-design
  - template-bibliothek
---

## Was ist dieses Projekt — und warum taucht es jetzt auf?

Am 17. April 2026 veröffentlichte Anthropic Claude Design, einen KI-basierten visuellen Workspace der HTML-Artefakte aus Textbeschreibungen generiert. Das neue Format dafür heißt DESIGN.md: eine Markdown-Datei die Claude mitteilt, welche Ästhetik ein Projekt haben soll — Farben, Typografie, Abstände, Komponentenverhalten. Ohne DESIGN.md produziert Claude Design generische Ausgaben; mit einer guten DESIGN.md soll unverwechselbare Markenpräsenz entstehen.

Einen Tag nach dem Launch veröffentlichte Rohit Ghumare (`rohitg00`) das Repository `awesome-claude-design`. Die Idee: 28+ produktionsfertige DESIGN.md-Dateien, sortiert nach neun ästhetischen Familien (Neon Brutalist, Editorial Minimalism, Warm Editorial, Terminal-Core, Data-Dense Pro, Cinematic Dark, Playful Color, Glass/Soft-Futurism, Cult/Indie). Wer ein "The-Verge-artiges Interface" bauen will, greift zur entsprechenden Datei und übergibt sie an Claude Design.

Das Repository erreichte bis Anfang Juni 2026 über 360 GitHub-Stars und wurde in zahlreichen Design-Blogs als Referenz-Ressource zitiert. Es ist damit das meistverlinkte DESIGN.md-Projekt im Ökosystem — und damit ist es für diesen Blog interessant genug für eine genaue Betrachtung.

## Was das Repo tut — und was es nicht tut

Der erste wichtige Befund bei der Sichtung: `awesome-claude-design` ist kein Skill im Sinne der bisher hier evaluierten Projekte. Ein SKILL.md lehrt Claude eine Methodik — wie man einen Heuristic-Walkthrough durchführt, wie man WCAG-Konformität prüft, wie man Interaktionsprinzipien anwendet. Das ist prozedurales Wissen.

`awesome-claude-design` enthält DESIGN.md-Dateien. Das ist deklaratives Wissen: "So sieht das Ergebnis aus, nicht: So kommt man dahin." Die DESIGN.md für The Verge listet Farbwerte (`--accent: #ff6600`), Typografieregeln (Polysans Median als Display-Schrift), Abstands- und Layout-Entscheidungen (2px-Rules statt Whitespace) und einen "Agent Prompt Guide" der Claude explizit sagt was es ablehnen soll: abgerundete Ecken, weiche Schatten, Pastellpaletten, Inter als Display-Schrift.

Das ist handwerklich korrekt recherchiert. Polysans Median ist tatsächlich The Verges Wahl für Display-Typografie. Das Orange #ff6600 ist eine akkurate Näherung an The Verges Akzentfarbe. Die 2px-Rule-Ästhetik und der Verzicht auf Kartenabtrennungen durch Hintergrundfarben — das stimmt mit dem Markenauftritt überein. Hier hat jemand wirklich nachgeschaut, nicht nur Kategorien benannt.

Das ist das Stärkste an diesem Projekt: Es ist keine Theorie über Markenästhetik. Es ist Markenarchäologie.

## Das Problem mit den ästhetischen Familien

Hier beginnt die kritische Betrachtung. Die DESIGN.md-Dateien selbst sind treffsicher. Aber die übergeordnete Klassifikation in neun "ästhetische Familien" hat keinen designtheoretischen Rückhalt.

"Neon Brutalist" ist ein Begriff der auf X und in Design-Communitys kursiert. Er beschreibt etwas Reales — harte Kanten, einzelne gesättigte Farbe, typografischer Kontrast, Null Kompromisse. Aber er ist kein etablierter Begriff aus der Designwissenschaft oder Designgeschichte. Das Brutalism-Konzept aus der Architektur wurde in den 2010er-Jahren für Webdesign adaptiert, der "Neon"-Zusatz ist jedoch eine Community-Erfindung ohne kanonische Definition.

Das gilt für mehrere der neun Familien. "Cult/Indie" als Kategorie ist vage: Was ist der Unterschied zwischen einem Indie-Projekt das zufällig ähnliche Designmuster hat und einem das bewusst "Cult"-Ästhetik anstrebt? Die Grenze bleibt im Repo unklar.

Für den Unterrichtseinsatz ist das ein wichtiger Unterschied: Die einzelnen DESIGN.md-Dateien sind citable und verifizierbar (öffne The Verge, prüfe die Schrift, prüfe die Farbe). Die Taxonomie der Familien ist es nicht.

<div class="callout"><div class="callout__title">Zentraler Kritikpunkt: Stil-Katalog versus Designmethodik</div>

Wer dieses Repository verwendet, lernt wie The Verge aussieht — nicht warum The Verge so aussieht. Das sind zwei verschiedene Dinge. The Verge hat sich für Neon Brutalism entschieden weil diese Ästhetik eine redaktionelle Haltung kommuniziert: laut, meinungsstark, keine Entschuldigungen. Das Repo zeigt das Ergebnis dieser Entscheidung, nicht den Denkprozess dahinter.

Wer DESIGN.md-Dateien einsetzt ohne den Kontext zu verstehen, ist in einer ähnlichen Lage wie jemand der ein Outfit nachkauft ohne zu verstehen für welchen Anlass es gedacht war. Das kann funktionieren — oder es endet als stilistischer Kategorienfehler.
</div>

## Das Anti-Slop-Kit: der wertvollste Teil des Repos

Ein Abschnitt des Repos ist bemerkenswert selbstkritisch: das Anti-Slop-Kit. Anthropic selbst beschreibt in seinem Frontend-Aesthetics-Cookbook das Problem: Claude neigt dazu, generische, "on-distribution" Ausgaben zu produzieren. Im Frontend-Design erzeugt das was Nutzerinnen "AI-Slop-Ästhetik" nennen — Rounded Cards, Inter oder System-UI als Standardschrift, `#3b82f6` Blau als Akzent, großzügige aber nichtssagende Abstände.

Das Anti-Slop-Kit in `awesome-claude-design` dokumentiert diese Fingerprints explizit und benennt Gegenstrategien. Das ist metakognitive Designarbeit: bevor man weiß was man will, muss man wissen was man nicht will, und warum Claude genau das produziert wenn man keine Direktive gibt.

Dieser Teil des Repos hat einen didaktischen Wert der über die DESIGN.md-Dateien hinausgeht. Er macht ein strukturelles Problem sichtbar — KI-Generierung konvergiert zu statistischen Mittelmäßen — und gibt Werkzeuge um dagegen zu arbeiten. Für den Unterrichtseinsatz ist das eine gute Ausgangsbasis für die Frage: Wie kommuniziert man Designintention so präzise, dass das Modell keine Lücken mit Defaults füllen kann?

## Wartbarkeit als strukturelles Problem des Formats

Markenästhetiken ändern sich. The Verge hat seit 2023 mehrfach typografische Anpassungen vorgenommen. Linear hat im letzten Jahr die Farbpalette erweitert. Ein DESIGN.md-File das im April 2026 akkurat war, kann in sechs Monaten veraltet sein — und Claude wird das nicht wissen.

Das Repo hat 0 offene Issues. Das kann zwei Dinge bedeuten: Entweder arbeiten die Templates so gut, dass es keinen Bedarf für Korrekturen gibt. Oder die Nutzerzahl ist noch zu klein für aktive Fehlermeldungen. Bei einem Repo das erst zwei Monate alt ist, ist letzteres wahrscheinlicher.

Rohit Ghumare ist als Maintainer verifizierbar — Google Developer Expert, Docker Captain, aktiver Open-Source-Contributor mit mehreren Projekten die technische Tiefe beweisen. Sein primärer Hintergrund liegt allerdings in DevRel und Cloud-Infrastruktur, nicht in Design. Das sieht man an manchen Stellen im Repo: Die Rezepte (Landing Page in 20 Minuten, Pitch Deck from README) sind ingenieursorientiert — schnelle Outputs, klarer Nutzen. Das ist kein Werturteil, aber es erklärt warum die Taxonomie der ästhetischen Familien weniger belastbar ist als die einzelnen DESIGN.md-Dateien.

## Empfehlung für den Unterrichtseinsatz

`awesome-claude-design` eignet sich gut als Praxis-Material — mit einer wichtigen Bedingung: Es sollte nicht als fertige Methodik eingesetzt werden, sondern als Ausgangsmaterial für eine kritische Analyse.

Eine produktive Übung: Studenten nehmen eine DESIGN.md aus dem Repo (zum Beispiel die The-Verge-Datei), öffnen die tatsächliche Website, und prüfen jede Behauptung. Stimmt die Schriftart? Stimmt der Farbwert? Werden die Do/Don't-Regeln tatsächlich eingehalten? Dann generieren sie mit Claude Design ein Interface und vergleichen das Ergebnis mit der Referenzmarke.

Diese Übung lehrt drei Dinge gleichzeitig: (1) wie DESIGN.md als Format funktioniert, (2) wie man Designentscheidungen auf ihre tatsächliche Herkunft zurückverfolgt, und (3) warum der Abstand zwischen "Stilbeschreibung" und "Designprinzip" größer ist als er zunächst erscheint.

Das Anti-Slop-Kit eignet sich als Einführungstext in die Diskussion über KI-Defaults und Kreativität — eine Diskussion die im Design-Unterricht immer relevanter wird.

Das Projekt sollte dabei ehrlich als das eingeführt werden was es ist: eine kuratierte Sammlung von Stil-Snapshots, kein Methodenbuch. Wer diesen Unterschied versteht, profitiert von dem was das Repo tatsächlich leistet.
