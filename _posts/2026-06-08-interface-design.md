---
layout: post
title: "interface-design: Handwerklich überzeugend, methodisch nicht verortbar"
date: 2026-06-08
category: Skill-Evaluation
skill_reviewed: "Dammyjay93/interface-design"
verdict: vorsicht
reading_time: 11
last_audited: "8. Juni 2026"
supersedes: /2026/05/04/interface-design/

skill_scores:
  methodische_fundierung: 2
  methodische_fundierung_note: "Keine einzige zitierte Quelle. Die Prinzipien sind empirisch plausibel und handwerklich solide. Sie sind aber vollständig auf persönlicher Autorphilosophie aufgebaut und nicht auf anerkannter Designliteratur"
  transparenz: 4
  transparenz_note: "Expliziter Scope-Ausschluss (nicht für Marketing). Ehrliche Selbstkritik an LLM-Grenzen direkt im Skill-Text. 'You will generate generic output' ist ungewöhnlich offene Kommunikation"
  validierbarkeit: 3
  validierbarkeit_note: "Before/After im README, zwei Referenz-system.md-Dateien, eigene Website mit Beispielen. Es gibt aber keine formalen Tests und keinen Vergleich mit Expertenbewertung"
  wartbarkeit: 4
  wartbarkeit_note: "Oyindamola Akinleye auf LinkedIn verifikbar, MIT-Lizenz, eigene Domain interface-design.dev, ca. 4.600 Stars. Aktiv, aber Einzelperson"

tags:
  - handwerksphilosophie
  - quellenfreiheit
  - memory-pattern
  - stateless-llm
  - craft-principles
  - interface-design
  - vorsicht-beispiel
  - scope-klarheit
---

<div class="callout">
<div class="callout__title">Re-Audit ersetzt die Evaluation vom 4. Mai 2026</div>
Dieser Skill wurde in diesem Blog zweimal geprüft. Die <a href="{{ '/2026/05/04/interface-design/' | relative_url }}">erste Evaluation vom 4. Mai</a> kam zum Urteil <code>vertrauen</code>. Zum Urteil <code>vorsicht</code> kommt diese. Der Unterschied hängt an einer einzigen Zahl. Damals wurde die methodische Fundierung mit 3 bewertet und hier mit 2. Alle übrigen Dimensionen stimmen überein.

Auf neue Befunde geht die Korrektur nicht zurück. Beide Evaluationen stellen denselben Sachverhalt fest. Der Skill nennt keine einzige Quelle. Ursache ist eine falsche Anwendung des eigenen Bewertungsrahmens. Dort ist der Wert 3 als „Quellen vorhanden aber lückenhaft" definiert. Bei null Quellen ist er nicht vergebbar. Der Wert 1 trifft ebenso wenig zu. Die Prinzipien sind handwerklich substanziell und nur eben unbelegt. Es bleibt die 2. Nach der Urteilsregel folgt daraus zwingend <code>vorsicht</code>. Eine Dimension liegt dann bei 2 oder darunter.

Die Mai-Fassung bleibt unverändert einsehbar. Löschen wäre bequemer. Es würde aber verbergen, was hier zu lernen ist. Ein Bewertungsrahmen schützt nicht davor, falsch angewendet zu werden. Er macht den Fehler nur nachweisbar.
</div>

Im Ökosystem der Claude-Design-Skills gibt es einen deutlich erkennbaren Grundtypus. Dieser Skill legitimiert sein Versprechen mit Frameworks. Nielsen. WCAG. Material Design. Verweise auf anerkannte Autoritäten sollen Vertrauen schaffen. `Dammyjay93/interface-design` geht den entgegengesetzten Weg. Es gibt keine Quellen, keine Frameworks und keine Fußnotenarchitektur. Dafür gibt es ein etwas anderes Angebot. Es ist ein System für Handwerk, Konsistenz und Designgedächtnis über Sessions hinweg. Das Gedächtnis ist die eigentliche Neuheit im Ökosystem.

Mit knapp 4.600 GitHub-Stars und einer eigenen Domain unter `interface-design.dev` gehört dieser Skill zu den meistgenutzten Designtools im Claude-Code-Umfeld. Als Qualitätsnachweis reicht das allein nicht. Es ist aber ein Grund, genauer hinzusehen.

## Was der Skill verspricht

