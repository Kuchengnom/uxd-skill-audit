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
  methodische_fundierung_note: "WCAG 2.2, WAI-ARIA, DTCG und Atomic Design sind korrekt portiert — inklusive der feinen Unterscheidung, dass grafische Bedienelemente nach 1.4.11 bei 3:1 und nicht bei 4.5:1 zu messen sind; ohne Quellenbasis bleiben dagegen die 138 Marken-Systeme und die Gewichtung der sechs Review-Dimensionen."
  transparenz: 3
  transparenz_note: "Einzelne Grenzen werden ungewöhnlich klar benannt (Taste-Audit als Heuristik, „gates don't prove pixels\", Skills laufen mit Agent-Rechten), doch die Persona „Senior Design Architect mit 15+ Jahren Erfahrung\" und die unqualifizierte Schlagzeile „25/25 = 100 %\" versprechen mehr, als der Apparat misst."
  validierbarkeit: 5
  validierbarkeit_note: "Ausführbare Gates messen echten Kontrast in Hell- und Dunkelmodus über alle Zustände, axe-core, Fokusfalle per echter Tastatureingabe, RTL und Überlauf bei 280/320/414 px — alles in CI erzwungen und mit dokumentierten Fehlfunden belegt."
  wartbarkeit: 4
  wartbarkeit_note: "Sehr aktiv (v2.4.0, 34 Commits, automatisierte Release-Pipeline mit npm-Provenance, MIT-Lizenz), aber getragen von einem einzigen pseudonymen Account ohne verifizierbare Identität."

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

Die bisherigen Evaluationen dieser Serie sind an einer Stelle immer wieder gelandet: Skills behaupten Qualität, aber sie messen sie nicht. `alirezarezvani/claude-skills` machte im Juli den Anfang mit einem öffentlichen Selbst-Audit, allerdings mit Verifikationsgates die laut eigenem Befund „all optional, none looped" waren. `plugin87/ux-ui-agent-skills` geht den Schritt weiter, der bislang fehlte: Hier laufen die Prüfungen tatsächlich, sie laufen in CI, und sie blockieren den Merge.

Das Repository ist mit 411 Sternen und 34 Commits vergleichsweise klein, deutlich unterhalb der Aufmerksamkeit die `impeccable` oder `ui-ux-pro-max` erhalten. Genau das macht es für diese Serie interessant. Es ist das erste Projekt im Ökosystem, bei dem die Frage „Woher weißt du, dass das stimmt?" eine technische Antwort bekommt.

## Was hier tatsächlich gemessen wird

Der Kern ist `scripts/accuracy_report.mjs`. Ein Befehl, ein Alles-oder-Nichts-Ergebnis. Dahinter stehen Prüfungen, die sich einzeln nachvollziehen lassen:

`verify_states.mjs` startet einen Headless-Chrome, rendert die Komponenten-Harnesses und misst den tatsächlich berechneten Kontrast jedes interaktiven Elements in den Zuständen Default, Hover und Focus, jeweils in Hell- und Dunkelmodus. Der Changelog nennt den Fehler, den das gefunden hat: ein Sekundär-Button, der beim Hover die Primärfüllung übernahm und damit unter AA fiel. Ein Ruhezustands-Test hätte das nie gesehen.

`verify_focustrap.mjs` öffnet einen Modal und prüft mit echten Tastatureingaben, ob Tab in der Falle bleibt, ob `role="dialog"` und `aria-modal` gesetzt sind und ob Escape schließt und den Fokus zurückgibt. Dokumentierter Fund: ein Drawer, der nie schloss, weil ein `display:none`-`position:fixed`-Dialog den Test zuvor fälschlich bestand. `verify_rtl.mjs` rendert LTR gegen `dir="rtl"` und meldet Layouts die nur gespiegelt überlaufen, das verlässliche Symptom physischer statt logischer CSS-Eigenschaften. `verify_responsive.mjs` bricht bei horizontalem Überlauf auf 280, 320 und 414 px ab. Dazu ein axe-core-Durchlauf gegen WCAG 2.0/2.1/2.2 A + AA, der einen echten fehlenden `<label>` im eigenen Beispielcode fand.

