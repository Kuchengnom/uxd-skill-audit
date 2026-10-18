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
  methodische_fundierung_note: "Marken-DNA korrekt und detailgenau portiert. Die übergeordnete Taxonomie der 9 ästhetischen Familien ist aber eine Community-Kategorie ohne designtheoretische Grundlage."
  transparenz: 4
  transparenz_note: "Ehrlich über Scope: kuratierter Stil-Katalog, kein Methodenbuch. Das Anti-Slop-Kit benennt Claudes Schwächen explizit und ist ungewöhnlich selbstkritisch."
  validierbarkeit: 3
  validierbarkeit_note: "Showcase mit Screenshots vorhanden, aber keine formalen Tests oder systematische Vergleiche gegen die referenzierten Marken."
  wartbarkeit: 3
  wartbarkeit_note: "Aktiver, verifizierbarer Maintainer (Rohit Ghumare, Google Developer Expert), aber Einzelperson. Das DESIGN.md-Format selbst ist erst zwei Monate alt."

tags:
  - design-md
  - stil-katalog
  - marken-sampling
  - anti-slop
  - claude-design
  - template-bibliothek
---

## Was ist dieses Projekt, und warum taucht es jetzt auf?

Am 17. April 2026 veröffentlichte Anthropic Claude Design. Es ist ein KI-basierter visueller Workspace und generiert HTML-Artefakte aus Textbeschreibungen. Das neue Format dafür heißt DESIGN.md. Mit dieser Markdown-Datei legt man für Claude die Ästhetik eines Projekts fest. Dazu gehören Farben, Typografie, Abstände und Komponentenverhalten. Ohne DESIGN.md produziert Claude Design generische Ausgaben. Mit einer guten DESIGN.md soll unverwechselbare Markenpräsenz entstehen.

Einen Tag nach dem Launch veröffentlichte Rohit Ghumare unter dem Namen `rohitg00` das Repository `awesome-claude-design`. Mehr als 28 produktionsfertige DESIGN.md-Dateien bilden die Idee. Sie sind nach neun ästhetischen Familien sortiert. Dazu zählen Neon Brutalist, Editorial Minimalism, Warm Editorial, Terminal-Core, Data-Dense Pro, Cinematic Dark, Playful Color, Glass/Soft-Futurism und Cult/Indie. Wer ein „The-Verge-artiges Interface" bauen will, greift zur entsprechenden Datei. An Claude Design übergibt er sie dann.

Das Repository erreichte bis Anfang Juni 2026 über 360 GitHub-Stars. Zahlreiche Design-Blogs zitierten es als Referenz-Ressource. Es ist damit das meistverlinkte DESIGN.md-Projekt im Ökosystem. Für diesen Blog verdient es eine genaue Betrachtung.

## Was das Repo tut, und was es nicht tut

Die Sichtung ergibt zuerst einen wichtigen Befund. `awesome-claude-design` ist kein Skill im Sinne der bisher hier evaluierten Projekte. Ein SKILL.md lehrt Claude eine Methodik. Es zeigt, wie man einen Heuristic-Walkthrough durchführt, WCAG-Konformität prüft oder Interaktionsprinzipien anwendet. Das ist prozedurales Wissen.

`awesome-claude-design` enthält DESIGN.md-Dateien. Das ist deklaratives Wissen. Es sagt, wie das Ergebnis aussieht. Den Weg dorthin sagt es nicht. Die DESIGN.md für The Verge listet Farbwerte wie `--accent: #ff6600`. Sie enthält Typografieregeln mit Polysans Median als Display-Schrift. Dazu kommen Abstands- und Layout-Entscheidungen wie 2px-Rules statt Whitespace. Ein „Agent Prompt Guide" sagt Claude explizit, was es ablehnen soll. Genannt werden abgerundete Ecken, weiche Schatten, Pastellpaletten und Inter als Display-Schrift.

Das ist handwerklich korrekt recherchiert. Polysans Median ist tatsächlich The Verges Wahl für Display-Typografie. Auch Orange #ff6600 ist eine akkurate Näherung an The Verges Akzentfarbe. Die 2px-Rule-Ästhetik und der Verzicht auf Kartenabtrennungen durch Hintergrundfarben stimmen mit dem Markenauftritt überein. Hier hat jemand wirklich nachgeschaut und nicht nur Kategorien benannt.

Hier liegt die Stärke des Projekts. Es ist keine Theorie über Markenästhetik. Es ist Markenarchäologie.

## Das Problem mit den ästhetischen Familien

Hier beginnt die kritische Betrachtung. Die DESIGN.md-Dateien selbst sind treffsicher. Die übergeordnete Klassifikation in neun "ästhetische Familien" hat aber keinen designtheoretischen Rückhalt.

„Neon Brutalist" ist ein Begriff, der auf X und in Design-Communitys kursiert. Er beschreibt etwas Reales. Gemeint sind harte Kanten, einzelne gesättigte Farbe, typografischer Kontrast und null Kompromisse. Er ist aber kein etablierter Begriff aus der Designwissenschaft oder Designgeschichte. Aus der Architektur wurde das Brutalism-Konzept in den 2010er-Jahren für Webdesign adaptiert. Der „Neon"-Zusatz ist dagegen eine Community-Erfindung ohne kanonische Definition.

Für mehrere der neun Familien gilt das. „Cult/Indie" als Kategorie ist vage. Ein Indie-Projekt kann zufällig ähnliche Designmuster haben. Ein anderes strebt bewusst „Cult"-Ästhetik an. Im Repo bleibt der Unterschied zwischen beiden unklar.

