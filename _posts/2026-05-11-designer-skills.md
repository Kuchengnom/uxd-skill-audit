---
layout: post
title: "designer-skills: Eine ehrliche Sammlung, die ihr eigenes Kernproblem benennt"
date: 2026-05-11
category: Skill-Evaluation
skill_reviewed: "Owl-Listener/designer-skills"
verdict: vertrauen
reading_time: 9
last_audited: "11. Mai 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "Reale Quellen vorhanden (Cooper, WCAG, Gothelf), aber als 'Further Reading' deklariert statt als methodisches Fundament — Struktur dominiert über Substanz."
  transparenz: 4
  transparenz_note: "Explizite Grenzkommunikation sowohl im Repository als auch im Begleitartikel; die Autorin benennt die Grenzen von KI-Unterstützung klar und ungewöhnlich ehrlich."
  validierbarkeit: 2
  validierbarkeit_note: "Keine Testfälle, keine Referenzoutputs, keine Before/After-Vergleiche — 23 Commits ohne erkennbare Validierungsinfrastruktur."
  wartbarkeit: 3
  wartbarkeit_note: "MIT-Lizenz und aktive Maintainerin (Stand März 2026), aber Einzelpersonenprojekt ohne Team, ohne Releases, ohne Versionierungsschema."

tags:
  - design-research
  - design-systems
  - ux-strategy
  - breadth-vs-depth
  - quellenarbeit
  - transparenz
  - strukturfrage
---

`Owl-Listener/designer-skills` von Marie-Claire Dean ist kein gewöhnlicher Claude-Skill. Es ist eine Sammlung aus 63 Skills, 27 Commands und 8 Plugins, die den gesamten Designprozess abdecken will: von der Nutzerforschung über Designsysteme und UX-Strategie bis hin zu Interaktionsdesign, Prototyping und Design-Ops. Das ist ein ehrgeiziger Anspruch, und er ist transparent formuliert. Die Sammlung soll „AI what designers know" beibringen, „so it can work with us, not around us."

Was diesen Skill für eine Evaluation besonders interessant macht, ist nicht sein Umfang. Es ist eine einzige Aussage, die Dean in ihrem Begleitartikel auf Substack macht: eine Selbstdiagnose, die das zentrale Spannungsfeld der gesamten Sammlung benennt.

## Wer steckt dahinter?

Marie-Claire Dean ist Designerin mit nachweisbarem Practitioner-Hintergrund. Sie schreibt regelmäßig auf Substack unter dem Titel „MC Dean percolates" über Design im KI-Zeitalter und hat neben `designer-skills` weitere verwandte Projekte veröffentlicht: `designpowers` mit 10 Agenten für einen inklusiven Designprozess, dazu `ai-design-skills` und `inclusive-design-skills`. Das Ökosystem ist kohärent und erkennbar aus einer gemeinsamen Designphilosophie heraus entwickelt.

Das Repository ist MIT-lizenziert, offen für Beiträge, und wurde zuletzt im März 2026 aktualisiert. Zum Zeitpunkt dieser Evaluation verzeichnet es 1 Star und 23 Commits. Diese Zahlen stehen im deutlichen Widerspruch zu den 928 Stars, die ältere Suchindex-Snapshots ausweisen. Die Diskrepanz ist nicht ungewöhnlich bei Projekten, die anderswo erwähnt werden, etwa in Medium-Artikeln, X-Posts oder auf LinkedIn, ohne dass der Verkehr direkt auf das Repository trifft. Für die methodische Bewertung ist die Zahl irrelevant. Für die Einschätzung der Wartbarkeit ist sie ein Signal: Breite Community-Nutzung und aktive Pflege sind nicht dasselbe.

## Die Selbstdiagnose, die alles erhellt

In ihrem Substack-Artikel schreibt Dean über den Prozess des Skill-Schreibens:

> "I also learned that the structure matters more than the content."

