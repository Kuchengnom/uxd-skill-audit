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

Die meisten Skills in diesem Oekosystem positionieren sich durch Umfang. `mastepanoski/claude-skills` positioniert sich durch Quellenangaben. Das ist ein seltener Unterschied — und ein wichtiger Startpunkt fuer eine Evaluation.

## Was das Repository verspricht

Mauro Stepanoski, Systems Engineer und Consultant aus dem GitHub-Profil erkennbar, hat ein Repository aufgebaut das zwei Welten unter einem Dach vereint: UX/UI-Evaluations-Skills einerseits, AI-Governance- und Security-Skills andererseits.

Die UX-Seite umfasst: `nielsen-heuristics-audit` (Jakobs Nielsens 10 Usability-Heuristiken), `wcag-accessibility-audit` (WCAG 2.2), `ux-audit-rethink` (ganzheitliche UX-Bewertung nach Interaction Design Foundation-Methodik) und `ui-design-review` (visuelle Designqualitaet). Die AI-Governance-Seite umfasst: `owasp-ai-testing` (OWASP AI Testing Guide v1), Skills fuer NIST AI RMF, ISO 42001 und OWASP LLM Top 10.

Das ist, verglichen mit allem bisher Evaluierten in diesem Blog, das Framework-dichteste Repository im Oekosystem. Nielsen, WCAG, Don Norman, NIST, ISO, OWASP — das sind keine selbst erfundenen Kategorien. Das sind publizierte Standards mit Versionen, Autorenschaft und unabhaengiger Verifikation.

## Die methodische Fundierung — stark, aber mit Vorbehalt

Das Erste was auffaellt: Die zitierten Frameworks existieren wirklich. Das klingt banal, ist es aber nicht. In einem Oekosystem in dem Skills auf "99 UX-Richtlinien ohne Quellenangabe" oder "26 Design-Rollen als Systemanweisung" aufbauen, ist der Schritt zu verifizierbaren Standards ein struktureller Qualitaetssprung.

Nielsens 10 Heuristiken sind seit 1994 publiziert, mehrfach revidiert und von der Nielsen Norman Group ausfuehrlich dokumentiert. WCAG 2.2 ist ein W3C-Standard mit formaler Spezifikation. Der OWASP AI Testing Guide v1 ist ein Open-Source-Dokument mit 44 definierten Testfaellen, die Objectives, Payloads, Observable Responses und Remediation Guidance enthalten. Das ist eine ungewoehnlich strukturierte methodische Basis.

Der Vorbehalt: Ohne direkten Zugang zu den SKILL.md-Dateien selbst laesst sich nicht vollstaendig beurteilen, wie praezise die Portierung ist. Entscheidend beim Einsatz von Quellenframeworks ist nicht ob sie benannt werden — sondern ob sie korrekt uebersetzt wurden. Nielsens Heuristik "Visibility of System Status" zum Beispiel ist praezise definiert und laesst sich falsch portieren, auch wenn der Name stimmt. Dieser Vorbehalt senkt den Score von 5 auf 4.

## Das strukturelle Problem: Zwei Domanen, ein Maintainer

<div class="callout">
<div class="callout__title">Das Breitendilemma</div>
UX-Evaluationsmethodik und AI-Compliance-Standards sind epistemisch verschiedene Domänen. UX-Evaluation erfordert interpretatives Urteilsvermögen, Design-Expertise und Praxis mit Nutzerverhalten. AI-Governance erfordert Kenntnis von Risikomanagement-Frameworks, Compliance-Strukturen und technischer AI-Systemarchitektur. Beides gleichzeitig auf dem Niveau der Quell-Standards zu portieren ist eine Hypothese — keine Garantie.
</div>

Mauro Stepanoskis Background ist als Software Engineer und Consultant verifikbar. Sein GitHub-Profil zeigt andere aktive Projekte: `keycloak-authz` (Keycloak Authorization Client API), `legiblesync` (WYSIWID-Architektur in TypeScript), eine SQL-Similitude-Funktion auf Basis des Jaccard-Koeffizienten. Das ist ein solider Software-Engineering-Track-Record.

Was dieser Track-Record nicht unmittelbar belegt: spezialisierte UX-Praxis oder zertifizierte Expertise in AI-Governance-Compliance. Das ist kein Vorwurf — ein guter Engineer kann Frameworks korrekt portieren ohne selbst seit Jahren als UX-Researcher zu arbeiten. Aber es ist eine Frage die gestellt werden muss: Welches der beiden Domanen wird tiefer behandelt?

