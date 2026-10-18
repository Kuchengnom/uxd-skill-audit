---
layout: default
title: Der 4-Dimensionen-Rahmen
permalink: /methodik/
example_scores:
  methodische_fundierung: 4
  transparenz: 3
  validierbarkeit: 4
  wartbarkeit: 5
---

<div class="post-header">
  <div class="container">
    <span class="post-category">Methodik</span>
    <h1 class="post-title">Wie werden Skills bewertet</h1>
    <p style="color: var(--color-text-muted); font-family: var(--font-ui); max-width: 55ch;">
      Ein Skill, der gut klingt, funktioniert nicht automatisch gut. Dieser Rahmen macht die Unterschiede sichtbar.
    </p>
  </div>
</div>

<div class="post-content container" markdown="1">

Das Skill-Ökosystem für Claude wächst schneller, als jemand es evaluiert. Stars auf GitHub, virale Tweets und schön formatierte READMEs sagen nichts über die methodische Qualität eines Skills. Dieser Blog bewertet deshalb entlang von vier Dimensionen.

---

## Das Vier-Dimensionen-Modell

<div class="scorecard-wrapper">
  <div style="width: 300px; margin: 0 auto;">
    {% include skill-radar.html scores=page.example_scores size="full" %}
  </div>
  <p style="color: var(--color-text-muted); font-family: var(--font-ui); margin-top: var(--space-l); text-align: center; font-size: 0.9rem;">
    <strong>Beispiel:</strong> Ein Skill mit hoher Wartbarkeit (5), solider Methodik (4) und Validierbarkeit (4). Die Transparenz über Grenzen fällt ab (3).
  </p>
</div>

---

## Dimension 1: Methodische Fundierung (1–5)

Ist die zugrunde liegende Technik anerkannt, korrekt verstanden und akkurat in den Skill übertragen?

Ein Skill verspricht Nielsens 10 Heuristiken. Dann muss er alle zehn korrekt wiedergeben. Ein Skill bietet Cognitive Walkthroughs an. Dann muss er die Methode von Wharton et al. kennen und keine vereinfachte Variante. Punkte fallen weg, wenn:

- die Terminologie frei erfunden oder ungenau ist
- die Quelle fehlt oder falsch zitiert wird
- die Methode vereinfacht wird, ohne die Vereinfachung zu nennen
- KI-Output als Ersatz für menschliche Expertise auftritt

## Dimension 2: Transparenz der Grenzen (1–5)

Sagt der Skill klar, was er nicht kann?

Für die Lehre ist das die kritischste Dimension. Ein Heuristic-Evaluation-Skill hat keine Nutzer befragt. Er kann Usability-Probleme deshalb nicht *beweisen*. Er erzeugt Hypothesen. Verschweigt der Skill das, führt er Studierende in die Irre. Punkte fallen weg, wenn:

- generierte Artefakte wissenschaftliche Autorität bekommen
- eine Warnung fehlt, wo menschliche Expertise unersetzbar bleibt
- Scores und Ratings ohne statistische Grundlage erscheinen
- der Skill Nutzerforschung *ersetzen* will, statt sie zu *unterstützen*

## Dimension 3: Validierbarkeit (1–5)

Gibt es Testfälle, Referenzoutputs oder Vergleiche mit menschlicher Expertenarbeit?

Ein guter Skill belegt, was er tut. Das heißt: Beispiel-Inputs mit dokumentierten Erwartungen, Python-Skripte, die Outputs prüfen, oder zumindest ein Before/After mit Erklärung. Punkte fallen weg, wenn:

- Beispiele fehlen
- keine ausführbaren Werkzeuge mitgeliefert werden
- kein Vergleich zwischen Skill-Output und Expertenurteil existiert
- der Skill nicht reproduzierbar ist

## Dimension 4: Wartbarkeit (1–5)

Wer steht dahinter, wie ist die Versionierung, wann gab es das letzte Update?

Ein archivierter Skill, ein anonymer Maintainer oder eine fehlende Lizenz sind Warnsignale. Punkte fallen weg, wenn:

- das Repository seit mehr als 6 Monaten keine Änderung bekam
- eine Lizenz fehlt
- ein einziger Maintainer ohne Nachfolger übrig bleibt
- Issues und Pull Requests liegen bleiben

---

## Wie man diese Bewertung liest

Keine Dimension wiegt mehr als die anderen. Die Kombination entscheidet. Hohe Wartbarkeit bei niedriger methodischer Fundierung ergibt gepflegten Unsinn. Hohe Fundierung ohne Validierbarkeit bleibt unüberprüfbare Theorie.

Die Bewertungen sind Momentaufnahmen zum angegebenen Datum. Skills ändern sich. Ich aktualisiere, wo es geht.

</div>
