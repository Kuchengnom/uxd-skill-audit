---
layout: post
title: "mobile-app-ui-design: Echte Fachbegriffe, keine einzige Quellenangabe"
date: 2026-06-22
category: Skill-Evaluation
skill_reviewed: "ceorkm/mobile-app-ui-design"
verdict: vorsicht
reading_time: 7
last_audited: "22. Juni 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "Peak-End-Rule, F-Pattern, Thumb Zone und 8-Point-Grid sind reale, anerkannte Konzepte — aber im Skill ohne einen einzigen Link, Autorennamen oder Studienverweis genannt."
  transparenz: 2
  transparenz_note: "Alle Regeln werden als universelle 'Design Laws' formuliert; keine Hinweise auf Geltungsbereich, Tablet-Formfaktoren oder die Kontroverse um das F-Pattern selbst."
  validierbarkeit: 1
  validierbarkeit_note: "Keine Vorher/Nachher-Beispiele, keine Testfälle, kein Lint-Skript für die eigenen Regeln (z. B. 8-Point-Grid) — nur Fließtext-Richtlinien."
  wartbarkeit: 3
  wartbarkeit_note: "Identifizierbarer Einzelentwickler mit belegbarem Track Record über mehrere Repos, MIT-Lizenz vorhanden, aber nur vier Commits und null Issues seit Veröffentlichung."

tags:
  - quellenarbeit
  - mobile-design
  - peak-end-rule
  - ueberpruefbarkeit
  - skill-evaluation
---

Manche Skills verkaufen sich über Zahlen, manche über große Namen. `ceorkm/mobile-app-ui-design` verkauft sich über etwas Drittes: über Begriffe, die in der UX-Literatur tatsächlich existieren. Peak-End-Rule. F-Pattern. Thumb Zone. 8-Point-Grid. 60/30/10-Regel. Wer diese Liste liest, erkennt sofort: Hier hat jemand recherchiert, nicht nur Stilrichtungen von Dribbble kopiert. Das macht diesen Skill zu einem interessanten Testfall. Nicht weil er besonders groß oder viral wäre, denn es sind 51 Stars, 8 Forks und vier Commits seit der Veröffentlichung, sondern weil er eine Frage zuspitzt die in dieser Serie immer wieder auftaucht: Reicht es, die richtigen Begriffe zu nennen?

## Was der Skill ist

Der Skill besteht aus einer rund 150 Zeilen langen `SKILL.md` und einer Referenzdatei `industry-conventions.md` für branchenspezifische Muster aus Fintech, Health, Crypto und weiteren Bereichen. Er führt durch einen Fünf-Schritte-Prozess: Kontext verstehen, Struktur vor Optik, visuelles Design, emotionales Design, Polish. Am Ende stehen konkrete Implementierungshinweise für React, Tailwind CSS und Lucide-Icons. Lizenziert unter MIT. Autor ist ceorkm, ein Entwickler mit sichtbarem Portfolio an KI-Tooling-Projekten, darunter `grably` mit knapp 300 Stars, `kratos-mcp` und `reactbits-mcp-server`. Das ist kein anonymer Wegwerf-Account, sondern jemand mit nachvollziehbarer Entwicklungsgeschichte im Ökosystem.

## Die richtigen Begriffe, aber ohne Beleg

<div class="callout">
<div class="callout__title">Der Unterschied zwischen Kennen und Belegen</div>
Die Peak-End-Rule stammt aus Daniel Kahnemans Forschung zum retrospektiven Erleben, jener Arbeit für die er den Nobelpreis erhielt. Der Skill nennt sie korrekt beim Namen. Aber nirgendwo in der SKILL.md steht „Kahneman". Kein Link, kein Jahr, keine Studie. Dasselbe gilt für das F-Pattern, das aus der Eyetracking-Forschung der Nielsen Norman Group stammt und in der eigenen Fachwelt seit Jahren umstritten ist, sowie für die Thumb-Zone-Heuristik aus ergonomischen Feldstudien, unter anderem von Steven Hoober. Alle drei Konzepte sind real. Keines davon ist im Skill nachvollziehbar verlinkt.
</div>

