---
layout: post
title: "ux-ui-agent-skills: Der bislang beste Prüfapparat der Serie — und eine Ebene, die er nicht prüft"
date: 2026-07-20
category: Skill-Evaluation
skill_reviewed: "plugin87/ux-ui-agent-skills"
verdict: vertrauen
reading_time: 12
last_audited: "20. Juli 2026"

skill_scores:
  methodische_fundierung: 4
  methodische_fundierung_note: "WCAG 2.2, WAI-ARIA, DTCG und Atomic Design sind korrekt portiert. Dazu gehört die feine Unterscheidung, dass grafische Bedienelemente nach 1.4.11 bei 3:1 und nicht bei 4.5:1 zu messen sind. Ohne Quellenbasis bleiben die 138 Marken-Systeme und die Gewichtung der sechs Review-Dimensionen."
  transparenz: 3
  transparenz_note: "Einzelne Grenzen benennt das Projekt ungewöhnlich klar. Das Taste-Audit gilt als Heuristik, „gates don't prove pixels\", Skills laufen mit Agent-Rechten. Die Persona „Senior Design Architect mit 15+ Jahren Erfahrung\" und die unqualifizierte Schlagzeile „25/25 = 100 %\" versprechen aber mehr, als der Apparat misst."
  validierbarkeit: 5
  validierbarkeit_note: "Ausführbare Gates messen echten Kontrast in Hell- und Dunkelmodus über alle Zustände, axe-core, Fokusfalle per echter Tastatureingabe, RTL und Überlauf bei 280/320/414 px. Alles wird in CI erzwungen und ist mit dokumentierten Fehlfunden belegt."
  wartbarkeit: 4
  wartbarkeit_note: "Sehr aktiv (v2.4.0, 34 Commits, automatisierte Release-Pipeline mit npm-Provenance, MIT-Lizenz). Getragen wird das Projekt aber von einem einzigen pseudonymen Account ohne verifizierbare Identität."

tags:
  - design-tokens
  - dtcg
  - wcag
  - accessibility
  - validierbarkeit
  - ci-gates
  - design-systeme
  - skill-evaluation
---

Die bisherigen Evaluationen dieser Serie sind immer an derselben Stelle gelandet. Skills behaupten Qualität und messen sie nicht. `alirezarezvani/claude-skills` machte im Juli den Anfang mit einem öffentlichen Selbst-Audit. Dessen Verifikationsgates waren laut eigenem Befund „all optional, none looped". `plugin87/ux-ui-agent-skills` geht den Schritt weiter, der bislang fehlte. Hier laufen die Prüfungen tatsächlich. Sie laufen in CI und blockieren den Merge.

Mit 411 Sternen und 34 Commits ist das Repository vergleichsweise klein. Die Aufmerksamkeit für `impeccable` oder `ui-ux-pro-max` liegt deutlich darüber. Genau das macht es für diese Serie interessant. Es ist das erste Projekt im Ökosystem, bei dem die Frage „Woher weißt du, dass das stimmt?" eine technische Antwort bekommt.

## Was hier tatsächlich gemessen wird

Kern ist `scripts/accuracy_report.mjs`. Ein Befehl liefert ein Alles-oder-Nichts-Ergebnis. Dahinter stehen Prüfungen, die sich einzeln nachvollziehen lassen.

`verify_states.mjs` startet einen Headless-Chrome und rendert die Komponenten-Harnesses. Es misst den tatsächlich berechneten Kontrast jedes interaktiven Elements. Geprüft werden die Zustände Default, Hover und Focus, jeweils in Hell- und Dunkelmodus. Der Changelog nennt den Fehler, den das gefunden hat. Ein Sekundär-Button übernahm beim Hover die Primärfüllung und fiel damit unter AA. Ein Ruhezustands-Test hätte das nie gesehen.

`verify_focustrap.mjs` öffnet einen Modal. Mit echten Tastatureingaben prüft es, ob Tab in der Falle bleibt. Es prüft auch, ob `role="dialog"` und `aria-modal` gesetzt sind und ob Escape schließt und den Fokus zurückgibt. Dokumentierter Fund war ein Drawer, der nie schloss. Ein `display:none`-`position:fixed`-Dialog hatte den Test zuvor fälschlich bestanden. `verify_rtl.mjs` rendert LTR gegen `dir="rtl"`. Es meldet Layouts, die nur gespiegelt überlaufen. Das ist das verlässliche Symptom physischer statt logischer CSS-Eigenschaften. `verify_responsive.mjs` bricht bei horizontalem Überlauf auf 280, 320 und 414 px ab. Dazu läuft axe-core gegen WCAG 2.0/2.1/2.2 A + AA. Es fand einen echten fehlenden `<label>` im eigenen Beispielcode.

