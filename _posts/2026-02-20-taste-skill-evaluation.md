---
layout: post
title: "taste-skill: Wenn Ästhetik-Präferenzen als Design-Methodik verkleidet werden"
date: 2026-02-20
category: Skill-Evaluation
skill_reviewed: "Leonxlnx/taste-skill"
lang: de
lang_url: "/en/2026/02/20/taste-skill-evaluation/"
verdict: vorsicht
reading_time: 8
last_audited: "20. Februar 2026"

skill_scores:
  methodische_fundierung: 2
  methodische_fundierung_note: "Keine anerkannte UX-Methodik — reine Ästhetikpräferenzen"
  transparenz: 2
  transparenz_note: "Kommuniziert nicht, dass Outputs keine Usability-Grundlage haben"
  validierbarkeit: 2
  validierbarkeit_note: "Keine Testfälle, kein Vergleich mit Nutzertests"
  wartbarkeit: 4
  wartbarkeit_note: "Aktiv gepflegt, eigene Domain, mehrere Varianten"

tags:
  - frontend
  - ästhetik
  - kritik
  - skill-evaluation
---

Der taste-skill von Leon Lin ist viral gegangen: eigene Domain, sieben Varianten, Tessl-Registry-Eintrag. Er löst ein echtes Problem, denn KI-generiertes Frontend sieht zu oft gleich aus. Und dennoch lohnt es sich, genau hinzuschauen was hier eigentlich behauptet wird.

## Was der Skill tut

taste-skill gibt Claude einen ästhetischen Rahmen für Frontend-Entwicklung. Das 3-Dial-System klingt nach kontrollierter Parametrisierung: `DESIGN_VARIANCE`, `MOTION_INTENSITY` und `VISUAL_DENSITY`, jeweils auf einer Skala von 1 bis 10. Die SKILL.md-Datei bannt konkrete Muster explizit: keine „3 gleich breiten Feature-Cards", kein „AI-Purple", keine isolierten Dark-Sections in Light-Mode-Pages.

Das Prinzip ist klar: Statt vage zu sagen "sei kreativ", gibt der Skill Anti-Pattern-Regeln vor. Claude weiß was verboten ist und weicht statistischen Mittelpunkten aus.

## Das zentrale Missverständnis

<div class="callout">
<div class="callout__title">Kritischer Punkt</div>
Der Skill löst ein Ästhetik-Problem, nicht ein Usability-Problem. Diese Unterscheidung fehlt komplett.
</div>

„Slop", das generische Einerlei der KI-generierten UIs, ist ein legitimes Problem. Aber taste-skill ersetzt einen statistischen Mittelpunkt durch einen anderen: den „Premium Soft UI"-Stil mit teueren Fonts, viel Whitespace, Spring-Animationen und subtilen Schatten. Das ist 2024er Saas-Ästhetik als Dogma.

Ein UX-Rahmen müsste andere Fragen beantworten. Ist dieses Interface für seine Zielgruppe verständlich? Reduziert es kognitive Last? Ist es zugänglich? Keine davon beantwortet der Skill. Er beantwortet eine einzige: Sieht es nach einem teuren Produkt aus?

Beides sind legitime Fragen. Aber sie sind nicht dieselbe Frage.

## Was das für Studierende bedeutet

Wer taste-skill ohne Kontext einsetzt, lernt:

- Dass Ästhetik = Qualität
- Dass Muster-Verbote = Methodik
- Dass "Premium" = nutzerzentriert

Keines davon stimmt. Ein hoher `DESIGN_VARIANCE`-Wert produziert interessantere Layouts. Aber interessant und verständlich sind verschiedene Achsen. Viel Whitespace hilft manchen Nutzern, überfordert andere. Spring-Animationen können bei kognitiver Belastung oder vestibularen Störungen schädlich sein.

Der Skill enthält keine `prefers-reduced-motion`-Logik. Das WCAG-Kriterium 2.3.3 Animation from Interactions wird nicht erwähnt.

## Was der Skill gut macht

Das ist keine vollständige Ablehnung. Der Anti-Pattern-Ansatz ist didaktisch wertvoll: explizite Verbote statt vager Ermutigungen. Die Framework-Agnostik ist korrekt umgesetzt. Und das Problem, das der Skill löst, ist real. KI-Output sieht zu gleich aus.

Für Prototyping und explorative Designphasen, wo Ästhetik vor Usability rangiert, ist taste-skill ein nützliches Werkzeug.

## Wie man den Skill richtig einsetzt

```markdown
# In der eigenen SKILL.md oder im Prompt ergänzen:

Nach dem Anwenden von taste-skill:
1. Prüfe WCAG AA Kontraste (Ziel: 4.5:1 für normalen Text)
2. Stelle sicher dass alle Animationen prefers-reduced-motion respektieren
3. Teste das Layout auf 320px Breite (mobiler Minimalfall)
4. Frage: Ist jede Design-Entscheidung auch für Erstbenutzer verständlich?
```

Die Ästhetik-Entscheidungen des Skills können als Ausgangspunkt dienen. Sie ersetzen aber keine Usability-Prüfung.

## Fazit

taste-skill ist ein ehrliches Ästhetik-Werkzeug, das sich nicht als UX-Methodik verkleidet. Es kommuniziert aber auch nicht, was es *nicht* ist. Für fortgeschrittene Nutzer mit UX-Grundkenntnissen ist das kein Problem. Für Studierende, die lernen sollen was Design-Qualität bedeutet, fehlt genau dieser Kontext.

Empfehlung: Einsetzen mit expliziter Ergänzung durch einen Accessibility-Audit-Skill. Nie allein als Qualitätsmerkmal verwenden.