Das ist ein bemerkenswerter Satz. Dean meint ihn positiv: Claude braucht keine Theorie, sondern klare Frameworks und Entscheidungskriterien. Aber als Beobachter liest man denselben Satz und fragt: Wenn Struktur wichtiger ist als Inhalt, wie tief geht dann der Inhalt wirklich?

Ein Blick in konkrete Skill-Dateien zeigt das Dilemma. Der `user-persona`-Skill zitiert Alan Cooper mit „About Face", Jeff Gothelf mit „Lean UX" und Erika Hall mit „Just Enough Research". Das sind legitime, überprüfbare Quellen. Cooper ist tatsächlich der Begründer des Persona-Konzepts, die Zitation ist korrekt. Aber die Quellen erscheinen unter der Überschrift „Further Reading" am Ende des Dokuments, nicht als verankerte methodische Basis im Instruktionstext selbst. Der Skill erklärt Cooper korrekt als „Archetypical users based on behavioral patterns, not demographics alone", aber er zeigt nicht, wie man das überprüft: welche Behavioral Patterns, nach welchen Kriterien gruppiert, mit welcher Fehlertoleranz.

Der `accessibility-audit`-Skill ist noch kürzer. Korrekte WCAG-2.2-Referenz, POUR-Prinzipien vollständig aufgezählt, Severity-Rating-Schema vorhanden, aber alles in kaum 15 Zeilen. WCAG ist eine verifizierbare Norm, die Referenz ist real. Was fehlt, ist der Schritt von der Norm zur Praxis: Wie entscheidet der Skill, welche Prüfreihenfolge sinnvoll ist? Was passiert bei Konflikten zwischen WCAG-Kriterien? Wie geht man mit kontextabhängigen Ausnahmen um?

<div class="callout">
<div class="callout__title">Das Strukturparadox</div>
Dean benennt selbst, was diese Sammlung auszeichnet und was ihr Limit ist: Struktur als primäres Qualitätsmerkmal. Das funktioniert als Einstiegspunkt, weil Claude strukturierte Instruktionen besser verarbeitet als freie Prosa. Es ist aber kein Ersatz für methodische Tiefe. Eine Skill-Datei, die Cooper zitiert ohne zu zeigen, wie man seine Methodik anwendet, ist gut strukturiert und gleichzeitig methodisch flach. Die Struktur schafft den Anschein von Fundierung, ohne sie vollständig einzulösen. Für Studierende ist das ein wichtiges Muster: „Quellen nennen" und „Quellen korrekt portieren" sind nicht dasselbe, auch wenn die genannten Quellen real sind.
</div>

## Was die Transparenz leistet

Bemerkenswert ist, wie offen Dean über die Grenzen ihres Projekts kommuniziert. Im Substack-Artikel steht explizit:

> "This isn't a replacement for design judgment. It's an amplifier for it."

Und am Ende, fast als Nachsatz:

> "Obviously (need I say) this is no workaround for having experienced researchers and designers on your team."

Dieser Satz steht im Begleitartikel, nicht im Repository selbst, aber er ist öffentlich und direkt mit dem Projekt verknüpft. Für die Transparenz-Bewertung zählt das. Die Autorin überverspricht nicht. Sie weiß, was ein Skill leisten kann und was nicht.

Relevant ist auch, dass Dean offen kommuniziert, sie habe die Sammlung „with my friend Claude" gebaut. Sie ist also co-generiert, nicht rein handgeschrieben. Das ist methodisch ehrlicher als viele vergleichbare Projekte, die ihre KI-Beteiligung verschweigen. Es wirft allerdings eine Folgefrage auf: Wer validiert die Ausgabe eines Sprachmodells, das Designwissen kodiert, wenn das Designwissen aus dem Training des Sprachmodells stammt? Das ist kein Vorwurf, sondern eine offene Frage. Dean selbst würde sie vermutlich stellen.

## Validierung als systematische Lücke

