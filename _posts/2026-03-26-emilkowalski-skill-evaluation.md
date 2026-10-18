---
layout: post
title: "emilkowalski/skill: So sollte ein Skill aussehen"
date: 2026-03-26
category: Skill-Evaluation
skill_reviewed: "emilkowalski/skill"
lang: de
lang_url: "/en/2026/03/26/emilkowalski-skill-evaluation/"
verdict: solide
reading_time: 9
last_audited: "26. März 2026"

skill_scores:
  methodische_fundierung: 5
  methodische_fundierung_note: "Jedes Prinzip ist in publizierten Artikeln nachlesbar und unabhängig prüfbar"
  transparenz: 4
  transparenz_note: "Explizit als situationsabhängig deklariert — kein Universalwerkzeug"
  validierbarkeit: 4
  validierbarkeit_note: "Quellartikel sind die Testfälle; Prinzipien an realen Projekten demonstriert"
  wartbarkeit: 4
  wartbarkeit_note: "Aktiver Maintainer mit verifizierbarer Expertise und öffentlichem Track-Record"

tags:
  - motion
  - design-engineering
  - positives-beispiel
  - skill-evaluation
---

Die bisherigen Posts dieses Blogs haben Lücken beschrieben. Es fehlten Quellenangaben. Anweisungen waren epistemisch unerfüllbar. Repos waren archiviert. Datenbanken gingen als Methodik durch. Dieser Post beschreibt das Gegenteil.

## Wer Emil Kowalski ist, und warum das relevant ist

Bevor der Skill bewertet wird, muss der Autor bewertet werden. Das klingt nach einem Ad-hominem-Argument. Beim Skill-Ökosystem ist es strukturell notwendig. Ein Skill ist destilliertes Urteilsvermögen. Wessen Urteil steckt drin?

Emil Kowalski ist Design Engineer bei Linear, vorher Vercel. Er ist Autor der Open-Source-Bibliotheken Sonner für Toast-Benachrichtigungen und Vaul für Drawer-Komponenten. Dazu gibt er Kurse bei [animations.dev](https://animations.dev). Seine Arbeit steckt in Production-Produkten, die Millionen von Nutzern täglich verwenden. Das ist verifizierbarer Track-Record und keine Selbstbeschreibung.

Für die erste Dimension spielt das eine entscheidende Rolle.

## Was die `/skill`-Seite anders macht

Der Einstieg zu diesem Skill ist kein GitHub-README. Es ist eine eigene Seite auf seiner persönlichen Website. Die Seite erklärt, was der Skill ist und woher er kommt. Vor allem erklärt sie, wie man ihn richtig einsetzt.

Emil empfiehlt explizit, den Skill **situationsabhängig einzusetzen**. Er soll keine permanente Hintergrundkonfiguration sein. Diese einfache Formulierung kommuniziert eine Grenze. Die meisten anderen Skills ignorieren sie stillschweigend. Emil sagt damit: Ich weiß, was dieser Skill kann, und ich weiß, was er nicht kann. Du solltest das auch wissen.

## Warum methodische Nachvollziehbarkeit hier funktioniert

<div class="callout">
<div class="callout__title">Das Kernprinzip guter Skill-Qualität</div>
Die Prinzipien eines Skills müssen unabhängig von ihm lesbar, prüfbar und diskutierbar sein. Dann kann man ihm vertrauen.
</div>

Emils SKILL.md ist aus den Artikeln auf seinem Blog destilliert. Jedes Prinzip hat deshalb eine Quelle. Wer wissen will, warum er `clip-path` als bevorzugtes Animations-Primitiv empfiehlt, liest den dazugehörigen Artikel. Dasselbe gilt für Animationen unter 300ms. Auch dass Raycast eine App ist, die besser ohne Animation funktioniert, hat dort seine Begründung.

Das ist der Unterschied zwischen einem Skill, der *behauptet*, und einem Skill, der *argumentiert*. Die Behauptung ist nicht prüfbar. Das Argument ist es.

Zum Vergleich haben die 99 UX-Richtlinien in `ui-ux-pro-max` keine einzige Quellenangabe. Beide Skills machen Aussagen über gutes Design. Nur einer zeigt die Arbeit.

## Was der Skill tatsächlich abdeckt

Der Scope ist klar und ehrlich: **UI-Animation und Design Engineering**. Usability, Nutzerforschung und Accessibility-Compliance gehören nicht dazu. Behandelt werden Animations-Timing unter 300ms und Spring-Parameter. Dazu kommt die kontextabhängige Entscheidung, ob überhaupt animiert wird. Auch Performance-Überlegungen wie CSS statt JavaScript für kritische Pfade stehen drin.

Das ist wenig im Vergleich zu Skills, die „344+ Design-Ressourcen" oder „26 Rollen und 60 Befehle" versprechen. Aber es ist wenig, das vollständig ist. Ein klar abgegrenzter Skill mit Tiefe ist wertvoller als ein breiter Skill ohne Boden.

Tiefe schlägt hier Breite.

## Was noch fehlt, auch hier

Einen perfekten Score vergebe ich nicht. Er ist nicht verdient. Zwei Punkte bleiben offen.

**Accessibility**. `prefers-reduced-motion` wird im Skill erwähnt. Als systematische Anforderung behandelt er es nicht. Animationen wirken für den durchschnittlichen Nutzer „inevitable and natural". Für Nutzer mit vestibularen Störungen können sie problematisch sein. Das verdient mehr als eine Randnotiz.

**Formale Testfälle**. Die Quellartikel sind die de-facto-Referenz. Strukturierte Erwartungen nach dem Muster Input X ergibt Output Y gibt es aber nicht. Prüfbar wären sie. Für diesen Skill-Typ ist das kein schwerwiegender Mangel. Es bleibt eine Grenze.

## Was Studierende hier lernen können

Dieser Skill zeigt konkret, was die vier Dimensionen des Bewertungsrahmens in der Praxis bedeuten.

Methodische Fundierung ist nicht die Menge der enthaltenen Regeln. Sie ist die Nachvollziehbarkeit der Begründungen dahinter.

Transparenz ist nicht der Disclaimer am Ende. Sie liegt in der Art, wie der Skill sich selbst beschreibt. Er versteht sich als situationsabhängiges Werkzeug und nicht als universelle Lösung.

Validierbarkeit ist nicht das Vorhandensein von Beispielen. Sie ist die Möglichkeit, die Prinzipien unabhängig vom Skill zu überprüfen. Quellartikel, reale Projekte und nachvollziehbare Argumentation leisten das.

Wartbarkeit ist nicht die Anzahl der Commits. Sie ist ein Maintainer mit verifizierbarem Urteilsvermögen und Haut im Spiel.

---

Der Skill erfüllt alle vier Dimensionen. Abstriche gibt es bei der Accessibility-Tiefe und der formalen Testbarkeit. Das reicht für das höchste Urteil in diesem Blog. Er ist nicht perfekt. Er zeigt aber, was ein solider Skill strukturell leisten muss.
