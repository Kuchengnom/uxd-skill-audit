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
  methodische_fundierung_note: "Reale Quellen sind vorhanden (Cooper, WCAG, Gothelf). Sie stehen aber als 'Further Reading' und nicht als methodisches Fundament. Die Struktur dominiert über die Substanz."
  transparenz: 4
  transparenz_note: "Die Grenzen sind im Repository und im Begleitartikel explizit kommuniziert. Die Autorin benennt die Grenzen von KI-Unterstützung klar und ungewöhnlich ehrlich."
  validierbarkeit: 2
  validierbarkeit_note: "Es gibt keine Testfälle, keine Referenzoutputs und keine Before/After-Vergleiche. Die 23 Commits zeigen keine erkennbare Validierungsinfrastruktur."
  wartbarkeit: 3
  wartbarkeit_note: "MIT-Lizenz und eine aktive Maintainerin (Stand März 2026) sprechen für das Projekt. Es ist aber ein Einzelpersonenprojekt ohne Team, ohne Releases und ohne Versionierungsschema."

tags:
  - design-research
  - design-systems
  - ux-strategy
  - breadth-vs-depth
  - quellenarbeit
  - transparenz
  - strukturfrage
---

`Owl-Listener/designer-skills` von Marie-Claire Dean ist kein gewöhnlicher Claude-Skill. Es ist eine Sammlung aus 63 Skills, 27 Commands und 8 Plugins. Sie will den gesamten Designprozess abdecken. Das reicht von der Nutzerforschung über Designsysteme und UX-Strategie bis zu Interaktionsdesign, Prototyping und Design-Ops. Der Anspruch ist ehrgeizig und transparent formuliert. Die Sammlung soll „AI what designers know" beibringen, „so it can work with us, not around us."

Interessant ist an diesem Skill nicht sein Umfang. Interessant ist eine einzige Aussage aus Deans Begleitartikel auf Substack. Es ist eine Selbstdiagnose. Sie benennt das zentrale Spannungsfeld der gesamten Sammlung.

## Wer steckt dahinter?

Marie-Claire Dean ist Designerin mit nachweisbarem Practitioner-Hintergrund. Sie schreibt regelmäßig auf Substack unter dem Titel „MC Dean percolates" über Design im KI-Zeitalter. Neben `designer-skills` hat sie weitere verwandte Projekte veröffentlicht. `designpowers` bringt 10 Agenten für einen inklusiven Designprozess. Dazu kommen `ai-design-skills` und `inclusive-design-skills`. Das Ökosystem ist kohärent. Es entstand erkennbar aus einer gemeinsamen Designphilosophie.

Das Repository ist MIT-lizenziert und offen für Beiträge. Zuletzt wurde es im März 2026 aktualisiert. Zum Zeitpunkt dieser Evaluation verzeichnet es 1 Star und 23 Commits. Ältere Suchindex-Snapshots weisen dagegen 928 Stars aus. Der Widerspruch ist deutlich. Er ist aber nicht ungewöhnlich. Projekte werden anderswo erwähnt, etwa in Medium-Artikeln, X-Posts oder auf LinkedIn. Der Verkehr trifft dann nicht direkt auf das Repository. Für die methodische Bewertung ist die Zahl irrelevant. Für die Wartbarkeit ist sie ein Signal. Breite Community-Nutzung und aktive Pflege sind nicht dasselbe.

## Die Selbstdiagnose, die alles erhellt

In ihrem Substack-Artikel schreibt Dean über den Prozess des Skill-Schreibens:

> "I also learned that the structure matters more than the content."

Das ist ein bemerkenswerter Satz. Dean meint ihn positiv. Claude braucht keine Theorie, sondern klare Frameworks und Entscheidungskriterien. Als Beobachter liest man denselben Satz anders. Wenn Struktur wichtiger ist als Inhalt, wie tief geht dann der Inhalt wirklich?

Ein Blick in konkrete Skill-Dateien zeigt das Dilemma. Der `user-persona`-Skill zitiert Alan Cooper mit „About Face", Jeff Gothelf mit „Lean UX" und Erika Hall mit „Just Enough Research". Das sind legitime, überprüfbare Quellen. Cooper ist tatsächlich der Begründer des Persona-Konzepts. Die Zitation ist korrekt. Die Quellen stehen aber unter der Überschrift „Further Reading" am Ende des Dokuments. Im Instruktionstext sind sie nicht als methodische Basis verankert. Der Skill erklärt Cooper korrekt als „Archetypical users based on behavioral patterns, not demographics alone". Er zeigt aber nicht, wie man das überprüft. Die gemeinten Behavioral Patterns bleiben offen. Die Kriterien der Gruppierung auch. Eine Fehlertoleranz fehlt.

Der `accessibility-audit`-Skill ist noch kürzer. Er enthält eine korrekte WCAG-2.2-Referenz. Die POUR-Prinzipien sind vollständig aufgezählt. Ein Severity-Rating-Schema ist vorhanden. Alles zusammen füllt kaum 15 Zeilen. WCAG ist eine verifizierbare Norm. Die Referenz ist real. Es fehlt der Schritt von der Norm zur Praxis. Wie entscheidet der Skill über eine sinnvolle Prüfreihenfolge? Was passiert bei Konflikten zwischen WCAG-Kriterien? Wie geht man mit kontextabhängigen Ausnahmen um?

