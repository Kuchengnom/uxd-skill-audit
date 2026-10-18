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

Mit `HermeticOrmus/LibreUIUX-Claude-Code` hat diese Serie im Mai den Extremfall der Quantitäts-Falle untersucht. LibreUIUX brachte 152 Agenten und 74 Skills bei kaum Kohärenz. `alirezarezvani/claude-skills` ist nominell noch größer. Es hat 355 Skills in 18 Domänen, 99 Agenten und 109 Commands. Zusammen sind das 454 Einträge gegen 226 bei LibreUIUX. Dazu kommen über 22.000 GitHub-Stars und 1.228 Commits. Sechs Tage vor diesem Audit lief der letzte Merge.

Nach der bisherigen Logik dieser Serie müsste das Urteil reflexhaft lauten. Zu breit, zu viel, Vorsicht. Doch dieses Repository macht etwas, das kein evaluierter Kandidat bisher gemacht hat. Es auditiert sich selbst. Es ist öffentlich und hat eine Rubrik. Die Ergebnisse schmeicheln dem Projekt nicht.

Für den Designkontext dieser Serie konzentriert sich die Evaluation auf die Produkt-Domäne. Sie umfasst 17 Skills. `ui-design-system` deckt Design-Tokens, Typografie-Skalen und Developer-Handoff ab. `ux-researcher-designer` deckt Personas, Journey Maps und Usability-Tests ab. Wer die Befunde verstehen will, liest die Governance-Struktur des Gesamtrepos mit.

## Was die Design-Skills konkret liefern

`ui-design-system` folgt einem klaren Muster. Es hat Trigger-Begriffe, vier Workflows, ein ausführbares Python-Skript namens `design_token_generator.py` und vier Referenzdateien. WCAG-Werte sind korrekt portiert. Normaltext braucht 4,5:1, großer Text 3:1. 8pt-Grid und Token-Kategorien entsprechen gängiger Praxis. `ux-researcher-designer` bringt einen Persona-Generator mit. Er leitet aus strukturierten Nutzerdaten Archetypen ab. Dazu liegen Referenzdateien zu Persona-Methodik, Journey Mapping und Usability-Test-Frameworks bei.

Inhaltlich ist das solides Praktikerwissen. Brauchbar ist die Methodenauswahl-Matrix für Usability-Tests. Die Persona-Methodik warnt vor fiktiven Personas ohne Datenbasis. Auffällig ist eine Detailabweichung. Nielsens Fünf-Nutzer-Regel gibt der Skill mit „75–80 % der Usability-Probleme" an. Die kanonische NN/g-Zahl aus Nielsen und Landauer liegt bei etwa 85 %. Ein grober Fehler ist das nicht, aber ein Symptom. Ohne zitierte Quelle bleibt offen, wie die Regel gemeint ist.

## Der bemerkenswerte Teil: das Repo weiß das selbst

Im Verzeichnis `audit/` liegen datierte Selbst-Audits. Das jüngste datiert vom 3. Juli 2026. Es hat eine sechsdimensionale Rubrik zur „Agentic-Readiness" und Smoke-Tests aller 31 Produkt-Skripte. Hart fällt das Scorecard-Urteil aus. Von 26 Skills der Produkt- und PM-Domäne sind nur 3 „harness-ready". 14 gelten als „TOOL-ONLY, good tools, no loop spine". Dann steht dort ein Satz. Er beantwortet die zentrale Frage dieser Blogserie: „60 of 64 reference files cite zero sources."

<div class="callout">
<div class="callout__title">Selbstdiagnose ersetzt keine Quellenarbeit, verändert aber die Bewertung</div>
Das wiederkehrende Problem dieser Serie liegt hier in vollem Umfang vor. Skills verwenden anerkannte Methoden und bauen keine Brücke zur Quelle. <code>alirezarezvani/claude-skills</code> hat es selbst gemessen und dokumentiert. Daraus entstand ein Verbesserungsplan. Autoritätsvokabular versteckt nichts. Für Lernende liegt hier der eigentliche Lehrwert des Repos. Ein ehrlich dokumentierter Mangel ist bewertbar und behebbar. Ein verschwiegener Mangel ist beides nicht. Wer heute die Design-Skills einsetzt, arbeitet trotzdem mit weitgehend unbelegten Referenzdateien. Die Selbstdiagnose bleibt ein Versprechen. Eingelöst ist es noch nicht.
</div>

Dieselbe Ernsthaftigkeit zeigt sich in der Infrastruktur. Ein CI-Gate namens `derive_counters.py --check` validiert inzwischen die Skill-Zahlen im README gegen den tatsächlichen Bestand. Eingeführt wurde es, nachdem die Zahlen „silently" gedriftet waren. Zum Auditzeitpunkt sagt der Repo-Titel „345", die README-Überschrift „355" und der Changelog „354". Die Drift hat das Gate also noch nicht vollständig eingefangen. Bei einem Projekt dieser Größe ist das verzeihlich. Erwähnenswert ist es trotzdem. Zahlengenauigkeit tritt hier ausdrücklich als Qualitätsversprechen auf.

## Wartung als Stärke, Skill-Ebene als Schwäche

Die Wartbarkeit ist die beste, die diese Serie bisher gemessen hat. Maintainer ist der identifizierbare Alireza Rezvani. Lizenz ist MIT. Semantic Versioning kommt mit gepflegtem Changelog und nachgetragenen Contributor-Credits. CONTRIBUTING-, SECURITY- und CODE_OF_CONDUCT-Dokumente liegen vor. Dazu kommt ein publizierter Skill-Authoring-Standard. Nur drei Issues sind bei über tausend Commits offen. Externe Pull Requests werden gemerged und danach „gehärtet". Im Changelog stehen die Autoren.

Die Schwäche liegt eine Ebene tiefer. Einzelne Design-Skills kommunizieren ihre Grenzen kaum. Der Persona-Generator warnt nicht davor, dass fünf Datensätze kein valides Archetyp-Clustering ergeben. `ui-design-system` erklärt nicht, wann ein algorithmisch generiertes Token-Set eine bewusste Farbentscheidung ersetzen kann. Genau das nennt das eigene Audit die schwächste Dimension. Die meisten Skills „accept any input silently".

## Empfehlung für den Unterricht

Für Lehrveranstaltungen eignet sich dieses Repository auf zwei Arten. Erstens dient es als Gegenbeispiel zu LibreUIUX. Authoring-Standard, CI-Gates und datierte Audits mit Rubrik sind Governance. Sie lässt sich direkt neben die Quantitäts-Falle legen. Zweitens taugt es als Übungsmaterial. Studierende prüfen die Fünf-Nutzer-Regel im Skill gegen die Originalquelle. Dabei erleben sie, warum „Quelle fehlt" kein Formalismus ist.

Für den produktiven Einsatz gilt eine klare Trennung. Ausführbare Werkzeuge wie Token-Generator und Kontrastprüfung sind nutzbar. Die Referenzdateien gelten bis zur angekündigten Quellen-Nachrüstung als unbelegtes Praktikerwissen. Begründet ist das Vertrauen, aber mit Vorbehalt. Das Projekt findet seine Mängel selbst, bevor ein Blog es tun muss.
