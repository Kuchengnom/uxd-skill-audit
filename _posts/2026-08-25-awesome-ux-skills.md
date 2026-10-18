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
  methodische_fundierung_note: "Die zehn Nielsen-Heuristiken sind vollständig und in kanonischer Reihenfolge portiert. Es gibt aber keinen einzigen Quellenlink im ganzen Repository. Nielsen wird in der installierten Datei nie genannt. Die zwölf craft-Regeln haben gar keine Grundlage."
  transparenz: 3
  transparenz_note: "Einzelne Dateien markieren ihre Grenzen ausdrücklich: Dark-Pattern-Warnung bei Fogg, 'im Code verifizieren' statt Raten bei Screenshots. Kein Skill sagt aber, was er nicht leisten kann. Zwei fordern unbedingten Vorrang vor jeder Designantwort."
  validierbarkeit: 2
  validierbarkeit_note: "Kein einziges Referenz-Output, kein Before/After, kein Testfall. Die einzige im Text angekündigte Vertiefungsdatei existiert im Repository nicht. Der Installer könnte sie auch gar nicht mitkopieren."
  wartbarkeit: 3
  wartbarkeit_note: "Namentlich greifbarer, aktiver Einzelmaintainer mit eigener Domain und 18 Commits. Es gibt aber keine Lizenzdatei. Das Repository lädt zu Forks und Pull Requests ein, die es rechtlich nicht deckt."

tags:
  - nielsen-heuristiken
  - bj-fogg
  - skill-kollision
  - lizenzierung
  - claude-code
  - skill-evaluation
---

Die bisher untersuchten Sammlungen dieser Serie waren entweder klein und fokussiert oder groß und unübersichtlich. `tommyjepsen/awesome-ux-skills` liegt dazwischen. Es enthält 22 Skills. Jeder ist eine einzelne Markdown-Datei im Wurzelverzeichnis. Drei Gruppen gliedern sie: UX-Forschung und Strategie, UI-Analyse, KI-Produktdesign. Das Repository hat rund 140 Sterne, 18 Forks, 18 Commits und einen einzigen Watcher. Es ist jung und wächst spürbar.

Interessant ist es aus einem anderen Grund. Den meisten Kandidaten dieser Serie fehlt eine Methode. Dieses Projekt hat eine, sogar mehrere, und gute. Dazu zählen Nielsens zehn Usability-Heuristiken, BJ Foggs sieben Persuasive-Technology-Tools und das Double Diamond des britischen Design Council. Dazu kommen das "I like, I wish, What if" der d.school und die zehn Prinzipien von Dieter Rams. Das ist keine Namensdekoration. Es ist der etablierte Kanon der Disziplin. Ausnahmsweise lautet die Frage nicht, ob eine Methode existiert. Sie lautet, ob 22 gleichzeitig geladene Methoden ein System ergeben.

## Die Nielsen-Portierung ist besser als ihr Ruf im Ökosystem

Ich habe `ux-heuristics-review.md` vollständig gegen das Original gelesen. Alle zehn Heuristiken sind vorhanden. Sie stehen in der kanonischen Reihenfolge und tragen korrekte Namen. Es sind Sichtbarkeit des Systemstatus, Übereinstimmung zwischen System und realer Welt, Nutzerkontrolle und Freiheit sowie Konsistenz und Standards. Dazu kommen Fehlervermeidung, Wiedererkennen statt Erinnern, Flexibilität und Effizienz sowie ästhetisches und minimalistisches Design. Den Schluss bilden Fehlerdiagnose und -behebung sowie Hilfe und Dokumentation. Keine ist erfunden, keine vergessen, keine verdreht. In dieser Serie ist das die Ausnahme.

Die Datei geht über bloßes Auflisten hinaus. Sie unterscheidet einen Kritikmodus von einem Entwurfsmodus. Je nach Eingabetyp weist sie unterschiedliche Heuristiken als vorrangig zu. Eingabetypen sind Screenshot, Textbeschreibung oder beides. Nicht zutreffende Heuristiken soll der Skill ausdrücklich überspringen. Pflichtschuldig abgearbeitet werden sie nicht. Man kennt KI-generierte Heuristik-Audits. Zu allen zehn Punkten steht dort etwas Unverbindliches. Dagegen ist diese eine Anweisung viel wert.

