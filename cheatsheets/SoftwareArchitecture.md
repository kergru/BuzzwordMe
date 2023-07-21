# Architecture styles

## REST - Represential State Transfer
(Roy Fielding)

Paradigma für die Softwarearchitektur von verteilten Systemen.

REST ist eine Abstraktion der Struktur und des Verhaltens des World Wide Web.
Eine Ressource kann dabei über verschiedene Medientypen dargestellt werden, auch Repräsentation der Ressource genannt.
Anders als bei vielen verwandten Architekturen kodiert REST keine Methodeninformation in den URI, da der URI Ort und Namen der Ressource angibt
Die Bezeichnung „Representational State Transfer“ soll den Übergang vom aktuellen Zustand zum nächsten Zustand (state) einer Applikation verbildlichen. Dieser Zustandsübergang erfolgt durch den Transfer der Daten, die den nächsten Zustand repräsentieren.

### Prinzipien

* Client Server Architekur: Server einen Dienst bereit, der bei Bedarf vom Client angefragt werden kann
* Zustandslosigkeit: Jede REST-Nachricht enthält alle Informationen, die für den Server bzw. Client notwendig sind, um die Nachricht zu verstehen. Weder der Server noch die Anwendung soll Zustandsinformationen zwischen zwei Nachrichten speichern
* Caching
* Einheitliche Schnittstelle
  * Adressierbarkeit von Ressourcen
  * Repräsentationen zur Veränderung von Ressourcen
  * Selbstbeschreibende Nachrichten
  * HATEOAS - Hypermedia as the Engine of Application State: Entwurfsprinzip von REST-Architekturen. Bei HATEOAS navigiert der Client einer REST-Schnittstelle ausschließlich über URLs, die vom Server bereitgestellt werden.

### Umsetzung
Für die Umsetzung des REST-Paradigmas wird ein zustandsloses Client-Server-Protokoll verwendet. Als Anwendungsschicht-Protokolle werden hauptsächlich HTTP und HTTPS eingesetzt.
Wird über HTTP zugegriffen, so gibt die verwendete HTTP-Methode, darunter GET, POST, PUT und DELETE, an, welche Operation des Dienstes gewünscht ist.

### Restful Webservices
Architeckturstil für verteilte Systeme
RESTful Webservices sind statuslos und liefern die Daten in unterschiedliche Repräsentationen (Formate) an den Aufrufer. Die Daten werden in mit einer URI eindeutig identifiziert und als Ressource bezeichnet.

Alternativen:
* RPC - Remote Procedure Call (OS dependent)
* RMI - Remote Method Invocation (Java), supports object-oriented programming)


## SOA - service-oriented architecture
software approach for distributed systems

The central concept behind your SOA design is the isolation of your sub-systems or services from the impact of change in other systems or services.
You can get there by declaring service boundaries.

## DDD
(Eric Evans)
basiert auf folgenden zwei Annahmen:
* Der Schwerpunkt des Softwaredesigns liegt auf der Fachlichkeit und der Fachlogik.
* Der Entwurf komplexer fachlicher Zusammenhänge sollte auf einem Modell der Anwendungsdomäne, dem Domänenmodell basieren.
* Bei DDD geht man davon aus, dass der größte Teil der Komplexität einer Software nicht in der technischen Umsetzung liegt, sondern in der Modellierung der Domäne.
Bestandteile:
* Ubiquitäre Sprache - common language between business analysts and developers for describing domain 
* Domain-Modell:
  * Entities
  * ValueObjects -  objects without conceptual identity
  * Aggregates - cluster of associated objects (customer, address, ...), Aggregates draw a boundary around one or more Entities.
  * Aggregate root - The root is the only member of the AGGREGATE that outside objects are allowed to hold references (customer)
  * Bounded Context
  * DomainEvent - customer's order


## Hexagonale Architektur (Ports & Adapters)
(Alistair Cockburn)

* clearly separates core logic from the input and output infrastructure
* dividing the system into loosely-coupled interchangeable components
* reducing coupling between the outside world and the core domain
* have inputs and outputs on the edges of technology-agnostic code

Components:
* Driving (primary) actor use the domain to achive goal
* Driven (secondary) actors – they provide functionality needed by the domain to achieve a goal
  * Recipient – only receives information from the domain (printer or message queue)
  * Repository – can both provide information to the domain and receive it (database or file system)

Driving Adapter -> Driving Port -> Domain -> Driven Port -> Driven Adapter

Domain besteht aus:
* Model
* Services
* Repositories
* Exceptions

statt globale Layer hat man Feature Packages mit jeweils Domain und Adpater

## Schichten Architektur

