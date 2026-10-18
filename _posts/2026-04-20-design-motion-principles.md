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
  methodische_fundierung_note: "Die Quellen sind drei real existierende, öffentlich verifizierbare Praktiker. Die Prinzipien sind plausibel und nachvollziehbar. Die Referenzdateien enthalten aber keine direkten Links zu Originalartikeln oder Kursen."
  transparenz: 3
  transparenz_note: "Die Kontext-Aware-Logik ist explizit kommuniziert. 'never apply rules blindly' steht im README. Eine Warnung vor LLM-Grenzen bei visueller Animationsbewertung fehlt."
  validierbarkeit: 2
  validierbarkeit_note: "Hohe Installationszahlen (861/Woche) sind kein Qualitätsnachweis. Dokumentiert sind weder Testfälle noch Before/After-Beispiele noch ein Vergleich mit Expertenbewertung."
  wartbarkeit: 3
  wartbarkeit_note: "Der Maintainer ist identifizierbar (Kyle Zantos, aktiv auf X). Es gibt eine MIT-Lizenz und Version v1.2.0 vom 16. April 2026. Dahinter steht aber eine Einzelperson mit 17 Commits insgesamt."

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

In diesem Blog wurde `emilkowalski/skill` bereits evaluiert. Das Urteil lautete „Solide". Der Skill stammt vom Designer selbst. Kyle Zantos' `design-motion-principles` verfolgt eine andere Strategie. Sie ist der Ausgangspunkt dieser Evaluation.

Das Repository verspricht einen Motion-Design-Audit-Skill „trained on Emil Kowalski, Jakub Krehel, and Jhey Tompkins." Statt eines Designers werden drei synthetisiert. Das klingt umfassender. Ob es das ist, bleibt offen.

## Was das Repository enthält

Die Struktur ist ordentlich. Es gibt ein SKILL.md mit Orchestrierungslogik, sieben Referenzdateien und Slash-Commands für verschiedene Audit-Szenarien. Auf jeden Designer entfällt eine Referenzdatei. Dazu kommen Dokumente zu Accessibility, Performance und Audit-Checkliste.

Kyle Zantos ist auf GitHub und X als Design Engineer auffindbar. Das Repository gehört zum größeren Ökosystem `design-engineer-auditor-package`. Die MIT-Lizenz ist vorhanden. Version v1.2.0 erschien am 16. April 2026. Der Skill hat 287 Stars und 861 Wocheninstallationen. Das ist erkennbare Verbreitung. Das für diesen Blog untersuchte `pbakaus/impeccable` kommt auf 10.000 Stars. Stars sind kein Qualitätsmerkmal, aber sie gehören zum Bild.

## Die drei Quellen: Wer steht dahinter?

**Emil Kowalski** ist der am stärksten dokumentierte der drei. Er ist Design Engineer bei Linear und war zuvor bei Vercel. Er schrieb Sonner und Vaul. Auf seiner Website emilkowal.ski stehen Artikel zu Animationspraxis und der Kurs „Animations on the Web". Seine Positionen lassen sich nachschlagen und gegen das Original halten.

**Jhey Tompkins** ist auf X als @jh3yy unterwegs. Er veröffentlicht CSS-Experimente auf Smashing Magazine und CSS-Tricks. Sein Ansatz lautet: durch spielerisches Ausprobieren lernen. „I want to make Y, can I learn X?" ist sein dokumentierter Designprozess und kein Zitat aus zweiter Hand.

**Jakub Krehel** ist der methodisch dünnste der drei. Eine eigene dokumentierte Quelle, ein Blog oder Kurs, ist öffentlich schwerer auffindbar als bei den anderen beiden. Seine Prinzipien sind deshalb nicht falsch. Sie sind nur schwerer unabhängig zu überprüfen.

## Das Quellen-Problem: Portierung ohne Verlinkung

Die Referenzdateien schreiben Prinzipien den Designern zu. Direkte Links zu den Originalquellen fehlen. Die Emil-Kowalski-Datei zitiert seine Kernthesen, darunter „Easing is the most important part of any animation", die Frequenz-Regel und das 300ms-Limit. Auf den Quellartikel oder Kurs verlinkt sie nicht. Die Jhey-Tompkins-Datei nennt Smashing Magazine und CSS-Tricks als Publikationsorte. Spezifische Stücke nennt sie nicht.

Dieses Muster taucht in diesem Blog immer wieder auf. Quellen nennen ist nicht dasselbe wie Quellen korrekt portieren. Quellen portieren ist nicht dasselbe wie Quellen verlinken. Wer prüfen will, ob „Easing is the most important part" tatsächlich Kowalskis Position ist, muss selbst suchen. Auch den Kontext seiner Formulierung findet nur, wer sucht.

Im Unterricht lässt sich genau dieser Schritt üben. Man geht von der Prinzipien-Behauptung zur Originalquelle zurück. Dabei sieht man, wie sich der Kontext verschiebt.

## Das konzeptuelle Kernproblem: Drei Stile, ein Skill