Wo die Sammlung klar schwächelt, ist die Frage der Validierbarkeit. Es gibt keine Testfälle, keine Referenzoutputs, keine Before/After-Vergleiche. Der Substack-Artikel zeigt Beispiel-Commands mit beschriebenen Outputs wie „a full persona set" oder „a production-ready colour system", aber keine konkreten Outputs, gegen die man prüfen könnte, ob der Skill das Versprochene liefert.

Das ist ein strukturelles Problem bei Prompt-basierten Skills: Der Output ist non-deterministisch. Derselbe Command kann je nach Kontext sehr unterschiedliche Ergebnisse produzieren. Ohne Referenzoutputs oder formale Evaluationskriterien ist es nicht möglich zu sagen, ob ein generierter Persona-Satz „gut" ist. Möglich ist nur das Urteil einer Person mit ausreichend Erfahrung. Das ist genau das Urteil, das der Skill zu delegieren versucht.

Für die Unterrichtspraxis ist das die wichtigste Lektion: Ein Skill ohne Validierungsinfrastruktur ist eine Hypothese, keine Methodik.

## Breite als Strategie und als Risiko

Die Entscheidung, 63 Skills zu bauen anstatt 10 tiefe, ist eine bewusste strategische Wahl. Dean erklärt das in ihrem Artikel: Die Sammlung soll „the full breadth of what designers typically do" abdecken. Das ist ein legitimes Ziel, besonders als Einstiegspunkt für Designstudierende, die Claude Code kennenlernen.

Aber Breite hat einen Preis. Wenn Struktur wichtiger ist als Inhalt, dann multipliziert eine breite Sammlung diese Schwäche: 63 gut strukturierte, methodisch flache Skills. Einzelne Bereiche sind besser ausgearbeitet als andere. Die Nutzerforschungs-Skills haben erkennbar mehr Tiefe als etwa die Design-Ops-Skills. Das ist nachvollziehbar, spiegelt aber auch wider, wo Deans Schwerpunkt liegt.

Für die Beurteilung im Unterricht: Die Sammlung ist besser als Explorationsraum denn als Referenzwerk geeignet. Sie zeigt, welche Designmethoden existieren und wie man sie benennt, nicht unbedingt wie man sie korrekt anwendet.

## Empfehlung für den Unterrichtseinsatz

`Owl-Listener/designer-skills` eignet sich gut für zwei spezifische Unterrichtsszenarien.

Erstens als **Strukturvorlage**: Die Plugin-Architektur mit Skills als Wissenseinheiten und Commands als Workflows ist ein gutes Lehrbeispiel dafür, wie man Designwissen modular organisiert. Studierende können die Struktur verwenden, um eigene, tiefere Skills zu einem ihrer Kompetenzbereiche zu bauen, und dabei direkt erleben, was Dean beschreibt: „The act of encoding design knowledge forces you to articulate what you actually know."

Zweitens als **Quellenanalyse-Übung**: Der User-Persona-Skill zitiert Cooper, der Accessibility-Skill referenziert WCAG, beides korrekt. Die Frage für den Unterricht lautet dann: Wie weit geht die Portierung? Was fehlt, damit aus einer Quellnennung eine methodische Grundlage wird? Das macht den Skill zu einem guten Ausgangstext für eine kritische Auseinandersetzung mit dem Unterschied zwischen Quellennachweis und Quellenarbeit.

Für den direkten produktiven Einsatz gilt: Die Sammlung ist nutzbar, aber mit Vorbehalt. Wer die zugrundeliegenden Designmethoden kennt, kann die Outputs einschätzen und korrigieren. Wer sie nicht kennt, bekommt gut strukturierte, möglicherweise oberflächliche Ergebnisse, ohne Warnsignal dass etwas fehlt.

Das ist keine Kritik an Dean, die das selbst sehr klar kommuniziert. Es ist ein Hinweis auf die Grenzen des Formats.