Zwei Einschränkungen sind trotzdem zu machen. Erstens fällt bei H8 die Warnung weg, die die Nielsen Norman Group selbst für wesentlich hält. "Aesthetic and Minimalist Design" meint nicht minimalistische Ästhetik. Gemeint ist das Weglassen irrelevanter Information. Die Formulierung der Datei, „Jedes Element konkurriert um Aufmerksamkeit", ist eine korrekte Paraphrase des zweiten Satzes des Originals. Es fehlt aber der Hinweis, dass die Heuristik regelmäßig als Stilanweisung missverstanden wird. Der Skill reproduziert genau dieses Missverständnis. Zweitens wiegt schwerer, dass in der Datei selbst der Name Nielsen nirgends steht. Dort steht nur "die 10 Usability-Heuristiken". Die Zuschreibung findet ausschließlich im README statt.

Das klingt kleinlich. Es ist aber nicht kleinlich, sobald man `install.sh` liest. Das Skript kopiert jede `.md`-Datei nach `~/.claude/skills/<name>/SKILL.md`. Das README bleibt zurück. Beim Nutzer kommt die Datei ohne Herkunftsangabe an. Das Modell sieht im Kontext ebenfalls nur diese Datei. Ein Studierender, der den Skill installiert und benutzt, bekommt zehn Regeln ohne Autor, ohne Jahr und ohne Verweis auf nngroup.com. Nachschlagen kann er damit nichts. Die Quelle steht dort, wo der Anwendungsfall sie nicht erreicht.

## Ein Nebenbefund im Installer

Dasselbe Skript hat ein zweites Problem. Die Schleife lautet `for file in "${REPO_DIR}"/*.md`. Sie greift alle Markdown-Dateien im Wurzelverzeichnis ab. Dazu gehört `README.md`. Nach der Installation liegt neben den 22 Skills ein 23. Verzeichnis namens `README`. Dessen `SKILL.md` enthält die Projektübersicht. Es gibt kein YAML-Frontmatter, kein `name`, keine `description`. Ein Sicherheitsproblem ist das nicht. Wahrscheinlich bleibt es folgenlos. Es ist aber ein sauber nachprüfbares Beispiel für etwas, das Studierende lernen sollten. Ein Installationsskript, das niemand rückwärts gelesen hat, ist die häufigste Fehlerquelle in diesem gesamten Ökosystem. Zwei Zeilen mehr hätten genügt. Eine Ausnahme für README und eine Prüfung auf vorhandenes Frontmatter.

## Fogg ist korrekt zitiert und falsch sortiert

`persuasive-ux.md` nennt seine Quelle ausdrücklich. Es sind BJ Fogg, Captology und die sieben Persuasive-Technology-Tools. Die Liste stimmt. Sie lautet Reduction, Tunneling, Tailoring, Suggestion, Self-Monitoring, Surveillance, Conditioning. Die Kurzdefinitionen treffen. Am Ende warnt die Datei ausdrücklich vor Dark Patterns. Surveillance und Conditioning markiert sie als besonders kippgefährdet. Ein Skill liefert hier Persuasionstechniken aus. Im selben Atemzug benennt er ihre Missbrauchsnähe. Das tut mehr, als die meisten Anbieter in diesem Feld für nötig halten.

Genau deshalb lohnt der Blick auf den Absatz darunter. Dort steht, die sieben Werkzeuge erhöhten entweder die Ability oder schärften den Prompt. Zur Ability zählt die Datei Reduction, Tunneling und Self-Monitoring. Den Prompt schärfen demnach Suggestion, Tailoring, Conditioning und Surveillance. Diese Zuordnung stammt nicht von Fogg. Sie stammt vom Autor und ist in zwei Punkten schief. Conditioning ist positive Verstärkung durch Belohnung. Es wirkt auf die Motivation und nicht auf den Auslöser. Surveillance ist soziale Sichtbarkeit gegenüber Peers. Auch sie wirkt auf die Motivation. Im Fogg-Modell ist Motivation die dritte Variable. Hier bleibt sie vollständig unbesetzt. Dazu kommt ein zweiter Bruch. Die sieben Tools stammen aus *Persuasive Technology* von 2003. B=MAP ist die spätere Formulierung des Fogg-Behavior-Modells. Zwei Werke, zwei Denkrahmen, ohne Zwischenschritt zusammengeschoben.

