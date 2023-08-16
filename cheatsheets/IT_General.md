# REST - Represential State Transfer 
(Roy Fielding)

Paradigma für die Softwarearchitektur von verteilten Systemen.

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

# OOAD - Objektorientierte Analyse und Design
sind objektorientierte Varianten der zwei allgemeinen Tätigkeiten Anforderungsanalyse (objektorientierte Analyse) und Systementwurf (objektorientiertes Design) im Entwicklungsprozess eines Softwaresystems.

In der Analyse geht es darum, die Anforderungen zu erfassen und zu beschreiben, die das zu entwickelnde Softwaresystem erfüllen soll.

Beim objektorientierten Design wird das in der Analyse erstellte Domänenmodell weiterentwickelt und darauf aufbauend ein Systementwurf erstellt.


* Geschäftsprozessmodellierung (business modeling): Ein Verständnis für die Geschäftsprozesse wird erreicht.
* Anforderungsanalyse (requirements): Die Anforderungen werden erfasst, dokumentiert und organisiert.
* Analyse und Design: Die fachliche Architektur wird in ein technisches Design überführt.
* Implementierung: Es wird ein lauffähiges Softwaresystem erstellt.
* Test: Das Softwaresystem wird getestet.
* Auslieferung (deployment): Das Softwaresystem wird an den Kunden ausgeliefert.

# OOP - Objektorientierte Programmierung

5 Prinzipien:

1. Abstraktion
   Die Objekte auf relevante Bestandteile beschränken
2. Datenabstraktion/Kapselung (Data hiding)
   Nutzung von getter/setter
3. Wiederverwendung
   Klassen können in versch. Kontexten eingesetzt werden
4. Beziehungen
   (mehrfache) Vererbung, Spezialisierung bzw. Generalisierung
5. Polymorphismus
   Überladen/Überschreiben von Namen -> gleiche Funktion, untersch. Implementierung

# Microservices

* Software Development Technik, die eine Applikation als eine Sammlung von lose gekoppelten Servicen arrangiert
* Variante von SOA (Service oriented architectecture)
* die Services sind feingranular und über leichtgewichtige Protokolle verbunden (Http/REST, AMQP)
* die Services sind unabhängig voneinander entwickelbar und deploybar und um Business-Anforderungen herum gruppiert
* die Services sind selfcontained, bringen alles mit was sie für ihren Betrieb benötigen

Fowler: do one thing and do it well

Vorteile:
* Modularität
* Skalierbarkeit
* Integration
* Verteilte, parallelisierbare Entwicklung

# Clean Code
(Robert C. Martin, Uncle Bob)

## Common Rules:
* **KISS**: keep it simple stupid
* **DRY**: don't repeat yourself
* **YAGNI**: you aint gonna need it
* Favor readability
* **Boyscout** rule
* Follow standard conventions
* **Demeter's law** (Reduzierung Abhängigkeiten)

## Testing Common Rules
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

# Protokolle

## AMQP Das Advanced Message Queuing Protocol
ist ein offener Standard, der ein binäres Netzwerkprotokoll auf Anwendungsebene für eine Message-orientierte Middleware (MOM) darstellt

## LDAP -  Lightweight Directory Access Protocol
ist ein Softwareprotokoll, das es jedem ermöglicht, Daten über Organisationen, Einzelpersonen 
und andere Ressourcen wie Dateien und Geräte in einem Netzwerk zu finden – sei es im öffentlichen 
Internet oder im Intranet eines Unternehmens.

## HTTP

### ETag
Entitäts-Kennzeichen‘) ist ein im HTTP 1.1 eingeführtes Header-Feld. Es dient zur Bestimmung von Änderungen an der angeforderten Ressource und wird hauptsächlich zum Caching, also der Vermeidung redundanter Datenübertragungen, verwendet.


# PKI - Public Key Infrastructure
ermöglicht einen sicheren Datenaustausch in einem öffentlichen Netzwerk. Zur Verschlüsselung rechnergestützter Kommunikation werden Zertifikate aus einem privaten sowie öffentlichen Kryptographie-Schlüssel ausgestellt, verteilt und geprüft.
Die PKI erstellt digitale Zertifikate, die öffentliche Schlüssel Instanzen zuordnen, speichert diese Zertifikate sicher in einem zentralen Repository und widerruft sie bei Bedarf.

asymetrische Verschlüsselung

## Komponenten der PKI

