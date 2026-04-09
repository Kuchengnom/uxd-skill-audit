---
layout: default
title: Next Steps
permalink: /next-steps/
published: false
---

# Next Steps — UX Skills Review

Interne Arbeitsnotiz. Nicht im Blog veröffentlicht.

---

## Nächste Skill-Evaluationen (Priorität 1–3)

### Priorität 1 — Sofort

**`pbakaus/impeccable`**
Aktuell das meistdiskutierte Projekt im Ökosystem — 10.000 GitHub-Stars in drei Wochen.
Positioniert sich explizit als "missing upgrade" zu Anthropics offiziellem Frontend-Skill.
7 Referenzdateien (Typografie, OKLCH-Farbe, Motion, Interaction), 20 Slash-Commands.
Autor Paul Bakaus: verifizierbarer Hintergrund (ex-Google), eigene Domain impeccable.style.
- Evaluationswinkel: Hält der "Upgrade"-Anspruch methodisch was er verspricht? Wo beginnt echter Mehrwert, wo ist es Marketing?
- Verdacht: solide — aber prüfen ob die 7 Referenzdateien wirklich Quellen haben oder nur Kategorien benennen.

**`mastepanoski/claude-skills`**
Einziger bekannter Skill der drei anerkannte Frameworks explizit kombiniert: Nielsen-Heuristiken, WCAG, Don Norman-Prinzipien.
Auch AI-Governance-Skills enthalten (NIST AI RMF, ISO 42001, OWASP).
- Evaluationswinkel: Werden die Frameworks korrekt portiert oder nur namentlich zitiert? Besonderes Augenmerk auf die Nielsen-Portierung — das ist verifizierbar.
- Verdacht: methodisch ambitionierter als alles bisher Evaluierte — wahrscheinlich positives Beispiel.

---

### Priorität 2 — Mittelfristig

**`szilu/ux-designer-skill`**
Behauptet Synthese aus 19 Autoritätsquellen: Nielsen Norman Group, WCAG 2.2, Material Design, Apple HIG, und weitere.
- Evaluationswinkel: Die Quellenbehauptung ist prüfbar. Sind die 19 Quellen korrekt portiert oder nur als Legitimationsnachweis aufgelistet?
- Lehrwert: Ideales Beispiel für "Quellen nennen ≠ Quellen korrekt anwenden."

**`kylezantos/design-motion-principles`**
Baut explizit auf drei realen Designern auf: Emil Kowalski, Jakub Krehel, Jhey Tompkins.
Gleiche Grundlogik wie emilkowalski/skill — traceable sources — aber mit drei Personen.
- Evaluationswinkel: Wie kohärent ist ein Skill der drei verschiedene Stile vereinen will? Entstehen Widersprüche?
- Interessant als Vergleich zu emilkowalski/skill (bereits evaluiert, Urteil: Solide).

**`Dammyjay93/interface-design`**
Verspricht Design-Gedächtnis und Konsistenz-Enforcement über Projektsessions hinweg.
Lädt system.md, dokumentiert Design-Entscheidungen, speichert neue Patterns.
- Evaluationswinkel: "Gedächtnis" in einem stateless LLM — ähnliches epistemisches Problem wie bei Anthropic PR #210. Ist das Versprechen technisch einlösbar?

**`Owl-Listener/designer-skills`** (Marie-Claire Dean)
63 Skills, 27 Commands, 8 Plugins — gesamter Designprozess abgedeckt.
Weitgehend geteilt, bekannt in der Community.
- Evaluationswinkel: Bei dieser Breite ist die Frage nicht ob einzelne Skills gut sind, sondern ob das Gesamtsystem kohärent ist. Überforderung als Anti-Pattern?
- Besonders: Autorin hat selbst kommuniziert "Struktur wichtiger als Inhalt" — diese Selbstdiagnose im Post aufgreifen.

---

### Priorität 3 — Lehrbeispiele für Quantität über Qualität