Für den Unterricht ist das ein besseres Beispiel als jede grobe Falschangabe. Die Quelle ist richtig benannt. Die Begriffe sind richtig geschrieben. Trotzdem ist die Aussage falsch. Nachprüfbar ist das nur, wenn man das Original kennt. Darum ist „die Quelle steht ja dran" kein Qualitätsnachweis.

<div class="callout">
<div class="callout__title">Zwei Skills, ein Auslöser, kein Schiedsrichter</div>
Bei Claude Code entscheidet das <code>description</code>-Feld darüber, wann ein Skill automatisch anspringt. Das README sagt das selbst: "The <code>description</code> field drives automatic activation". Nun steht in <code>ux-heuristics-review.md</code>: "Always apply this skill before giving any UX or product design recommendations — even if the request seems simple". Und in <code>persuasive-ux.md</code>: "Always use this skill before giving UX improvement advice — even if the user doesn't explicitly mention persuasion, Fogg, or Captology". Beide Beschreibungen listen dieselben Auslöser auf. Es sind ein geteilter Screenshot, ein Mockup und die Bitte "improve this UI". Zwei Skills beanspruchen also unbedingten Vorrang im selben Auslöseraum. Nichts im Repository regelt, wer gewinnt. Das ist keine Redundanz. Es ist ein Zielkonflikt. Der eine Skill prüft gegen Nutzbarkeitskriterien. Der andere optimiert auf Verhaltensbeeinflussung. Wer <code>dieter-rams-principles</code> mit seinem Maßstab der Ehrlichkeit dazunimmt, hat drei Bewertungslogiken auf einem Prompt. Zwei davon können einander direkt widersprechen. Sichtbar wird das nirgends. Der Nutzer sieht nur eine Antwort. Welcher Rahmen sie erzeugt hat, erfährt er nicht. Für Studierende ist das die zentrale Lektion dieses Repositories. Bei Skill-Sammlungen ist nicht die Qualität der Einzelteile die schwierige Frage. Schwierig ist die Konfliktregel zwischen ihnen. Wo keine steht, entscheidet der Zufall der Aktivierungsreihenfolge. Die Antwort sieht in jedem Fall gleich souverän aus.
</div>

## Zwölf Regeln ohne Herkunft

`craft.md` ist die konkreteste Datei der Sammlung. Sie ist auch die am schwächsten begründete. Sie enthält zwölf Regeln auf CSS-Ebene. Dazu zählen keine Verläufe, kein Glow, kein `transition: all` und kein Blindtext. `isolation: isolate` ersetzt das z-index-Wettrüsten. Reines Schwarz auf reinem Weiß ist verboten. Abstände stammen nur aus einer Skala. Die Zeilenhöhe liegt zwischen 1,1 und 1,2 für Display und bei 1,5 bis 1,6 für Fließtext. Die Zeilenlänge beträgt 65 bis 75 Zeichen. Bewegung dauert zwischen 120 und 250 Millisekunden.

Ein Teil davon ist fachlich unstrittig und stammt erkennbar aus geltenden Konventionen. Die Zeilenlänge kommt aus der Typografie. Die Abstandsregel kommt aus dem Gestaltgesetz der Nähe. `focus-visible` und `prefers-reduced-motion` kommen aus den Barrierefreiheitsanforderungen. Ein anderer Teil ist Geschmack im Gewand einer Norm. "Keine Verläufe" ist keine Regel. Es ist eine Position. Sie ist gut begründbar. Sie beißt sich aber mit Material 3, mit jeder Marke, deren Identität auf einem Verlauf beruht, und mit dem Nachbarskill `design-analysis`. Dieser liest laut README Paletten realer Websites aus und gibt sie als Token aus. Quellen nennt die Datei keine. Das erklärte Ziel, Oberflächen sollen „less AI-generated" wirken, ist ein Modekriterium mit Verfallsdatum. Einen Qualitätsmaßstab ergibt es nicht.

