---
layout: post
title: "awesome-ux-skills: 22 Frameworks, von denen zwei gleichzeitig Vorfahrt beanspruchen"
date: 2026-08-25
category: Skill-Evaluation
skill_reviewed: "tommyjepsen/awesome-ux-skills"
verdict: vorsicht
reading_time: 9
last_audited: "25. August 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "Die zehn Nielsen-Heuristiken sind vollständig und in kanonischer Reihenfolge portiert, aber es gibt keinen einzigen Quellenlink im ganzen Repository, Nielsen wird in der installierten Datei nie genannt, und die zwölf craft-Regeln haben gar keine Grundlage."
  transparenz: 3
  transparenz_note: "Einzelne Dateien markieren ihre Grenzen ausdrücklich — Dark-Pattern-Warnung bei Fogg, 'im Code verifizieren' statt Raten bei Screenshots — aber kein Skill sagt, was er nicht leisten kann, und zwei fordern unbedingten Vorrang vor jeder Designantwort."
  validierbarkeit: 2
  validierbarkeit_note: "Kein einziges Referenz-Output, kein Before/After, kein Testfall — und die einzige im Text angekündigte Vertiefungsdatei existiert im Repository nicht und könnte vom Installer auch gar nicht mitkopiert werden."
  wartbarkeit: 3
  wartbarkeit_note: "Namentlich greifbarer, aktiver Einzelmaintainer mit eigener Domain und 18 Commits, aber keine Lizenzdatei — das Repository lädt zu Forks und Pull Requests ein, die es rechtlich nicht deckt."

tags:
  - nielsen-heuristiken
  - bj-fogg
  - skill-kollision
  - lizenzierung
  - claude-code
  - skill-evaluation
---

Die bisher in dieser Serie untersuchten Sammlungen waren entweder klein und fokussiert oder groß und unübersichtlich. `tommyjepsen/awesome-ux-skills` liegt dazwischen: 22 Skills, jeder eine einzelne Markdown-Datei im Wurzelverzeichnis, verteilt auf drei Gruppen — UX-Forschung und Strategie, UI-Analyse, KI-Produktdesign. Rund 140 Sterne, 18 Forks, 18 Commits, ein einziger Watcher. Das Projekt ist jung und wächst spürbar.

Interessant ist es aus einem anderen Grund. Die meisten Kandidaten dieser Serie scheitern daran, dass sie keine Methode haben. Dieses Projekt hat eine — sogar mehrere, und gute: Nielsens zehn Usability-Heuristiken, BJ Foggs sieben Persuasive-Technology-Tools, das Double Diamond des britischen Design Council, das "I like, I wish, What if" der d.school, die zehn Prinzipien von Dieter Rams. Das ist keine Namensdekoration, sondern der etablierte Kanon der Disziplin. Die Frage lautet hier also ausnahmsweise nicht, ob eine Methode existiert, sondern ob 22 gleichzeitig geladene Methoden ein System ergeben.

## Die Nielsen-Portierung ist besser als ihr Ruf im Ökosystem

Ich habe `ux-heuristics-review.md` vollständig gegen das Original gelesen. Alle zehn Heuristiken sind vorhanden, in der kanonischen Reihenfolge, mit korrekten Namen: Sichtbarkeit des Systemstatus, Übereinstimmung zwischen System und realer Welt, Nutzerkontrolle und Freiheit, Konsistenz und Standards, Fehlervermeidung, Wiedererkennen statt Erinnern, Flexibilität und Effizienz, ästhetisches und minimalistisches Design, Fehlerdiagnose und -behebung, Hilfe und Dokumentation. Keine erfunden, keine vergessen, keine verdreht. In dieser Serie ist das die Ausnahme, nicht die Regel.

Die Datei geht sogar über bloßes Auflisten hinaus. Sie unterscheidet einen Kritikmodus von einem Entwurfsmodus, weist je nach Eingabetyp — Screenshot, Textbeschreibung, beides — unterschiedliche Heuristiken als vorrangig zu, und verlangt ausdrücklich, nicht zutreffende Heuristiken zu überspringen statt sie pflichtschuldig abzuarbeiten. Wer schon einmal einen KI-generierten Heuristik-Audit gelesen hat, in dem zu allen zehn Punkten etwas Unverbindliches steht, weiß, wie viel diese eine Anweisung wert ist.

