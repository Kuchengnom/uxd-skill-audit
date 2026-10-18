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
  - überprüfbarkeit
  - skill-evaluation
---

Manche Skills verkaufen sich über Zahlen, manche über große Namen. `ceorkm/mobile-app-ui-design` verkauft sich über etwas Drittes. Es sind Begriffe, die in der UX-Literatur tatsächlich existieren. Peak-End-Rule. F-Pattern. Thumb Zone. 8-Point-Grid. 60/30/10-Regel. Wer diese Liste liest, erkennt sofort, dass hier jemand recherchiert hat. Von Dribbble kopiert wurden nicht nur Stilrichtungen.

Das macht den Skill zu einem interessanten Testfall. Groß oder viral ist er nicht. Er hat 51 Stars, 8 Forks und vier Commits seit der Veröffentlichung. Er spitzt aber eine Frage zu, die in dieser Serie immer wieder auftaucht. Reicht es, die richtigen Begriffe zu nennen?

## Was der Skill ist

Der Skill besteht aus einer rund 150 Zeilen langen `SKILL.md` und einer Referenzdatei `industry-conventions.md`. Die Datei sammelt branchenspezifische Muster aus Fintech, Health, Crypto und weiteren Bereichen. Ein Fünf-Schritte-Prozess führt durch die Arbeit. Die Schritte heißen Kontext verstehen, Struktur vor Optik, visuelles Design, emotionales Design und Polish. Am Ende stehen konkrete Implementierungshinweise für React, Tailwind CSS und Lucide-Icons. Die Lizenz ist MIT.

Autor ist ceorkm. Er entwickelt KI-Tooling und hat ein sichtbares Portfolio. Dazu zählen `grably` mit knapp 300 Stars, `kratos-mcp` und `reactbits-mcp-server`. Einen anonymen Wegwerf-Account sehe ich hier nicht. Dahinter steht jemand mit nachvollziehbarer Entwicklungsgeschichte im Ökosystem. Das zählt.

## Die richtigen Begriffe, aber ohne Beleg

<div class="callout">
<div class="callout__title">Der Unterschied zwischen Kennen und Belegen</div>
Die Peak-End-Rule stammt aus Daniel Kahnemans Forschung zum retrospektiven Erleben. Für diese Arbeit erhielt er den Nobelpreis. Der Skill nennt die Regel korrekt beim Namen. Nirgendwo in der SKILL.md steht aber „Kahneman". Es gibt keinen Link, kein Jahr und keine Studie. Dasselbe gilt für das F-Pattern. Es stammt aus der Eyetracking-Forschung der Nielsen Norman Group und ist in der eigenen Fachwelt seit Jahren umstritten. Dasselbe gilt für die Thumb-Zone-Heuristik aus ergonomischen Feldstudien, unter anderem von Steven Hoober. Alle drei Konzepte sind real. Keines davon ist im Skill nachvollziehbar verlinkt.
</div>

Dieses Problem ist ein anderes als bei Skills, die Quellen frei erfinden oder gar nicht erwähnen. Die Begriffe sind hier korrekt. Im Text funktionieren sie aber wie Gütesiegel und nicht wie Referenzen. Man liest „Peak-End Rule" und nimmt automatisch an, dass dahinter etwas Geprüftes steht. Das stimmt sogar. Nur steht es nicht in diesem Dokument. Der Skill formuliert die Anwendung als „Identifiziere deinen Peak-Moment: Abschluss einer Kernaufgabe, Erreichen eines Meilensteins". Entspricht das der Forschung von Kahneman? Oder ist es eine stark vereinfachte Faustregel daraus? Wer das nachschlagen will, findet keine Spur. Es gibt nichts zu verfolgen.

## Gesetze ohne Geltungsbereich

Die SKILL.md spricht wiederholt von „Design Laws". Genannt werden Thumb Zone, F-Pattern, 60/30/10 und 8-Point-Grid. Das Wort „Gesetz" suggeriert Allgemeingültigkeit. Tatsächlich sind es größtenteils craft-bewährte Heuristiken. Ihre Grenzen sind bekannt.

Die 60/30/10-Regel stammt ursprünglich aus der Innenarchitektur. Man hat sie locker auf UI übertragen. Für Bildschirmoberflächen wurde sie nicht empirisch hergeleitet. Die UX-Forschung selbst relativiert das F-Pattern seit Jahren. Es beschreibt ein Lesemuster bei textschweren Webseiten und nicht jede App-Oberfläche. Die Thumb-Zone-Regel ignoriert einen Trend. Ein wachsender Anteil der Endgeräte sind Tablets oder gefaltete Displays. Bei ihnen hat „unteres Drittel" wenig Aussagekraft.

Nutzlos macht das die Heuristiken nicht. Ein Skill, der sie als „Laws" präsentiert, verschweigt aber die Bedingungen, unter denen sie greifen. Er verschweigt auch die, unter denen sie es nicht tun.

## Was fehlt: jede Form von Beleg

Der Skill liefert keine Vorher-Nachher-Vergleiche und keine Screenshots realer Implementierungen. Testfälle fehlen ebenfalls. Keiner zeigt, dass eine nach diesen Regeln gebaute Oberfläche besser performt als eine, die sie ignoriert. Ein Lint-Skript, das prüft, ob generierter Code wirklich dem 8-Point-Grid folgt, gibt es auch nicht. Technisch ließe sich diese Regel leicht automatisiert verifizieren. Hier bleibt sie reine Textanweisung an Claude.

`pbakaus/impeccable` liefert zumindest ein OKLCH-Farbskript mit. `ehmo/platform-design-skills` hinterlegt die Apple HIG als PDF direkt im Repository. `mobile-app-ui-design` bleibt dagegen durchgehend auf der Ebene der reinen Anweisung.

## Wartbarkeit: kein Geisterprojekt, aber auch kein aktives

Vier Commits seit der Erstellung, null Issues, null Pull Requests. Das Repository wirkt fertig und abgelegt. In laufender Entwicklung ist es nicht. Positiv zu werten ist der Maintainer. Er ist real und im Ökosystem aktiv. Seine anderen Projekte, etwa `kratos-mcp`, erhalten spürbar mehr Aufmerksamkeit und Pflege. Das senkt das Risiko eines vollständig verwaisten Projekts. Geändert hat sich der Skill dadurch nicht. Seit dem initialen Push wurde er nicht weiterentwickelt.

Eine Community-Diskussion auf Reddit, Hacker News oder X war zu diesem Skill nicht auffindbar. Erwähnt wird er nur von automatisierten Skill-Marktplatz-Aggregatoren. Sie listen jedes öffentliche Repository, unabhängig von Qualität oder Erprobung. Das beweist nichts.

## Empfehlung für den Unterrichtseinsatz

Als Einstiegsübung eignet sich der Skill gut für eine sehr konkrete Aufgabe. Studierende schlagen jeden genannten Fachbegriff einzeln nach. Sie identifizieren die Originalquelle. Dann prüfen sie, ob die Anwendung im Skill der Quelle entspricht oder sie vereinfacht. Die Begriffe sind real und auffindbar, deshalb lässt sich das hier gut durchführen. Bei Skills mit erfundenen oder vagen Quellenbehauptungen läuft dieselbe Übung ins Leere.

Für die produktive Anwendung gilt Folgendes. Als craft-basierte Checkliste für schnelle mobile Mockups ist der Skill brauchbar. Eine belegte Designmethodik ist er nicht. Wer damit arbeitet, behandelt jede „Law" als Ausgangshypothese. Im jeweiligen Projektkontext bleibt sie zu prüfen. Ein geprüftes Endergebnis ist sie nicht.
