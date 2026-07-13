---
layout: post
title: "interface-design: Handwerklich überzeugend, methodisch nicht verortbar"
date: 2026-06-08
category: Skill-Evaluation
published: false
skill_reviewed: "Dammyjay93/interface-design"
verdict: vorsicht
reading_time: 11
last_audited: "8. Juni 2026"

skill_scores:
  methodische_fundierung: 2
  methodische_fundierung_note: "Keine einzige zitierte Quelle; Prinzipien empirisch plausibel und handwerklich solide, aber vollstaendig auf persoenlicher Autorphilosophie aufgebaut — nicht auf anerkannter Designliteratur"
  transparenz: 4
  transparenz_note: "Expliziter Scope-Ausschluss (nicht fuer Marketing), ehrliche Selbstkritik an LLM-Grenzen direkt im Skill-Text; 'You will generate generic output' ist ungewoehnlich offene Kommunikation"
  validierbarkeit: 3
  validierbarkeit_note: "Before/After im README, zwei Referenz-system.md-Dateien, eigene Website mit Beispielen — aber keine formalen Tests und kein Vergleich mit Expertenbewertung"
  wartbarkeit: 4
  wartbarkeit_note: "Oyindamola Akinleye auf LinkedIn verifikbar, MIT-Lizenz, eigene Domain interface-design.dev, ca. 4.600 Stars — aktiv, aber Einzelperson"

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

Im Oekosystem der Claude-Design-Skills gibt es einen deutlich erkennbaren Grundtypus: der Skill der sein Versprechen mit Frameworks legitimiert. Nielsen. WCAG. Material Design. Der Verweis auf anerkannte Autoritaeten soll Vertrauen schaffen. `Dammyjay93/interface-design` geht den entgegengesetzten Weg. Keine Quellen, keine Frameworks, keine Fussnotenarchitektur. Dafuer ein etwas anderes Angebot: ein System fuer Handwerk, Konsistenz und — das ist die eigentliche Neuheit im Oekosystem — Designgedaechtnis ueber Sessions hinweg.

Mit knapp 4.600 GitHub-Stars und einer eigenen Domain (`interface-design.dev`) gehoert dieser Skill zu den meistgenutzten Designtools im Claude-Code-Umfeld. Das allein ist kein Qualitaetsnachweis. Aber es ist ein Grund, genauer hinzusehen.

## Was der Skill verspricht

Die drei Saeulenbegriffe im README sind `Craft`, `Memory` und `Consistency`. Dahinter steckt eine klar umrissene Idee: Wer UI mit Claude baut, entscheidet in jeder Session neu — Abstaende, Farbtemperaturen, Tiefenstrategie. Ohne Struktur driften diese Entscheidungen. Interface-design loest das durch eine Datei namens `.interface-design/system.md`, die Designentscheidungen persistent speichert und zu Beginn jeder neuen Session automatisch geladen wird.

Der Scope ist explizit eingegrenzt: Dashboards, Admin-Panels, SaaS-Anwendungen, Tools. Explizit *nicht* fuer: Landing Pages, Marketingseiten, Kampagnen. Diese Selbstbegrenzung ist selten und erwaehnenswert. Viele Skills im Oekosystem formulieren so breite Versprechen, dass jede Evaluation mit dem Problem beginnt, was der Skill ueberhaupt meint. Hier ist das von Anfang an klar.

## Die Handwerksphilosophie

Das Herzstuck des Skills ist kein Framework — es ist eine in Prosa formulierte Designphilosophie. Die Grundthese: Wenn ein LLM ohne explizite Intention baut, gewinnen immer die Defaults. `--gray-700` statt `--ink`. Standard-Sidebar-Breite statt einer Entscheidung. Vertraute Font-Stacks statt einer Wahl. Die Skill-Anweisung reagiert darauf mit einem Gegengewicht: Vor jeder Komponente muss Intention explizit formuliert werden. Wer ist der Mensch der dieses Interface nutzt? Was muss er tun? Wie soll es sich anfuehlen?