Zwei Einschränkungen sind trotzdem zu machen. Erstens fällt bei H8 die Warnung weg, die die Nielsen Norman Group selbst für wesentlich hält: "Aesthetic and Minimalist Design" meint nicht minimalistische Ästhetik, sondern das Weglassen irrelevanter Information. Die Formulierung der Datei ("Jedes Element konkurriert um Aufmerksamkeit") ist eine korrekte Paraphrase des zweiten Satzes des Originals — aber ohne den Hinweis, dass die Heuristik regelmäßig als Stilanweisung missverstanden wird, reproduziert der Skill genau dieses Missverständnis. Zweitens, und gravierender: In der Datei selbst steht der Name Nielsen nirgends. Nur "die 10 Usability-Heuristiken". Die Zuschreibung findet ausschließlich im README statt.

Das klingt kleinlich, ist es aber nicht, sobald man `install.sh` liest. Das Skript kopiert jede `.md`-Datei nach `~/.claude/skills/<name>/SKILL.md`. Das README bleibt zurück. Was beim Nutzer ankommt und was das Modell im Kontext sieht, ist die Datei ohne Herkunftsangabe. Ein Studierender, der den Skill installiert und benutzt, bekommt zehn Regeln ohne Autor, ohne Jahr, ohne Verweis auf nngroup.com — und damit nichts, was er nachschlagen könnte. Die Quellenangabe existiert an der einen Stelle, an der sie den Anwendungsfall nicht erreicht.

## Ein Nebenbefund im Installer

Dasselbe Skript hat ein zweites Problem. Die Schleife lautet `for file in "${REPO_DIR}"/*.md` — sie greift also alle Markdown-Dateien im Wurzelverzeichnis ab, und dazu gehört `README.md`. Nach der Installation liegt neben den 22 Skills ein 23. Verzeichnis namens `README`, dessen `SKILL.md` die Projektübersicht enthält: kein YAML-Frontmatter, kein `name`, keine `description`. Das ist kein Sicherheitsproblem und wahrscheinlich folgenlos, aber es ist ein sauber nachprüfbares Beispiel für etwas, das Studierende lernen sollten: Ein Installationsskript, das niemand rückwärts gelesen hat, ist die häufigste Fehlerquelle in diesem gesamten Ökosystem. Zwei Zeilen mehr — eine Ausnahme für README, eine Prüfung auf vorhandenes Frontmatter — hätten genügt.

## Fogg ist korrekt zitiert und falsch sortiert

`persuasive-ux.md` nennt seine Quelle ausdrücklich: BJ Fogg, Captology, die sieben Persuasive-Technology-Tools. Die Liste stimmt — Reduction, Tunneling, Tailoring, Suggestion, Self-Monitoring, Surveillance, Conditioning — und die Kurzdefinitionen treffen. Bemerkenswert ist, dass die Datei am Ende ausdrücklich vor Dark Patterns warnt und Surveillance und Conditioning als besonders kippgefährdet markiert. Ein Skill, der Persuasionstechniken ausliefert und im selben Atemzug ihre Missbrauchsnähe benennt, tut mehr, als die meisten Anbieter in diesem Feld für nötig halten.

Genau deshalb lohnt sich der genaue Blick auf den Absatz darunter. Dort steht, die sieben Werkzeuge erhöhten entweder die Ability (Reduction, Tunneling, Self-Monitoring) oder schärften den Prompt (Suggestion, Tailoring, Conditioning, Surveillance). Diese Zuordnung stammt nicht von Fogg, sondern vom Autor — und sie ist in zwei Punkten schief. Conditioning, also positive Verstärkung durch Belohnung, wirkt auf die Motivation, nicht auf den Auslöser. Surveillance, die soziale Sichtbarkeit gegenüber Peers, ebenfalls. Beides sind Motivationshebel, und im Fogg-Modell ist Motivation die dritte, hier vollständig unbesetzte Variable. Dazu kommt, dass die sieben Tools aus *Persuasive Technology* (2003) stammen, während B=MAP die spätere Formulierung des Fogg-Behavior-Modells ist. Zwei Werke, zwei Denkrahmen, ohne Zwischenschritt zusammengeschoben.

