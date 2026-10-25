# What is MySQL?
-> MySQL is an open-source relational database management system used to store and manage structured data. It uses SQL for performing operations such as inserting, updating, deleting, and retrieving data.

# What is the difference between DBMS and RDBMS?
-> What is the difference between DBMS and RDBMS? DBMS stands for Database Management System, and RDBMS stands for Relational Database Management System. The main difference is that an RDBMS stores data in tables and allows relationships between those tables using keys such as primary keys and foreign keys.

# What is a Primary Key?
->A primary key is a column or combination of columns that uniquely identifies each record in a table. It cannot contain duplicate or NULL values. For example, in an employee table, employee_id can be a primary key because every employee has a unique ID. It helps the database uniquely identify and access a particular record.

# What is a Foreign Key?
-> A foreign key is a column that establishes a relationship between two tables by referencing the primary key of another table. It helps maintain referential integrity and ensures that related data remains consistent between the tables.

# What is the difference between DELETE, DROP, and TRUNCATE in MySQL?
->DELETE removes selected rows from a table and can be used with a WHERE condition. TRUNCATE removes all rows from the table and is generally faster because it removes the table's data as a whole. DROP removes the entire table, including its structure.

# What is the difference between WHERE and HAVING in MySQL?
-> WHERE is used to filter individual rows before grouping or aggregation, while HAVING is used to filter the grouped results after GROUP BY. For example, if I want employees with a salary above 50,000, I use WHERE; if I want departments whose average salary is above 50,000, I use HAVING.

# What is GROUP BY in MySQL?
-> GROUP BY is used to group rows that have the same values in one or more columns. It is commonly used with aggregate functions such as COUNT(), SUM(), AVG(), MAX(), and MIN() to perform calculations on each group. For example, I can use GROUP BY department to calculate the average salary for each department.

# What are aggregate functions in MySQL?
->Aggregate functions perform calculations on multiple rows and return a single result. Common aggregate functions are COUNT(), SUM(), AVG(), MAX(), and MIN(). They are commonly used with GROUP BY to calculate results for each group, such as finding the average salary of employees in each department.

# What is a JOIN in MySQL?
->A JOIN is used to combine data from two or more tables based on a related column between them. For example, if I have Customers and Orders tables, I can use a JOIN on customer_id to retrieve customer details along with their orders. MySQL provides different types of joins such as INNER JOIN, LEFT JOIN, RIGHT JOIN, and CROSS JOIN.

# What is the difference between INNER JOIN and LEFT JOIN?

Answer: An INNER JOIN returns only the records that have matching values in both tables. A LEFT JOIN returns all records from the left table, along with the matching records from the right table; if there is no match, the right-side columns contain NULL.

# What is a RIGHT JOIN in MySQL?
->A RIGHT JOIN returns all records from the right table and the matching records from the left table. If there is no matching record in the left table, the columns from the left table will contain NULL. It is essentially the opposite of a LEFT JOIN.

# What is a SELF JOIN in MySQL?
-> A SELF JOIN is a join where a table is joined with itself. It is useful when records within the same table have a relationship with each other. For example, in an employee table, if each employee has a manager_id that refers to another employee's employee_id, we can use a SELF JOIN to find each employee along with their manager.

# What is a Subquery in MySQL?
->A subquery is a query written inside another SQL query. It is used when the result of one query is needed as input for another query. For example, I can use a subquery to find employees whose salary is greater than the average salary of all employees.

# What is an Index in MySQL?
-> An index is a database structure used to speed up data retrieval from a table. Instead of scanning every row, MySQL can use the index to find the required records more efficiently. However, indexes require additional storage and can make INSERT, UPDATE, and DELETE operations slightly slower because the index also needs to be updated.

# What is a UNIQUE constraint in MySQL?
->A UNIQUE constraint ensures that all values in a column are different, so duplicate values are not allowed. Unlike a primary key, a table can have multiple UNIQUE constraints, and a UNIQUE column can contain NULL values. For example, we can use UNIQUE on an employee's email column to prevent two employees from registering with the same email address.

