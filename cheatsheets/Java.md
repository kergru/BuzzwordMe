Java Features
================================

JDK
JRE
JVM

## AOT vs JIT
There are two ways of compiling a Java application: using Just in Time Compilation (JIT) or Ahead of Time Compilation (AOT). The first is the default mode, and it is used by the Java Hotspot Virtual Machine to translate bytecode into machine code at runtime. The latter is supported by the novel GraalVM compiler and allows statically compiling bytecode directly into machine code at build time.

To transform JVM bytecode into machine code that is executable in a specific hardware architecture, the JVM interprets the bytecode at runtime and figures out in which architecture is the program running.
JIT compilers make programs cross-platform. (Indeed, the slogan “)write once, run anywhere)

AOT compilation is a form of static compilation that consists in transforming the program into a machine code before it is executed.
AOT compilers run programs more efficiently. AOT compilation is particularly suited for cloud applications. They offer faster startup speed, which results in shorter boot time and more straightforward horizontal scale-up of cloud services.

## OOP Objektorientierte Programmierung

Modell der Computerprogrammierung, bei dem das Softwaredesign auf Daten oder Objekten basiert und nicht auf Funktionen und Logik. Ein Objekt kann als ein Datenfeld definiert werden, das eindeutige Attribute und Verhaltensweisen aufweist.

The main aim of object-oriented programming is to implement real-world entities.

The core concept of the object-oriented approach is to break complex problems into smaller objects.

### Prinzipien der OOP
* Kapselung. Dieser Grundsatz besagt, dass alle wichtigen Informationen innerhalb eines Objekts enthalten sind und nur ausgewählte Informationen offengelegt werden.
* Abstraktion. Objekte legen nur die internen Mechanismen offen, die für die Verwendung durch andere Objekte relevant sind
* Vererbung. Klassen können Code von anderen Klassen wiederverwenden
* Polymorphismus. Objekte sind so konzipiert, dass sie sich gemeinsam verhalten und mehr als eine Form annehmen können. Das Programm bestimmt, welche Bedeutung oder Verwendung für jede Ausführung dieses Objekts aus einer übergeordneten Klasse erforderlich ist, wodurch die Notwendigkeit, Code zu duplizieren, verringert wird. (describes a pattern in object oriented programming in which classes have different functionality while sharing a common interface.)

#### SOLID 
(Robert C. Martin)

* S - Single Responsibility (of a class)
* O - Open-Closed - open for extension but closed for modification
* L - Liskov substitution - objects in a programm should be replacable with instance of their subtypes without altering the correctness of that programm
* I - Interface segregation - many client specific interfaces are better than one general purpose interface
* D - Dependeny inversion - Depend on abstraction not concretion

Solid Example: AreaCalculator
* Single Responsibility: should only calculate not print result
* Open-Closed: Should not be extended if you want to compute the area for a new type of shape, better each shape computes it's area
* Liskov substitution: 
* Interface segregation: AreaCalculator should only expose it's calculate function
* Dependeny inversion: Inject a general Printer into the AreaCalculator instead of instantiate a concrete <HTML>Printer


### Vorteile der objektorientierten Programmierung
* **Modularität**. Durch die Kapselung können Objekte in sich geschlossen werden,
* **Wiederverwendbarkeit**. Code kann durch Vererbung wiederverwendet werden
* **Produktivität**. Durch die Verwendung mehrerer Bibliotheken und wiederverwendbaren Codes können Programmierer neue Programme schneller erstellen.
* Leichte **Erweiterbarkeit** und **Skalierbarkeit**. Programmierer können Systemfunktionalitäten unabhängig voneinander implementieren.
* **Schnittstellenbeschreibungen**. Die Beschreibungen externer Systeme sind einfach, da für die Kommunikation von Objekten Nachrichtenaustauschtechniken verwendet werden.
* **Sicherheit**. Durch Kapselung und Abstraktion wird komplexer Code verborgen
* **Flexibilität**. Die Polymorphie ermöglicht es einer einzelnen Funktion, sich an die Klasse anzupassen


### Composition over Inheritance
1. Inheritance is tightly coupled whereas composition is loosely coupled.
2. There is no access control in inheritance whereas access can be restricted in composition.
3. Composition provides flexibility in invocation of methods that is useful with multiple subclass scenario.

Use inheritance only when you are sure that superclass will not be changed, otherwise go for composition.


## Funktionale Programmierung
Ein funktionales Programm besteht aus einer Reihe von Funktionsaufrufen. Eigenständige Wertzuweisungen existieren nicht. Alle Elemente können als Funktionen aufgefasst werden.

## Reactive Programming 
is the processing of the asynchronous event stream, on which you can observe with backpressure.

