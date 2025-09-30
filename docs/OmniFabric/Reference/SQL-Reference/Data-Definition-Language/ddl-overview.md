# Data Definition Language (DDL) Overview

Data Definition Language (DDL) statements are used to define, modify, and manage database schema objects in OmniFabric. This page provides an overview of all available DDL statements organized by category.

## CREATE Statements
Create new database objects.

| Statement | Description |
|-----------|-------------|
| [CREATE DATABASE](create-database.md) | Create a new database |
| [CREATE TABLE](create-table.md) | Create a new table |
| [CREATE TABLE AS SELECT](create-table-as-select.md) | Create table from SELECT query results |
| [CREATE TABLE ... LIKE](create-table-like.md) | Create table with same structure as existing table |
| [CREATE EXTERNAL TABLE](create-external-table.md) | Create external table for accessing external data |
| [CREATE CLUSTER TABLE](create-cluster-table.md) | Create clustered table for improved performance |
| [CREATE DYNAMIC TABLE](create-dynamic-table.md) | Create dynamic table with automatic refresh |
| [CREATE INDEX](create-index.md) | Create index on table columns |
| [CREATE INDEX...USING IVFFLAT](create-index-ivfflat.md) | Create vector index using IVFFLAT |
| [CREATE FULLTEXT INDEX](create-fulltext-index.md) | Create full-text search index |
| [CREATE VIEW](create-view.md) | Create virtual table based on query |
| [CREATE SEQUENCE](create-sequence.md) | Create sequence for generating numbers |
| [CREATE FUNCTION (Python)](create-function-python.md) | Create Python user-defined function |
| [CREATE FUNCTION (SQL)](create-function-sql.md) | Create SQL user-defined function |
| [CREATE PITR](create-pitr.md) | Create Point-in-Time Recovery configuration |
| [CREATE SNAPSHOT](create-snapshot.md) | Create database snapshot |
| [CREATE PUBLICATION](create-publication.md) | Create publication for data replication |
| [CREATE SUBSCRIPTION](create-subscription.md) | Create subscription for data replication |
| [CREATE STAGE](create-stage.md) | Create stage for data loading |
| [CREATE SOURCE](create-source.md) | Create external data source |

## ALTER Statements
Modify existing database objects.

| Statement | Description |
|-----------|-------------|
| [ALTER TABLE](alter-table.md) | Modify table structure and properties |
| [ALTER VIEW](alter-view.md) | Modify view definition |
| [ALTER SEQUENCE](alter-sequence.md) | Modify sequence properties |
| [ALTER PITR](alter-pitr.md) | Modify Point-in-Time Recovery settings |
| [ALTER PUBLICATION](alter-publication.md) | Modify publication settings |
| [ALTER STAGE](alter-stage.md) | Modify stage configuration |
| [ALTER REINDEX](alter-reindex.md) | Rebuild indexes for better performance |

## DROP Statements
Remove existing database objects.

| Statement | Description |
|-----------|-------------|
| [DROP DATABASE](drop-database.md) | Remove database and all its objects |
| [DROP TABLE](drop-table.md) | Remove table and its data |
| [DROP VIEW](drop-view.md) | Remove view |
| [DROP INDEX](drop-index.md) | Remove index |
| [DROP SEQUENCE](drop-sequence.md) | Remove sequence |
| [DROP FUNCTION](drop-function.md) | Remove user-defined function |
| [DROP PITR](drop-pitr.md) | Remove Point-in-Time Recovery configuration |
| [DROP SNAPSHOT](drop-snapshot.md) | Remove database snapshot |
| [DROP PUBLICATION](drop-publication.md) | Remove publication |
| [DROP STAGE](drop-stage.md) | Remove stage |

## Other DDL Statements

| Statement | Description |
|-----------|-------------|
| [TRUNCATE TABLE](truncate-table.md) | Remove all data from table while keeping structure |
| [RENAME TABLE](rename-table.md) | Change table name |
| [RESTORE PITR](restore-pitr.md) | Restore database to specific point in time |
| [RESTORE SNAPSHOT](restore-snapshot.md) | Restore database from snapshot |

## DDL Statement Categories

### Schema Management
- Database and table creation/modification/removal
- Index management for performance optimization
- View management for data abstraction

### Advanced Features
- **Clustering**: Improve query performance with clustered tables
- **External Tables**: Access data from external sources
- **Dynamic Tables**: Automatically refresh materialized views
- **Full-text Search**: Enable text search capabilities
- **Vector Search**: Support for AI/ML vector operations

### Data Replication
- **Publications**: Define what data to replicate
- **Subscriptions**: Subscribe to data changes
- **Stages**: Manage data loading processes

### Backup & Recovery
- **PITR**: Point-in-Time Recovery for precise restoration
- **Snapshots**: Create consistent database backups
- **Restore**: Recover data from backups

### User-Defined Objects
- **Functions**: Create custom Python or SQL functions
- **Sequences**: Generate unique numbers automatically

## Usage Tips

1. **Always backup** before running DDL statements on production data
2. **Use transactions** where supported to ensure atomicity
3. **Check dependencies** before dropping objects
4. **Monitor performance** after creating/dropping indexes
5. **Test DDL scripts** in development environments first