Die konkreten Handwerksprinzipien die daraus folgen sind gut: Subtle Layering als Rueckgrat jeder Tiefenstrategie, Border-Progressionen die gluecklich nicht haerter als noetig wahrgenommen werden, Token-Architektur die auf eine Handvoll Primitive reduziert ist, vier Textebenen statt zweier. Wer mit UI-Entwicklung vertraut ist, erkennt diese Prinzipien als solide destillierte Praxis. Vercel, Linear, Stripe werden als Vorbilder genannt — nicht als Quellen, sondern als Beispiele fuer Interfaces die genau das zeigen, wovon der Skill spricht.

<div class="callout">
<div class="callout__title">Das methodische Kernproblem</div>
Alle Prinzipien in diesem Skill lassen sich auf ihren Ursprung hin befragen — und keine einzige Antwort findet sich im Repository. Wo kommt "Subtle Layering" her? Von wem wurde die Vier-Ebenen-Texthierarchie entwickelt? Welche Studie, welches Buch, welche oeffentlich zugaengliche Methodik steht hinter der Border-Progression? Die Antwort: nirgendwo dokumentiert. Das bedeutet nicht, dass die Prinzipien falsch sind — empirisch sind sie plausibel und stimmig. Aber fuer Lernende die verstehen wollen *warum* etwas gilt und nicht nur *was*, ist dieser Skill eine Sackgasse. Er liefert gut formulierte Anweisungen, aber keine epistemische Verankerung.
</div>

Das ist kein Vorwurf an den Autor. Ein erfahrener UI-Entwickler der sein Handwerk in einer Prompt-Datei kondensiert, muss keine Dissertation schreiben. Fuer den professionellen Einsatz ist das akzeptabel. Fuer den Unterrichtseinsatz ist es eine ernst zu nehmende Luecke.

## Das Gedaechtnis — was es wirklich ist

Der Begriff "Memory" auf der Website und im README koennte zu einer Fehlinterpretation fuehren, die im Oekosystem haeufig vorkommt: die Vorstellung, das LLM selbst erinnere sich. Das ist nicht was hier passiert.

Was tatsaechlich passiert: Der Skill schreibt nach Abschluss einer Session Designentscheidungen in eine Datei auf dem Filesystem des Nutzers (`.interface-design/system.md`). Beim Start einer neuen Session laedt Claude Code diese Datei und hat damit Zugriff auf die frueheren Entscheidungen. Das LLM bleibt stateless — was sich veraendert hat, ist die externe Persistenz der Eingabe.

Das ist technisch legitim und praktisch wirksam. Und es ist im Skill selbst und im README transparent beschrieben — die Website formuliert es sogar explizit: "Saves your design decisions to `.interface-design/system.md`." Das Missverstaendnispotenzial liegt im Marketing-Begriff "Memory" und im Slogan "Claude forgets your design decisions — this plugin remembers them." Beides stimmt im Ergebnis. Aber das *wie* bleibt dem Nutzer ueberlassen zu verstehen.

Fuer Design-Studierende ist dieser Mechanismus lehrreich: Er zeigt einen praktischen Umgang mit einer echten LLM-Einschraenkung, ohne zu uebertreiben. Die Loesung ist simpel, transparent und reproduzierbar.

## Was der Skill an Selbstkritik enthält

Ungewoehnlich offen und deshalb besonders erwaehnenwert: Das SKILL.md selbst schreibt an den Nutzer Claude direkt: "You will generate generic output. Your training has seen thousands of dashboards. The patterns are strong." Und weiter: "process alone doesn't guarantee craft. You have to catch yourself."

