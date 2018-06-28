![MongoDB](https://www.codeproject.com/KB/database/1037052/image001.png)

## MongoDB Introduction
___Almost all web applications depend on some sort of database for persisting information. Databases are primarily either relational or NoSQL. Relational databases, are identified by their use of SQL. The NoSQL family of databases, do not use SQL, popular choice due to the perceived ease of use and speed. MongoDB is one of the most popular NoSQL databases.___

#### NoSQL Databases
The name NoSQL is a bit generic, referring to a number of data store types. Essentially, NoSQL represents any data store that does not use SQL. NoSQL databases are generally faster than relational databases because they don’t typically follow a predefined schema or enforce data consistency as strictly as their relational cousins. This means that NoSQL data stores are usually suited to prototyping, and to social media applications that don’t require the data to be perfectly consistent at all times.

#### What is MongoDB?
MongoDB falls into the document store class of NoSQL databases. Mongo stores data in binary JSON (BSON) formatted documents. Mongo’s native use of JSON provides a simple and convenient interface for JavaScript applications.
- NoSQL database
- Consists of Collections and Documents
- Document is a JSON object
- Think of a Collection as an array of Documents
- Mongo runs as a process on its own port on local machine
- Can create remote instances (MLab)
- Can connect to MongoDB inside our Node.js applications
 
#### Documents
MongoDB is a document database, which means that the equivalent of a record is a document, or an object. In a relational database, one has to use rows and columns, whereas in a document database, an entire object can be written as a document.

For simple objects, this may seem no different from a relational database. But let’s say you have objects with nested objects (called embedded documents) and arrays. Now, when using a relational database, you typically need multiple tables. For example, an Invoice object may be stored in a combination of an invoice table and invoice_lines table in a relational database. In MongoDB, you store the entire Invoice object as one document.

A document is a data structure composed of field and value pairs. The values of fields may include other documents, arrays, and arrays of documents. MongoDB documents are similar to JSON objects, so it is easy to think of them as JavaScript objects. Compared to a JSON object, a MongoDB document has support not only for the primitive data types boolean, numbers, and strings, but also other common data types such as dates, timestamps, regular expressions, and binary data. You can even store JavaScript functions as document fields.

#### Collections
A collection is like a table in a relational database. It is a set of documents, and you access each document via the collection. Just like in a relational database, you can have a primary key and indexes on the collection.

A primary key is mandated in MongoDB, and it has the reserved field name _id. Even if you don’t supply an _id field when creating a document, MongoDB creates this field and auto-generates a unique key for every document. More often than not, the auto- generation is used as is, since it is convenient and guaranteed to produce unique keys even when multiple clients are writing to the database simultaneously. MongoDB uses a special data type called the ObjectId for the primary key.

The _id field is automatically indexed. Apart from this, indexes can be created on other fields, and this includes fields within embedded documents and array fields. Indexes are used to efficiently access a subset of documents in a collection.

#### [Return: Express README](../../README.md)