Die drei Säulenbegriffe im README sind `Craft`, `Memory` und `Consistency`. Dahinter steckt eine klar umrissene Idee. Wer UI mit Claude baut, entscheidet in jeder Session neu über Abstände, Farbtemperaturen und Tiefenstrategie. Ohne Struktur driften diese Entscheidungen. Interface-design löst das durch eine Datei namens `.interface-design/system.md`. Sie speichert Designentscheidungen persistent. Zu Beginn jeder neuen Session wird sie automatisch geladen.

Der Scope ist explizit eingegrenzt. Er umfasst Dashboards, Admin-Panels, SaaS-Anwendungen und Tools. Explizit *nicht* gedacht ist der Skill für Landing Pages, Marketingseiten und Kampagnen. Diese Selbstbegrenzung ist selten und erwähnenswert. Viele Skills im Ökosystem formulieren so breite Versprechen, dass jede Evaluation mit dem Problem beginnt, was der Skill überhaupt meint. Hier ist das von Anfang an klar.

## Die Handwerksphilosophie

Im Herzstück des Skills steckt kein Framework, sondern eine in Prosa formulierte Designphilosophie. Ihre Grundthese lautet, dass bei einem LLM ohne explizite Intention immer die Defaults gewinnen. Das zeigt sich an `--gray-700` statt `--ink`, an der Standard-Sidebar-Breite statt einer Entscheidung und an vertrauten Font-Stacks statt einer Wahl. Dem setzt die Skill-Anweisung ein Gegengewicht entgegen. Vor jeder Komponente muss Intention explizit formuliert werden. Gefragt wird nach dem Menschen, der das Interface nutzt, nach seiner Aufgabe und nach dem gewünschten Gefühl.

Die konkreten Handwerksprinzipien, die daraus folgen, sind gut. Dazu zählen Subtle Layering als Rückgrat jeder Tiefenstrategie und Border-Progressionen, die nicht härter als nötig wahrgenommen werden. Die Token-Architektur ist auf eine Handvoll Primitive reduziert. Es gibt vier Textebenen statt zweier. Wer mit UI-Entwicklung vertraut ist, erkennt solide destillierte Praxis. Vercel, Linear und Stripe werden als Vorbilder genannt. Sie sind keine Quellen. Sie sind Beispiele für Interfaces, die genau das zeigen, wovon der Skill spricht.

<div class="callout">
<div class="callout__title">Methodisches Kernproblem</div>
Alle Prinzipien in diesem Skill lassen sich auf ihren Ursprung hin befragen. Keine einzige Antwort findet sich im Repository. Für „Subtle Layering" nennt der Skill keine Herkunft. Er sagt nicht, von wem die Vier-Ebenen-Texthierarchie stammt. Eine Studie, ein Buch oder eine öffentlich zugängliche Methodik hinter der Border-Progression fehlt ebenfalls. Dokumentiert ist nichts davon. Das bedeutet nicht, dass die Prinzipien falsch sind. Empirisch sind sie plausibel und stimmig. Für Lernende, die verstehen wollen, *warum* etwas gilt und nicht nur *was*, ist dieser Skill aber eine Sackgasse. Er liefert gut formulierte Anweisungen und keine epistemische Verankerung.
</div>

Ein Vorwurf an den Autor ist das nicht. Ein erfahrener UI-Entwickler, der sein Handwerk in einer Prompt-Datei kondensiert, muss keine Dissertation schreiben. Für den professionellen Einsatz ist das akzeptabel. Für den Unterrichtseinsatz ist es eine ernst zu nehmende Lücke.

## Das Gedächtnis, und was es wirklich ist

Der Begriff „Memory" auf der Website und im README kann zu einer Fehlinterpretation führen. Sie kommt im Ökosystem häufig vor. Man stellt sich vor, das LLM selbst erinnere sich. Hier passiert das nicht.

Tatsächlich schreibt der Skill nach Abschluss einer Session Designentscheidungen in die Datei `.interface-design/system.md` auf dem Filesystem des Nutzers. Beim Start einer neuen Session lädt Claude Code diese Datei. Damit hat es Zugriff auf die früheren Entscheidungen. Das LLM bleibt stateless. Verändert hat sich die externe Persistenz der Eingabe.

Technisch legitim und praktisch wirksam ist das. Im Skill selbst und im README ist es transparent beschrieben. Die Website formuliert es sogar explizit: „Saves your design decisions to `.interface-design/system.md`." Das Missverständnispotenzial liegt im Marketing-Begriff „Memory" und im Slogan „Claude forgets your design decisions — this plugin remembers them." Beides stimmt im Ergebnis. Das *wie* bleibt dem Nutzer überlassen zu verstehen.