<div class="callout">
<div class="callout__title">Das Strukturparadox</div>
Dean benennt selbst, was diese Sammlung auszeichnet und was ihr Limit ist. Es ist Struktur als primäres Qualitätsmerkmal. Als Einstiegspunkt funktioniert das. Claude verarbeitet strukturierte Instruktionen besser als freie Prosa. Methodische Tiefe ersetzt Struktur aber nicht. Eine Skill-Datei zitiert Cooper und zeigt nicht, wie man seine Methodik anwendet. Sie ist dann gut strukturiert und methodisch flach. Die Struktur schafft den Anschein von Fundierung. Eingelöst wird sie nicht vollständig. Für Studierende ist das ein wichtiges Muster. „Quellen nennen" und „Quellen korrekt portieren" sind nicht dasselbe, auch wenn die genannten Quellen real sind.
</div>

## Was die Transparenz leistet

Bemerkenswert ist, wie offen Dean über die Grenzen ihres Projekts spricht. Im Substack-Artikel steht explizit:

> "This isn't a replacement for design judgment. It's an amplifier for it."

Und am Ende, fast als Nachsatz:

> "Obviously (need I say) this is no workaround for having experienced researchers and designers on your team."

Er steht im Begleitartikel. Das Repository nennt ihn nicht. Er ist aber öffentlich und direkt mit dem Projekt verknüpft. Für die Transparenz-Bewertung zählt das. Die Autorin überverspricht nicht. Sie weiß, was ein Skill leisten kann und was nicht.

Dean sagt außerdem offen, sie habe die Sammlung „with my friend Claude" gebaut. Die Sammlung ist also co-generiert und nicht rein handgeschrieben. Das ist methodisch ehrlicher als bei vielen vergleichbaren Projekten. Die verschweigen ihre KI-Beteiligung. Es wirft allerdings eine Folgefrage auf. Wer validiert die Ausgabe eines Sprachmodells, das Designwissen kodiert? Das Designwissen stammt ja aus dem Training des Sprachmodells. Einen Vorwurf stellt das nicht dar. Es ist eine offene Frage. Dean selbst würde sie vermutlich stellen.

## Validierung als systematische Lücke

Bei der Validierbarkeit schwächelt die Sammlung klar. Es gibt keine Testfälle, keine Referenzoutputs und keine Before/After-Vergleiche. Der Substack-Artikel zeigt Beispiel-Commands mit beschriebenen Outputs wie „a full persona set" oder „a production-ready colour system". Konkrete Outputs fehlen. Man kann also nicht prüfen, ob der Skill das Versprochene liefert.

Bei Prompt-basierten Skills ist das ein strukturelles Problem. Der Output ist non-deterministisch. Derselbe Command kann je nach Kontext sehr unterschiedliche Ergebnisse produzieren. Ohne Referenzoutputs oder formale Evaluationskriterien lässt sich nicht sagen, ob ein generierter Persona-Satz „gut" ist. Möglich ist nur das Urteil einer Person mit ausreichend Erfahrung. Genau dieses Urteil versucht der Skill zu delegieren.

Für die Unterrichtspraxis ist das die wichtigste Lektion. Ein Skill ohne Validierungsinfrastruktur ist eine Hypothese und keine Methodik.

## Breite als Strategie und als Risiko

Dean baut bewusst 63 Skills statt 10 tiefer Skills. Sie erklärt das in ihrem Artikel. Die Sammlung soll „the full breadth of what designers typically do" abdecken. Das ist ein legitimes Ziel. Besonders gilt das für Designstudierende, die Claude Code kennenlernen.

Breite hat aber einen Preis. Wenn Struktur wichtiger ist als Inhalt, multipliziert eine breite Sammlung diese Schwäche. Es entstehen 63 gut strukturierte, methodisch flache Skills. Einzelne Bereiche sind besser ausgearbeitet als andere. Die Nutzerforschungs-Skills haben erkennbar mehr Tiefe als die Design-Ops-Skills. Das ist nachvollziehbar. Es spiegelt auch wider, wo Deans Schwerpunkt liegt.

Für den Unterricht taugt die Sammlung besser als Explorationsraum denn als Referenzwerk. Sie zeigt, dass es diese Designmethoden gibt und wie man sie benennt. Wie man sie korrekt anwendet, zeigt sie nicht unbedingt.

## Empfehlung für den Unterrichtseinsatz

`Owl-Listener/designer-skills` eignet sich gut für zwei spezifische Unterrichtsszenarien.

Erstens als **Strukturvorlage**. Die Plugin-Architektur trennt Skills als Wissenseinheiten von Commands als Workflows. Das ist ein gutes Lehrbeispiel für modular organisiertes Designwissen. Studierende können die Struktur nutzen und eigene, tiefere Skills zu einem ihrer Kompetenzbereiche bauen. Dabei erleben sie direkt, was Dean beschreibt: „The act of encoding design knowledge forces you to articulate what you actually know."

Zweitens als **Quellenanalyse-Übung**. Der User-Persona-Skill zitiert Cooper. Der Accessibility-Skill referenziert WCAG. Beides ist korrekt. Die Frage für den Unterricht lautet dann, wie weit die Portierung geht. Was fehlt, damit aus einer Quellnennung eine methodische Grundlage wird? So wird der Skill zum Ausgangstext für eine kritische Auseinandersetzung. Es geht um den Unterschied zwischen Quellennachweis und Quellenarbeit.

Für den direkten produktiven Einsatz gilt ein Vorbehalt. Wer die zugrundeliegenden Designmethoden kennt, kann die Outputs einschätzen und korrigieren. Wer sie nicht kennt, bekommt gut strukturierte, möglicherweise oberflächliche Ergebnisse. Ein Warnsignal, dass etwas fehlt, bekommt er nicht.

Das ist keine Kritik an Dean. Sie kommuniziert das selbst sehr klar. Es ist ein Hinweis auf die Grenzen des Formats.
