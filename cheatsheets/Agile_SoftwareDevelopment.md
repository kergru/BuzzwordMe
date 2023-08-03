# Agiles Projektmanagement / Agile Softwareentwicklung

Agile software development teams today are able to leverage these same JIT principles by matching the amount of work in progress (WIP) to the team's capacity. This gives teams more flexible planning options, faster output, clearer focus, and transparency throughout the development cycle.

## Agiles Manifest

1. Individuen und Interaktionen sind wichtiger als Prozesse und Werkzeuge. (individuals and interactions over processes and tools)
2. Funktionierende Software ist wichtiger als umfassende Dokumentation. (working software over comprehensive documentation)
3. Zusammenarbeit mit dem Kunden ist wichtiger als Vertragsverhandlungen. (customer collaboration over contract negotiations)
4. Reagieren auf Veränderung ist wichtiger als das Befolgen eines Plans. (responding to change over following a plan)

### Prinzipien hinter dem Agilen Manifest
1. Our highest priority is to satisfy the customer through early and continuous delivery of valuable software.
2. Welcome changing requirements, even late in development. Agile processes harness change for the customer's competitive advantage.
3. Deliver working software frequently, from a couple of weeks to a couple of months, with a preference to the shorter timescale.
4. Business people and developers must work together daily throughout the project.
5. Build projects around motivated individuals. Give them the environment and support they need, and trust them to get the job done.
6. The most efficient and effective method of conveying information to and within a development team is face-to-face conversation.
7. Working software is the primary measure of progress.
8. Agile processes promote sustainable development. The sponsors, developers, and users should be able to maintain a constant pace indefinitely.
9. Continuous attention to technical excellence and good design enhances agility.
10. Simplicity--the art of maximizing the amount of work not done--is essential.
11. The best architectures, requirements, and designs emerge from self-organizing teams.
12. At regular intervals, the team reflects on how to become more effective, then tunes and adjusts its behavior accordingly.


## Scrum
is an agile project management framework that helps teams structure and manage their work through a set of values, principles, and practices. 
Scrum encourages teams to learn through experiences, self-organize while working on a problem, and reflect on their wins and losses to continuously improve.

### Scrum-Werte:
* Selbstverpflichtung (Commitment)
* Mut (Courage)
* Offenheit (Openness)
* Fokus (Focus)
* Respekt (Respect)

### Rollen
* ProductOwner (owns ProductBacklog)
* Scrum-Master
* Developer (owns SprintBacklog)

### Ereignisse
* Sprint-Planning
* Daily Review
* Sprint Review
* Sprint Retrospektive

also:
* Grooming 
* Refinement
* Definition of Ready, check with INVEST
  * I: Indepedent
  * N: Negotioable (verhandelbar was ihre Implementierung anbelangt)
  * V: Valueable
  * E: Estimable
  * S: Small
  * T: Testable

## Kanban
Kanban ist eine einfache, agile "Best Practice"-Methode, die darauf abzielt, einen kontinuierlichen Workflow
zu schaffen - und einen dauerhaften Mehrwert für den Kunden. Ziel ist es, jeden Softwareentwicklungsprozess
zu visualisieren und zu verbessern. Das Endergebnis ist eine Entwicklungspipeline, die zuverlässig und effizient hochwertige Arbeit leistet.

### 3 Grundprinzipien
* Workflow-Abbildung> Testing -> Approval -> Done
* WIP begrenzen
* Vorlaufzeit messen
  * Backlog -> Ready -> Coding -


## SAFe - Scaled Agile Framework

Die Scaled-Agile-Framework-Prinizpien

SAFe ist um neun Schlüssel-Prinzipien herum aufgebaut, die auf bereits existierenden Lean-Management- und Agile-Methoden basieren:

1. Eine ökonomische Perspektive für eine optimale Lead-Zeit einnehmen und dabei die beste Qualität und den größten Mehrwert liefern;
2. Alle Facetten der Softwareentwicklung bei der Implementierung von Systemen mit einbeziehen;
3. Flexible Wahlmöglichkeiten bewahren und innovative Ideen fördern;
4. Schrittweise entwickeln mit schnellen, integrierten Lernzyklen, die Kundenfeedback zulassen und Risiken reduzieren;
5. Meilensteine setzen und funktionierende Systeme evaluieren, um einen wirtschaftlichen Benefit sicherzustellen;
6. "Work in Progress" soweit wie möglich reduzieren, Batch-Größen reduzieren und Warteschlangen managen, um einen fortlaufenden Workflow zu garantieren;
7. Bereichsübergreifende Synchronisation, um neue Geschäftsmöglichkeiten zu erkennen und notwendige Korrekturen bei Bedarf umsetzen zu können;
8. Wissensarbeiter mit intrinsischer Motivation ausstatten, um ihr volles Potenzial zu erschließen;
9. Dezentralisierung der Entscheidungsfindung für mehr Agilität und Effektivität;


## Techniken der agilen Softwareentwicklung

### TDD - Test Driven Development
(Kent Beck)

Bei der testgetriebenen Entwicklung erstellt der Programmierer Softwaretests konsequent vor den zu testenden Komponenten.

Programmierung erfolgt in kleinen, wiederholten Mikroiterationen:
1. Red: Schreibe einen Test für eine neue Funktion, Test schlägt zunächst fehl
2. Green: Anpassung des Programmcodes mit möglichst wenig Aufwand, bis der Testdurchlauf den Test besteht
3. Refactoring

### BDD - Behavior Driven Development
(Dan North)
Technik der agilen Softwareentwicklung

Beim Behavior Driven Development werden während der Anforderungsanalyse die Aufgaben, Ziele und Ergebnisse der Software in einer bestimmten Textform festgehalten, die später als automatisierte Tests ausgeführt werden kann. Damit kann die Software auf ihre korrekte Implementierung getestet werden
Die Softwareanforderungen werden dabei meist in „Wenn-dann“-Sätzen basierend auf der Sprache des Domain-driven Designs verfasst.
Damit soll der Übergang zwischen der Sprache der Definition der fachlichen Anforderungen und der Programmiersprache, mittels derer die Anforderungen umgesetzt werden, erleichtert werden.

Frameworks: JBehave, JGiven
