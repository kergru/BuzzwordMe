Java Features
================================

JDK
JRE
JVM

## OOP Objektorientierte Programmierung

Modell der Computerprogrammierung, bei dem das Softwaredesign auf Daten oder Objekten basiert und nicht auf Funktionen und Logik. Ein Objekt kann als ein Datenfeld definiert werden, das eindeutige Attribute und Verhaltensweisen aufweist.

### Prinzipien der OOP
* Kapselung. Dieser Grundsatz besagt, dass alle wichtigen Informationen innerhalb eines Objekts enthalten sind und nur ausgewählte Informationen offengelegt werden.
* Abstraktion. Objekte legen nur die internen Mechanismen offen, die für die Verwendung durch andere Objekte relevant sind
* Vererbung. Klassen können Code von anderen Klassen wiederverwenden
* Polymorphismus. Objekte sind so konzipiert, dass sie sich gemeinsam verhalten und mehr als eine Form annehmen können. Das Programm bestimmt, welche Bedeutung oder Verwendung für jede Ausführung dieses Objekts aus einer übergeordneten Klasse erforderlich ist, wodurch die Notwendigkeit, Code zu duplizieren, verringert wird.

#### SOLID
* S - Single Responsibility (of a class)
* O - Open-Closed - open for extension but closed for modification
* L - Liskov substitution - objects in a programm should be replacable with instance of their subtypes without altering the correctness of that programm
* I - Interface segregation - many client specific interfaces are better than one general purpose interface
* D - Dependeny inversion - Depend on abstraction not concretion


### Vorteile der objektorientierten Programmierung
* **Modularität**. Durch die Kapselung können Objekte in sich geschlossen werden,
* **Wiederverwendbarkeit**. Code kann durch Vererbung wiederverwendet werden
* **Produktivität**. Durch die Verwendung mehrerer Bibliotheken und wiederverwendbaren Codes können Programmierer neue Programme schneller erstellen.
* Leichte **Erweiterbarkeit** und **Skalierbarkeit**. Programmierer können Systemfunktionalitäten unabhängig voneinander implementieren.
* **Schnittstellenbeschreibungen**. Die Beschreibungen externer Systeme sind einfach, da für die Kommunikation von Objekten Nachrichtenaustauschtechniken verwendet werden.
* **Sicherheit**. Durch Kapselung und Abstraktion wird komplexer Code verborgen
* **Flexibilität**. Die Polymorphie ermöglicht es einer einzelnen Funktion, sich an die Klasse anzupassen

## Funktionale Programmierung
Ein funktionales Programm besteht aus einer Reihe von Funktionsaufrufen. Eigenständige Wertzuweisungen existieren nicht. Alle Elemente können als Funktionen aufgefasst werden.

## Reactive Programming 
is the processing of the asynchronous event stream, on which you can observe.

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

CompletableFuture is built as an advancement to Future interface. Both of these are used for asynchronous programming in java. While Future interface has limitations in terms of what can be done with a result of an asynchronous call, CompletableFuture provides an array of APIs for composing, combining and error handling in asynchronous situations. It also provides a way to build a pipeline which will perform all the operations in asynchronous manner, in the order we define.

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