**`HermeticOrmus/LibreUIUX-Claude-Code`**
Extremfall: 152 Agenten, 76 Commands, 74 Skills, 70 Plugins.
- Evaluationswinkel: Ab wann wird Komplexität selbst zum Anti-Pattern? Wie viel davon ist kohärentes System, wie viel ist akkumulierte Komplexität?
- Lehrwert: Bestes verfügbares Beispiel für das "mehr = besser"-Fehlschluss-Problem.

**`HermeticOrmus/design-mastery-claude-code`**
"Learn from Saul Bass and Dieter Rams."
Name-Dropping historischer Designer als Methodik.
- Evaluationswinkel: Was bedeutet es einen verstorbenen Grafikdesigner als Skill-Quelle zu deklarieren? Was kann Claude daraus wirklich lernen?
- Lehrwert: Zeigt wie Autorität durch Assoziation suggeriert wird.

---

## Inhaltliche Lücken im Blog (eigene Skills entwickeln)

Diese Themen haben keinen guten öffentlichen Skill — hier entsteht eigener Content:

1. **Cognitive Walkthrough als ausführbarer Skill** — Methode von Wharton et al. (1994), bisher nicht korrekt portiert
2. **Diary Study Framework** — Langzeit-Nutzerforschung, im Ökosystem komplett absent
3. **A/B-Test-Analyse-Skill** — Statistische Auswertung von Design-Experimenten
4. **Information Architecture Mapping** — Sitemap, Card Sorting, Taxonomie
5. **DESIGN.md Schreiben lernen** — Tutorial-Post: Wie schreibt man ein gutes DESIGN.md?

---

## Visualisierung — Radar/Spinnengrafik

Jede Skill-Evaluation soll eine Spinnengrafik (Radar Chart) bekommen die die vier Bewertungsdimensionen zeigt.

**Ziele:**
- Auf der Methodik-Seite: Erklärender Muster-Chart der zeigt wie die vier Achsen funktionieren
- Auf einzelnen Skill-Posts: Vollständiger Radar-Chart neben oder statt der Balken-Scorecard
- Auf der Skills-Index-Seite: Mini-Radar je Card für schnellen visuellen Vergleich

**Technische Entscheidung:**
Reines SVG via Jekyll/Liquid — kein JavaScript, kein Build-Step, funktioniert auf GitHub Pages ohne Plugins.
Die vier Achsen bilden eine Raute (0°, 90°, 180°, 270°):
- Oben: Methodische Fundierung
- Rechts: Transparenz
- Unten: Validierbarkeit
- Links: Wartbarkeit

Werte 1–5 werden auf einen Radius von 0–80px skaliert (Faktor 16).
Hintergrund-Gitter: 5 konzentrische Rauten für die Skalierung.

**Status:** Implementiert als `_includes/skill-radar.html` ✓

---

## Technische To-dos

- [ ] GitHub Pages: Sicherstellen dass `jekyll-seo-tag` korrekt rendert (Titel, Description, OG-Tags prüfen)
- [ ] RSS-Feed testen (`/feed.xml`)
- [ ] Skills-Seite: Verdict-Gruppierung mit echten Daten testen sobald `impeccable` live ist
- [ ] Radar-Chart auf Methodik-Seite als erklärendes Muster ergänzen
- [ ] Überlegen ob deutsche Umlaute in Dateinamen durch ae/oe/ue ersetzt werden sollen für URL-Sauberkeit
- [ ] `.DS_Store` dauerhaft aus gitignore — erledigt ✓

---

## Offene Fragen

- Soll die Blog-Sprache für internationale Reichweite auf Englisch wechseln, oder bleibt Deutsch für den Lehrkontext?
- Soll die Skills-Seite eine Filterfunktion nach Urteil / Tag bekommen (JS-basiert, kein Build-Step)?
- Wann kommt der erste "eigene Skill" Post — also ein Post der nicht evaluiert sondern einen neuen Skill mitliefert?
