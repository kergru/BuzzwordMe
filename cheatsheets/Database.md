# Datenbanken

## Relational DBs (RDBMS)
store data in rows and tables. These systems connect information from various tables with keys — unique identifiers that the database assigns to rows of data in tables. Primary keys and foreign keys facilitate this process

## Non-Relational DBs
they don't contain any rows, tables, or keys. This type of database utilizes a storage model based on the type of data it stores.

## SQL vs NoSQL DBs

SQL databases are typically used in applications that require complex queries and transaction management,
whereas NoSQL databases are used in applications that require high performance and scalability, such as web applications and mobile apps.
  
| SQL (structured query language)                             | NoSQL (NotOnlySQL)                                    |
|-------------------------------------------------------------|-------------------------------------------------------|
| Relational database management system (RDBMS)               | Non-relational database management system             |
| structured data with predefined schema                      | dynamic schemas for un/semi-structured data           |
| vertically scalable                                         | horizontally scalable                                 |
| table-based                                                 | document, key-value, graph, or wide-column stores     |
| better for multi-row transactions                           | better for unstructured data like documents or JSON   |
| supports JOINS and complex queries                          | Does not support JOIN and complex queries             |
| Uses normalized data structure                              | Uses denormalized data structure                      |
| follows ACID                                                | follows BASE                                          |
| MySQL, PostgreSQL, Oracle, SQL Server, Microsoft SQL Server | MongoDB, Cassandra, Couchbase, Amazon DynamoDB, Redis |

## ACID vs BASE

* A - Atomic: Eine Transaktion ist eine Folge von Datenbank-Operationen. Atomarität stellt sicher, dass diese entweder ganz oder gar nicht ausgeführt wird
* C - Consistent: eine Transaktion nach Beendigung einen konsistenten Datenbankzustand hinterlässt
* I - Isolated: nebenläufig in Ausführung befindliche Transaktionen beeinflussen sich nicht gegenseitig
* D - Durable:  Daten sind nach dem erfolgreichen Abschluss einer Transaktion garantiert dauerhaft in der Datenbank gespeichert 


* BA - Basically available: cluster is available even if single node fails
* S - Soft state: state of system may change even without input (data with TTL)
* E - Eventually consistent: change propagated thru all nodes, systen will become consistent over time

## TransactionLevel

| Isolationsebene  | Dirty Read | Lost Updates | Non-Repeatable Read | Phantom Read |
|------------------|------------|--------------|---------------------|--------------|
| Read Uncommitted | möglich    | möglich      | möglich             | möglich      |
| Read Committed   | unmöglich  | möglich      | möglich             | möglich      |
| Repeatable Read  | unmöglich  | unmöglich    | unmöglich           | möglich      |
| Serializable     | unmöglich  | unmöglich    | unmöglich           | unmöglich    |

### Optimistic Locking vs Pessimistic Locking

Bei der Optimistic Concurrency wird mehreren Nutzern Parallelzugriff gewährt. Somit haben alle Benutzer grundsätzlich Leserechte. Wenn aber ein Artikel von einem der Benutzer geändert wurde, so bekommen andere Nutzer, die denselben Datensatz fast gleichzeitig zu ändern versuchen, eine Benachrichtigung, dass der Artikel aktualisiert wurde. In diesem Fall ist also der Nutzer privilegiert, der zuerst den Datensatz geändert hat. Wenn der Nutzer den Datensatz verlässt, wird ihm sein Privileg wieder entzogen, und ein nächster Anwender erhält Schreibzugriff.

Im Gegensatz dazu wird bei der Pessimistic Concurrency (Pessimistisches Locking) beim Zugriff eines Benutzers auf den Datensatz der Schreib- und Lesezugriff für alle anderen Nutzer gesperrt. Es ist damit also für weitere Benutzer nicht mehr möglich, einen Datensatz aufzurufen oder auszudrucken, bis der Datensatz wieder freigegeben wird.

