---
layout: post
title: "mastepanoski/claude-skills: Methodisch ambitioniert — aber zwei Domänen, eine Warteschlange"
date: 2026-04-13
category: Skill-Evaluation
skill_reviewed: "mastepanoski/claude-skills"
verdict: vertrauen
reading_time: 12
last_audited: "13. April 2026"

skill_scores:
  methodische_fundierung: 4
  methodische_fundierung_note: "Anerkannte Standards korrekt benannt; Portierungstiefe ohne direkten Quellzugang nicht vollständig prüfbar"
  transparenz: 3
  transparenz_note: "Skill-Kombinationshinweise vorhanden, aber fundamentale LLM-Grenzen bei Compliance-Prüfung bleiben unbenannt"
  validierbarkeit: 3
  validierbarkeit_note: "OWASP-Skill strukturiert mit 44 Testfällen; UX-Evaluation-Skills ohne überprüfbare Referenzoutputs"
  wartbarkeit: 3
  wartbarkeit_note: "Einzelner Maintainer mit verifizierbarem Software-Hintergrund; aktiv per Februar 2026, Lizenzstatus unklar"

tags:
  - nielsen-heuristiken
  - wcag
  - ai-governance
  - owasp
  - positives-beispiel
  - domainkomplexität
  - skill-evaluation
---

Die meisten Skills in diesem Ökosystem positionieren sich durch Umfang. `mastepanoski/claude-skills` positioniert sich durch Quellenangaben. Das ist ein seltener Unterschied. Für eine Evaluation ist er ein wichtiger Startpunkt.

## Was das Repository verspricht

Mauro Stepanoski ist laut GitHub-Profil Systems Engineer und Consultant. Er hat ein Repository aufgebaut, das zwei Welten vereint. Auf der einen Seite stehen UX/UI-Evaluations-Skills. Auf der anderen stehen AI-Governance- und Security-Skills.

Die UX-Seite umfasst vier Skills. `nielsen-heuristics-audit` deckt Jakob Nielsens 10 Usability-Heuristiken ab. `wcag-accessibility-audit` deckt WCAG 2.2 ab. `ux-audit-rethink` bewertet UX ganzheitlich nach der Methodik der Interaction Design Foundation. `ui-design-review` prüft die visuelle Designqualität. Die AI-Governance-Seite umfasst `owasp-ai-testing` nach dem OWASP AI Testing Guide v1. Dazu kommen Skills für NIST AI RMF, ISO 42001 und OWASP LLM Top 10.

Verglichen mit allem bisher Evaluierten ist das das Framework-dichteste Repository im Ökosystem. Nielsen, WCAG, Don Norman, NIST, ISO und OWASP sind keine selbst erfundenen Kategorien. Es sind publizierte Standards mit Versionen, Autorenschaft und unabhängiger Verifikation.

## Die methodische Fundierung: stark, aber mit Vorbehalt

Zuerst fällt auf, dass die zitierten Frameworks wirklich existieren. Banal klingt das. Banal ist es nicht. Viele Skills bauen auf „99 UX-Richtlinien ohne Quellenangabe" oder „26 Design-Rollen als Systemanweisung". Verglichen damit ist der Schritt zu verifizierbaren Standards ein struktureller Qualitätssprung.

Nielsens 10 Heuristiken sind seit 1994 publiziert. Sie wurden mehrfach revidiert, und die Nielsen Norman Group dokumentiert sie ausführlich. WCAG 2.2 ist ein W3C-Standard mit formaler Spezifikation. Der OWASP AI Testing Guide v1 ist ein Open-Source-Dokument mit 44 definierten Testfällen. Sie enthalten Objectives, Payloads, Observable Responses und Remediation Guidance. Eine ungewöhnlich strukturierte methodische Basis.

Der Vorbehalt betrifft die SKILL.md-Dateien. Ohne direkten Zugang lässt sich nicht vollständig beurteilen, wie präzise die Portierung ist. Beim Einsatz von Quellenframeworks zählt nicht, ob sie benannt werden. Es zählt, ob sie korrekt übersetzt wurden. Nielsens Heuristik „Visibility of System Status" ist präzise definiert. Auch bei stimmendem Namen kann man sie falsch portieren. Der Vorbehalt senkt den Score von 5 auf 4.

## Das strukturelle Problem: Zwei Domänen, ein Maintainer

<div class="callout">
<div class="callout__title">Das Breitendilemma</div>
UX-Evaluationsmethodik und AI-Compliance-Standards sind epistemisch verschiedene Domänen. UX-Evaluation erfordert interpretatives Urteilsvermögen, Design-Expertise und Praxis mit Nutzerverhalten. AI-Governance erfordert Kenntnis von Risikomanagement-Frameworks, Compliance-Strukturen und technischer AI-Systemarchitektur. Beides auf dem Niveau der Quell-Standards zu portieren, ist eine Hypothese. Eine Garantie ist es nicht.
</div>

Mauro Stepanoskis Background als Software Engineer und Consultant ist verifizierbar. Sein GitHub-Profil zeigt andere aktive Projekte. `keycloak-authz` ist eine Keycloak Authorization Client API. `legiblesync` nutzt eine WYSIWID-Architektur in TypeScript. Dazu kommt eine SQL-Similitude-Funktion auf Basis des Jaccard-Koeffizienten. Das ist ein solider Software-Engineering-Track-Record.

