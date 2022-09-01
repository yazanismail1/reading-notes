# Mongo and Mongoose

> When it comes to data, we need to store them inside a database , a place which contains data, depending on the type of data and the application we choose the type of database.

---
---

**Fill in the chart below with five differences between SQL and NoSQL databases:**

|ID|SQL|NoSQL|
|---|---|---|
|01| primarily called as Relational Databases (RDBMS)|primarily called as non-relational or distributed database|
|03|table based databases|document based, key-value pairs|
|04|have predefined schema| have dynamic schema for unstructured data|
|05|vertically scalable whereas|horizontally scalable|
|06|uses SQL ( structured query language ) for defining and manipulating the data|ueries are focused on collection of documents. Sometimes it is also called as UnQL (Unstructured Query Language)|
|07|examples: MySql, Oracle, Sqlite, Postgres and MS-SQL|MongoDB, BigTable, Redis, RavenDb, Cassandra, Hbase, Neo4j and CouchDb|
|08|For complex queries|not good fit for complex queries|
|09|not best fit for hierarchical data storage|fits better for the hierarchical data storage as it follows the key-value pair way of storing data similar to JSON data|
|10|best fit for heavy duty transactional type applications, as it is more stable and promises the atomicity as well as integrity of the data|you can use NoSQL for transactions purpose, it is still not comparable and sable enough in high load and for complex transactional applications.|
|11|Excellent support are available for all SQL database from their vendors|have to rely on community support, and only limited outside experts are available for you to setup and deploy your large scale|
|12|emphasizes on ACID properties ( Atomicity, Consistency, Isolation and Durability)|follows the Brewers CAP theorem ( Consistency, Availability and Partition tolerance )|
|13|can classify SQL databases as either open-source or close-sourced from commercial vendors|can be classified on the basis of way of storing data as graph databases, key-value store databases, document store databases, column store database and XML databases.|

**What kind of data is a good fit for an SQL database?**

Best fit for heavy duty transactional type applications.

**Give a real world example.**

Customers and sales, what the customer purchased and the customer info.

**What kind of data is a good fit a NoSQL database?**

Objects, which contains key-pair value.

**Give a real world example.**

A place to store the E-commerce ads.

**Which type of database is best for hierarchical data storage?**

SQL is a better for hierarchical storage.

**Which type of database is best for scalability?**

NoSQL as it does not require to upgrade the hardware.

**What does SQL stand for?**

Structured Query Language.

**What is a relational database?**

A database structured to recognize relations between stored items of information.

**What type of structure does a relational database work with?**

A relational database organizes data into rows and columns, which collectively form a table.

**What is a 'schema'?**

Is the structure of a database described in a formal language supported by the database management system. The term "schema" refers to the organization of data as a blueprint of how the database is constructed

**What is a NoSQL database?**

A place (database) that stores data in a form of key-value pair.

**How does it work?**

Store data in documents rather than relational tables.

**What is inside of a Mongo database?**

MongoDB stores data records as documents (specifically BSON documents) which are gathered together in collections.

**Which is more flexible - SQL or MongoDB? and why.**

MongoDB as it ensures high and diverse data availability

**What is the disadvantage of a NoSQL database?**

Don't have the reliability functions which Relational Databases have (basically don't support ACID).

---
---

## Things I want to know more about

- webpack
- Mongoose
- SQL

 ---

## References

[1] LUKE P. ISSAC, Jan 14, 2014, _SQL vs NoSQL Database Differences Explained with few Example DB_, thegeekstuff.com, accessed 1 September 2022, <https://www.thegeekstuff.com/2014/01/sql-vs-nosql-db/?utm_source=tuicool>
