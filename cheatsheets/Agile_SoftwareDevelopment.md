# Agiles Projektmanagement / Agile Softwareentwicklung

## Agiles Manifest

1. Individuen und Interaktionen sind wichtiger als Prozesse und Werkzeuge.
2. Funktionierende Software ist wichtiger als umfassende Dokumentation.
3. Zusammenarbeit mit dem Kunden ist wichtiger als Vertragsverhandlungen.
4. Reagieren auf Veränderung ist wichtiger als das Befolgen eines Plans.

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

### Scrum-Werte:
* Selbstverpflichtung bzw. Commitment
* Mut
* Offenheit
* Fokus
* Respekt

### Rollen
* ProductOwner
* Scrum-Master
* Developer

### Ereignisse
* Sprint-Planning
* Daily Review
* Sprint Review
* Sprint Retrospektive

## Kanban
Kanban ist eine einfache, agile "Best Practice"-Methode, die darauf abzielt, einen kontinuierlichen Workflow
zu schaffen - und einen dauerhaften Mehrwert für den Kunden. Ziel ist es, jeden Softwareentwicklungsprozess
zu visualisieren und zu verbessern. Das Endergebnis ist eine Entwicklungspipeline, die zuverlässig und effizient hochwertige Arbeit leistet.

### 3 Grundprinzipien
* Workflow-Abbildung
    * Backlog -> Ready -> Coding -> Testing -> Approval -> Done
* WIP begrenzen
* Vorlaufzeit messen

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