# What is a NULL value in MySQL?
->A NULL value represents the absence or unknown value in a database. It is different from 0, an empty string, or false. We use IS NULL or IS NOT NULL to check for NULL values because we cannot compare NULL using = or !=.

# What is the difference between CHAR and VARCHAR in MySQL?
-> CHAR is a fixed-length data type, so it always uses the defined length, while VARCHAR is variable-length and stores only the required characters. I would use CHAR when the data has a fixed length, such as a country code, and VARCHAR for variable-length data such as names, emails, or addresses.

# What is the difference between PRIMARY KEY and UNIQUE KEY?
->A PRIMARY KEY uniquely identifies each record in a table and cannot contain NULL values. A table can have only one primary key, whereas it can have multiple UNIQUE keys. A UNIQUE key also prevents duplicate values, but it can allow NULL values.

# What is Normalization in MySQL?
-> Normalization is the process of organizing data into multiple related tables to reduce data duplication and improve data consistency. For example, instead of storing customer details repeatedly in every order record, we can keep customer information in a separate Customers table and reference it using a foreign key.

# What are the different types of Normalization?
-> The main normal forms are 1NF, 2NF, 3NF, and BCNF. 1NF ensures that each column contains atomic values and there are no repeating groups. 2NF removes partial dependency on a composite key. 3NF removes transitive dependency, meaning non-key columns should depend only on the key. In practice, 3NF is commonly used to reduce redundancy while maintaining good database design.

# What is a Transaction in MySQL?
-> A transaction is a group of SQL operations that are treated as a single unit of work. Either all operations are successfully completed, or they can be rolled back if something fails. MySQL uses commands such as COMMIT to permanently save changes and ROLLBACK to undo changes. For example, during a bank transfer, money should be deducted from one account and added to another; both operations should succeed together to maintain data consistency.

# What are ACID properties in MySQL?
-> ACID stands for Atomicity, Consistency, Isolation, and Durability. These properties ensure that database transactions are processed reliably. Atomicity means all operations in a transaction succeed or none do. Consistency keeps the database in a valid state. Isolation ensures that concurrent transactions do not incorrectly affect each other. Durability means that once a transaction is committed, the changes are permanently stored even if the system fails.

# What is a Stored Procedure in MySQL?
-> A stored procedure is a set of SQL statements stored in the database and executed whenever required. It helps us reuse database logic, reduce repeated SQL code, and perform multiple operations through a single procedure call.

# What is a View in MySQL?
-> A View is a virtual table created from the result of a SQL query. It does not normally store the actual data separately; instead, it retrieves data from the underlying tables when we query the view. Views are useful for simplifying complex queries and restricting access to sensitive columns or rows.

# What is the difference between UNION and UNION ALL in MySQL?
-> UNION combines the results of two or more SELECT queries and removes duplicate records, whereas UNION ALL combines the results without removing duplicates. Because UNION ALL does not perform duplicate elimination, it is generally faster when duplicate records are acceptable.

# What is a PRIMARY KEY constraint, and why is it important?
-> A primary key is used to uniquely identify each record in a table. It ensures that every row has a unique and non-NULL identifier. It is important because it prevents duplicate records and provides a reliable way to reference a specific row from other tables using a foreign key.

# What is a Composite Key in MySQL?
-> A composite key is a key made up of two or more columns that together uniquely identify a record. We use it when a single column is not sufficient to uniquely identify a row. For example, in an OrderItems table, order_id and product_id together can form a composite primary key because the same product can appear in different orders, but the same product should not be repeated within one order.

# What is a Foreign Key Constraint?
-> A foreign key constraint is used to establish a relationship between two tables. It references a primary key or unique key in another table and ensures that the value exists in the parent table. This helps maintain referential integrity and prevents invalid relationships between records.

# What is the difference between ON DELETE CASCADE and ON DELETE SET NULL?
->ON DELETE CASCADE automatically deletes the related child records when the corresponding parent record is deleted. ON DELETE SET NULL keeps the child record but sets its foreign key value to NULL. We choose between them based on the business requirement—for example, deleting an order might delete its order items, while deleting a manager could set an employee's manager_id to NULL.

