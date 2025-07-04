# Explore SQL with OmniFabric

OmniFabric is compatible with MySQL, you can use MySQL statements directly in most of the cases. For unsupported features, see [MySQL Compatibility](../Overview/feature/mysql-compatibility.md).

## What is SQL?

The Structured Query Language (SQL) is used to manage a relational database management system (RDBMS). The scope of SQL includes data insertion, query, update, and delete, database schema creation and modification, and data access control.

## How many types SQL does OmniFabric have?

SQL is divided into the following 6 types according to their functions in OmniFabric:

- DDL (Data Definition Language): It is used to define database objects, including databases, tables, and views. Such as `CREATE`, `ALTER`, and `DROP`.

- DML (Data Manipulation Language): It is used to manipulate application related records. Such as `SELECT`, `DELETE`, and `INSERT`.

- DQL (Data Query Language): It is used to query the records after conditional filtering. Such as `SELECT...FROM...[WHERE]`.

- TCL (Transaction Control Language): It is used to manage transactions. Such as `COMMIT`,`ROLLBACK`, or `SET TRANSACTION`.

- DCL (Data Control Language): It is used to define access privileges and security levels. Such as `CREATET ACCOUNT`, `DROP ACCOUNT`, and `GRANT`.

- Other: Other types of management languages ​​in OmniFabric are not directly related to data and are a general term for the acquisition and modification of database parameters and resource allocation. Such as `SHOW`, `SET variable`, and `KILL`.

## Basic SQL about SHOW, CREATE and DROP a database

A database in OmniFabric can be considered as a collection of objects such as tables.

- To show the list of databases, use the `SHOW DATABASES` statement:

```sql
SHOW DATABASES;
```

- To create the database named *dbdemo*, use the `CREATE DATABASE db_name [options];` statement, for example:

```sql
CREATE DATABASE dbdemo;
```

or:

```sql
CREATE DATABASE IF NOT EXISTS dbdemo;
```

Add `IF NOT EXISTS` to prevent an error if the database exists.

- To use the database named *dbdemo*, use the following statement:

```sql
USE dbdemo;
```

- To show all the tables in a database, use the `SHOW TABLES` statement:

```sql
SHOW TABLES FROM dbdemo;
```

- To delete a database, use the `DROP DATABASE` statement:

```sql
DROP DATABASE dbdemo;
```

## Basic SQL about CREATE, SHOW, and DROP a table

- To create a table, use the `CREATE TABLE` statement:

```sql
CREATE TABLE table_name column_name data_type constraint;
```

For example, to create a table named *person* which includes fields such as *number*, *name*, and *birthday*, use the following statement:

```sql
CREATE TABLE person (
    id INT(11),
    name VARCHAR(255),
    birthday DATE
    );
```

- To view the statement that creates the table (DDL), use the `SHOW CREATE` statement:

```sql
SHOW CREATE table person;
```

Expected result:

```sql
+--------+-----------------------------------------------------------------------------------------------------------------+
| Table  | Create Table                                                                                                    |
+--------+-----------------------------------------------------------------------------------------------------------------+
| person | CREATE TABLE `person` (
`id` INT DEFAULT NULL,
`name` VARCHAR(255) DEFAULT NULL,
`birthday` DATE DEFAULT NULL
) |
+--------+-----------------------------------------------------------------------------------------------------------------+
1 row in set (0.01 sec)
```

- To delete a table, use the `DROP TABLE` statement:

```sql
DROP TABLE person;
```

## Basic SQL about INSERT, UPDATE, and DELETE data

Common DML features are adding, modifying, and deleting table records. The corresponding commands are `INSERT`, `UPDATE`, `REPLACE` and `DELETE`.

- To insert data into a table, use the `INSERT` statement:

```sql
INSERT INTO person VALUES(1,'tom','20170912');
```

- To insert a record containing data of some fields into a table, use the `INSERT` statement:

```sql
INSERT INTO person(id,name) VALUES('2','bob');
```

- To update some fields of a record in a table, use the `UPDATE` statement:

```sql
UPDATE person SET birthday='20180808' WHERE id=2;
```

- To replace some field data of table records in the table, use the `UPDATE` statement:

```sql
REPLACE INTO person SET birthday='20180809' WHERE id=2;
```

- To delete the data in a table, use the `DELETE` statement:

```sql
DELETE FROM person WHERE id=2;
```

!!! note
    The `UPDATE` and `DELETE` statements without the `WHERE` clause as a filter operate on the entire table.

## Basic SQL about Query data

DQL is used to retrieve the desired data rows from a table or multiple tables.

- To view the data in a table, use the `SELECT` statement:

```sql
SELECT * FROM person;
```

Expected result:

```sql
+------+------+------------+
| id   | name | birthday   |
+------+------+------------+
|    1 | tom  | 2017-09-12 |
+------+------+------------+
1 row in set (0.00 sec)
```

- To query a specific column, add the column name after the `SELECT` keyword:

```sql
SELECT name FROM person;
+------+
| name |
+------+
| tom  |
+------+
1 rows in set (0.00 sec)
```

Use the `WHERE` clause to filter all records that match the conditions and then return the result:

```sql
SELECT * FROM person where id<5;
```

Expected result:

```sql
+------+------+------------+
| id   | name | birthday   |
+------+------+------------+
|    1 | tom  | 2017-09-12 |
+------+------+------------+
1 row in set (0.00 sec)
```

## Basic SQL about CREATE, GRANT, and DROP a user

`CREATE`, `GRANT`, and `DROP` are usually used to create or delete users, and manage user privileges.

- To create a user, use the `CREATE USER` statement. The following example creates a user named *mouser* with the password *111*:

```sql
> CREATE USER mouser IDENTIFIED BY '111';
Query OK, 0 rows affected (0.10 sec)
```

- To create a role for the user:

```sql
> CREATE ROLE role_r1;
Query OK, 0 rows affected (0.05 sec)
```

- To grant mouser the role_r1:

```sql
> GRANT role_r1 to mouser;
Query OK, 0 rows affected (0.04 sec)
```

- To grant mouser the privilege to create table in the dbdemo database:

```sql
GRANT create table on database * to role_r1;
```

- To check the privileges of mouser:

```sql
> SHOW GRANTS for mouser@localhost;
+-------------------------------------------------------+
| Grants for mouser@localhost                           |
+-------------------------------------------------------+
| GRANT create table ON database * `mouser`@`localhost` |
| GRANT connect ON account  `mouser`@`localhost`        |
+-------------------------------------------------------+
2 rows in set (0.02 sec)
```

You have successfully granted the permission of `create table` in the database to *mouser*.

- To delete mouser:

```sql
DROP USER mouser;
```