Reactive Programming verspricht eine höhere Performance von Enterprise-Java-Anwendungen bei geringerem Speicherbedarf. 
Erreicht wird dieses Versprechen, indem blockierende Aufrufe vermieden werden. 
Blockierende Aufrufe führen im Betriebssystem immer zu Prozess- und damit zu Kontextwechseln. Solche Kontextwechsel haben einen hohen CPU- und Speicher-Overhead. Dieser Overhead wird durch weniger Kontextwechsel reduziert.
Die oben erwähnte Realisierung der Java-Threading-Abstraktion hat aktuell allerdings einen gravierenden Nachteil: Java-Threads sind als Betriebssystemprozesse realisiert, sodass jeder Threadwechsel einen (sehr teuren) Kontextwechsel im Betriebssystem bedeutet.
Hier setzt Reactive Programming an. Das Paradigma ist genau entgegengesetzt zum Java-Threading-Modell. Während das Threading-Modell versucht, Asynchronität vom Benutzer fernzuhalten („Alles passiert in einem Thread“) ist bei Reactive Programming die Asynchronität quasi das Prinzip. Der Programmablauf wird als eine Sequenz von Ereignissen angesehen, die natürlich asynchron auftreten können. Jedes dieser Ereignisse wird von einem Publisher veröffentlicht. Auf welchem Thread der Publisher das tut, ist dabei unerheblich. Der Programmcode besteht in einer reaktiven Anwendung aus Funktionen, die auf diese asynchrone Veröffentlichung von Ereignissen hören, sie verarbeiten und gegebenenfalls neue Ereignisse veröffentlichen.
Dieses Vorgehen ist vor allem dann sinnvoll, wenn mit externen Ressourcen wie z. B. einer Datenbank gearbeitet wird.
Der Vorteil von Reactive Programming liegt also darin, dass eine Entkopplung von auszuführendem Code und dem ausführenden Thread entsteht. Damit gibt es weniger teure Kontextwechsel auf Betriebssystemebene.

Probleme entstehen bei der Integration in klassische Enterprise-Anwendungen. Dort hängen die klassischen Themen wie Security, Transaktionen oder Tracing bisher noch immer am aktuellen Thread. Beginnt man mit Reactive Programming, funktioniert dieses Konstrukt nicht mehr und es müssen andere Lösungen gefunden werden.

### Backpressure

Was passiert, wenn zu viele Ereignisse zu schnell eintreten, so dass das System sie nicht verarbeiten kann?
Datenfluss zwischen Ereignisproduzenten und -konsumenten zu managen und sicherzustellen, dass letzterer die Menge der eingehenden Events verarbeiten kann, ohne überfordert zu werden

* Dropping: Wenn sich die Events stauen, werden sie "weggeworfen". Sobald der Konsument in der Lage ist, mehr zu verarbeiten, werden die aktuellsten Ereignisse geliefert. Hier liegt der Fokus auf Lebendigkeit.
* Buffering: Eine Warteschlange mit unverarbeiteten Ereignissen wird erstelllt und schrittweise an den Konsumenten übergeben, sobald dieser dazu in der Lage ist, sie zu verarbeiten. Der Fokus: Konsistenz.
* Throttling: Die Rate der Ereignisbereitstellung wird durch diverse Strategien wie Zeitdrosselung, Zähldrosselung oder Token-Buckets verringert.
* Signaling: Eine Möglichkeit wird geschaffen, um dem Event-Produzenten den Backpressure-Status-Quo mitzuteilen, damit dieser entsprechend reagieren kann.

## Java Keywords


Neuerungen in den Java Versionen
================================

## Java 17

### Sealed classes

can restrict which other classes may extend them

    public abstract sealed class Shape permits Circle, Rectangle {...}


## Java 16

### records
Das neue Schlüsselwort record bietet einen besonders effizienten Weg an, um Klassen zu definieren, deren Objekte unveränderlich (immutable) sind. Die Zeile

> public record Rectangle(double length, double width) { }

definiert eine Klasse mit den unveränderlichen Instanzvariablen length und width, die über die gleichnamigen Methoden ausgelesen werden können (length() und width()). Einen geeigneten Konstruktor bekommen Sie frei Haus geliefert, ebenso brauchbare Implementierungen von toString, equals und hashCode.

Besonders gut eignen sich Records für Data Transfer Objects (DTOs).


## Java 15

### Mehrzeilige Zeichenketten

mit """ begonnen und abgeschlossen, nach den einleitenden """ muss eine neue Zeile beginnen

    String sql = """
    SELECT books.id, title, publId, name
    FROM books
    JOIN publishers ON publId = publishers.id  
    WHERE books.id >= 167""";

## Java 11

### Schlüsselwort var

vereinfachte lokale Variablendeklaration

### HttpClient

Standard HTTP Client featuring HTTP/2, WebSocket support and non-blocking API

## Java 9

### Flow API: Reactive Streams publish-subscribe framework for asynchronous stream processing with non-blocking backpressure

Reactive Programming is the processing of the asynchronous event stream, on which you can observe.

#### Reactive Streams

## Java 8

### CompletableFutures

CompletableFuture is built as an advancement to Future interface. Both of these are used for asynchronous programming in java. 
While Future interface has limitations in terms of what can be done with a result of an asynchronous call, 
CompletableFuture provides an array of APIs for composing, combining and error handling in asynchronous situations. 
It also provides a way to build a pipeline which will perform all the operations in asynchronous manner, in the order we define.