# What is the difference between WHERE and ON in a JOIN?
-> ON specifies the condition used to match records between two tables during a JOIN, while WHERE filters the records after the JOIN result is formed. This difference becomes especially important with LEFT JOIN, because putting a condition in WHERE can remove unmatched rows and effectively change the result.

# What is a DEFAULT constraint in MySQL?

Answer: A DEFAULT constraint is used to assign an automatic value to a column when no value is provided during insertion. It helps avoid NULL values when a meaningful default value is available. For example, we can set an employee's status to 'ACTIVE' by default when a new employee is created.

# What is the AUTO_INCREMENT attribute in MySQL?

Answer: AUTO_INCREMENT automatically generates a unique numeric value for a column whenever a new record is inserted. It is commonly used with a primary key, such as employee_id, so we don't have to manually provide a unique ID for every new record.

# What is the difference between COUNT(*), COUNT(column), and COUNT(DISTINCT column)?

Answer: COUNT(*) counts all rows in the table, including rows containing NULL values. COUNT(column) counts only the rows where that particular column is not NULL. COUNT(DISTINCT column) counts only the unique non-NULL values in that column.

# What is the difference between IN and EXISTS in MySQL?

Answer: IN checks whether a value matches any value returned by a subquery or a given list, while EXISTS checks whether the subquery returns at least one row. EXISTS is often useful when we only need to know whether a related record exists, especially with correlated subqueries.

# What is a Correlated Subquery in MySQL?

Answer: A correlated subquery is a subquery that depends on the current row of the outer query. It is executed repeatedly for each row processed by the outer query. For example, we can use it to find employees whose salary is greater than the average salary of their own department.

# What is a CTE in MySQL?

Answer: A CTE (Common Table Expression) is a temporary named result set that we define using the WITH keyword and use within a SQL statement. It makes complex queries easier to read, understand, and maintain, especially when we need to reuse intermediate results or work with recursive queries.

# What is a Trigger in MySQL?
->A trigger is a database object that automatically executes a predefined SQL statement when a specific event such as INSERT, UPDATE, or DELETE occurs on a table. It is useful for automatically maintaining audit records, enforcing certain business rules, or keeping related data synchronized.

# What is a Cursor in MySQL?
->A cursor is a database object used to process the result of a query row by row. It is mainly used inside stored procedures when we need to perform specific operations on each record individually. However, cursors can be slower than set-based SQL operations, so they should be used only when necessary.

# What is the difference between CHAR_LENGTH() and LENGTH() in MySQL?
-> CHAR_LENGTH() returns the number of characters in a string, while LENGTH() returns the number of bytes used to store the string. For English text they usually return the same value, but for multibyte characters such as Unicode text, LENGTH() can return a larger value than CHAR_LENGTH().

# What is the difference between UNION and JOIN in MySQL?
-> JOIN combines columns from multiple tables based on a related condition, so it is used to retrieve related data from different tables. UNION combines the rows returned by two or more SELECT queries into a single result, and the queries must have the same number of compatible columns.

# What is the difference between DELETE and TRUNCATE in MySQL?
-> DELETE removes rows from a table and can be used with a WHERE condition to remove specific records. TRUNCATE removes all rows from the table at once and does not support WHERE. TRUNCATE is generally faster because it deallocates the table's data pages rather than deleting rows individually.

# What is the difference between DROP and TRUNCATE in MySQL?
-> DROP completely removes the table, including its data and structure, so the table no longer exists. TRUNCATE removes all the data from the table but keeps the table structure, allowing us to use it again.

# What is a Constraint in MySQL?
-> A constraint is a rule applied to a table or column to control the type of data that can be stored and maintain data integrity. Common constraints include PRIMARY KEY, FOREIGN KEY, UNIQUE, NOT NULL, DEFAULT, and CHECK.

# What is the NOT NULL constraint in MySQL?
-> The NOT NULL constraint ensures that a column cannot contain NULL values. It is used when a particular field is mandatory and must always have a value. For example, if an employee's name is required, we can define the column as name VARCHAR(100) NOT NULL.

