---
layout: default
title: Der 4-Dimensionen-Rahmen
permalink: /methodik/
---

<div class="post-header">
  <div class="container">
    <span class="post-category">Methodik</span>
    <h1 class="post-title">Wie werden Skills bewertet</h1>
    <p style="color: var(--color-text-muted); font-family: var(--font-ui); max-width: 55ch;">
      Ein Skill der gut klingt, ist kein Skill der gut funktioniert. Dieser Rahmen macht die Unterschiede sichtbar.
    </p>
  </div>
</div>

<div class="post-content container" markdown="1">

Das Skill-Oekosystem fuer Claude wächst schneller als es evaluiert wird. Stars auf GitHub, viral gegangene Tweets und schön formatierte READMEs sagen nichts über die methodische Qualitaet eines Skills aus. Dieser Blog benutzt deshalb vier Dimensionen zur Bewertung.

## Dimension 1: Methodische Fundierung (1–5)

Ist die zugrundeliegende Technik anerkannt, korrekt verstanden und akkurat in den Skill portiert?

Ein Skill der behauptet, Nielsen's 10 Heuristiken umzusetzen, muss alle zehn korrekt wiedergeben. Ein Skill der Cognitive Walkthroughs anbietet, muss die Methode von Wharton et al. kennen, nicht eine vereinfachte Variante daraus. Punkte werden abgezogen wenn:

- Terminologie frei erfunden oder ungenau verwendet wird
- Die Quelle nicht genannt oder falsch zitiert wird
- Die Methode vereinfacht wird ohne die Vereinfachung zu kommunizieren
- KI-Output als Ersatz fuer menschliche Expertise dargestellt wird

## Dimension 2: Transparenz der Grenzen (1–5)

Kommuniziert der Skill klar, was er nicht kann?

Dies ist die kritischste Dimension fuer den Lehrkontext. Ein Heuristic-Evaluation-Skill der keine Nutzer befragt hat, kann keine Usability-Probleme *beweisen* — er kann nur Hypothesen generieren. Ein Skill der das nicht kommuniziert, fuehrt Studierende in die Irre. Punkte werden abgezogen wenn:

- Generierten Artefakten wissenschaftliche Autoritaet zugeschrieben wird
- Keine Warnung vorhanden ist wo menschliche Expertise unersetzbar bleibt
- Scores und Ratings ohne statistische Grundlage praesentiert werden
- Der Skill impliziert, Nutzerforschung zu *ersetzen* statt zu *unterstuetzen*

## Dimension 3: Validierbarkeit (1–5)

Gibt es Testfaelle, Referenzoutputs oder Vergleiche mit menschlicher Expertenarbeit?

Ein guter Skill kann beweisen was er tut. Das bedeutet: Beispiel-Inputs mit dokumentierten Erwartungen, Python-Skripte die Outputs pruefen, oder zumindest ein Before/After mit Erklaerung. Punkte werden abgezogen wenn:

- Keine Beispiele vorhanden sind
- Keine ausfuehrbaren Werkzeuge mitgeliefert werden
- Kein Vergleich zwischen Skill-Output und Expertenurteil existiert
- Der Skill nicht reproduzierbar ist

## Dimension 4: Wartbarkeit (1–5)

Wer steht dahinter, wie ist die Versionierung, wann wurde zuletzt aktualisiert?

Ein archivierter Skill, ein anonymer Maintainer oder eine fehlende Lizenz sind Warnsignale. Punkte werden abgezogen wenn:

- Das Repository seit mehr als 6 Monaten nicht aktualisiert wurde
- Keine Lizenz vorhanden ist
- Ein einziger Maintainer ohne Nachfolger existiert
- Issues und Pull Requests ignoriert werden

---

## Wie man diese Bewertung liest

Keine Dimension ist wichtiger als die anderen — aber die Kombination entscheidet. Ein Skill mit hoher Wartbarkeit und niedriger methodischer Fundierung ist gepflegter Unsinn. Ein Skill mit hoher Fundierung und keiner Validierbarkeit ist unueberprüfbare Theorie.

Die Bewertungen auf diesem Blog sind Momentaufnahmen zum angegebenen Datum. Skills aendern sich, und wir aktualisieren wo moeglich.

</div>