Zu allem bisher Evaluierten ist das ein qualitativer Unterschied. Diese Skripte können scheitern. Sie sind gescheitert, und die Fehlschläge stehen im Changelog. Ein Skill, der seine eigenen Bugs mit Datum und Ursache dokumentiert, hat eine Prüfkultur. Prüfrhetorik allein wäre weniger.

## Die Portierung der Standards hält der Prüfung stand

Stichproben gegen die Primärquellen bestätigen die Sorgfalt. Kontrast 4,5:1 für Text und 3:1 für UI-Komponenten sind korrekt. Die Mindest-Zielgröße von 24 × 24 px unter Verweis auf WCAG 2.5.8 ist korrekt. Focus Not Obscured, Target Size und Accessible Authentication nennt der Skill als neu in 2.2. Alle drei sind richtig zugeordnet. Die Fokusfalle wird gegen 2.4.3 und 2.1.2 geprüft. Das sind die richtigen Kriterien.

Aufschlussreich ist ein Detail aus Version 2.3.0. Das Gate hält grafische und rein ikonische Bedienelemente bei 3:1 statt 4,5:1. Es verweist dafür auf WCAG 1.4.11 und nimmt deaktivierte Elemente aus. Eine Formel aus einer Zusammenfassung ist das nicht. Solche Unterscheidungen trifft nur, wer die Erfolgskriterien selbst gelesen hat. Auch die DTCG-Dreiteilung Primitive → Semantic → Component ist sauber umgesetzt. Die Konsequenz stimmt ebenfalls. Dark Mode funktioniert über den Tausch semantischer Token und lässt Primitive unangetastet.

## Die Ebene, die kein Gate berührt

Neben diesem Apparat steht eine zweite Ebene mit gänzlich anderer epistemischer Qualität. In `design-systems/library/` liegen 138 „brand-grade" Spezifikationen für apple, linear, stripe, vercel, notion, spotify und tesla. Aufgerufen wird die Bibliothek über `/apply-aesthetic stripe`, mit der Beschreibung „make the dashboard feel like Stripe".

Woher diese Spezifikationen stammen, sagt das Repository nicht. Es gibt keine Methodik für die Rekonstruktion einer fremden Design-Sprache. Ein Erhebungsdatum fehlt. Kein Hinweis deutet darauf, dass Stripe sein Interface seither geändert haben könnte. Als Bibliothek erscheint eine Sammlung von Zuschreibungen ohne Beleg.

<div class="callout">
<div class="callout__title">Die 100 % gelten nicht für das, was man sieht</div>
Der Accuracy Report meldet prominent „25/25 = 100 %". Ein Blick auf die 25 Checks zeigt ein klares Bild. Sie decken Token-Gültigkeit, Alias-Auflösung, Kontrast, Zustandsvollständigkeit, Spec-Vollständigkeit, keine hartcodierten Werte, keine Emoji, Fokusfalle, RTL und Überlauf ab. Alles davon ist mechanisch entscheidbar. Keine einzige Prüfung fragt, ob die Datei <code>library/stripe/DESIGN.md</code> irgendetwas mit Stripe zu tun hat. Die rigoroseste Prüfinfrastruktur des Ökosystems liegt damit exakt neben der am wenigsten belegten Wissensschicht. Ausgerechnet diese Schicht prägt das visuelle Ergebnis am stärksten. Die 100 % sind nicht falsch. Sie beantworten nur eine engere Frage, als die Zahl suggeriert. Wer sie als Gesamtqualitätsurteil liest, verwechselt Messbarkeit mit Richtigkeit.
</div>

Dasselbe Muster wiederholt sich beim Design Review. Es hat sechs gewichtete Dimensionen. Visual Hierarchy, Consistency, Accessibility und Usability zählen je 20 %. Responsiveness und Performance zählen je 10 %. Nielsens zehn Heuristiken werden zitiert. Sie sind belegbar und korrekt benannt. Die Gewichtung dagegen ist eine Eigenschöpfung ohne genannte Herleitung. Warum Responsiveness halb so schwer wiegt wie Consistency, steht nirgends. Prozentzahlen erzeugen den Eindruck von Kalibrierung. Tatsächlich liegt eine Setzung vor.