Spezialisierte UX-Praxis belegt er nicht unmittelbar. Zertifizierte Expertise in AI-Governance-Compliance belegt er auch nicht. Ein Vorwurf ist das nicht. Ein guter Engineer kann Frameworks korrekt portieren. Dafür muss er nicht seit Jahren als UX-Researcher arbeiten. Trotzdem muss man eine Frage stellen. Welche der beiden Domänen wird tiefer behandelt?

Empirisch lässt sich die Antwort prüfen. Ein direkter Vergleich mit den Quellstandards genügt. Im Unterrichtseinsatz sollte genau das explizit gemacht werden.

## Was der OWASP-Skill besonders interessant macht

Der `owasp-ai-testing`-Skill verdient besondere Aufmerksamkeit. Er kommuniziert einen anderen Reifegrad als die UX-Skills. Der OWASP AI Testing Guide v1 ist selbst ein strukturiertes Dokument mit 44 Testfällen in vier Layers. Wurde das in den Skill übertragen, gibt es hier tatsächlich nachvollziehbare Prüfpfade.

Zur UX-Evaluation-Seite besteht ein bedeutender Unterschied. Ein WCAG-Audit oder eine Nielsen-Heuristik-Prüfung liefert interpretative Outputs. Ein Beispiel ist der Satz „diese Schnittstelle verletzt Heuristik 5, Error Prevention". Ein OWASP-AI-Testing-Testfall liefert zumindest konzeptionell einen binären Output. Der Test ist bestanden oder nicht. Das ist ein anderer Typ von Validierbarkeit.

## Was der Skill nicht benennt, und benennen sollte

Hier liegt das zentrale Transparenzproblem. Ein Claude-Skill kann keinen WCAG-Audit durchführen wie ein Accessibility-Prüfwerkzeug. Er berechnet keine Color-Contrast-Ratios automatisch. Er testet keine Keyboard-Navigation. Er prüft keine Screen-Reader-Kompatibilität. Er kann das Wissen um WCAG-Anforderungen aktivieren und Strukturprobleme identifizieren. Die Compliance eines Produkts bestätigt er nicht.

Für AI-Governance gilt dasselbe. Ein Skill kann nicht prüfen, ob ein internes AI-System wirklich den NIST AI RMF-Anforderungen entspricht. Er kann Prüf-Fragen stellen, Risikofelder benennen und Gaps aufzeigen. Eine formale Compliance-Zertifizierung führt er nicht durch.

Diese Grenze verläuft zwischen „mit einem Framework informiert analysieren" und „nach einem Standard zertifizieren". Das Repository kommuniziert sie nach aktuellem Forschungsstand nicht explizit. Das ist keine katastrophale Lücke. Im Unterrichtskontext ist sie trotzdem wichtig.

## Wartbarkeit: Aktiv, aber mit offenen Fragen

Das Repository wurde zuletzt im Februar 2026 aktualisiert und ist damit aktuell. Es hat einen einzelnen Maintainer. Das ist typisch für Community-Skills. Die Frage der Nachfolge bleibt offen. Den Lizenzstatus konnte ich nicht direkt prüfen. Der GitHub-Zugang war bei dieser Evaluation blockiert. Vor einem professionellen Unterrichtseinsatz ist das zu klären.

Ein positives Signal gibt es. Stepanoski ist als Medium-Autor aktiv, etwa mit dem Artikel „Building Legible Software for the Age of LLMs" vom November 2025. Auf X/Twitter ist er präsent. Das deutet auf echtes inhaltliches Engagement hin und nicht nur auf Code-Ablage.

## Empfehlung für den Unterrichtseinsatz

`mastepanoski/claude-skills` eignet sich gut als Lehrbeispiel auf zwei Ebenen.

**Positiv**: Das Repository ist der Gegenpol zu den quellenlosen Datenbank-Skills in diesem Blog. Es zeigt, wie methodische Fundierung konkret aussieht. Studierende lernen hier, Frameworks korrekt zu benennen. Danach überprüfen sie selbst, ob die Portierung stimmt. Nielsens Heuristiken sind gut dokumentiert. Ein Vergleich zwischen den Quellen und dem Skill-Output ist deshalb ein prüfbares Lernprojekt.

**Kritisch**: Als Einstieg in die Frage „Was kann ein LLM-Skill wirklich leisten?" ist das Repository exemplarisch. Die Skills behaupten implizit Fähigkeiten wie WCAG-Compliance prüfen oder NIST-Risiken bewerten. Ein LLM erfüllt sie strukturell nur teilweise. Frameworks korrekt benennen und Frameworks vollständig anwenden sind zwei Dinge. Diese Lücke ist eine zentrale Lernfrage im Umgang mit AI-gestützten Design-Werkzeugen.

Das Urteil ist **vertrauen**, mit zwei Auflagen. Vor dem Einsatz sollte man die Portierungsqualität einzelner Skills anhand der Quellstandards vergleichen. Und dem Nutzer muss klar sein, was „AI-gestützte WCAG-Analyse" leistet. Automatisierte Accessibility-Tests ersetzt sie nicht. Manuelle Expertenprüfungen ersetzt sie auch nicht.
