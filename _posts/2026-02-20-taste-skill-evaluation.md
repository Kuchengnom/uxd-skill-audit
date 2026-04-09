---
layout: post
title: "taste-skill: Wenn Aesthetik-Praeferenzen als Design-Methodik verkleidet werden"
date: 2026-02-20
category: Skill-Evaluation
skill_reviewed: "Leonxlnx/taste-skill"
verdict: vorsicht
reading_time: 8
last_audited: "20. Februar 2026"

skill_scores:
  methodische_fundierung: 2
  methodische_fundierung_note: "Keine anerkannte UX-Methodik — reine Aesthetikpraeferenzen"
  transparenz: 2
  transparenz_note: "Kommuniziert nicht, dass Outputs keine Usability-Grundlage haben"
  validierbarkeit: 2
  validierbarkeit_note: "Keine Testfaelle, kein Vergleich mit Nutzertests"
  wartbarkeit: 4
  wartbarkeit_note: "Aktiv gepflegt, eigene Domain, mehrere Varianten"

tags:
  - frontend
  - aesthetik
  - kritik
  - skill-evaluation
---

Der taste-skill von Leon Lin ist viral gegangen — eigene Domain, sieben Varianten, Tessl-Registry-Eintrag. Er loest ein echtes Problem: KI-generiertes Frontend sieht zu oft gleich aus. Und dennoch lohnt es sich, genau hinzuschauen was hier eigentlich behauptet wird.

## Was der Skill tut

taste-skill gibt Claude einen aesthetischen Rahmen fuer Frontend-Entwicklung. Das 3-Dial-System — `DESIGN_VARIANCE` (1–10), `MOTION_INTENSITY` (1–10), `VISUAL_DENSITY` (1–10) — klingt nach kontrollierter Parametrisierung. Die SKILL.md-Datei bannt konkrete Muster explizit: keine "3 gleich breiten Feature-Cards", kein "AI-Purple", keine isolierten Dark-Sections in Light-Mode-Pages.

Das Prinzip ist klar: Statt vage zu sagen "sei kreativ", gibt der Skill Anti-Pattern-Regeln vor. Claude weiss was verboten ist und weicht statistischen Mittelpunkten aus.

## Das zentrale Missverstaendnis

<div class="callout">
<div class="callout__title">Kritischer Punkt</div>
Der Skill loest ein Aesthetik-Problem, nicht ein Usability-Problem. Diese Unterscheidung fehlt komplett.
</div>

"Slop" — das generische Einerlei der KI-generierten UIs — ist ein legitimes Problem. Aber taste-skill ersetzt einen statistischen Mittelpunkt durch einen anderen: den "Premium Soft UI"-Stil mit teueren Fonts, viel Whitespace, Spring-Animationen und subtilen Schatten. Das ist 2024er Saas-Aesthetik als Dogma.

Die Fragen, die ein UX-Rahmen beantworten muesste — Ist dieses Interface fuer seine Zielgruppe verstaendlich? Reduziert es kognitive Last? Ist es zugaenglich? — beantwortet der Skill nicht. Er beantwortet: Sieht es nach einem teuren Produkt aus?

Beides sind legitime Fragen. Aber sie sind nicht dieselbe Frage.

## Was das fuer Studierende bedeutet

Wer taste-skill ohne Kontext einsetzt, lernt:

- Dass Aesthetik = Qualitaet
- Dass Muster-Verbote = Methodik
- Dass "Premium" = nutzerzentriert

Keines davon stimmt. Ein hoher `DESIGN_VARIANCE`-Wert produziert interessantere Layouts — aber interessant und verstaendlich sind verschiedene Achsen. Viel Whitespace hilft manchen Nutzern, ueberfordert andere. Spring-Animationen koennen bei kognitiver Belastung oder vestibularen Stoerungen schaedlich sein.

Der Skill enthaelt keine `prefers-reduced-motion`-Logik. Das WCAG-Kriterium 2.3.3 (Animation from Interactions) wird nicht erwaehnt.

## Was der Skill gut macht

Das ist keine vollstaendige Ablehnung. Der Anti-Pattern-Ansatz — explizite Verbote statt vager Ermutigungen — ist didaktisch wertvoll. Die Framework-Agnostik ist korrekt umgesetzt. Und das Problem, das der Skill loest (KI-Output sieht zu gleich aus), ist real.

Fuer Prototyping und explorative Designphasen, wo Aesthetik vor Usability rangiert, ist taste-skill ein nuetzliches Werkzeug.

## Wie man den Skill richtig einsetzt

```markdown
# In der eigenen SKILL.md oder im Prompt ergaenzen:

Nach dem Anwenden von taste-skill:
1. Pruefe WCAG AA Kontraste (Ziel: 4.5:1 fuer normalen Text)
2. Stelle sicher dass alle Animationen prefers-reduced-motion respektieren
3. Teste das Layout auf 320px Breite (mobiler Minimalfall)
4. Frage: Ist jede Design-Entscheidung auch fuer Erstbenutzer verstaendlich?
```

Die Aesthetik-Entscheidungen des Skills koennen als Ausgangspunkt dienen — aber sie ersetzen keine Usability-Pruefung.

## Fazit

taste-skill ist ein ehrliches Aesthetik-Werkzeug, das sich nicht als UX-Methodik verkleidet — aber auch nicht kommuniziert, was es *nicht* ist. Fuer fortgeschrittene Nutzer mit UX-Grundkenntnissen ist das kein Problem. Fuer Studierende, die lernen sollen was Design-Qualitaet bedeutet, fehlt genau dieser Kontext.

**Empfehlung:** Einsetzen mit expliziter Erg&auml;nzung durch einen Accessibility-Audit-Skill. Nie allein als Qualitaetsmerkmal verwenden.