Bei der Pessimistic Concurrency wird angenommen, dass ein Datensatz bei (fast) jedem Zugriff geändert werden soll. Die Optimistic Concurrency hingegen geht von der Prämisse aus, dass Datensätze vorwiegend für den Lesezugriff geöffnet werden.

Die Optimistic Concurrency minimiert Zugriffskonflikte im laufenden Betrieb, da nur gleichzeitige Zugriffe für Änderungen zu einem Konflikt führen, gleichzeitige Lesezugriffe hingegen nicht.

## Skalierung
vertikal: increase the load on a single server by adding more CPU, RAM, or SSD capacity
horizontal: sharding, which adds more servers


## Performance

### Database Performance

* RAM
* Cluster & Replication, Master-, Slave- Nodes
* Indexe
* Partitionierung, Sharding: logisch zusammengehörende Datensätze werden getrennt abgespeichert


### SQL Query Performance

* Queries:
  * join, group by, temp-tables, full table scan
* Execution Plan

## Normalisierung

Aufteilung von Attributen auf Tabellen die keine Redundanzen enthalten, weil Mehrfachdatenhaltung mehr Speicherplatz verbraucht und die Gefahr von Inkonsistenzen mitsichbringt

engl: is the process of structuring a relational database in accordance with a series of so-called normal forms in order to reduce data redundancy and improve data integrity.

1. Normalform: atomar, frei von Wiederholung
2. Normalform:  jedes Nichtschlüsselattribut von jedem Schlüsselkandidaten voll funktional abhängig ist. (every non-prime attribute of the relation is dependent on the whole of every candidate key)
3. Normalform: kein Nichtschlüsselattribut transitiv von einem Kandidatenschlüssel abhängt. (all the attributes (e.g. database columns) are functionally dependent on solely the primary key)



# BLOB Binary Large Object 

beschreibt eine große Datei, die in binärer Form vorliegt und in einer Datenbank abgelegt (Bspw Bilddatei)

# MongoDB

## aggregate
Aggregation is a way of processing a large number of documents in a collection by means of passing them through different stages. The stages make up what is known as a pipeline. The stages in a pipeline can filter, sort, group, reshape and modify documents that pass through the pipeline.

	input ->$match -> $group -> $sort -> output

When to use MongoDB aggregate?

You can use aggregation operations to:
* Group values from multiple documents together.
* Perform operations on the grouped data to return a single result.
* Analyze data changes over time.

	db.orders.aggregate( [
	   // Stage 1: Filter pizza order documents by pizza size
	   {
	      $match: { size: "medium" }
	   },
	   // Stage 2: Group remaining documents by pizza name and calculate total quantity
	   {
	      $group: { _id: "$name", totalQuantity: { $sum: "$quantity" } }
	   }
	] )
	
What are the limitations of aggregate in MongoDB?

The aggregate command can either return a cursor or store the results in a collection. Each document in the result set is subject to the 16 megabyte BSON Document Size limit. If any single document exceeds the BSON Document Size limit, the aggregation produces an error. The limit only applies to the returned documents.


### $lookup
join collections

	{
	   $lookup:
	     {
	       from: <collection to join>,
	       localField: <field from the input documents>,
	       foreignField: <field from the documents of the "from" collection>,
	       as: <output array field>
	     }
	}


### $facet 
allows you to create multi-faceted aggregations


### $bucket
Categorizes incoming documents into groups, called buckets, based on a specified expression and bucket boundaries and outputs a document per each bucket.
    
### $search 
performs a full-text search of the field or fields in an Atlas collection. The fields must be covered by an Atlas Search index.

## Anwendung
* Echtzeitanalye -> BigData wg Skalierung
* ContentManagement, Produktkatalog -> Das flexible Datenmodell erleichtert das Speichern verschiedener Arten von Inhalten, einschließlich Bilder, Texte und Videos, sowie von Metadaten.

# ETL

* Extracting data from sources
* Transforming data into data models
* Loading data into data warehouses