Die folgenden Hauptkomponenten der PKI werden in diesem Artikel ausführlich besprochen:

1. Zertifizierungsstelle (CA)
   Die Hauptaufgabe der Zertifizierungsstelle besteht darin, den an einen bestimmten Benutzer gebundenen öffentlichen Schlüssel digital zu signieren und zu veröffentlichen. Dies geschieht mithilfe des eigenen privaten Schlüssels der Zertifizierungsstelle, sodass sich das Vertrauen in den Schlüssel eines Nutzers beziehungsweise einer Nutzerin aus dem Vertrauen in die Gültigkeit des Schlüssels der Zertifizierungsstelle ergibt.

2. Digitales Zertifikat
   Mit einer PKI können Nachrichten digital signiert und verschlüsselt werden. Der oder die Sender:in benötigt dafür den öffentlichen Schlüssel (Public Key) des Empfängers beziehungsweise der Empfängerin. Dieser wurde z. B. von einer Webseite heruntergeladen oder per E-Mail versandt. Zur Bestätigung der Authentizität dieses Schlüssels dienen digitale Zertifikate. Mit ihnen wird überprüft, ob ein bestimmter öffentlicher Schlüssel zu einer bestimmten Instanz gehört.

   X.509-Zertifikat


3. Digitale Signatur
   Ein Zertifikat wiederum ist durch eine digitale Signatur geschützt, deren Authentizität mit dem öffentlichen Schlüssel des Zertifikatsausstellers geprüft werden kann. Die Echtheit des letzten Zertifikats in einer solchen Kette muss durch höchstmögliche Sicherheitsanforderungen gewährleistet sein.

3. Registrierungsbehörde
 
4. Validierungsbehörde (OSCP oder CRL)
5. Sichere Lagerung 
6. Öffentliches/privates Schlüsselpaar

* TSL - Trusted Service List
* CRL - Certificate Revocation List, Zertifikatssperrlisten
* CTL - Zertifikatsvertrauenslisten
* CMS - Cryptographic Message Syntax 
* PEM - Private Enhanced Mail, Standardformat für X.509 Zertifikate
* DER - Distinguished Encoding Rules,  is a binary encoding for X.509 certificates and private keys
* PKCS - Public-Key Cryptography Standards, ist eine Sammlung von Standards für asymmetrische Verschlüsselungsverfahren.
* CVC - Card Verifiable Certificate, ist ein Public-Key-Zertifikat, das in einem besonders kompakten Format gespeichert wurde.

## Bestandteile eines Zertifikats

* Informationen zur Schlüsselgenerierung, einschließlich des öffentlichen Schlüssels, des privaten Schlüssels und anderer Details.
* Ein Zertifikat mit einer digitalen Signatur von einem vertrauenswürdigen Dritten, der Zertifizierungsstelle oder CA genannt wird.
* Die Signatur macht diese Informationen vertrauenswürdig, da nur der Eigentümer des privaten Schlüssels diese Signaturen generieren kann (bei selbstsignierten Zertifikaten).
* Nachweis des Zertifikatsbesitzes (d. h. Nachweis), der typischerweise Identifikationsdaten wie Firmenname, Adresse usw. umfasst.



# Monitoring
4 goldene Signale:
* Latenz -> Histogramme (keine Durchscnittswerte)
* Datenverkehr
* Fehler
* Sättigung

2 Methoden:
* USE-Methode 2 : Auslastung, Sättigung und Fehler. Mit dieser Methode kann die Leistung fast aller Systeme analysiert werden.
* RED-Methode 3 : Rate, Fehler und Dauer. Diese Methode konzentriert sich auf die Serviceüberwachung.


## Synthetic monitoring
also called synthetic testing, is an application performance monitoring practice that emulates the paths users might take when engaging with an application

## Tools
* Datadog (SaaS)
* Cloudprober
* Prometheus
* Grafana


# Bücher
| Title                                                              | Autor                                                   |
|--------------------------------------------------------------------|---------------------------------------------------------|
| Design Patterns. Elements of Reusable Object-Oriented Software     | Erich Gamma, Richard Helm, Ralph Johnson, John Vlisside |
| Clean Code                                                         | Robert C. Martin                                        |
| Patterns für Enterprise Application-Architekturen                  | Martin Fowler                                           |
| Refactoring                                                        | Martin Fowler                                           |
| Domain-Driven Design: Tackling Complexity in the Heart of Software | Eric Evans                                              |