# What is the CHECK constraint in MySQL?
-> The CHECK constraint is used to restrict the values that can be inserted into a column based on a specified condition. For example, if an employee's age must be 18 or above, we can define CHECK (age >= 18). This helps prevent invalid data from being stored in the database.

# What is a Database Schema?
->A database schema is the logical structure or blueprint of a database. It defines how data is organized, including tables, columns, relationships, constraints, indexes, and other database objects. For example, in an e-commerce application, the schema can define Customer, Product, and Order tables and the relationships between them.

# What is a Database Index?
-> A database index is a data structure that improves the speed of retrieving records from a table. It works similar to an index in a book, allowing MySQL to find the required data without scanning every row. However, indexes require extra storage and can slow down INSERT, UPDATE, and DELETE operations because the index also needs to be maintained.


# What is a Composite Index in MySQL?
->A composite index is an index created on two or more columns. It is useful when queries frequently filter or sort using those columns together. For example, if we often search employees using both department_id and salary, we can create a composite index on those columns to improve query performance.

# What is a Clustered Index and Non-Clustered Index?
-> A clustered index determines the physical order in which data is stored in a table, while a non-clustered index stores a separate structure containing indexed values and references to the actual rows. A table can have only one clustered index because the data can have only one physical ordering, whereas it can have multiple non-clustered indexes.

# What is EXPLAIN in MySQL?
-> EXPLAIN is used to understand how MySQL executes a SQL query. It shows information such as which indexes are being used, how tables are accessed, the number of rows MySQL expects to examine, and the join strategy. I use EXPLAIN mainly to identify performance problems and optimize slow queries.

# What is MongoDB?
->MongoDB is a NoSQL, document-oriented database that stores data in BSON documents instead of rows and tables. It provides a flexible schema, which makes it suitable for applications where the data structure can change frequently.

# What is the difference between a collection and a document in MongoDB?
-.A collection is a group of related documents, similar to a table in MySQL. A document is an individual record stored inside a collection, represented in BSON format.

For example, employees is a collection, while {name: "John", age: 25} is a document.

# What is BSON in MongoDB?
->BSON stands for Binary JSON. It is the format MongoDB uses to store documents. BSON extends JSON by supporting additional data types such as ObjectId, Date, Decimal128, and Binary data, making it suitable for efficient database storage and processing.

# What is the difference between SQL and MongoDB?
->SQL databases store data in tables, rows, and columns with a fixed schema, while MongoDB stores data in collections and BSON documents with a flexible schema. SQL databases are generally better for complex relationships and joins, whereas MongoDB is well suited for flexible, semi-structured data.

# What is the difference between find() and findOne() in MongoDB?
->find() returns a cursor containing all documents that match the query, while findOne() returns only the first matching document.

# What is the difference between insertOne() and insertMany() in MongoDB?
->insertOne() is used to insert a single document into a collection, while insertMany() is used to insert multiple documents at once. Both methods automatically generate a unique _id if one is not provided.

# What is the _id field in MongoDB?
->_id is the unique identifier for each document in a MongoDB collection. MongoDB automatically creates an ObjectId for _id if we don't provide one. It is used to uniquely identify and efficiently retrieve a document.

# What is the difference between updateOne() and updateMany() in MongoDB?
->updateOne() modifies only the first document that matches the given condition, while updateMany() modifies all documents that match the condition. Both are commonly used with update operators such as $set, $inc, and $unset.

# What is the difference between $set and $inc in MongoDB?
->$set is used to assign or update a field with a specific value, while $inc is used to increase or decrease a numeric field by a specified amount.

# What is the difference between deleteOne() and deleteMany() in MongoDB?
->deleteOne() removes only the first document that matches the specified condition, while deleteMany() removes all documents that match the condition. Both methods permanently remove the matching documents from the collection.

# What is the difference between $push and $addToSet in MongoDB?
->$push adds an element to an array even if the element already exists, while $addToSet adds an element only if it doesn't already exist, preventing duplicates.

