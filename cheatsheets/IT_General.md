# REST - Represential State Transfer 
(Roy Fielding)

Paradigma für die Softwarearchitektur von verteilten Systemen
REST ist eine Abstraktion der Struktur und des Verhaltens des World Wide Web.
Eine Ressource kann dabei über verschiedene Medientypen dargestellt werden, auch Repräsentation der Ressource genannt.
Anders als bei vielen verwandten Architekturen kodiert REST keine Methodeninformation in den URI, da der URI Ort und Namen der Ressource angibt
Die Bezeichnung „Representational State Transfer“ soll den Übergang vom aktuellen Zustand zum nächsten Zustand (state) einer Applikation verbildlichen. Dieser Zustandsübergang erfolgt durch den Transfer der Daten, die den nächsten Zustand repräsentieren.

## Prinzipien

* Client Server Architekur: Server einen Dienst bereit, der bei Bedarf vom Client angefragt werden kann
* Zustandslosigkeit: Jede REST-Nachricht enthält alle Informationen, die für den Server bzw. Client notwendig sind, um die Nachricht zu verstehen. Weder der Server noch die Anwendung soll Zustandsinformationen zwischen zwei Nachrichten speichern
* Caching
* Einheitliche Schnittstelle
  * Adressierbarkeit von Ressourcen
  * Repräsentationen zur Veränderung von Ressourcen
  * Selbstbeschreibende Nachrichten
  * HATEOAS - Hypermedia as the Engine of Application State: Entwurfsprinzip von REST-Architekturen. Bei HATEOAS navigiert der Client einer REST-Schnittstelle ausschließlich über URLs, die vom Server bereitgestellt werden.

## Umsetzung
Für die Umsetzung des REST-Paradigmas wird ein zustandsloses Client-Server-Protokoll verwendet. Als Anwendungsschicht-Protokolle werden hauptsächlich HTTP und HTTPS eingesetzt.
Wird über HTTP zugegriffen, so gibt die verwendete HTTP-Methode, darunter GET, POST, PUT und DELETE, an, welche Operation des Dienstes gewünscht ist. 


# SOAP - Simple Object Access Protocol

SOAP API ermöglicht es Anwendungen, Nachrichten zu übermitteln, auch wenn sie in verschiedenen Programmiersprachen geschrieben sind. Es handelt sich um ein Protokoll mit mehr Komplexität in Bezug auf Sicherheit und Datenkommunikation. Da es sich bei diesem Protokoll um Nachrichten handelt, liegt das Hauptaugenmerk auf dem Schutz vor unbefugtem Zugriff durch die Sicherheit von WS.
* SOAP Nachrichten im Standard-XML-Format

## WSDL - Web Services Description Language
WSDL ist eine XML-Notation für die Beschreibung von Web-Services. WSDL-Definitionen informieren einen Client über den Aufbau einer Web-Service-Anforderung und beschreiben die Schnittstelle, die vom Web-Service-Provider bereitgestellt wird.
Bestandteile:
* types: Definition der Datentypen
* bindings: Bestimmt das konkrete Protokoll und Datenformat
* port: Eine Menge von abstrakten Operationen (one-way, request-response,..)
* message


# Microservices

* Software Development Technik, die eine Applikation als eine Sammlung von lose gekoppelten Servicen arrangiert
* Variante von SOA (Service oriented architectecture)
* die Services sind feingranular und über leichtgewichtige Protokolle verbunden (Http/REST, AMQP)
* die Services sind unabhängig voneinander entwickelbar und deploybar und um Business-Anforderungen herum gruppiert
* die Services sind selfcontained, bringen alles mit was sie für ihren Betrieb benötigen

Fowler: do one thin and do it well

Vorteile:
* Modularität
* Skalierbarkeit
* Integration
* Verteilte, parallelisierbare Entwicklung

# Clean Code
(Robert C. Martin, Uncle Bob)

## Common rules:
* **KISS**: keep it simple stupid
* **DRY**: don't repeat yourself
* **YAGNI**: you aint gonna need it
* Favor readability
* **Boyscout** rule
* Follow standard conventions
* **Demeter's law** (Reduzierung Abhängigkeiten)
* AAA (Triple A)
  * arrange (given)
  * act   (when)
  * assert (then)
* FIRST - Testing Principle
  * Fast
  * Independent
  * Repeatable
  * Self-validating
  * Thorough (gründlich, sorgfältig)

## Design rules
* Keep configurable data at high levels.
* Separate multi-threading code.
* Use dependency injection.
* Prevent over-configurability.

## Understandibility
* Be consistent.
* Use explanatory variables.
* Encapsulate boundary conditions.
* Prefer dedicated value objects to primitive type.
* Avoid logical dependency. Don't write methods which works correctly depending on something else in the same class.
* Avoid negative conditionals.

## Name rules
* Choose descriptive and unambiguous names.
* Make meaningful distinction.
* Use pronounceable names.
* Use searchable names.
* Replace magic numbers with named constants.

## Function rules
* Small
* Do one thing
* Use descriptive names
* Prefer fewer arguments.
* Have no side effects.
* Don't use flag arguments. Split method into several independent methods that can be called from the client without the flag.

## Comment rules
* Always try to explain yourself in code.
* Don't be redundant.
* Don't comment out code. Just remove.
* Use as explanation of intent.
* Use as clarification of code.

## Source code structure
* Separate concepts vertically.
* Related code should appear vertically dense.
* Keep lines short.
* Don't break indentation.

## Object and data structures
* Hide internal structure.
* Should be small.
* Do one thing
* Small number of instance variables.
* Base class should know nothing about their derivatives.