Das ist ein anderes Problem als bei Skills, die Quellen frei erfinden oder gar nicht erst erwähnen. Hier sind die Begriffe korrekt, aber sie funktionieren im Text wie Gütesiegel und nicht wie Referenzen. Man liest „Peak-End Rule" und nimmt automatisch an, dass dahinter etwas Geprüftes steht. Das stimmt sogar, nur eben nicht in diesem Dokument. Der Skill formuliert die Anwendung als „Identifiziere deinen Peak-Moment: Abschluss einer Kernaufgabe, Erreichen eines Meilensteins". Wer nachschlagen möchte, ob das der Forschung von Kahneman wirklich entspricht oder eine stark vereinfachte Faustregel daraus macht, hat keine Spur der er folgen kann.

## Gesetze ohne Geltungsbereich

Die SKILL.md spricht wiederholt von „Design Laws": Thumb Zone, F-Pattern, 60/30/10, 8-Point-Grid. Das Wort „Gesetz" suggeriert Allgemeingültigkeit. Tatsächlich handelt es sich größtenteils um craft-bewährte Heuristiken mit bekannten Grenzen. Die 60/30/10-Regel stammt ursprünglich aus der Innenarchitektur und wurde locker auf UI übertragen, nicht empirisch für Bildschirmoberflächen hergeleitet. Das F-Pattern wird in der UX-Forschung selbst seit Jahren relativiert. Es beschreibt ein Lesemuster bei textschweren Webseiten, nicht universell jede App-Oberfläche. Die Thumb-Zone-Regel ignoriert, dass ein wachsender Anteil der Endgeräte Tablets oder gefaltete Displays sind, bei denen „unteres Drittel" wenig Aussagekraft hat.

Nichts davon macht die Heuristiken nutzlos. Aber ein Skill, der sie als „Laws" präsentiert, verschweigt genau die Bedingungen unter denen sie greifen, und die unter denen sie es nicht tun.

## Was fehlt: jede Form von Beleg

Der Skill liefert keine Vorher-Nachher-Vergleiche, keine Screenshots realer Implementierungen und keine Testfälle, die zeigen, dass eine nach diesen Regeln gebaute Oberfläche tatsächlich besser performt als eine, die sie ignoriert. Es gibt auch kein Lint-Skript, das prüft ob generierter Code wirklich dem 8-Point-Grid folgt. Das wäre eine Regel, die sich technisch leicht automatisiert verifizieren ließe, hier aber reine Textanweisung an Claude bleibt. Im Vergleich zu `pbakaus/impeccable`, das zumindest ein OKLCH-Farbskript mitliefert, oder zu `ehmo/platform-design-skills`, das die Apple HIG als PDF direkt im Repository hinterlegt, bleibt `mobile-app-ui-design` durchgehend auf der Ebene der reinen Anweisung.

## Wartbarkeit: kein Geisterprojekt, aber auch kein aktives

Vier Commits seit der Erstellung, null Issues, null Pull Requests. Das Repository wirkt fertig und abgelegt, nicht in laufender Entwicklung. Positiv zu werten: Der Maintainer ist real und im Ökosystem aktiv. Seine anderen Projekte, etwa `kratos-mcp`, erhalten spürbar mehr Aufmerksamkeit und Pflege. Das senkt das Risiko eines vollständig verwaisten Projekts, ändert aber nichts daran, dass dieser spezifische Skill seit dem initialen Push nicht weiterentwickelt wurde. Eine Community-Diskussion auf Reddit, Hacker News oder X war zu diesem Skill nicht auffindbar. Die einzigen Erwähnungen stammen von automatisierten Skill-Marktplatz-Aggregatoren, die jedes öffentliche Repository listen, unabhängig von Qualität oder Erprobung.

## Empfehlung für den Unterrichtseinsatz

Dieser Skill eignet sich gut als Einstiegsübung für eine sehr konkrete Aufgabe: Studierende sollen jeden im Skill genannten Fachbegriff einzeln nachschlagen, die Originalquelle identifizieren und prüfen, ob die im Skill formulierte Anwendung der Quelle entspricht oder sie vereinfacht. Das lässt sich hier gut durchführen, weil die Begriffe real und auffindbar sind. Bei Skills mit erfundenen oder vagen Quellenbehauptungen läuft dieselbe Übung ins Leere.

Für die produktive Anwendung gilt: als craft-basierte Checkliste für schnelle mobile Mockups brauchbar, nicht als belegte Designmethodik. Wer mit diesem Skill arbeitet, sollte jede „Law" als Ausgangshypothese behandeln, die im jeweiligen Projektkontext noch zu prüfen ist, nicht als geprüftes Endergebnis.