# What is an index in MongoDB?
->An index is a data structure that improves the speed of query operations by allowing MongoDB to find documents without scanning the entire collection. However, indexes require additional storage and can make insert and update operations slightly slower.

# What is a compound index in MongoDB?
->A compound index is an index created on multiple fields. It improves query performance when queries frequently filter or sort using those fields.

# What is the difference between COLLSCAN and IXSCAN in MongoDB?
->COLLSCAN means MongoDB scans the entire collection to find matching documents, while IXSCAN means MongoDB uses an index to find the matching documents. IXSCAN is generally faster for suitable queries because it avoids scanning every document.

# What is the MongoDB aggregation pipeline?
->The MongoDB aggregation pipeline is a framework used to process, transform, and analyze documents through multiple stages. Each stage performs an operation such as filtering, grouping, sorting, or projecting data.

Common stages include $match, $group, $sort, $project, $limit, and $unwind.

# What is the difference between $match and $group in MongoDB aggregation?
->$match is used to filter documents based on a condition, similar to the WHERE clause in SQL. $group is used to group documents based on a field and perform calculations such as $sum, $avg, $min, and $max.

# What is $unwind in MongoDB?
->$unwind is an aggregation stage used to deconstruct an array field, creating a separate document for each element in the array. It is commonly used when we need to process or analyze individual array elements.

# What is $lookup in MongoDB?
->$lookup is an aggregation stage used to combine documents from two different collections, similar to a JOIN in SQL. It matches a field from one collection with a related field in another collection and returns the matching documents as an array.

# What is the difference between embedding and referencing in MongoDB?
->Embedding stores related data inside the same document, while referencing stores related data in separate documents or collections and connects them using an identifier. Embedding is preferred for small, closely related data, while referencing is better for large, shared, or frequently changing data.

# What is the difference between embedding and referencing in MongoDB?
->Embedding means storing related data directly inside the same document. Referencing means storing related data separately and connecting the documents using an identifier such as ObjectId.

Embedding: Best for small, closely related data that is usually accessed together.
Referencing: Best for large, shared, or frequently changing data.

# What is the difference between countDocuments() and estimatedDocumentCount() in MongoDB?
->countDocuments() returns the exact number of documents that match a specified filter, while estimatedDocumentCount() returns an estimated total number of documents in a collection and is generally faster because it uses collection metadata.

# What is the difference between drop() and deleteMany() in MongoDB?
->deleteMany() removes documents that match a specified condition but keeps the collection. drop() removes the entire collection, including all its documents and indexes.

# What is a MongoDB transaction?
->A MongoDB transaction allows multiple database operations to execute as a single atomic unit. If all operations succeed, the transaction is committed; if any operation fails, the transaction can be aborted and the changes are rolled back.

# What are ACID properties in MongoDB transactions?

Answer:
ACID stands for Atomicity, Consistency, Isolation, and Durability. These properties ensure that transactions are processed reliably: all operations succeed or fail together, data remains valid, concurrent transactions are isolated appropriately, and committed changes are permanently stored.

# What is schema validation in MongoDB?

Answer:
Schema validation is used to enforce rules on documents in a MongoDB collection. It allows us to specify requirements such as field types, required fields, and allowed values, helping maintain data consistency even though MongoDB has a flexible schema.

# What is the difference between MongoDB and MongoDB Atlas?

Answer:
MongoDB is the database technology itself, while MongoDB Atlas is a fully managed cloud service that allows you to deploy, manage, scale, and monitor MongoDB databases in the cloud without managing the database infrastructure yourself.

# What is MongoDB Atlas?

Answer:
MongoDB Atlas is a fully managed cloud database service for MongoDB. It handles database deployment, scaling, backups, security, and monitoring, allowing developers to use MongoDB without managing the underlying servers and infrastructure.

# What is a replica set in MongoDB?

Answer:
A replica set is a group of MongoDB servers that maintain copies of the same data. It provides high availability and data redundancy. Typically, one node acts as the primary for write operations, while secondary nodes replicate the data and can take over if the primary fails.

