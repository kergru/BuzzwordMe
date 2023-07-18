# Microservice Archtekture
(Martin Fowler)

# SOA
service-oriented architecture, software approach for distributed systems

The central concept behind your SOA design is the isolation of your sub-systems or services from the impact of change in other systems or services.
You can get there by declaring service boundaries.

# DDD
(Eric Evans)
basiert auf folgenden zwei Annahmen:
* Der Schwerpunkt des Softwaredesigns liegt auf der Fachlichkeit und der Fachlogik.
* Der Entwurf komplexer fachlicher Zusammenhänge sollte auf einem Modell der Anwendungsdomäne, dem Domänenmodell basieren.

Bestandteile:
* Ubiquitäre Sprache
* Domain-Modell:
  * Entities
  * ValueObjects
  * Aggregates
  * Bounded Context


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

# Schichten Architektur

Layered architectures are said to be the most common and widely used architectural framework in software development. It is also known as an n-tier architecture and describes an architectural pattern composed of several separate horizontal layers that function together as a single unit of software
A layer is a logical separation of components or code:
* Presentation: responsible for user interactions with the software system  
* Application/Business: handles aspects related to accomplishing functional requirements
* Domain: responsible for algorithms, and programming components
* Infrastructure/Persistence: responsible for handling data, databases


# Restful Webservices
Architeckturstil für verteilte Systeme
RESTful Webservices sind statuslos und liefern die Daten in unterschiedliche Repräsentationen (Formate) an den Aufrufer. Die Daten werden in mit einer URI eindeutig identifiziert und als Ressource bezeichnet.

Alternativen:
* RPC - Remote Procedure Call (OS dependent)
* RMI - Remote Method Invocation (Java), supports object-oriented programming)


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

