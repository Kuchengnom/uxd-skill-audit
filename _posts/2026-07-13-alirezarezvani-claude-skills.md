---
layout: post
title: "claude-skills: Die Mega-Sammlung, die ihre eigene Schwäche schriftlich dokumentiert"
date: 2026-07-13
category: Skill-Evaluation
skill_reviewed: "alirezarezvani/claude-skills"
verdict: vertrauen
reading_time: 11
last_audited: "13. Juli 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "Die Design-Skills nutzen anerkannte Methoden (Personas, Journey Maps, WCAG-AA-Werte korrekt), aber das repo-eigene Audit vom Juli 2026 bestätigt: 60 von 64 Referenzdateien der Produkt-Domäne zitieren keine einzige Quelle."
  transparenz: 3
  transparenz_note: "Auf Repo-Ebene vorbildlich (öffentliche Selbst-Audits mit hartem Urteil), auf Skill-Ebene schwach — die einzelnen Design-Skills kommunizieren kaum Grenzen und akzeptieren laut eigenem Audit 'any input silently'."
  validierbarkeit: 4
  validierbarkeit_note: "602 stdlib-only Python-Skripte, CI-Zählervalidierung, dokumentierte Audit-Rubrik mit Smoke-Tests aller 31 Produkt-Skripte — aber Verifikationsgates sind laut Audit 'all optional, none looped'."
  wartbarkeit: 5
  wartbarkeit_note: "Identifizierbarer Maintainer, MIT-Lizenz, Semver mit gepflegtem Changelog, CONTRIBUTING/SECURITY/CODE_OF_CONDUCT, externe Contributor-PRs, letzter Commit sechs Tage vor diesem Audit."

tags:
  - skill-sammlung
  - mega-collection
  - self-audit
  - quellenarbeit
  - ux-research
  - design-tokens
  - skill-evaluation
---

Mit `HermeticOrmus/LibreUIUX-Claude-Code` hat diese Serie im Mai den Extremfall der Quantitäts-Falle untersucht: 152 Agenten, 74 Skills, kaum Kohärenz. `alirezarezvani/claude-skills` ist mit 355 Skills in 18 Domänen, 99 Agenten und 109 Commands nominell noch größer. Über 22.000 GitHub-Stars, 1.228 Commits, letzter Merge sechs Tage vor diesem Audit. Nach der bisherigen Logik dieser Serie müsste das Urteil reflexhaft lauten: zu breit, zu viel, Vorsicht. Doch dieses Repository macht etwas, das bislang kein evaluierter Kandidat gemacht hat. Es auditiert sich selbst, öffentlich, mit Rubrik, und mit Ergebnissen die dem Projekt nicht schmeicheln.

Für den Designkontext dieser Serie konzentriert sich die Evaluation auf die Produkt-Domäne: 17 Skills, darunter `ui-design-system` für Design-Tokens, Typografie-Skalen und Developer-Handoff und `ux-researcher-designer` für Personas, Journey Maps und Usability-Tests. Die Befunde lassen sich aber nur verstehen, wenn man die Governance-Struktur des Gesamtrepos mitliest.

## Was die Design-Skills konkret liefern

`ui-design-system` folgt einem klaren Muster: Trigger-Begriffe, vier Workflows, ein ausführbares Python-Skript namens `design_token_generator.py`, vier Referenzdateien. Die WCAG-Werte sind korrekt portiert, also 4,5:1 für Normaltext und 3:1 für großen Text. Das 8pt-Grid und die Token-Kategorien entsprechen gängiger Praxis. `ux-researcher-designer` bringt einen Persona-Generator mit, der aus strukturierten Nutzerdaten Archetypen ableitet, dazu Referenzdateien zu Persona-Methodik, Journey Mapping und Usability-Test-Frameworks.

Inhaltlich ist das solide Praktikerwissen. Die Methodenauswahl-Matrix für Usability-Tests ist brauchbar, die Persona-Methodik warnt vor fiktiven Personas ohne Datenbasis. Auffällig ist eine Detailabweichung. Der Skill gibt Nielsens bekannte Fünf-Nutzer-Regel mit „75–80 % der Usability-Probleme" an, während die kanonische NN/g-Zahl aus Nielsen und Landauer bei etwa 85 % liegt. Das ist kein grober Fehler, aber ein Symptom. Wo keine Quelle zitiert wird, lässt sich auch nicht prüfen welche Fassung der Regel gemeint ist.

## Der bemerkenswerte Teil: das Repo weiß das selbst