Das ist ein qualitativer Unterschied zu allem bisher Evaluierten. Diese Skripte können scheitern, sie sind gescheitert, und die Fehlschläge stehen im Changelog. Ein Skill, der seine eigenen Bugs mit Datum und Ursache dokumentiert, hat eine Prüfkultur, nicht nur Prüfrhetorik.

## Die Portierung der Standards hält der Prüfung stand

Stichproben gegen die Primärquellen bestätigen die Sorgfalt. Kontrast 4,5:1 für Text, 3:1 für UI-Komponenten: korrekt. Mindest-Zielgröße 24 × 24 px unter Verweis auf WCAG 2.5.8: korrekt. Die als neu in 2.2 genannten Kriterien Focus Not Obscured, Target Size und Accessible Authentication sind korrekt zugeordnet. Die Fokusfalle wird gegen 2.4.3 und 2.1.2 geprüft: die richtigen Kriterien.

Besonders aufschlussreich ist ein Detail aus Version 2.3.0: Das Gate hält grafische und rein ikonische Bedienelemente bei 3:1 statt 4,5:1, mit Verweis auf WCAG 1.4.11, und nimmt deaktivierte Elemente aus. Das ist keine Formel, die man aus einer Zusammenfassung abschreibt. Das ist die Art von Unterscheidung, die man nur trifft, wenn man die Erfolgskriterien selbst gelesen hat. Auch die DTCG-Dreiteilung Primitive → Semantic → Component ist sauber umgesetzt, samt der zutreffenden Konsequenz, dass Dark Mode über den Tausch semantischer Token funktioniert und Primitive unangetastet lässt.

## Die Ebene, die kein Gate berührt

Neben diesem Apparat steht eine zweite Ebene mit gänzlich anderer epistemischer Qualität: `design-systems/library/` mit 138 „brand-grade" Spezifikationen für apple, linear, stripe, vercel, notion, spotify und tesla. Aufgerufen wird sie über `/apply-aesthetic stripe`, mit der Beschreibung „make the dashboard feel like Stripe".

Woher diese Spezifikationen stammen, sagt das Repository nicht. Es gibt keine Methodik, wie die Design-Sprache eines fremden Unternehmens rekonstruiert wurde, keine Angabe eines Erhebungsdatums, keinen Hinweis darauf, dass Stripe sein Interface seither geändert haben könnte. Was hier als Bibliothek erscheint, ist eine Sammlung von Zuschreibungen ohne Beleg.

<div class="callout">
<div class="callout__title">Die 100 % gelten nicht für das, was man sieht</div>
Der Accuracy Report meldet prominent „25/25 = 100 %". Prüft man, was diese 25 Checks abdecken, ergibt sich ein klares Bild: Token-Gültigkeit, Alias-Auflösung, Kontrast, Zustandsvollständigkeit, Spec-Vollständigkeit, keine hartcodierten Werte, keine Emoji, Fokusfalle, RTL, Überlauf. Alles davon ist mechanisch entscheidbar. Keine einzige Prüfung stellt die Frage, ob die Datei <code>library/stripe/DESIGN.md</code> irgendetwas mit Stripe zu tun hat. Die rigoroseste Prüfinfrastruktur des Ökosystems liegt damit exakt neben der am wenigsten belegten Wissensschicht, und die unbelegte ist diejenige die das visuelle Ergebnis am stärksten prägt. Die 100 % sind nicht falsch. Sie beantworten nur eine engere Frage, als die Zahl suggeriert. Wer sie als Gesamtqualitätsurteil liest, verwechselt Messbarkeit mit Richtigkeit.
</div>

Dasselbe Muster wiederholt sich beim Design Review. Sechs Dimensionen mit Gewichten: Visual Hierarchy 20 %, Consistency 20 %, Accessibility 20 %, Usability 20 %, Responsiveness 10 %, Performance 10 %. Nielsens zehn Heuristiken werden dabei zitiert und sind belegbar und korrekt benannt. Die Gewichtung dagegen ist eine Eigenschöpfung ohne genannte Herleitung. Warum Responsiveness halb so schwer wiegt wie Consistency, steht nirgends. Prozentzahlen erzeugen den Eindruck von Kalibrierung, wo eine Setzung vorliegt.

## Transparenz: bemerkenswert differenziert, aber nicht durchgehend