Für den Unterrichtseinsatz ist das ein wichtiger Unterschied. Die einzelnen DESIGN.md-Dateien sind zitierbar und verifizierbar. The Verge öffnen, Schrift prüfen, Farbe prüfen. Die Taxonomie der Familien ist es nicht.

<div class="callout"><div class="callout__title">Stil-Katalog versus Designmethodik</div>

Wer dieses Repository verwendet, lernt, wie The Verge aussieht. Warum The Verge so aussieht, lernt er nicht. Das sind zwei verschiedene Dinge. The Verge hat sich für Neon Brutalism entschieden. Dahinter steht eine redaktionelle Haltung. Die Ästhetik kommuniziert sie laut, meinungsstark und ohne Entschuldigungen. Das Repo zeigt das Ergebnis dieser Entscheidung. Den Denkprozess dahinter zeigt es nicht.

Wer DESIGN.md-Dateien einsetzt, ohne den Kontext zu verstehen, gleicht jemandem, der ein Outfit nachkauft. Er weiß nicht, wofür es gedacht war. Das kann funktionieren. Oder es endet als stilistischer Kategorienfehler.
</div>

## Das Anti-Slop-Kit: der wertvollste Teil des Repos

Ein Abschnitt des Repos ist bemerkenswert selbstkritisch. Es ist das Anti-Slop-Kit. Anthropic beschreibt das Problem selbst in seinem Frontend-Aesthetics-Cookbook. Claude neigt dazu, generische, „on-distribution" Ausgaben zu produzieren. Im Frontend-Design erzeugt das, was Nutzerinnen „AI-Slop-Ästhetik" nennen. Gemeint sind Rounded Cards, Inter oder System-UI als Standardschrift, `#3b82f6` Blau als Akzent und großzügige, aber nichtssagende Abstände.

Das Anti-Slop-Kit in `awesome-claude-design` dokumentiert diese Fingerprints explizit. Es benennt auch Gegenstrategien. Metakognitive Designarbeit ist das. Man muss zuerst wissen, was man nicht will. Dann erst weiß man, was man will. Dazu gehört das Wissen, warum Claude genau das produziert, wenn man keine Direktive gibt.

Einen didaktischen Wert, der über die DESIGN.md-Dateien hinausgeht, hat dieser Teil des Repos. Er macht ein strukturelles Problem sichtbar. KI-Generierung konvergiert zu statistischen Mittelmäßen. Er gibt auch Werkzeuge, um dagegen zu arbeiten. Die Leitfrage lautet, wie man Designintention so präzise kommuniziert, dass das Modell keine Lücken mit Defaults füllen kann. Für den Unterricht ist das eine gute Ausgangsbasis.

## Wartbarkeit als strukturelles Problem des Formats

Markenästhetiken ändern sich. The Verge hat seit 2023 mehrfach typografische Anpassungen vorgenommen. Linear hat im letzten Jahr die Farbpalette erweitert. Eine DESIGN.md-Datei, die im April 2026 akkurat war, kann in sechs Monaten veraltet sein. Claude wird das nicht wissen.

Das Repo hat 0 offene Issues. Zwei Dinge kann das bedeuten. Entweder arbeiten die Templates so gut, dass es keinen Bedarf für Korrekturen gibt. Oder die Nutzerzahl ist noch zu klein für aktive Fehlermeldungen. Bei einem zwei Monate alten Repo ist letzteres wahrscheinlicher.

Rohit Ghumare ist als Maintainer verifizierbar. Er ist Google Developer Expert und Docker Captain. Als aktiver Open-Source-Contributor hat er mehrere Projekte, die technische Tiefe beweisen. Sein primärer Hintergrund liegt allerdings in DevRel und Cloud-Infrastruktur und nicht in Design. Das sieht man an manchen Stellen im Repo. Ingenieursorientiert sind die Rezepte. Dazu zählen Landing Page in 20 Minuten und Pitch Deck from README. Sie bieten schnelle Outputs und klaren Nutzen. Das erklärt, warum die Taxonomie der ästhetischen Familien weniger belastbar ist als die einzelnen DESIGN.md-Dateien. Ein Werturteil ist das nicht.

## Empfehlung für den Unterrichtseinsatz

`awesome-claude-design` eignet sich gut als Praxis-Material, mit einer wichtigen Bedingung. Es sollte nicht als fertige Methodik eingesetzt werden. Es taugt als Ausgangsmaterial für eine kritische Analyse.

Eine produktive Übung beginnt mit einer DESIGN.md aus dem Repo, zum Beispiel der The-Verge-Datei. Studenten öffnen die tatsächliche Website und prüfen jede Behauptung. Sie prüfen Schriftart, Farbwert und Einhaltung der Do/Don't-Regeln. Dann generieren sie mit Claude Design ein Interface. Das Ergebnis vergleichen sie mit der Referenzmarke.

Drei Dinge lehrt diese Übung gleichzeitig. Sie zeigt, wie DESIGN.md als Format funktioniert. Sie zeigt, wie man Designentscheidungen auf ihre tatsächliche Herkunft zurückverfolgt. Und sie zeigt, warum der Abstand zwischen „Stilbeschreibung" und „Designprinzip" größer ist, als er zunächst erscheint.

Das Anti-Slop-Kit eignet sich als Einführungstext in die Diskussion über KI-Defaults und Kreativität. Diese Diskussion wird im Design-Unterricht immer relevanter.

Das Projekt sollte dabei ehrlich als das eingeführt werden, was es ist. Es ist eine kuratierte Sammlung von Stil-Snapshots und kein Methodenbuch. Wer diesen Unterschied versteht, profitiert vom Repo.