Positiv hervorzuheben ist eine Anweisung, die in diesem Ökosystem selten ist. Liegt nur ein Screenshot vor, sollen codebezogene Regeln als "im Code zu verifizieren" markiert statt geraten werden. Das ist eine ausdrückliche Grenzmarkierung gegenüber dem eigenen Verfahren. Sie ist der Grund, warum die Transparenzdimension hier nicht schlechter ausfällt.

## Was fehlt: Belege und eine Lizenz

Zwei Lücken bleiben. Die erste betrifft die Nachprüfbarkeit. Es gibt in diesem Repository kein einziges Beispiel-Output, keinen Before/After-Vergleich und keinen Testfall. Nichts lässt sich daran prüfen, ob ein Skill leistet, was er ankündigt. Die Ausgabeformate sind zwar streng spezifiziert. Sie verlangen ein Ein-Zeilen-Verdikt, Stichpunkte statt Absätzen und maximal drei Priority Actions. Das macht die Form reproduzierbar. Über die Güte des Inhalts sagt es nichts. Verschärfend kommt hinzu, dass `persuasive-ux.md` zweimal auf `references/tools.md` als Vertiefungsquelle verweist. Diese Datei existiert im Repository nicht. Selbst wenn es sie gäbe, würde `install.sh` sie nicht mitkopieren. Das Skript sammelt ausschließlich `*.md` im Wurzelverzeichnis. Unterordner sind ihm unbekannt. Der Verweis ist also nicht bloß offen. Er ist konstruktionsbedingt tot. Ein Modell, das dieser Anweisung folgt, sucht eine Datei, die es nie geben wird.

Die zweite Lücke ist rechtlich. Das Repository enthält keine Lizenzdatei. In der GitHub-Seitenleiste steht unter "Resources" nur "Readme". Ohne Lizenz gilt der Vorbehalt aller Rechte. Damit steht das README-Angebot „PRs welcome" auf ungesichertem Grund. Das gilt ebenso für den gesamten beworbenen Arbeitsablauf aus Klonen, Kopieren und Anpassen. Der Autor ist namentlich greifbar und betreibt eine eigene Domain. Er hat das Projekt in wenigen Monaten sichtbar weiterentwickelt. An der Person liegt es also nicht. Es fehlt schlicht die Datei, die aus einem öffentlichen Repository ein benutzbares macht. Eine Hochschule gibt Material in Lehrveranstaltungen weiter. Für sie ist das kein Randdetail.

## Empfehlung für den Unterrichtseinsatz

Diese Sammlung eignet sich gut als Lesestoff. Als Werkzeug eignet sie sich nur eingeschränkt. Wer sie einsetzen will, sollte selektiv installieren und `install.sh` nicht laufen lassen. `ux-heuristics-review` und `craft` sind einzeln brauchbar. `persuasive-ux` gehört in der Lehre nur mit der korrigierten Fogg-Zuordnung daneben. Mehr als drei bis vier Skills gleichzeitig sind zu viel. Welcher Rahmen eine Antwort erzeugt hat, ist dann praktisch unbeantwortbar.

Als Unterrichtsgegenstand ist der Wert höher. Drei Übungen bieten sich an. Erstens stellen Studierende die zehn Heuristiken der Datei gegen die Originalformulierungen der Nielsen Norman Group und begründen die Abweichung bei H8. Das dauert eine gute halbe Stunde. Der Unterschied zwischen Paraphrase und Verkürzung wird an einem einzigen Absatz greifbar. Zweitens korrigieren sie die Fogg-Zuordnung selbst. Dabei erklären sie, warum eine richtig benannte Quelle eine falsche Aussage nicht verhindert. Drittens legen sie beide `description`-Felder nebeneinander, markieren die überlappenden Auslöser und formulieren eine Konfliktregel, die im Repository fehlt. Diese Übung ist am ergiebigsten. Wer sie einmal gemacht hat, liest jede weitere Skill-Sammlung anders. Er sieht ein System mit Aktivierungslogik und keine Liste guter Absichten.