Für den Unterricht ist das ein besseres Beispiel als jede grobe Falschangabe: Die Quelle ist richtig benannt, die Begriffe sind richtig geschrieben, und trotzdem ist die Aussage falsch. Nachprüfbar ist das nur, wenn man das Original kennt — und genau das ist der Grund, warum "die Quelle steht ja dran" kein Qualitätsnachweis ist.

<div class="callout">
<div class="callout__title">Zwei Skills, ein Auslöser, kein Schiedsrichter</div>
Bei Claude Code entscheidet das <code>description</code>-Feld darüber, wann ein Skill automatisch anspringt. Das README sagt das selbst: "The <code>description</code> field drives automatic activation." Nun steht in <code>ux-heuristics-review.md</code>: "Always apply this skill before giving any UX or product design recommendations — even if the request seems simple." Und in <code>persuasive-ux.md</code>: "Always use this skill before giving UX improvement advice — even if the user doesn't explicitly mention persuasion, Fogg, or Captology." Beide Beschreibungen listen dieselben Auslöser auf: ein geteilter Screenshot, ein Mockup, die Bitte "improve this UI". Zwei Skills beanspruchen also unbedingten Vorrang im selben Auslöseraum, und nichts im Repository regelt, wer gewinnt. Das ist keine Redundanz, sondern ein Zielkonflikt: Der eine Skill prüft gegen Nutzbarkeitskriterien, der andere optimiert auf Verhaltensbeeinflussung. Wer <code>dieter-rams-principles</code> mit seinem Maßstab der Ehrlichkeit dazunimmt, hat drei Bewertungslogiken auf einem Prompt, von denen zwei einander direkt widersprechen können. Sichtbar wird das nirgends — der Nutzer sieht nur eine Antwort und erfährt nicht, welcher Rahmen sie erzeugt hat. Für Studierende ist das die zentrale Lektion dieses Repositories: Bei Skill-Sammlungen ist nicht die Qualität der Einzelteile die schwierige Frage, sondern die Konfliktregel zwischen ihnen. Wo keine steht, entscheidet der Zufall der Aktivierungsreihenfolge — und die Antwort sieht in jedem Fall gleich souverän aus.
</div>

## Zwölf Regeln ohne Herkunft

`craft.md` ist die konkreteste Datei der Sammlung und die am schwächsten begründete. Zwölf Regeln auf CSS-Ebene: keine Verläufe, kein Glow, kein `transition: all`, kein Blindtext, `isolation: isolate` statt z-index-Wettrüsten, kein reines Schwarz auf reinem Weiß, Abstände nur aus einer Skala, Zeilenhöhe zwischen 1,1 und 1,2 für Display und 1,5 bis 1,6 für Fließtext, Zeilenlänge 65 bis 75 Zeichen, Bewegung zwischen 120 und 250 Millisekunden.

Ein Teil davon ist fachlich unstrittig und stammt erkennbar aus geltenden Konventionen: die Zeilenlänge aus der Typografie, die Abstandsregel aus dem Gestaltgesetz der Nähe, `focus-visible` und `prefers-reduced-motion` aus den Barrierefreiheitsanforderungen. Ein anderer Teil ist Geschmack im Gewand einer Norm. "Keine Verläufe" ist keine Regel, sondern eine Position — eine gut begründbare, aber eine, die sich mit Material 3, mit jeder Marke, deren Identität auf einem Verlauf beruht, und mit dem Nachbarskill `design-analysis` beißt, der laut README Paletten realer Websites ausliest und als Token ausgibt. Quellen nennt die Datei keine, und das erklärte Ziel — Oberflächen sollen "less AI-generated" wirken — ist ein Modekriterium mit Verfallsdatum, kein Qualitätsmaßstab.

