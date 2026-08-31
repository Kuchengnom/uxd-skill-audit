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
  methodische_fundierung_note: "Jedes Prinzip ist in publizierten Artikeln nachlesbar und unabhaengig pruefbar"
  transparenz: 4
  transparenz_note: "Explizit als situationsabhaengig deklariert — kein Universalwerkzeug"
  validierbarkeit: 4
  validierbarkeit_note: "Quellartikel sind die Testfaelle; Prinzipien an realen Projekten demonstriert"
  wartbarkeit: 4
  wartbarkeit_note: "Aktiver Maintainer mit verifizierbarer Expertise und oeffentlichem Track-Record"

tags:
  - motion
  - design-engineering
  - positives-beispiel
  - skill-evaluation
---

Die bisherigen Posts dieses Blogs haben Lücken beschrieben: fehlende Quellenangaben, epistemisch unerfüllbare Anweisungen, archivierte Repos, Datenbanken die als Methodik durchgehen. Dieser Post beschreibt das Gegenteil.

## Wer Emil Kowalski ist, und warum das relevant ist

Bevor der Skill bewertet wird, muss der Autor bewertet werden. Das klingt nach einem Ad-hominem-Argument, ist aber beim Skill-Ökosystem strukturell notwendig: Ein Skill ist destilliertes Urteilsvermögen. Wessen Urteil steckt drin?

Emil Kowalski ist Design Engineer bei Linear, vorher Vercel. Er ist Autor der Open-Source-Bibliotheken Sonner für Toast-Benachrichtigungen und Vaul für Drawer-Komponenten, und Kursersteller bei [animations.dev](https://animations.dev). Seine Arbeit ist in Production-Produkten, die Millionen von Nutzern täglich verwenden. Das ist verifizierbarer Track-Record, keine Selbstbeschreibung.

Das spielt für die erste Dimension eine entscheidende Rolle.

## Was die `/skill`-Seite anders macht

Der Einstieg zu diesem Skill ist nicht ein GitHub-README. Es ist eine eigene Seite auf seiner persönlichen Website, die erklärt was der Skill ist, woher er kommt, und vor allem wie man ihn richtig einsetzt.

Emil empfiehlt explizit: Den Skill **situationsabhängig einsetzen**, nicht als permanente Hintergrundkonfiguration. Diese einfache Formulierung kommuniziert eine Grenze, die die meisten anderen Skills stillschweigend ignorieren. Er sagt damit: Ich weiß was dieser Skill kann, und ich weiß was er nicht kann. Du solltest das auch wissen.

## Warum methodische Nachvollziehbarkeit hier funktioniert

<div class="callout">
<div class="callout__title">Das Kernprinzip guter Skill-Qualität</div>
Ein Skill dessen Prinzipien unabhängig von ihm selbst lesbar, prüfbar und diskutierbar sind, ist ein Skill dem man vertrauen kann.
</div>

Emils SKILL.md ist aus den Artikeln auf seinem Blog destilliert. Das bedeutet: Jedes Prinzip hat eine Quelle. Wer wissen will warum er `clip-path` als bevorzugtes Animations-Primitiv empfiehlt, liest den dazugehörigen Artikel. Wer wissen will warum er Animationen unter 300ms hält und Raycast als Beispiel nennt für eine App die besser ohne Animation funktioniert, findet die Begründung.

Das ist der Unterschied zwischen einem Skill der *behauptet* und einem Skill der *argumentiert*. Die Behauptung ist nicht prüfbar. Das Argument ist es.

Zum Vergleich: Die 99 UX-Richtlinien in `ui-ux-pro-max` haben keine einzige Quellenangabe. Beide Skills machen Aussagen über gutes Design. Nur einer davon zeigt die Arbeit.

## Was der Skill tatsächlich abdeckt

Der Scope ist klar und ehrlich: **UI-Animation und Design Engineering**. Nicht Usability, nicht Nutzerforschung, nicht Accessibility-Compliance. Behandelt werden Animations-Timing unter 300ms, Spring-Parameter, die kontextabhängige Entscheidung ob überhaupt animiert wird, und Performance-Überlegungen wie CSS statt JavaScript für kritische Pfade.

Das ist wenig im Vergleich zu Skills die „344+ Design-Ressourcen" oder „26 Rollen und 60 Befehle" versprechen. Aber es ist wenig was vollständig ist. Ein klar abgegrenzter Skill mit Tiefe ist wertvoller als ein breiter Skill ohne Boden.

## Was noch fehlt, auch hier

Ein perfekter Score wird nicht vergeben, weil er nicht verdient ist. Zwei Punkte bleiben offen:

**Accessibility**: `prefers-reduced-motion` wird im Skill erwähnt, aber nicht als systematische Anforderung behandelt. Animationen die für den durchschnittlichen Nutzer „inevitable and natural" wirken, können für Nutzer mit vestibularen Störungen problematisch sein. Das verdient mehr als eine Randnotiz.

**Formale Testfälle**: Die Quellartikel sind die de-facto-Referenz, aber es gibt keine strukturierten Erwartungen nach dem Muster Input X ergibt Output Y, die prüfbar wären. Das ist kein schwerwiegender Mangel für diesen Skill-Typ, aber es ist eine Grenze.

## Was Studierende hier lernen können

Dieser Skill zeigt konkret was die vier Dimensionen des Bewertungsrahmens in der Praxis bedeuten:

Methodische Fundierung ist nicht die Menge der enthaltenen Regeln, sondern die Nachvollziehbarkeit der Begründungen dahinter.

Transparenz ist nicht der Disclaimer am Ende. Es ist die Art wie der Skill sich selbst beschreibt: als situationsabhängiges Werkzeug, nicht als universelle Lösung.

Validierbarkeit ist nicht das Vorhandensein von Beispielen. Es ist die Möglichkeit, die Prinzipien unabhängig vom Skill selbst zu überprüfen: durch Quellartikel, reale Projekte, nachvollziehbare Argumentation.

Wartbarkeit ist nicht Anzahl der Commits. Es ist ein Maintainer mit verifizierbarem Urteilsvermögen und Haut im Spiel.

---

Dieser Skill erfüllt alle vier Dimensionen mit Abstrichen in Accessibility-Tiefe und formaler Testbarkeit. Das reicht für das höchste Urteil in diesem Blog. Nicht weil er perfekt ist, sondern weil er zeigt was ein solider Skill strukturell leisten muss.