### Stream API

### Functionale Interfaces

### Lambda Expressions 

Lambdas: Implementierung Funktionaler Interfaces, kapselt eine 'single unit of behavior' welche an anderen Code weitergegeben werden kann

(args,..) -> {body}

    Arrays.sort(rosterAsArray,
        (Person a, Person b) -> {
            return a.getBirthday().compareTo(b.getBirthday());
        }
    );

### Method References

> Arrays.sort(rosterAsArray, Person::compareByAge);

* Reference to a static method
* Reference to an instance method of a particular object
* Reference to an instance method of an arbitrary object of a particular type
* Reference to a constructor

### Closures

Eine Closure (oder Funktionsabschluss) ist ein Konzept aus der funktionalen Programmierung. Es beschreibt eine Funktion, die Zugriffe auf ihren Erstellungskontext enthält.
Beim Aufruf greift die Funktion dann auf diesen Erstellungskontext zu. Dieser Kontext (Speicherbereich, Zustand) ist außerhalb der Funktion nicht referenzierbar, d. h. nicht sichtbar.


### Optionals
The purpose of the class is to provide a type-level solution for representing optional values instead of null references.

### DateTime API

### Interface Default and Static Methods

## Java 7

### Diamond Operator
Der Diamant-Operator vereinfacht die Schreibweise bei der Deklaration bevorzugt geschachtelter generischer Typen, indem er diese verkürzt.
The diamond operator adds the type inference feature to the compiler and reduces the verbosity in the assignments introduced with generics.

### Fork-Join Framework

### Java NIO 2.0 and improved File API

## Java 5

### Generics
Mit Generics werden Sprachmittel bezeichnet, mit denen Klassen und Methoden mit Typparametern parametrisiert werden können, um Typsicherheit trotz generischer Programmierung zu ermöglichen.
Generics werden nur während der Kompilierung ausgewertet.

#### Wildcards

| Wildcards                                 | Name                   | Beschreibung                                                         |
|-------------------------------------------|------------------------|----------------------------------------------------------------------|
| <?>                                       | unbounded wildcard     | Beliebiger Typ (vermeidet Compiler-Warnung) |
| <? super [Type]>                          | lower bounded wildcard | Superklasse von [Type] |
| <? extends [Type]>                        | upper bounded wildcard | Von [Type] (Klasse oder Interface) abgeleiteter Typ |
| <? extends [Type1] & [IType2] & [IType3]> | multiple bounds        | Subtyp von mehreren Typen (außer dem ersten Typ nur Interfaces erlaubt) |

### Atomic Klassen
(AtomicInteger)
Variable eines Ganzzahldatentyps werden als Zählvariable unbrauchbar, sobald mehrere Threads auf den Counter zugreifen.
Seit Java 1.5 gibt es jedoch eine Satz von Atomicklassen, die atomare Methoden anbieten und damit synchronized überflüssig machen.

### Annotations
Sprachelement, das die Einbindung von Metadaten in den Quelltext erlaubt

# Java Keywords
* **volatile**: guarantees variable visibility across threads, meaning reads and writes are visible across threads.
* **var**: Type inference is used in var keyword in which it detects automatically the datatype of a variable based on the surrounding context
* **transient**: Variable wird nicht serialisiert
* **synchronized**: synchronized keyword prevents concurrent access to a block of code or object by multiple threads


# Blocking vs NonBlocking

Blocking methods execute synchronously and non-blocking methods execute asynchronously. 

# Servlet API
* **Servlet 2.5:** Servlet containers will assign a request to a thread until that request has been fully processed.
* **Servlet 3.0:** async processing, the server can dispatch the request processing in a separate thread pool while the request is being processed by the application. However, when it comes to I/O, work always happens on a server thread and it is always blocking. This means that a "slow client" can monopolize a server thread, since the server is blocked while reading/writing to that client with a poor network connection.
* **Servlet 3.1:** async I/O is allowed and in that case the "one request/thread" model isn't anymore.
* **Servlet 4.0:** server push
## Netty
is an asynchronous event-driven network application framework.

## Tomcat
is a Web Server that manages HTTP request/responses and implements a set of standards such as the Java Servlet API. 

per default 100 Threads, ein Request pro Thread

# ORM - Object-Relational-Mapping
process of converting Java objects to database

## JPA - Java Persistence API
specification that defines how to persist data in Java applications

## Hibernate
* Java ORM framework
* Hibernate is a standard implementation of the JPA specification

## Spring Data API
* is a JPA data access abstraction. Spring Data JPA cannot work without a JPA provider.
* layer on top of jpa

# GraalVM 
is a Java Virtual Machine for compiling and running applications written in different languages to a native machine binary. 


# Stream.map() vs Stream.flatMap() in Java 8
In short, here are the key difference between map() vs flatMap() in Java 8:

* The function you pass to the map() operation returns a single value.
* The function you pass to flatMap() operation returns a Stream of value.
* flatMap() is a combination of map and flat operation. 
* map() is used for transformation only, but flatMap() is used for both transformation and flattening. 