Im Verzeichnis `audit/` liegen datierte Selbst-Audits, zuletzt vom 3. Juli 2026, mit einer sechsdimensionalen Rubrik zur „Agentic-Readiness", Smoke-Tests aller 31 Produkt-Skripte und einem Scorecard-Urteil, das hart ausfällt: Von 26 Skills der Produkt- und PM-Domäne sind nur 3 „harness-ready", 14 werden als „TOOL-ONLY, good tools, no loop spine" eingestuft. Und dann steht dort dieser Satz, der die zentrale Frage dieser Blogserie in einem Nebensatz beantwortet: „60 of 64 reference files cite zero sources."

<div class="callout">
<div class="callout__title">Selbstdiagnose ersetzt keine Quellenarbeit, aber sie verändert die Bewertung</div>
Das wiederkehrende Problem dieser Serie liegt hier in vollem Umfang vor: Skills, die anerkannte Methoden verwenden, ohne die Brücke zur Quelle zu bauen. Der Unterschied ist, dass <code>alirezarezvani/claude-skills</code> es selbst gemessen, dokumentiert und in einen Verbesserungsplan überführt hat, statt es hinter Autoritätsvokabular zu verstecken. Für Lernende ist das der eigentliche Lehrwert dieses Repos. Ein ehrlich dokumentierter Mangel ist bewertbar und behebbar. Ein verschwiegener Mangel ist beides nicht. Wer aber heute die Design-Skills einsetzt, arbeitet trotzdem mit weitgehend unbelegten Referenzdateien. Die Selbstdiagnose ist ein Versprechen, noch kein eingelöstes.
</div>

Dieselbe Ernsthaftigkeit zeigt sich in der Infrastruktur. Ein CI-Gate namens `derive_counters.py --check` validiert inzwischen, dass die im README behaupteten Skill-Zahlen mit dem tatsächlichen Bestand übereinstimmen. Eingeführt wurde es, nachdem die Zahlen „silently" gedriftet waren. Dass der Repo-Titel zum Auditzeitpunkt „345" sagt, die README-Überschrift „355" und der Changelog „354", zeigt allerdings, dass dieses Gate die Drift noch nicht vollständig eingefangen hat. Bei einem Projekt dieser Größe ist das verzeihlich. Erwähnenswert ist es, weil Zahlengenauigkeit hier explizit als Qualitätsversprechen auftritt.

## Wartung als Stärke, Skill-Ebene als Schwäche

Die Wartbarkeit ist die beste, die in dieser Serie bisher gemessen wurde: identifizierbarer Maintainer namens Alireza Rezvani, MIT-Lizenz, Semantic Versioning mit gepflegtem Changelog inklusive nachgetragener Contributor-Credits, CONTRIBUTING-, SECURITY- und CODE_OF_CONDUCT-Dokumente, ein publizierter Skill-Authoring-Standard und nur drei offene Issues bei über tausend Commits. Externe Pull Requests werden nicht nur gemerged, sondern nachträglich „gehärtet" und im Changelog attribuiert.

Die Schwäche liegt eine Ebene tiefer. Die einzelnen Design-Skills kommunizieren ihre Grenzen kaum: Der Persona-Generator warnt nicht davor, dass aus fünf Datensätzen kein valides Archetyp-Clustering entsteht; `ui-design-system` erklärt nicht, wann ein algorithmisch generiertes Token-Set eine bewusste Farbentscheidung ersetzen kann und wann nicht. Das eigene Audit benennt genau das als schwächste Dimension: Die meisten Skills „accept any input silently".

## Empfehlung für den Unterricht

Für Lehrveranstaltungen eignet sich dieses Repository auf zwei Arten. Erstens als Gegenbeispiel zu LibreUIUX in der Frage, wie ein Großprojekt mit Komplexität umgehen kann. Authoring-Standard, CI-Gates, datierte Audits mit Rubrik: das ist Governance, die sich direkt neben die Quantitäts-Falle legen lässt. Zweitens als Übungsmaterial. Studierende können die Fünf-Nutzer-Regel im Skill gegen die Originalquelle prüfen und erleben dabei konkret, warum „Quelle fehlt" kein Formalismus ist. Für den produktiven Einsatz gilt: Die ausführbaren Werkzeuge wie Token-Generator und Kontrastprüfung sind nutzbar, die Referenzdateien sollten bis zur angekündigten Quellen-Nachrüstung als unbelegtes Praktikerwissen behandelt werden. Also mit Vorbehalt, aber mit begründetem Vertrauen in ein Projekt, das seine Mängel selbst findet bevor es ein Blog tun muss.