Positiv hervorzuheben ist eine Anweisung, die in diesem Ökosystem selten ist: Wenn nur ein Screenshot vorliegt, sollen codebezogene Regeln als "im Code zu verifizieren" markiert statt geraten werden. Das ist eine ausdrückliche Grenzmarkierung gegenüber dem eigenen Verfahren, und sie ist der Grund, warum die Transparenzdimension hier nicht schlechter ausfällt.

## Was fehlt: Belege und eine Lizenz

Zwei Lücken bleiben. Die erste betrifft die Nachprüfbarkeit. Es gibt in diesem Repository kein einziges Beispiel-Output, keinen Before/After-Vergleich, keinen Testfall — nichts, woran sich prüfen ließe, ob ein Skill leistet, was er ankündigt. Die Ausgabeformate sind zwar streng spezifiziert (Ein-Zeilen-Verdikt, Stichpunkte statt Absätze, maximal drei Priority Actions), was die Form reproduzierbar macht; über die Güte des Inhalts sagt das nichts. Verschärfend kommt hinzu, dass `persuasive-ux.md` zweimal auf `references/tools.md` als Vertiefungsquelle verweist — eine Datei, die im Repository nicht existiert. Und selbst wenn es sie gäbe, würde `install.sh` sie nicht mitkopieren: Das Skript sammelt ausschließlich `*.md` im Wurzelverzeichnis, Unterordner sind ihm unbekannt. Der Verweis ist also nicht bloß offen, er ist konstruktionsbedingt tot. Ein Modell, das dieser Anweisung folgt, sucht eine Datei, die es nie geben wird.

Die zweite Lücke ist rechtlich. Das Repository enthält keine Lizenzdatei. In der GitHub-Seitenleiste steht unter "Resources" nur "Readme". Ohne Lizenz gilt der Vorbehalt aller Rechte — und damit steht das README-Angebot "PRs welcome" ebenso auf ungesichertem Grund wie der gesamte beworbene Arbeitsablauf aus Klonen, Kopieren und Anpassen. Der Autor ist namentlich greifbar, betreibt eine eigene Domain und hat das Projekt in wenigen Monaten sichtbar weiterentwickelt; an der Person liegt es also nicht. Es fehlt schlicht die Datei, die aus einem öffentlichen Repository ein benutzbares macht. Für eine Hochschule, die Material in Lehrveranstaltungen weitergibt, ist das kein Randdetail.

## Empfehlung für den Unterrichtseinsatz

Diese Sammlung eignet sich gut als Lesestoff und nur eingeschränkt als Werkzeug. Wer sie einsetzen will, sollte selektiv installieren statt `install.sh` laufen zu lassen: `ux-heuristics-review` und `craft` sind einzeln brauchbar, `persuasive-ux` gehört in der Lehre nur mit der korrigierten Fogg-Zuordnung daneben, und mehr als drei bis vier Skills gleichzeitig machen die Frage, welcher Rahmen eine Antwort erzeugt hat, praktisch unbeantwortbar.

Als Unterrichtsgegenstand ist der Wert höher. Drei Übungen bieten sich an. Erstens: Die zehn Heuristiken der Datei gegen die Originalformulierungen der Nielsen Norman Group stellen und die Abweichung bei H8 begründen — eine gute halbe Stunde, und der Unterschied zwischen Paraphrase und Verkürzung wird an einem einzigen Absatz greifbar. Zweitens: Die Fogg-Zuordnung selbst korrigieren und dabei erklären, warum eine richtig benannte Quelle eine falsche Aussage nicht verhindert. Drittens, und am ergiebigsten: Beide `description`-Felder nebeneinanderlegen, die überlappenden Auslöser markieren und eine Konfliktregel formulieren, die im Repository fehlt. Wer das einmal gemacht hat, liest jede weitere Skill-Sammlung anders — nämlich als System mit Aktivierungslogik und nicht als Liste guter Absichten.
