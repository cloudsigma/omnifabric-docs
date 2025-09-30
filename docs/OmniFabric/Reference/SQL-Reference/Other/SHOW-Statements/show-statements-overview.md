# SHOW Statements Overview

SHOW statements provide information about databases, tables, columns, and other database objects in OmniFabric. This page lists all available SHOW statements.

## Available SHOW Statements

| Statement | Description |
|-----------|-------------|
| [SHOW ACCOUNTS](show-account.md) | Display information about accounts |
| [SHOW COLLATION](show-collation.md) | Display available collations |
| [SHOW COLUMNS](show-columns.md) | Display column information for tables |
| [SHOW CREATE PUBLICATION](show-create-publication.md) | Display the CREATE statement for publications |
| [SHOW CREATE TABLE](show-create-table.md) | Display the CREATE statement for tables |
| [SHOW CREATE VIEW](show-create-view.md) | Display the CREATE statement for views |
| [SHOW DATABASES](show-databases.md) | Display available databases |
| [SHOW FUNCTION STATUS](show-function-status.md) | Display function status information |
| [SHOW GRANTS](show-grants.md) | Display privilege information for users |
| [SHOW INDEX](show-index.md) | Display index information for tables |
| [SHOW PITRS](show-pitrs.md) | Display Point-in-Time Recovery information |
| [SHOW PROCESSLIST](show-processlist.md) | Display running processes |
| [SHOW PUBLICATIONS](show-publications.md) | Display publication information |
| [SHOW ROLES](show-roles.md) | Display role information |
| [SHOW SEQUENCES](show-sequences.md) | Display sequence information |
| [SHOW STAGE](show-stage.md) | Display stage information |
| [SHOW SUBSCRIPTIONS](show-subscriptions.md) | Display subscription information |
| [SHOW TABLES](show-tables.md) | Display tables in databases |
| [SHOW VARIABLES](show-variables.md) | Display system variable values |

## Usage Pattern

Most SHOW statements follow this general pattern:

```sql
SHOW [statement_type] [FROM database_name] [WHERE condition] [LIKE 'pattern']
```

For specific syntax and examples, click on any statement above to view its detailed documentation.