## Transparenz: bemerkenswert differenziert, aber nicht durchgehend

An mehreren Stellen kommuniziert das Projekt seine Grenzen ungewöhnlich präzise. Das Taste-Audit trägt den Zusatz „Heuristic by design". Es folgt „a strong signal, not proof (taste is subjective)". Im `design-component`-Skill steht die Regel „RENDER AND LOOK" samt Begründung „gates don't prove pixels". Sie warnt ausdrücklich davor, den eigenen Prüfapparat zu überschätzen. Die Projektstruktur warnt: „Skills under `.claude/skills/` run with agent permissions". Weiter heißt es „review before use." Die Hierarchie ist explizit geregelt: „Taste serves the Aesthetics tier and never overrides accessibility."

Solche Sätze findet man in dieser Serie selten. Sie stehen neben einer Selbstbeschreibung, die in die Gegenrichtung zieht. Sie lautet „Turn Claude into a Senior Design Architect" und verspricht „15+ years of expertise". Berufserfahrung kann eine Instruktionsdatei nicht besitzen. Die Formulierung ist unprüfbar und passt schlecht zur sonst nüchternen Tonlage. Für die Bewertung heißt das: Wo das Projekt technisch spricht, ist es ehrlich. Wo es wirbt, fällt es in die Muster des Ökosystems zurück.

## Wartbarkeit: professionelle Prozesse, dünne Personendecke

Stark ist die Prozessseite. Das Projekt hat eine MIT-Lizenz und Semantic Versioning mit gepflegtem Changelog bis v2.4.0. CI läuft auf jedem Push und PR. Die Release-Pipeline ist automatisiert und nutzt `npm publish --provenance`. Die projektbezogene MCP-Konfiguration kommt ohne eingecheckte Secrets aus. Das entspricht der Praxis ernsthafter Open-Source-Projekte.

Die Personenseite ist dünn. `plugin87` ist ein pseudonymer Account ohne verifizierbare Identität. Bei Paul Bakaus von `impeccable` und Ivan Morgillo von `material-3-skill` ist der Hintergrund unabhängig nachprüfbar. Hier stehen 34 Commits, 33 Forks und ein offener Pull Request. Ein sichtbares Team gibt es nicht. Der Busfaktor liegt bei eins. Für eine Lehrveranstaltung über ein Semester ist das unkritisch. Eine mehrjährige Produktionsabhängigkeit verlangt, dass man es weiß.

## Empfehlung für den Unterrichtseinsatz

Dieser Skill ist die beste verfügbare Grundlage für eine neue Übung. Diese Serie konnte sie bisher nicht führen. **Was kann automatisierte Prüfung leisten, und wo hört sie auf?**

Ein konkreter Vorschlag für ein Seminar: Studierende klonen das Repository und führen `npm run verify` aus. Sie bekommen 25/25. Dann sollen sie eine Änderung formulieren, die das Ergebnis nicht antastet und das Design trotzdem verschlechtert. Das gelingt schnell. Man schreibt etwa `library/linear/DESIGN.md` beliebig um. Alle Kontrastwerte bleiben konform und alle Token gültig. Das Gate bleibt grün, die visuelle Aussage ist eine völlig andere. Die Lernfrage lautet dann nicht „Ist dieser Skill gut?" Sie lautet „Welche Klasse von Fehlern kann ein Test dieser Bauart prinzipiell nicht finden?"

Eine zweite Übung ist die Quellenprüfung. Studierende greifen sich drei Einträge aus der 138-System-Bibliothek. Sie vergleichen diese mit dem aktuellen Interface der jeweiligen Produkte. Wie viel stimmt? Woran erkennt man, dass eine Beschreibung veraltet ist? Was müsste im Repository stehen, damit die Behauptung überhaupt überprüfbar wäre? Erhebungsdatum, Methode, Screenshots?

Für den produktiven Einsatz ist der Skill empfehlenswert, mit klarer Rollentrennung. Die Token-, Accessibility- und Gate-Ebene ist belastbar. Sie lässt sich in echte Projekte übernehmen. Die Taste- und Marken-Bibliothek ist Ideengeber und keine Referenz. Als Beleg dafür, dass ein Ergebnis „wie Stripe" aussieht, taugt sie keinesfalls. Das Urteil lautet deshalb **vertrauen** und nicht **solide**. Die Substanz fehlt nicht. Für einen erheblichen Teil seines Inhalts bleibt das Projekt aber denselben Prüfmaßstab schuldig, den es an anderer Stelle vorbildlich anlegt.
