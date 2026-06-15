---
draft: false
tags: [LBYCPG2]
title: Entering Queries
date: 2024-10-17, 20:22
---

## Sources

1. Entering Queries (Lecture Slides)

## DBMS

A *database management system* (DBMS) is an application that facilitates the retrieval, storage, and management of data. It provides an interface for users to interact with the database.

### Key Components of DBMS

1. Database engine
2. Database schema
	- Defines the structures found in the database
3. Query Processor
4. Transaction Management
	- Ensures that all operations are done right
5. Concurrency Control
	- Ensures a stable performance when multiple users are accessing the database
6. Data Security Management
	- Authentication component

## RDBMS

### What is MySQL?

*MySQL* is a relational database management system (RDBMS) that provides multi-user access to numerous databases.

SQL is an open source database systems which we can do the following things with:

- Design table structures (i.e. *schema*)
- Add, delete, sort, and manipulate data
- Query database
- Produce lists based on queries

### Getting Started

Find the binary then run it to start the server using `mysqld` (or the *daemon*).

### Connecting to Database

Start the client by typing: `mysql -u root -p`. Press enter when asked a password.

### Commands

| Syntax                                                                                                        | Function                                                                                          |
| ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| SHOW DATABASES;                                                                                               | Shows all the databases                                                                           |
| CREATE DATABASE database_name;                                                                                | Creates a database                                                                                |
| DROP DATABASE database_name;                                                                                  | Drops a database                                                                                  |
| USE databasename;                                                                                             | Use a database                                                                                    |
| SHOW TABLES;                                                                                                  | Lists down all tables in a selected database                                                      |
| CREATE TABLE table_name (<br>  column1 datatype,<br>  column2 datatype<br>);                                  | Creates a new table in the selected database                                                      |
| ALTER TABLE table_name<br>ADD column_name datatype;<br><br>ALTER TABLE table_name<br>DROP COLUMN column_name; | Is used to add, remove, or alter columns in a table. It is also used to add and drop constraints. |
| DROP TABLE table_name;                                                                                        | Drops a table                                                                                     |
| INSERT INTO table_name VALUES(Value1‘,’Value 2‘,…);                                                           | Inserts a record/row in the table                                                                 |
| UPDATE table_name<br>SET column_name = value<br>WHERE conditions<br><br>                                      | Update values in the table                                                                        |

### Choosing the Right Numeric Type

- Numeric Keys for primary keys
- DECIMAL for really large numbers
- DECIMAL for currency to retain accuracy
- Using a number larger than needed results inn inefficiency

## Constraints

Constraints can be specified during the creation of a table, or during an alteration of it.

Syntax:

```
CREATE TABLE table_name (
	column1 datatype constraint,
	column2 datatype constraint
);
```

> [!INFO] Types of Constraints
> 1. `NOT NULL` - Ensures that the column cannot have a NULL value.
> 2. `UNIQUE` - Ensures that all values in a column differ.
> 3. `PRIMARY KEY` - A combination of `NOT NULL` and `UNIQUE` for identification purposes.
> 4. `FOREIGN KEY` - Prevents actions that destroys a link between tables.
> 5. `CHECK` - Ensures that values in a column satisfies a particular condition.
> 6. `DEFAULT` - Sets a default value if none is specified.
> 7. `CREATE INDEX` - For quick creation and retrieval of data.

### UNIQUE Constraint

Syntax:

```
CREATE TABLE table_name (
	column1 datatype constraint,
	column2 datatype constraint,
	UNIQUE (column1)
);
```

Syntax for constraint applied to multiple columns:

```
CREATE TABLE table_name (
	column1 datatype constraint,
	column2 datatype constraint,
	CONSTRAINT constraint_name UNIQUE (column1,column2)
);
```

Syntax for altering tables:

```
ALTER TABLE tablename
ADD UNIQUE (column);
```

```
ALTER TABLE tablename
ADD CONSTRAINT constraint_name UNIQUE (column1, column2);
```

Syntax for dropping a constraint with name:

```
ALTER TABLE table_name
DROP INDEX constraint_name;
```

### PRIMARY KEY Constraint

Syntax:

```
CREATE TABLE table_name (
	column1 datatype NOT NULL,
	column2 datatype constraint,
	PRIMARY KEY (column1)
);
```

Syntax for constraint applied to multiple columns:

```
CREATE TABLE table_name (
	column1 datatype constraint NOT NULL,
	column2 datatype constraint NOT NULL,
	CONSTRAINT constraint_name PRIMARY KEY (column1,column2)
);
```

### FOREIGN KEY

Syntax:

```
CREATE TABLE table1 (
	column1 datatype NOT NULL,
	column2 datatype,
	PRIMARY KEY (column1),
	FOREIGN KEY (column2) REFERENCES table2(column2)
);
```

Syntax for constraint applied to multiple columns:

```
CREATE TABLE table1 (
	column1 datatype NOT NULL,
	column2 datatype,
	PRIMARY KEY (column1),
	CONSTRAINT constraint_name FOREIGN KEY (column2) 
	REFERENCES table2(column2)
);
```

## CHECK Constraint

Syntax:

```
CREATE TABLE table1 (
	column1 datatype, 
	column2 datatype,
	CHECK (column1 operator value) 
);
```

```
CREATE TABLE table1 (
	column1 datatype, 
	column2 datatype,
	CONSTRAINT constraint_name CHECK (column1 operator value1 AND column2 operator value2) 
);
```

## DEFAULT Constraint

```
CREATE TABLE table1 (
	column1 datatype DEFAULT default_value, 
	column2 datatype,
);
```