Für Design-Studierende ist dieser Mechanismus lehrreich. Er zeigt einen praktischen Umgang mit einer echten LLM-Einschränkung, ohne zu übertreiben. Simpel, transparent und reproduzierbar ist die Lösung.

## Was der Skill an Selbstkritik enthält

Ungewöhnlich offen und deshalb besonders erwähnenswert ist die Selbstkritik. Das SKILL.md selbst schreibt an den Nutzer Claude direkt: „You will generate generic output. Your training has seen thousands of dashboards. The patterns are strong." Und weiter: „process alone doesn't guarantee craft. You have to catch yourself."

Das ist keine typische Skill-Rhetorik. Meist positionieren sich Skills im Ökosystem als Lösungen. Seine Grenzen kommuniziert dieser Skill direkt in der Instruktion. Er tut das nicht als Fußnote, sondern als strukturell eingeplante Selbstkritik. Der Autor weiß, dass der LLM-Raum für Defaults anfällig ist. Dieses Wissen baut er direkt in den Prozess ein.

Die vier Checks am Ende des Builds heißen Swap-Test, Squint-Test, Signature-Test und Token-Test. Sie zeigen, wie sich Validierung als Schritt im Workflow verankern lässt. Einen formalen Testrahmen gibt es nicht. Es gibt aber eine bewusste Unterbrechung des Automatismus.

## Scope-Klarheit als strukturelle Stärke

Die explizite Eingrenzung auf Interface-Design statt Marketing ist mehr als eine Randnotiz. Im Unterricht lässt sich daraus fragen, warum unterschiedliche Design-Kontexte unterschiedliche Skills brauchen. Ebenso lässt sich fragen, was ein Marketingdesign-Skill methodisch anders macht als ein Interface-Design-Skill. Der Skill hat eine Identität. Er weiß, was er ist und was er nicht ist.

Die Abgrenzung ist auch insofern ehrlich, als sie das Versagen verhindert, das häufig beim Einsatz zu breit formulierter Skills entsteht. Wird ein Skill für alles eingesetzt, versagt er bei allem ein bisschen.

## Wartbarkeit und Community

Oyindamola Akinleye ist auf LinkedIn identifizierbar. Das Projekt steht unter MIT-Lizenz und hat eine eigene, gepflegte Website. Es wurde von `claude-design-skill` umbenannt. Alte URLs leiten automatisch weiter. Aktive Pflege zeigt sich darin. Mit ca. 4.600 Stars und ca. 316 Forks hat das Projekt eine reale Community.

Die berichtete Issue #13 beschreibt ein konkretes Problem. Skills und Commands erscheinen nach der Installation nicht im Slash-Menu. Seit März 2026 ist der Bug offen. Er kann den Einsatz in bestimmten Konfigurationen beeinträchtigen. Konzeptionell ist er kein Problem. Bei der Installation sollte man ihn aber im Blick haben.

## Empfehlung für den Unterrichtseinsatz

`interface-design` eignet sich gut als Ausgangsmaterial für eine Unterrichtseinheit über die Grenzen empirischer Handwerksphilosophie. Die Kernfrage lautet, wann „funktioniert in der Praxis" ein ausreichender Qualitätsnachweis ist und wann theoretische Verankerung notwendig wird.

Konkret empfiehlt sich folgender Einsatz. Man lässt den SKILL.md lesen und stellt dann eine Aufgabe. „Nennt für jedes Prinzip eine anerkannte Quelle, die es stützt." Das erfordert längere Recherchearbeit. Die Prinzipien sind nicht aus der Luft gegriffen. Sie finden sich in UI-Literatur, in Designsystem-Dokumentationen großer Unternehmen und in akademischen Schriften zur visuellen Hierarchie. Nur sind sie dort nicht verlinkt. Eine wertvolle Übung ist es, diese Lücke eigenständig zu schließen.

Für den praktischen Einsatz gilt Folgendes. Wer Dashboards und Admin-Interfaces mit Claude Code baut, bekommt mit diesem Skill ein konsistentes, ernsthaftes Fundament. Der system.md-Mechanismus ist keine Magie, sondern eine gut durchdachte Konvention. Die eingebettete Selbstkritik an LLM-Defaults ist einer der ehrlichsten Umgänge mit dieser Einschränkung im gesamten Ökosystem.

Das Urteil lautet `vorsicht`. Der Skill ist nicht schlecht. Seine Stärken liegen in Handwerk und Transparenz. Die fehlende methodische Verankerung hinterlässt aber für alle, die *lernen* wollen, eine echte Lücke.
