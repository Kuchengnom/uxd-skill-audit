---
layout: post
title: "design-motion-principles: Drei Designer, ein Skill — und das Kohärenzproblem liegt im Konzept"
date: 2026-04-20
category: Skill-Evaluation
skill_reviewed: "kylezantos/design-motion-principles"
verdict: vorsicht
reading_time: 11
last_audited: "20. April 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "Drei real existierende, öffentlich verifizierbare Praktiker als Quellen; Prinzipien plausibel und nachvollziehbar — aber keine direkten Links zu Originalartikeln oder Kursen in den Referenzdateien"
  transparenz: 3
  transparenz_note: "Kontext-Aware-Logik explizit kommuniziert; 'never apply rules blindly' steht im README — aber keine Warnung vor LLM-Grenzen bei visueller Animationsbewertung"
  validierbarkeit: 2
  validierbarkeit_note: "Hohe Installationszahlen (861/Woche) sind kein Qualitätsnachweis; keine Testfälle, keine Before/After-Beispiele, kein Vergleich mit Expertenbewertung dokumentiert"
  wartbarkeit: 3
  wartbarkeit_note: "Identifizierbarer Maintainer (Kyle Zantos, aktiv auf X), MIT-Lizenz, Version v1.2.0 vom 16. April 2026 — aber Einzelperson mit 17 Commits insgesamt"

tags:
  - motion-design
  - css-animation
  - drei-quellen-problem
  - emil-kowalski
  - jhey-tompkins
  - jakub-krehel
  - vorsicht-beispiel
  - quellenportierung
  - kontext-awareness
  - design-engineer
---

In diesem Blog wurde `emilkowalski/skill` bereits evaluiert und mit dem Urteil „Solide" versehen. Das Besondere an diesem Skill: Er stammt vom Designer selbst. Kyle Zantos' `design-motion-principles` verfolgt eine andere Strategie, und das ist der Ausgangspunkt dieser Evaluation.

Das Repository verspricht einen Motion-Design-Audit-Skill „trained on Emil Kowalski, Jakub Krehel, and Jhey Tompkins." Statt eines Designers werden drei synthetisiert. Das klingt umfassender. Ob es das ist, ist eine andere Frage.

## Was das Repository enthält

Die Struktur ist ordentlich: ein SKILL.md mit Orchestrierungslogik, sieben Referenzdateien und Slash-Commands für verschiedene Audit-Szenarien. Auf jeden Designer entfällt eine Referenzdatei, dazu kommen Dokumente zu Accessibility, Performance und Audit-Checkliste.

Kyle Zantos ist auf GitHub und X als Design Engineer auffindbar. Das Repository gehört zum grösseren Ökosystem `design-engineer-auditor-package`. MIT-Lizenz vorhanden, Version v1.2.0 erschien am 16. April 2026. Mit 287 Stars und 861 Wocheninstallationen hat der Skill erkennbare Verbreitung, liegt aber weit unter dem für diesen Blog untersuchten `pbakaus/impeccable` mit seinen 10.000 Stars. Das ist kein Qualitätsmerkmal, aber es gehört zum Bild.

## Die drei Quellen: Wer steht dahinter?

**Emil Kowalski** ist der am stärksten dokumentierte der drei. Design Engineer bei Linear, ehemals Vercel, Autor von Sonner und Vaul, Betreiber der eigenen Website emilkowal.ski mit publizierten Artikeln zu Animationspraxis und einem Kurs „Animations on the Web". Seine Positionen lassen sich nachschlagen und gegen das Original halten.

**Jhey Tompkins**, auf X als @jh3yy, veröffentlicht CSS-Experimente auf Smashing Magazine und CSS-Tricks. Sein Ansatz: durch spielerisches Ausprobieren lernen. „I want to make Y, can I learn X?" ist sein dokumentierter Designprozess, kein Zitat aus zweiter Hand.

**Jakub Krehel** ist der methodisch dünnste der drei. Eine eigene dokumentierte Quelle, ein Blog oder Kurs, ist öffentlich schwerer auffindbar als bei den anderen beiden. Das bedeutet nicht, dass seine Prinzipien falsch sind. Es bedeutet, dass sie schwerer unabhängig zu überprüfen sind.

## Das Quellen-Problem: Portierung ohne Verlinkung

In den Referenzdateien werden Prinzipien den Designern zugeschrieben, ohne direkte Links zu den Originalquellen. Die Emil-Kowalski-Datei zitiert seine Kernthesen, darunter „Easing is the most important part of any animation", die Frequenz-Regel und das 300ms-Limit, ohne auf den Quellartikel oder Kurs zu verlinken. Die Jhey-Tompkins-Datei nennt Smashing Magazine und CSS-Tricks als Publikationsorte, aber keine spezifischen Stücke.

Das wiederholt ein Muster das in diesem Blog immer wieder auftaucht: Quellen nennen ist nicht dasselbe wie Quellen korrekt portieren, und Quellen portieren ist nicht dasselbe wie Quellen verlinken. Wer überprüfen will, ob „Easing is the most important part" tatsächlich Kowalskis Position ist und in welchem Kontext er sie formuliert hat, muss selbst suchen.

Im Unterricht lässt sich genau dieser Schritt üben: von der Prinzipien-Behauptung zur Originalquelle zurückverfolgen und beobachten, wie sich der Kontext dabei verschiebt.