Layered architectures are said to be the most common and widely used architectural framework in software development. It is also known as an n-tier architecture and describes an architectural pattern composed of several separate horizontal layers that function together as a single unit of software
A layer is a logical separation of components or code:
* Presentation: responsible for user interactions with the software system  
* Application/Business: handles aspects related to accomplishing functional requirements
* Domain: responsible for algorithms, and programming components
* Infrastructure/Persistence: responsible for handling data, databases


## Event-driven / Message-drivenArchitecture

* uses events / messages to trigger and communicate between decoupled services
* can be divided into three components: producer, consumer, and broker.

The main difference between event-driven and message-driven systems is that a message is sent to a pre-determined location, whereas an event is broadcast to any potential listeners. Messages are stored in a queue and are then processed (and usually deleted) once, by a single, predefined consumer.

# DesignPatterns

Pattern: wiederverwendbare Entwurfsmuster
## GOF (GangOfFour) Patterns
(Design Patterns. Elements of Reusable Object-Oriented Software, Erich Gamma, Richard Helm, Ralph Johnson, John Vlisside)

### Creational Patterns

#### AbstractFactory
lets you produce families of related objects without specifying their concrete classes.

#### Builder
Lets you construct complex objects step by step.

#### Factory Methoden
Provides an interface for creating objects in a superclass, but allows subclasses to alter the type of objects that will be created.

#### Singleton (Antipattern)
Lets you ensure that a class has only one instance, while providing a global access point to this instance.
Example: java.lang.Runtime#getRuntime()


### Structural Patterns

#### Adapter
Allows objects with incompatible interfaces to collaborate.The Adapter acts as a wrapper between two objects. It catches calls for one object and transforms them to format and interface recognizable by the second object.

#### Bridge
Divides business logic or huge class into separate class hierarchies that can be developed independently.
One of these hierarchies (often called the Abstraction) will get a reference to an object of the second hierarchy (Implementation). The abstraction will be able to delegate some (sometimes, most) of its calls to the implementations object. Since all implementations will have a common interface, they’d be interchangeable inside the abstraction.
Example: Device and Remote Control

#### Composite
Lets you compose objects into tree structures and then work with these structures as if they were individual objects.
Usage examples: The Composite pattern is pretty common in Java code. It’s often used to represent hierarchies of user interface components or the code that works with graphs.

#### Decorator
Lets you attach new behaviors to objects by placing these objects inside special wrapper objects that contain the behaviors.
Example: Encoding and compression decorators

#### Facade
Provides a simplified interface to a library, a framework, or any other complex set of classes.

#### Proxy
Lets you provide a substitute or placeholder for another object. A proxy controls access to the original object, allowing you to perform something either before or after the request gets through to the original object.

### Behavioral Patterns

#### Chain of Responsibility
Lets you pass requests along a chain of handlers. Upon receiving a request, each handler decides either to process the request or to pass it to the next handler in the chain.

#### Iterator
Lets you traverse elements of a collection without exposing its underlying representation

#### Observer
Lets you define a subscription mechanism to notify multiple objects about any events that happen to the object they're observing.

#### Strategy
Lets you define a family of algorithms, put each of them into a separate class, and make their objects interchangeable.

#### Visitor
Lets you separate algorithms from the objects on which they operate.

#### Interceptor
Erweiterung eines Frameworks oder einer Middleware, ohne diese selbst zu verändern

## Architektur Patterns

### CQRS - Command and Query Responsibility Segregation
Pattern, das Lese- und Aktualisierungsvorgänge für einen Datenspeicher trennt

### EventSourcing
ist ein Verfahren, bei dem alle Veränderungen des Zustands einer Softwareanwendung als Sequenz von Events abgebildet und aufgezeichnet werden.
Alle Events werden von einem Event Store aufgezeichnet. Der Einsatz eines Event Stores bietet den Vorteil, dass alle Änderungen am System jederzeit durch eine Wiederholung der Events deterministisch nachgestellt werden können.


### MVC - Model View Controller
Unterteilung einer Software in die drei Komponenten Datenmodell, Ansicht und Programmsteuerung

### REST

## Core J2EE Patterns

### Presentation Layer

#### Interceptor (Intercepting Filter)

The presentation-tier request handling mechanism receives many different types of requests, which require varied types of processing. Some requests are simply forwarded to the appropriate handler component, while other requests must be modified, audited, or uncompressed before being further processed.


### Business Layer

#### DTO - Data Transfer Object
Data Transfer Objects, dieser Fachbegriff bezeichnet den Datenaustausch zwischen Methoden oder anderen Software-Komponenten.

#### Service Locator
The goal of this pattern is to improve the modularity of your application by removing the dependency between the client and the implementation of an interface.

### Integration Layer

#### DAO - Data Access Object

