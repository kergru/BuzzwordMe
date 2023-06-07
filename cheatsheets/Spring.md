# Spring

ein quelloffenes Framework für die Java-Plattform, welches oft für Web-Anwendungen verwendet wird. Ziel des Spring Frameworks ist es, die Entwicklung mit Java/Java EE zu vereinfachen und gute Programmierpraktiken zu fördern.[3] Spring bietet mit einem breiten Spektrum an Funktionalität eine ganzheitliche Lösung zur Entwicklung von Anwendungen und deren Geschäftslogiken; dabei steht die Entkopplung der Applikationskomponenten im Vordergrund.

flexible Modulsammlung nutzen. So erhalten Sie eine leistungsstarke Grundstruktur, die Sie kaum verändern müssen, und können sich ganz auf die Entwicklung der eigentlichen Business-Logik konzentrieren.


## Vorteile:
* Logik kann in Form von POJOs angelegt werden
* Fertiges Basiscodegerüst, das kaum Veränderungen bedarf
* Kein Applikationsserver notwendig
* Ermöglicht Unit- und Integrations-Tests
* MVC-Architektur
* Aspektorientierte Programmierung mit AspectJ möglich
* Dependency Injection (externe Abhängigkeitsregulierung)
* Programmatisches Transaktions-Management

## Eigenschaften
* Dependency Injection: Den Objekten werden die benötigten Ressourcen und Objekte zugewiesen. Sie müssen sie nicht selbst suchen.
* AOP: technische Aspekte wie Transaktionen oder Sicherheit isolieren und den eigentlichen Programmcode davon freihalten
* Templates: Spring Klassen für verschiedene Programmschnittstellen bezeichnet, die die Arbeit mit APIs vereinfachen, indem sie automatisches Ressourcenmanagement, einheitliche Fehlerbehandlungen und andere Hilfestellungen bieten.

## Spring Boot
einfache Entwicklung eigenständig lauffähiger Spring-Anwendungen per Konvention vor Konfiguration, die ohne XML-Konfiguration auskommen und alle nötigen Klassenbibliotheken mitbringen.
JPA-basierte Repositories Implementierung (Interfaces)

Vorteile: 
* Reduzierung Boilerplate  

## Spring WebFlux
Entwicklung von Webanwendungen auf dem reactive stack (Reactive Stream API) die auf non-blocking Webserver (Netty) laufen

### Was bedeuted reactive?
Interaktion asynchroner Resourcen mit backpressure

+ **Subscriber**: Der Subscriber abonniert einen Publisher und wird mittels Callbacks über Neuerungen informiert
+ **Subscription**: Die Subscription beschreibt die Beziehung zwischen Subscriber und Publisher
+ **Publisher**: Der Publisher ist verantwortlich für die Veröffentlichung von Daten an die angemeldeten Subscriber
+ **Processor**: Ein Processor transformiert Elemente, die zwischen Publisher und Subscriber übertragen werden


### Reactor
Reactive Library für WebFlux (Mono,  Flux)
### Ziel
* Concurrency mit kleinerer Anzahl von Threads
* Skalierung mit wenigener Hardware Ressourcen

### Eigenschaften
* non-blocking
* unterstützt backpressure

#### Backpressure
Backpressure in software systems is the capability to overload the traffic communication. In other words, emitters of information overwhelm consumers with data they are not able to process.
* slow down publishing (not always possible)
* buffering incoming events (memory issue)
* dropping exta events, loosing track of them
* Controlling backpressure:
  * Send new events only when the subscriber requests them (pull strategy)
  * Limiting the number of events to receive at the client-side
  * Canceling the data streaming when the consumer cannot process more events.

### map vs flatMap
map: Innerhalb des map-Befehls  muss nicht mit den Webflux-Publishern gearbeitet werden, die eigentliche Geschäftslogik kann also mit gewöhnlichem Java-Code implementiert werden.
flatMap: als Rückgabewert der übergebenen Methode wieder einen Publisher erwartet
Das ist etwa dann sinnvoll, wenn diese Methode ihrerseits wieder einen API-Aufruf absetzen muss.

## Spring Data JPA
provides repository support for the Jakarta Persistence API (JPA). It eases development of applications that need to access JPA data sources.

* NamedQuery
* JPQL:  eigene QL in JPA angelehnt am Domain-Modell
* PersistenceProvider: generiert (DB-unabhängiges) SQL basierend auf Domain-Mapping

## Spring Security 
is a framework that provides authentication, authorization, and protection against common attacks.

Der Authentifizierungsmechanismus von Spring Security basiert auf verschiedenen Filtern und deren Interaktion untereinander.

* Servlet Filters: DefaultSecurityFilterChain triggers a chain of filters before the request reaches the DispatcherServlet
* Authentication: Filter extended from AbstractAuthenticationProcessingFilter.
* Authorization: FilterSecurityInterceptor

## Spring Alternativen

### Micronaut
* JVM-based framework for building lightweight, modular applications
* Micronaut builds its dependency injection data at compile time instead using reflection and proxies to perform dependency injection at runtime
* first class support for reactive programming, for both clients and servers
* excellent framework for developing cloud-native applications

### Quarkus
* Kubernetes-natives Full-Stack Java Framework für JVMs (Java Virtual Machines) und native Kompilierung, mit dem Java speziell für Container optimiert wird. Es bietet eine effektive Plattform für Serverless-, Cloud- und Kubernetes-Umgebungen
* promise of delivering smaller artifacts with fast boot time, better resource utilization, and efficiency (container first Ansatz)
* it allows us to use both blocking and non-blocking strategies simultaneously. 