## Das konzeptuelle Kernproblem: Drei Stile, ein Skill

<div class="callout">
<div class="callout__title">Das Kohärenzproblem ist kein Fehler, es ist das Konzept</div>
Emil Kowalski und Jhey Tompkins vertreten unterschiedliche ästhetische Positionen, nicht nur verschiedene Schwerpunkte. Kowalski: Animation ist dann gut, wenn sie nicht auffällt. Seine Frequenz-Regel besagt, dass Aktionen die hunderte Mal täglich ausgeführt werden minimale oder keine Animation brauchen. Jhey Tompkins: Der beste Einstieg in eine Technik ist ein spielerisches Experiment ohne definierten Zweck. „I want to make Y, can I learn X?" ist sein Designprozess. Das eine minimiert Animation als störendes Element. Das andere feiert Animation als Erkenntnisweg. Beide sind legitime Perspektiven für ihren jeweiligen Kontext. Aber sie zusammen in einem „Motion Design Audit" zu bündeln und Context-Awareness als Lösung zu deklarieren, verschiebt das epistemische Problem nur. Wer entscheidet welcher Kontext vorliegt, und auf welcher Grundlage?
</div>

Der Skill gibt eine Antwort darauf: Reconnaissance. Bevor ein Audit beginnt, analysiert Claude den Projekttyp und priorisiert die passende Designer-Perspektive. Unterschieden werden Produktivitätstool, Consumer App und kreative Seite. Emil steht für Produktivität, Jhey für Portfolios, Jakub für polished Consumer-Apps.

Das klingt sinnvoll. Aber es setzt voraus, dass Claude den Projektkontext korrekt einschätzt und auch bei Mischformen brauchbar entscheidet, etwa bei einem spielerischen B2B-Tool oder einem ernsthaften Portfolio. Keine dieser Annahmen ist im Skill dokumentiert, keine durch Testfälle abgedeckt.

Dazu kommt ein grundlegenderes Problem: Claude kann Animationen nicht sehen. Der Audit findet auf Code-Ebene statt, CSS-Eigenschaften, Timing-Werte, Easing-Kurven. Ob eine Animation tatsächlich „natural" wirkt oder ob das Timing zu lang ist, lässt sich nicht allein aus dem Quellcode ableiten. Der Skill gibt CSS-Empfehlungen ohne Rückkopplungsschleife.

## Vergleich mit emilkowalski/skill

Dieser Blog hat `emilkowalski/skill` mit „Solide" bewertet. Ein zentrales Argument war, dass der Skill vom Designer selbst stammt: kein Zwischenlayer der verzerren kann.

`design-motion-principles` ist ein Drittpartei-Skill. Kyle Zantos hat Kowalskis, Krehels und Tompkins' Arbeit gelesen, interpretiert und in Prompt-Form übersetzt. Bei jeder Übersetzungsstufe kann sich die Bedeutung verschieben: Was Kowalski mit „restraint" meinte, was Zantos darunter verstand, und was Claude im Audit-Kontext daraus macht, sind drei verschiedene Dinge. Nur das erste davon ist direkt verifizierbar.

Das ist eine strukturelle Beobachtung über Drittpartei-Portierung, keine Kritik an Zantos' Arbeit. First-Party-Skills haben dieses Problem schlicht nicht.

## Wartung und Community

Kyle Zantos kommuniziert auf X über seine Skill-Entwicklung. Das Repository ist Teil eines grösseren `design-engineer-auditor-package`. MIT-Lizenz vorhanden, v1.2.0 erschien vier Tage vor diesem Post.

17 Commits insgesamt ist eine überschaubare Historie. Das kann auf einen schlank gehaltenen Skill hindeuten oder auf frühes Stadium. Ein offenes Issue ist ein normales Signal für ein aktives Projekt.

## Empfehlung für den Unterrichtseinsatz

`design-motion-principles` eignet sich als Fallbeispiel für zwei konkrete Fragen.

Das Verifikationsproblem: Die drei Designer sind real, ihre Prinzipien öffentlich nachvollziehbar, aber die Referenzdateien verlinken nicht auf die Originalquellen. Woher kommt das 300ms-Limit genau? In welchem Artikel von Emil Kowalski steht das, und in welchem Kontext? Dieser Weg lässt sich nachverfolgen. Das ist eine lohnende Übung.

Das Kohärenzproblem bei Stil-Synthesisen: Drei Designer mit verschiedenen ästhetischen Ausgangspositionen zusammenzufassen löst kein Problem, es definiert ein neues. Mehr Stimmen bedeutet nicht einen klareren Standpunkt. „Context-aware" ist Zantos' Antwort auf die Frage welche Perspektive gilt. Im Unterricht kann man genau untersuchen, was das konkret bedeutet und wo es abbricht.

Als Werkzeug für einen Motion-Design-Audit funktioniert der Skill dort, wo der Nutzer bereits weiß welchen Designer-Modus er braucht. Wer weiß, dass er einen Emil-Kowalski-Audit für ein Produktivitätstool möchte, bekommt nützliche Impulse. Wer das nicht weiß, bekommt eine Entscheidung die Claude für ihn trifft, ohne Testfälle und ohne visuelle Wahrnehmung.
