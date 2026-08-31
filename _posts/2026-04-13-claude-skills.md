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
  methodische_fundierung_note: "Anerkannte Standards korrekt benannt; Portierungstiefe ohne direkten Quellzugang nicht vollstaendig pruefbar"
  transparenz: 3
  transparenz_note: "Skill-Kombinationshinweise vorhanden, aber fundamentale LLM-Grenzen bei Compliance-Pruefung bleiben unbenannt"
  validierbarkeit: 3
  validierbarkeit_note: "OWASP-Skill strukturiert mit 44 Testfaellen; UX-Evaluation-Skills ohne ueberprueifbare Referenzoutputs"
  wartbarkeit: 3
  wartbarkeit_note: "Einzelner Maintainer mit verifizierbarem Software-Hintergrund; aktiv per Februar 2026, Lizenzstatus unklar"

tags:
  - nielsen-heuristiken
  - wcag
  - ai-governance
  - owasp
  - positives-beispiel
  - domainkomplexitaet
  - skill-evaluation
---

Die meisten Skills in diesem Ökosystem positionieren sich durch Umfang. `mastepanoski/claude-skills` positioniert sich durch Quellenangaben. Das ist ein seltener Unterschied und ein wichtiger Startpunkt für eine Evaluation.

## Was das Repository verspricht

Mauro Stepanoski, Systems Engineer und Consultant aus dem GitHub-Profil erkennbar, hat ein Repository aufgebaut das zwei Welten unter einem Dach vereint: UX/UI-Evaluations-Skills einerseits, AI-Governance- und Security-Skills andererseits.

Die UX-Seite umfasst vier Skills: `nielsen-heuristics-audit` für Jakob Nielsens 10 Usability-Heuristiken, `wcag-accessibility-audit` für WCAG 2.2, `ux-audit-rethink` für eine ganzheitliche UX-Bewertung nach der Methodik der Interaction Design Foundation und `ui-design-review` für visuelle Designqualität. Die AI-Governance-Seite umfasst `owasp-ai-testing` nach dem OWASP AI Testing Guide v1 sowie Skills für NIST AI RMF, ISO 42001 und OWASP LLM Top 10.

Das ist, verglichen mit allem bisher Evaluierten in diesem Blog, das Framework-dichteste Repository im Ökosystem. Nielsen, WCAG, Don Norman, NIST, ISO, OWASP: das sind keine selbst erfundenen Kategorien. Das sind publizierte Standards mit Versionen, Autorenschaft und unabhängiger Verifikation.

## Die methodische Fundierung: stark, aber mit Vorbehalt

Das Erste was auffällt: Die zitierten Frameworks existieren wirklich. Das klingt banal, ist es aber nicht. In einem Ökosystem in dem Skills auf „99 UX-Richtlinien ohne Quellenangabe" oder „26 Design-Rollen als Systemanweisung" aufbauen, ist der Schritt zu verifizierbaren Standards ein struktureller Qualitätssprung.

Nielsens 10 Heuristiken sind seit 1994 publiziert, mehrfach revidiert und von der Nielsen Norman Group ausführlich dokumentiert. WCAG 2.2 ist ein W3C-Standard mit formaler Spezifikation. Der OWASP AI Testing Guide v1 ist ein Open-Source-Dokument mit 44 definierten Testfällen, die Objectives, Payloads, Observable Responses und Remediation Guidance enthalten. Das ist eine ungewöhnlich strukturierte methodische Basis.

Der Vorbehalt: Ohne direkten Zugang zu den SKILL.md-Dateien selbst lässt sich nicht vollständig beurteilen, wie präzise die Portierung ist. Entscheidend beim Einsatz von Quellenframeworks ist nicht ob sie benannt werden, sondern ob sie korrekt übersetzt wurden. Nielsens Heuristik „Visibility of System Status" zum Beispiel ist präzise definiert und lässt sich falsch portieren, auch wenn der Name stimmt. Dieser Vorbehalt senkt den Score von 5 auf 4.

## Das strukturelle Problem: Zwei Domanen, ein Maintainer

<div class="callout">
<div class="callout__title">Das Breitendilemma</div>
UX-Evaluationsmethodik und AI-Compliance-Standards sind epistemisch verschiedene Domänen. UX-Evaluation erfordert interpretatives Urteilsvermögen, Design-Expertise und Praxis mit Nutzerverhalten. AI-Governance erfordert Kenntnis von Risikomanagement-Frameworks, Compliance-Strukturen und technischer AI-Systemarchitektur. Beides gleichzeitig auf dem Niveau der Quell-Standards zu portieren ist eine Hypothese, keine Garantie.
</div>

Mauro Stepanoskis Background ist als Software Engineer und Consultant verifikbar. Sein GitHub-Profil zeigt andere aktive Projekte: `keycloak-authz` als Keycloak Authorization Client API, `legiblesync` mit WYSIWID-Architektur in TypeScript, dazu eine SQL-Similitude-Funktion auf Basis des Jaccard-Koeffizienten. Das ist ein solider Software-Engineering-Track-Record.