<div class="callout">
<div class="callout__title">Das Kohärenzproblem ist kein Fehler, es ist das Konzept</div>
Emil Kowalski und Jhey Tompkins vertreten unterschiedliche ästhetische Positionen. Sie setzen nicht nur verschiedene Schwerpunkte. Für Kowalski ist Animation dann gut, wenn sie nicht auffällt. Seine Frequenz-Regel besagt, dass Aktionen mit hunderten Ausführungen täglich minimale oder keine Animation brauchen. Für Jhey Tompkins ist der beste Einstieg in eine Technik ein spielerisches Experiment ohne definierten Zweck. „I want to make Y, can I learn X?" ist sein Designprozess. Das eine minimiert Animation als störendes Element. Das andere feiert Animation als Erkenntnisweg. Beide sind legitime Perspektiven für ihren Kontext. Beide zusammen in einem „Motion Design Audit" zu bündeln und Context-Awareness als Lösung zu deklarieren, verschiebt das epistemische Problem nur. Wer legt den Kontext fest? Und worauf stützt sich das?
</div>

Der Skill gibt darauf eine Antwort: Reconnaissance. Vor dem Audit analysiert Claude den Projekttyp und priorisiert die passende Designer-Perspektive. Unterschieden werden Produktivitätstool, Consumer App und kreative Seite. Emil steht für Produktivität, Jhey für Portfolios und Jakub für polished Consumer-Apps.

Das klingt sinnvoll. Es setzt aber voraus, dass Claude den Projektkontext korrekt einschätzt. Auch bei Mischformen müsste Claude brauchbar entscheiden, etwa bei einem spielerischen B2B-Tool oder einem ernsthaften Portfolio. Keine dieser Annahmen ist im Skill dokumentiert. Keine ist durch Testfälle abgedeckt.

Dazu kommt ein grundlegenderes Problem. Claude kann Animationen nicht sehen. Der Audit findet auf Code-Ebene statt: CSS-Eigenschaften, Timing-Werte, Easing-Kurven. Ob eine Animation „natural" wirkt, lässt sich nicht allein aus dem Quellcode ableiten. Das gilt auch für die Frage, ob das Timing zu lang ist. Der Skill gibt CSS-Empfehlungen ohne Rückkopplungsschleife.

## Vergleich mit emilkowalski/skill

Dieser Blog hat `emilkowalski/skill` mit „Solide" bewertet. Ein zentrales Argument war die Herkunft. Er stammt vom Designer selbst. Es gibt keinen Zwischenlayer, der verzerren kann.

`design-motion-principles` ist ein Drittpartei-Skill. Kyle Zantos hat die Arbeit von Kowalski, Krehel und Tompkins gelesen, interpretiert und in Prompt-Form übersetzt. Bei jeder Stufe kann sich die Bedeutung verschieben. Was Kowalski mit „restraint" meinte, ist eine Sache. Was Zantos darunter verstand, ist die zweite. Was Claude im Audit-Kontext daraus macht, ist die dritte. Nur die erste ist direkt verifizierbar.

Das ist eine strukturelle Beobachtung über Drittpartei-Portierung. Eine Kritik an Zantos' Arbeit ist es nicht. First-Party-Skills haben dieses Problem schlicht nicht.

## Wartung und Community

Kyle Zantos kommuniziert auf X über seine Skill-Entwicklung. Das Repository ist Teil des größeren `design-engineer-auditor-package`. Die MIT-Lizenz ist vorhanden. Version v1.2.0 erschien vier Tage vor diesem Post.

17 Commits insgesamt sind eine überschaubare Historie. Es kann auf einen schlank gehaltenen Skill hindeuten. Es kann auch ein frühes Stadium sein. Ein offenes Issue ist ein normales Signal für ein aktives Projekt.

## Empfehlung für den Unterrichtseinsatz

`design-motion-principles` eignet sich als Fallbeispiel für zwei konkrete Fragen.

Die erste ist das Verifikationsproblem. Die drei Designer sind real und ihre Prinzipien öffentlich nachvollziehbar. Die Referenzdateien verlinken aber nicht auf die Originalquellen. Woher kommt das 300ms-Limit genau? Wo steht es bei Emil Kowalski, und wie ist es dort eingebettet? Dieser Weg lässt sich nachverfolgen. Die Übung lohnt sich.

Die zweite ist das Kohärenzproblem bei Stil-Synthesen. Drei Designer mit verschiedenen ästhetischen Ausgangspositionen zusammenzufassen löst kein Problem. Es definiert ein neues. Mehr Stimmen ergeben keinen klareren Standpunkt. „Context-aware" ist Zantos' Antwort auf die Frage nach der geltenden Perspektive. Im Unterricht kann man untersuchen, was das konkret bedeutet. Man sieht auch, wo es abbricht.

Als Werkzeug für einen Motion-Design-Audit funktioniert der Skill dort, wo der Nutzer den Designer-Modus bereits kennt. Wer einen Emil-Kowalski-Audit für ein Produktivitätstool will, bekommt nützliche Impulse. Wer das nicht weiß, bekommt eine Entscheidung von Claude. Testfälle gibt es dafür nicht. Visuelle Wahrnehmung fehlt ebenfalls.