Die Antwort koennte durch direkten Vergleich mit den Quellstandards empirisch geprueft werden — etwas das im Unterrichtseinsatz explizit gemacht werden sollte.

## Was der OWASP-Skill besonders interessant macht

Der `owasp-ai-testing`-Skill verdient besondere Aufmerksamkeit, weil er einen anderen Reifegrad kommuniziert als die UX-Skills. Der OWASP AI Testing Guide v1 ist selbst ein strukturiertes Dokument mit 44 Testfaellen, die in vier Layers organisiert sind — und wenn das in den Skill uebertragen wurde, hat man hier tatsaechlich nachvollziehbare Pruefpfade.

Das ist ein bedeutender Unterschied zur UX-Evaluation-Seite: Ein WCAG-Audit oder eine Nielsen-Heuristik-Pruefung produziert interpretative Outputs (diese Schnittstelle verletzt Heuristik 5 "Error Prevention"). Ein OWASP-AI-Testing-Testfall produziert — zumindest konzeptionell — binaeere Outputs (Test bestanden oder nicht). Das ist ein anderer Typ von Validierbarkeit.

## Was der Skill nicht benennt — und benennen sollte

Hier liegt der zentrale Transparenzproblem. Ein Claude-Skill kann keinen WCAG-Audit durchfuehren wie ein Accessibility-Pruefwerkzeug es tut. Er kann nicht automatisch Color-Contrast-Ratios berechnen, Keyboard-Navigation testen oder Screen-Reader-Kompatibilitaet pruefen. Er kann das Wissen um WCAG-Anforderungen aktivieren und Strukturprobleme identifizieren — aber nicht die Compliance eines Produkts bestätigen.

Das gleiche gilt fuer AI-Governance: Ein Skill kann nicht pruefen ob ein internes AI-System wirklich den NIST AI RMF-Anforderungen entspricht. Er kann Pruef-Fragen stellen, Risikofelder benennen und Gaps aufzeigen — aber keine formale Compliance-Zertifizierung durchfuehren.

Diese Grenze — zwischen "mit einem Framework informiert analysieren" und "nach einem Standard zertifizieren" — wird im Repository nach aktuellem Forschungsstand nicht explizit kommuniziert. Das ist keine katastrophale Luecke, aber es ist eine, die im Unterrichtskontext wichtig ist.

## Wartbarkeit: Aktiv, aber mit offenen Fragen

Das Repository wurde zuletzt im Februar 2026 aktualisiert — das ist aktuell. Es handelt sich um einen einzelnen Maintainer, was typisch fuer Community-Skills ist, aber die Frage der Nachfolge offen laesst. Der Lizenzstatus war nicht direkt pruefbar (GitHub-Zugang war bei dieser Evaluation blockiert), was in einem professionellen Unterrichtseinsatz vor der Nutzung zu klaeren ist.

Ein positives Signal: Stepanoski ist als Medium-Autor aktiv (Artikel "Building Legible Software for the Age of LLMs", November 2025) und auf X/Twitter praesenh. Das deutet auf echtes inhaltliches Engagement hin, nicht nur Code-Ablage.

## Empfehlung fuer den Unterrichtseinsatz

`mastepanoski/claude-skills` eignet sich gut als Lehrbeispiel auf zwei Ebenen.

**Positiv**: Als Gegenpol zu den quellenlosen Datenbank-Skills in diesem Blog zeigt es, wie methodische Fundierung konkret aussieht. Studierende koennen an diesem Repository lernen, was es bedeutet Frameworks korrekt zu benennen — und dann selbst ueberpruefen ob die Portierung stimmt. Nielsens Heuristiken sind so gut dokumentiert dass ein Vergleich zwischen den Quellen und dem Skill-Output ein pruefbares Lernprojekt ist.

**Kritisch**: Als Einstieg in die Frage "Was kann ein LLM-Skill wirklich leisten?" ist das Repository exemplarisch. Die Skills behaupten implizit Faehigkeiten (WCAG-Compliance prufen, NIST-Risiken bewerten), die ein LLM strukturell nur teilweise erfullen kann. Diese Luecke zwischen Frameworks korrekt benennen und Frameworks vollstaendig anwenden ist eine der zentralen Lernfragen im Umgang mit AI-gestuetzten Design-Werkzeugen.

Das Urteil ist **vertrauen** — mit der expliziten Empfehlung, vor dem Einsatz die Portierungsqualitaet einzelner Skills anhand der Quellstandards zu vergleichen, und mit dem Nutzer im Klaren darueber zu sein, dass "AI-gestutzte WCAG-Analyse" kein Ersatz fuer automatisierte Accessibility-Tests oder manuelle Expertenpruefungen ist.