Das Projekt kommuniziert Grenzen an mehreren Stellen ungewöhnlich präzise. Das Taste-Audit trägt den Zusatz „Heuristic by design — a strong signal, not proof (taste is subjective)". Im `design-component`-Skill steht die Regel „RENDER AND LOOK — gates don't prove pixels", also die ausdrückliche Warnung den eigenen Prüfapparat nicht zu überschätzen. Zur Projektstruktur heißt es: „Skills under `.claude/skills/` run with agent permissions — review before use." Und die Hierarchie ist explizit geregelt: „Taste serves the Aesthetics tier and never overrides accessibility."

Solche Sätze findet man in dieser Serie selten. Sie stehen jedoch neben einer Selbstbeschreibung, die in die Gegenrichtung zieht: „Turn Claude into a Senior Design Architect — 15+ years of expertise". Berufserfahrung ist keine Eigenschaft, die eine Instruktionsdatei besitzen kann. Die Formulierung ist unprüfbar und kontrastiert seltsam mit der sonst nüchternen Tonlage. Für die Bewertung heißt das: Wo das Projekt technisch spricht, ist es ehrlich; wo es wirbt, fällt es in die Muster des Ökosystems zurück.

## Wartbarkeit: professionelle Prozesse, dünne Personendecke

Die Prozessseite ist stark. MIT-Lizenz, Semantic Versioning mit gepflegtem Changelog bis v2.4.0, CI auf jedem Push und PR, automatisierte Release-Pipeline, `npm publish --provenance`, projektbezogene MCP-Konfiguration ohne eingecheckte Secrets. Das entspricht der Praxis ernsthafter Open-Source-Projekte.

Die Personenseite ist dünn. `plugin87` ist ein pseudonymer Account ohne verifizierbare Identität, anders als Paul Bakaus bei `impeccable` oder Ivan Morgillo bei `material-3-skill`, deren Hintergrund unabhängig nachprüfbar ist. 34 Commits, 33 Forks, ein offener Pull Request, kein sichtbares Team. Der Busfaktor liegt bei eins. Für eine Lehrveranstaltung über ein Semester ist das unkritisch. Für eine mehrjährige Produktionsabhängigkeit sollte man es wissen.

## Empfehlung für den Unterrichtseinsatz

Dieser Skill ist die beste verfügbare Grundlage für eine Übung, die diese Serie bisher nicht führen konnte: **Was kann automatisierte Prüfung leisten, und wo hört sie auf?**

Konkreter Vorschlag für ein Seminar: Studierende klonen das Repository und führen `npm run verify` aus. Sie bekommen 25/25. Anschließend erhalten sie die Aufgabe, eine Änderung zu formulieren, die das Ergebnis nicht antastet und das Design trotzdem verschlechtert. Das gelingt schnell, etwa indem man `library/linear/DESIGN.md` beliebig umschreibt. Alle Kontrastwerte bleiben konform, alle Token bleiben gültig, das Gate bleibt grün, und die visuelle Aussage ist eine völlig andere. Die Lernfrage lautet dann nicht „Ist dieser Skill gut?", sondern „Welche Klasse von Fehlern kann ein Test dieser Bauart prinzipiell nicht finden?"

Als zweite Übung eignet sich eine Quellenprüfung: Studierende greifen sich drei Einträge aus der 138-System-Bibliothek und vergleichen sie mit dem tatsächlichen aktuellen Interface der jeweiligen Produkte. Wie viel stimmt? Woran erkennt man, dass eine Beschreibung veraltet ist? Was müsste im Repository stehen, damit die Behauptung überhaupt überprüfbar wäre? Erhebungsdatum, Methode, Screenshots?

Für den produktiven Einsatz: empfehlenswert, mit einer klaren Rollentrennung. Die Token-, Accessibility- und Gate-Ebene ist belastbar und kann in echte Projekte übernommen werden. Die Taste- und Marken-Bibliothek sollte als Ideengeber behandelt werden, nicht als Referenz, und keinesfalls als Beleg dafür, dass ein Ergebnis „wie Stripe" aussieht. Das Urteil lautet daher **vertrauen** und nicht **solide**. Nicht weil die Substanz fehlt, sondern weil das Projekt für einen erheblichen Teil seines Inhalts denselben Prüfmaßstab schuldig bleibt, den es an anderer Stelle vorbildlich anlegt.