Das ist keine typische Skill-Rhetorik. Die meisten Skills im Oekosystem positionieren sich als Loesungen. Dieser Skill kommuniziert seine Grenzen direkt in der Instruktion — nicht als Fussnote, sondern als strukturell eingeplante Selbstkritik. Der Autor weiss, dass der LLM-Raum fuer Defaults anfaellig ist, und baut das als Wissen direkt in den Prozess ein.

Die vier "Checks" am Ende des Builds (Swap-Test, Squint-Test, Signature-Test, Token-Test) sind ein Beispiel dafuer, wie Validierung als Schritt im Workflow verankert werden kann. Kein formaler Testrahmen, aber eine bewusste Unterbrechung des Automatismus.

## Scope-Klarheit als strukturelle Staerke

Die explizite Eingrenzung auf Interface-Design (nicht Marketing) ist mehr als eine Randnotiz. Sie bedeutet: Der Skill hat eine Identitaet. Er weiss was er ist und was er nicht ist. Im Unterricht laesst sich daraus eine direkte Frage ableiten: Warum brauchen unterschiedliche Design-Kontexte unterschiedliche Skills? Was macht ein Marketingdesign-Skill methodisch anders als ein Interface-Design-Skill?

Die Abgrenzung ist auch insofern ehrlich, als sie das Versagen verhindert das haeufig beim Einsatz zu breit formulierter Skills entsteht: wenn ein Skill fuer alles eingesetzt wird, versagt er bei allem ein bisschen.

## Wartbarkeit und Community

Oyindamola Akinleye ist auf LinkedIn identifizierbar, das Projekt steht unter MIT-Lizenz und hat eine eigene, gepflegte Website. Dass das Projekt von `claude-design-skill` umbenannt wurde und alte URLs automatisch weiterleiten, zeigt aktive Pflege. Mit ca. 4.600 Stars und ca. 316 Forks hat das Projekt eine reale Community.

Die berichtete Issue #13 (Skills und Commands erscheinen nach Installation nicht im Slash-Menu) ist ein konkreter Bug, der seit Maerz 2026 offen ist. Das ist ein technisches Problem das den Einsatz in bestimmten Konfigurationen beeintraechtigen kann — kein konzeptionelles Problem, aber etwas das bei der Installation beruecksichtigt werden sollte.

## Empfehlung fuer den Unterrichtseinsatz

`interface-design` eignet sich gut als Ausgangsmaterial fuer eine Unterrichtseinheit ueber die Grenzen empirischer Handwerksphilosophie. Die Kernfrage: Wann ist "funktioniert in der Praxis" ein ausreichender Qualitaetsnachweis, und wann ist theoretische Verankerung notwendig?

Konkret empfiehlt sich folgender Einsatz: Den SKILL.md lesen lassen, dann eine Aufgabe stellen — "Nennt fuer jedes Prinzip eine anerkannte Quelle, die es stuetzt." Das wird laengere Recherchearbeit erfordern. Die Prinzipien sind nicht aus der Luft gegriffen, sie finden sich in UI-Literatur, in Designsystem-Dokumentationen grosser Unternehmen, in akademischen Schriften zur visuellen Hierarchie. Nur sind sie dort eben nicht verlinkt. Diese Luecke eigenstaendig zu schliessen ist eine wertvolle Uebung.

Fuer den praktischen Einsatz: Wer Dashboards und Admin-Interfaces mit Claude Code baut, bekommt mit diesem Skill ein konsistentes, ernsthaftes Fundament. Der system.md-Mechanismus ist keine Magie — er ist eine gut durchdachte Konvention. Und die eingebettete Selbstkritik an LLM-Defaults ist einer der ehrlichsten Umgaenge mit dieser Einschraenkung im gesamten Oekosystem.

Das Urteil lautet `vorsicht` — nicht weil der Skill schlecht ist, sondern weil seine Staerken in Handwerk und Transparenz liegen, waehrend die fehlende methodische Verankerung fuer alle die *lernen* wollen eine echte Luecke hinterlaesst.