## Tests
* One assert per test.
* Readable
* Fast
* Independent
* Repeatable


# Reactive Manifest
  >"Wir glauben, dass die Anforderungen, die heute an Computersysteme gestellt werden, nur zu erfüllen sind durch die gleichzeitige Ausrichtung an vier Qualitäten, deren Wert bislang nur einzeln betrachtet wurde: Systeme müssen stets antwortbereit, widerstandsfähig, elastisch und nachrichtenorientiert sein. Dann nennen wir sie reaktive Systeme.
  Computersysteme, die nach diesen Anforderungen entwickelt werden, erweisen sich als anpassungsfähiger, mit weniger starr gekoppelten Komponenten und in jeder Hinsicht skalierbarer. Sie sind einfacher weiterzuentwickeln und zu verändern. Sie reagieren zuverlässiger und eleganter auf Fehler und vermeiden so desaströse Ausfälle. Reaktive Systeme bereiten dem Benutzer durch ihre fortwährende Antwortfreudigkeit eine interaktive und höchst befriedigende Erfahrung."
  
## Reactive System
* Responsive (antwortbereit): Das System antwortet unter allen Umständen zeitgerecht, solange dies überhaupt möglich ist
* Resilient (widerstandsfähig): Das System bleibt selbst bei Ausfällen von Hard- oder Software antwortbereit.
* Elastic (skalierbar): Das System bleibt auch unter sich ändernden Lastbedingungen antwortbereit.
* Message-driven (nachrichtenorientiert): Das System verwendet asynchrone Nachrichtenübermittlung zwischen seinen Komponenten zur Sicherstellung von deren Entkopplung und Isolation sowie zwecks Übermittlung von Fehlern an übergeordnete Komponenten.

# Agiles Projektmanagement / Agile Softwareentwicklung 

## Agiles Manifest

1. Individuen und Interaktionen sind wichtiger als Prozesse und Werkzeuge.
2. Funktionierende Software ist wichtiger als umfassende Dokumentation.
3. Zusammenarbeit mit dem Kunden ist wichtiger als Vertragsverhandlungen.
4. Reagieren auf Veränderung ist wichtiger als das Befolgen eines Plans.

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
* Spring Retrospektive

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

# Idempotenz
Programmcode, das mehrfach hintereinander ausgeführt das gleiche Ergebnis wie bei einer einzigen Ausführung liefert

# Security

* **CSRF** - Cross-Site-Request-Forgery:  Kriminelle übernehmen eine vom Nutzer autorisierte Session (Session Riding) und können so schadhafte Aktionen durchführen. Dies geschieht über HTTP-Request.
  * Schutz durch serverseitig generierten CSRF token
* **JWT** - JSON Web Token: auf JSON basiertes Access-Token. JWT eignen sich vor allem zur Implementierung von "Stateless Sessions", da sämtliche authentifizierungsrelevanten Informationen im Token übertragen werden können
* **CORS** - Cross-Origin-Resource-Sharing, also das Bereitstellen von Inhalten aus einer anderen Quelle. Um dies zu ermöglichen, bedient man sich bestimmter HTTP-Header.
* **OAuth** - Open Authorization: ist ein Standard, mithilfe dessen eine Website oder Anwendung auf Ressourcen zugreifen kann
  * Rollen:
    * Resource Owner
    * Resource Server
    * Client
    * Authorization Server
  * Abstrakter OAuth-2.0-Protokollfluss (Protocol Flow von OAuth 2.0)
    * Der Client fordert eine Autorisierung vom Resource Owner an. Diese Autorisierungsanforderung kann direkt erfolgen, wird aber bevorzugt indirekt über den Authorization Server durchgeführt.
    * Der Client erhält eine Autorisierungsgenehmigung vom Resource Owner. Die Autorisierung kann über einen der vier Autorisierungsgenehmigungsprozesse (authorisation grant types) erfolgen oder es wird ein erweiterter Genehmigungsprozess verwendet.
    * Der Client fordert ein Access Token vom Authorization Server an. Hierfür nutzt er die Autorisierungsgenehmigung vom Resource Owner.
    * Der Authorization Server authentisiert den Client (permission to ask) und prüft die Autorisierungsgenehmigung des Resource Owners. Ist diese erfolgreich, stellt er ein Access Token aus.
    * Der Client fragt die geschützten Daten beim Resource Server an. Zur Authentisierung benutzt er das Access Token.
    * Der Resource Server prüft das Access Token und stellt, wenn gültig, die gewünschten Daten zur Verfügung.
* **OpenID Connect** - is a simple identity layer on top of the OAuth 2.0 protocol. It allows Clients to verify the identity of the End-User based on the authentication performed by an Authorization Server, as well as to obtain basic profile information about the End-User in an interoperable and REST-like manner.
* **Keycloak** - is an open source identity and access management solution, ermöglicht Single-Sign On, Identity Brokering and Social Login, Fedaration (LDAP Anbindung)

# Bücher
| Title                                                              | Autor                                                   |
|--------------------------------------------------------------------|---------------------------------------------------------|
| Design Patterns. Elements of Reusable Object-Oriented Software     | Erich Gamma, Richard Helm, Ralph Johnson, John Vlisside |
| Clean Code                                                         | Robert C. Martin                                        |
| Patterns für Enterprise Application-Architekturen                  | Martin Fowler                                           |
| Refactoring                                                        | Martin Fowler                                           |
| Domain-Driven Design: Tackling Complexity in the Heart of Software | Eric Evans                                              |