# What is the difference between a primary node and a secondary node in a MongoDB replica set?

Answer:
The primary node receives all write operations and maintains the latest data. Secondary nodes replicate data from the primary and can take over as the primary if the current primary fails, providing high availability and redundancy.

# What is sharding in MongoDB?

Answer:
Sharding is a technique used to distribute large amounts of data across multiple servers. It improves horizontal scalability and performance by splitting data into smaller portions called chunks and distributing them across different shards.


# What is the difference between replication and sharding in MongoDB?

Answer:
Replication creates multiple copies of the same data across different servers to provide high availability and data redundancy, while sharding distributes different portions of data across multiple servers to provide horizontal scalability and handle large datasets.

# What is a replica set in MongoDB, and why is it used?

Answer:
A replica set is a group of MongoDB servers that maintain copies of the same data. It is mainly used for high availability, data redundancy, and automatic failover. If the primary server fails, an eligible secondary can be elected as the new primary.

# What is horizontal scaling in MongoDB?

Answer:
Horizontal scaling means adding more servers to distribute data and workload instead of increasing the capacity of a single server. MongoDB achieves horizontal scaling primarily through sharding, which distributes data across multiple servers.

# What is a shard key in MongoDB?

Answer:
A shard key is a field or combination of fields used by MongoDB to distribute documents across different shards in a sharded cluster. Choosing a good shard key is important because it affects data distribution, query performance, and scalability.

# What makes a good shard key in MongoDB?

Answer:
A good shard key should provide high cardinality, good data distribution, and support common query patterns. It should avoid creating a hotspot where most writes are directed to a single shard.

# What is the difference between a replica set and sharding in MongoDB?

Answer:
A replica set maintains multiple copies of the same data across servers for high availability and fault tolerance, while sharding distributes different portions of data across multiple servers for horizontal scaling and handling large datasets

# What is the difference between $push and $addToSet in MongoDB?

Answer:
$push adds a value to an array even if the value already exists, while $addToSet adds the value only if it does not already exist, preventing duplicates.

# What is the difference between skip() and limit() in MongoDB?

Answer:
skip() is used to skip a specified number of documents, while limit() restricts the maximum number of documents returned. They are commonly used together for pagination.

# What is the difference between sort() and limit() in MongoDB?

Answer:
sort() is used to arrange documents in ascending (1) or descending (-1) order, while limit() is used to restrict the number of documents returned.

# What is the difference between $in and $nin in MongoDB?

Answer:
$in selects documents where a field matches any value from a specified list, while $nin selects documents where the field matches none of the specified values

# What is the difference between $and and $or in MongoDB?

Answer:
$and returns documents that satisfy all specified conditions, while $or returns documents that satisfy at least one condition.



Quick comparison

$and->	All conditions must match
$or->	At least one condition must match
$in	->Value exists in given list
$nin->	Value does not exist in given list
$gt	->Greater than
$gte->	Greater than or equal
$lt	->Less than
$lte->	Less than or equal
$ne->	Not equal
insertOne() → inserts one document
insertMany() → inserts multiple documents
updateOne()->	Update first matching document
updateMany()->	Update all matching documents
$set->	Set/change a field
$inc->	Increase/decrease number
$unset->	Remove a field
$push->	Add value to an array
deleteOne() → deletes one document
deleteMany() → deletes multiple documents
db.users.drop()->This removes the collection and all its documents.
$pull->Remove an item from an array
access nexted doc->The . is used to access a nested field.

Projection means selecting which fields you want MongoDB to return.
db.users.find(
    {},
    {
        _id: 0,
        name: 1,
        age: 1
    }
)

1 → include the field
0 → exclude the field

countDocuments()->	Counts matching documents
distinct()->	Returns unique field values
find()	->Returns matching documents
findOne()->	Returns one matching document

$match->	Filter documents
$group->	Group documents
$sort->	Sort results
$limit->	Limit results
$project->	Select/transform fields
$unwind->	Break array elements into documents
$lookup->	Join collections



