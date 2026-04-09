---
layout: post
title: "emilkowalski/skill: So sollte ein Skill aussehen"
date: 2026-03-26
category: Skill-Evaluation
skill_reviewed: "emilkowalski/skill"
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

Die bisherigen Posts dieses Blogs haben Luecken beschrieben: fehlende Quellenangaben, epistemisch unerfuellbare Anweisungen, archivierte Repos, Datenbanken die als Methodik durchgehen. Dieser Post beschreibt das Gegenteil.

## Wer Emil Kowalski ist — und warum das relevant ist

Bevor der Skill bewertet wird, muss der Autor bewertet werden. Das klingt nach einem Ad-hominem-Argument, ist aber beim Skill-Oekosystem strukturell notwendig: Ein Skill ist destilliertes Urteilsvermoegen. Wessen Urteil steckt drin?

Emil Kowalski ist Design Engineer bei Linear (vorher Vercel), Autor der Open-Source-Bibliotheken Sonner (Toast-Benachrichtigungen) und Vaul (Drawer-Komponenten), und Kursersteller bei [animations.dev](https://animations.dev). Seine Arbeit ist in Production-Produkten, die Millionen von Nutzern taeglich verwenden. Das ist verifizierbarer Track-Record — keine Selbstbeschreibung.

Das spielt fuer die erste Dimension eine entscheidende Rolle.

## Was die `/skill`-Seite anders macht

Der Einstieg zu diesem Skill ist nicht ein GitHub-README. Es ist eine eigene Seite auf seiner persoenlichen Website, die erklaert was der Skill ist, woher er kommt, und — entscheidend — wie man ihn richtig einsetzt.

Emil empfiehlt explizit: Den Skill **situationsabhaengig einsetzen**, nicht als permanente Hintergrundkonfiguration. Diese einfache Formulierung kommuniziert eine Grenze, die die meisten anderen Skills stillschweigend ignorieren. Er sagt damit: Ich weiss was dieser Skill kann, und ich weiss was er nicht kann — und du solltest das auch wissen.

## Warum methodische Nachvollziehbarkeit hier funktioniert

<div class="callout">
<div class="callout__title">Das Kernprinzip guter Skill-Qualitaet</div>
Ein Skill dessen Prinzipien unabhaengig von ihm selbst lesbar, pruefbar und diskutierbar sind, ist ein Skill dem man vertrauen kann.
</div>

Emils SKILL.md ist aus den Artikeln auf seinem Blog destilliert. Das bedeutet: Jedes Prinzip hat eine Quelle. Wer wissen will warum er `clip-path` als bevorzugtes Animations-Primitiv empfiehlt, liest den dazugehoerigen Artikel. Wer wissen will warum er Animationen unter 300ms haelt und Raycast als Beispiel nennt fuer eine App die besser ohne Animation funktioniert, findet die Begruendung.

Das ist der Unterschied zwischen einem Skill der *behauptet* und einem Skill der *argumentiert*. Die Behauptung ist nicht pruefbar. Das Argument ist es.

Zum Vergleich: Die 99 UX-Richtlinien in `ui-ux-pro-max` haben keine einzige Quellenangabe. Beide Skills machen Aussagen ueber gutes Design. Nur einer davon zeigt die Arbeit.

## Was der Skill tatsaechlich abdeckt

Der Scope ist klar und ehrlich: **UI-Animation und Design Engineering**. Nicht Usability, nicht Nutzerforschung, nicht Accessibility-Compliance. Animations-Timing (unter 300ms), Spring-Parameter, kontextabhaengige Entscheidung ob ueberhaupt animiert wird, Performance-Ueberlegungen (CSS statt JavaScript fuer kritische Pfade).

Das ist wenig im Vergleich zu Skills die "344+ Design-Ressourcen" oder "26 Rollen und 60 Befehle" versprechen. Aber es ist wenig was vollstaendig ist. Ein klar abgegrenzter Skill mit Tiefe ist wertvoller als ein breiter Skill ohne Boden.

## Was noch fehlt — auch hier

Ein perfekter Score wird nicht vergeben, weil er nicht verdient ist. Zwei Punkte bleiben offen:

**Accessibility**: `prefers-reduced-motion` wird im Skill erwaehnt, aber nicht als systematische Anforderung behandelt. Animationen die fuer den durchschnittlichen Nutzer "inevitable and natural" wirken, koennen fuer Nutzer mit vestibularen Stoerungen problematisch sein. Das verdient mehr als eine Randnotiz.

**Formale Testfaelle**: Die Quellartikel sind die de-facto-Referenz, aber es gibt keine strukturierten Erwartungen (Input X → Output Y) die pruefbar waeren. Das ist kein schwerwiegender Mangel fuer diesen Skill-Typ, aber es ist eine Grenze.

## Was Studierende hier lernen koennen

Dieser Skill zeigt konkret was die vier Dimensionen des Bewertungsrahmens in der Praxis bedeuten:

**Methodische Fundierung** ist nicht die Menge der enthaltenen Regeln. Es ist die Nachvollziehbarkeit der Begruendungen dahinter.

**Transparenz** ist nicht der Disclaimer am Ende. Es ist die Art wie der Skill sich selbst beschreibt: als situationsabhaengiges Werkzeug, nicht als universelle Loesung.

**Validierbarkeit** ist nicht das Vorhandensein von Beispielen. Es ist die Moeglichkeit, die Prinzipien unabhaengig vom Skill selbst zu ueberpruefen — durch Quellartikel, reale Projekte, nachvollziehbare Argumentation.

**Wartbarkeit** ist nicht Anzahl der Commits. Es ist ein Maintainer mit verifizierbarem Urteilsvermoegen und Haut im Spiel.

---

Dieser Skill erfuellt alle vier Dimensionen mit Abstrichen in Accessibility-Tiefe und formaler Testbarkeit. Das reicht fuer das hoechste Urteil in diesem Blog — nicht weil er perfekt ist, sondern weil er zeigt was ein solider Skill strukturell leisten muss.