Was dieser Track-Record nicht unmittelbar belegt: spezialisierte UX-Praxis oder zertifizierte Expertise in AI-Governance-Compliance. Das ist kein Vorwurf. Ein guter Engineer kann Frameworks korrekt portieren ohne selbst seit Jahren als UX-Researcher zu arbeiten. Aber es ist eine Frage die gestellt werden muss: Welches der beiden Domanen wird tiefer behandelt?

Die Antwort könnte durch direkten Vergleich mit den Quellstandards empirisch geprüft werden. Genau das sollte im Unterrichtseinsatz explizit gemacht werden.

## Was der OWASP-Skill besonders interessant macht

Der `owasp-ai-testing`-Skill verdient besondere Aufmerksamkeit, weil er einen anderen Reifegrad kommuniziert als die UX-Skills. Der OWASP AI Testing Guide v1 ist selbst ein strukturiertes Dokument mit 44 Testfällen, die in vier Layers organisiert sind. Wenn das in den Skill übertragen wurde, hat man hier tatsächlich nachvollziehbare Prüfpfade.

Das ist ein bedeutender Unterschied zur UX-Evaluation-Seite. Ein WCAG-Audit oder eine Nielsen-Heuristik-Prüfung produziert interpretative Outputs, etwa den Satz „diese Schnittstelle verletzt Heuristik 5, Error Prevention". Ein OWASP-AI-Testing-Testfall produziert zumindest konzeptionell einen binären Output: Test bestanden oder nicht. Das ist ein anderer Typ von Validierbarkeit.

## Was der Skill nicht benennt, und benennen sollte

Hier liegt der zentrale Transparenzproblem. Ein Claude-Skill kann keinen WCAG-Audit durchführen wie ein Accessibility-Prüfwerkzeug es tut. Er kann nicht automatisch Color-Contrast-Ratios berechnen, Keyboard-Navigation testen oder Screen-Reader-Kompatibilität prüfen. Er kann das Wissen um WCAG-Anforderungen aktivieren und Strukturprobleme identifizieren, aber nicht die Compliance eines Produkts bestätigen.

Das gleiche gilt für AI-Governance: Ein Skill kann nicht prüfen ob ein internes AI-System wirklich den NIST AI RMF-Anforderungen entspricht. Er kann Prüf-Fragen stellen, Risikofelder benennen und Gaps aufzeigen, aber keine formale Compliance-Zertifizierung durchführen.

Diese Grenze verläuft zwischen „mit einem Framework informiert analysieren" und „nach einem Standard zertifizieren". Sie wird im Repository nach aktuellem Forschungsstand nicht explizit kommuniziert. Das ist keine katastrophale Lücke, aber es ist eine, die im Unterrichtskontext wichtig ist.

## Wartbarkeit: Aktiv, aber mit offenen Fragen

Das Repository wurde zuletzt im Februar 2026 aktualisiert, ist also aktuell. Es handelt sich um einen einzelnen Maintainer, was typisch für Community-Skills ist, aber die Frage der Nachfolge offen lässt. Der Lizenzstatus war nicht direkt prüfbar, weil der GitHub-Zugang bei dieser Evaluation blockiert war. Das ist in einem professionellen Unterrichtseinsatz vor der Nutzung zu klären.

Ein positives Signal: Stepanoski ist als Medium-Autor aktiv, etwa mit dem Artikel „Building Legible Software for the Age of LLMs" vom November 2025, und auf X/Twitter präsent. Das deutet auf echtes inhaltliches Engagement hin, nicht nur Code-Ablage.

## Empfehlung für den Unterrichtseinsatz

`mastepanoski/claude-skills` eignet sich gut als Lehrbeispiel auf zwei Ebenen.

**Positiv**: Als Gegenpol zu den quellenlosen Datenbank-Skills in diesem Blog zeigt es, wie methodische Fundierung konkret aussieht. Studierende können an diesem Repository lernen, was es bedeutet Frameworks korrekt zu benennen, und dann selbst überprüfen ob die Portierung stimmt. Nielsens Heuristiken sind so gut dokumentiert dass ein Vergleich zwischen den Quellen und dem Skill-Output ein prüfbares Lernprojekt ist.

**Kritisch**: Als Einstieg in die Frage „Was kann ein LLM-Skill wirklich leisten?" ist das Repository exemplarisch. Die Skills behaupten implizit Fähigkeiten wie WCAG-Compliance prüfen oder NIST-Risiken bewerten, die ein LLM strukturell nur teilweise erfüllen kann. Diese Lücke zwischen Frameworks korrekt benennen und Frameworks vollständig anwenden ist eine der zentralen Lernfragen im Umgang mit AI-gestützten Design-Werkzeugen.

Das Urteil ist **vertrauen**, mit zwei Auflagen. Vor dem Einsatz sollte die Portierungsqualität einzelner Skills anhand der Quellstandards verglichen werden. Und dem Nutzer muss klar sein, dass „AI-gestützte WCAG-Analyse" kein Ersatz für automatisierte Accessibility-Tests oder manuelle Expertenprüfungen ist.
