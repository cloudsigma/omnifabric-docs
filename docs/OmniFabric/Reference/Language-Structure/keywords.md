# Keywords

This chapter describes the keywords for OmniFabric. Reserved and non-reserved keywords are categorized in OmniFabric. When you use SQL statements, you can consult both reserved and non-reserved keywords.

**Keywords** are words in SQL statements that have special meanings, such as `SELECT`, `UPDATE`, `DELETE`, and so on.

- **Reserved keyword**: A word in a keyword that requires special processing to be used as an identifier. It is called a reserved keyword.

   When using the reserved keyword as an identifier, you must wrap it in back quotes, otherwise an error will occur:

   ```
   \\Failure to wrap the reserved keyword select in backquotes produces an error
   mysql> CREATE TABLE select (a INT);
   ERROR 1064 (HY000): SQL parser error: You have an error in your SQL syntax; check the manual that corresponds to your OmniFabric server version for the right syntax to use. syntax error at line 1 column 19 near " select (a INT)";

   \\Correctly wrap the reserved keyword select in backquotes
   mysql> CREATE TABLE `select` (a INT);
   Query OK, 0 rows affected (0.02 sec)
   ```

- **Non-reserved keywords**: Keywords can be used directly as identifiers and are called non-reserved keywords.

   When using non-reserved keywords as identifiers, you can use them directly without wrapping them in back quotes.

   ```
   \\ACCOUNT is a non-reserved keyword that can be wrapped without backquotes
   mysql> CREATE TABLE `select` (ACCOUNT int);
   Query OK, 0 rows affected (0.01 sec)
   ```

!!! note
   Unlike MySQL, in OmniFabric, if the qualifier \*.* is used, the reserved keyword also generates an error if it is not wrapped in back quotes. It is recommended to avoid using the reserved keyword when creating tables and databases:

   ```
   mysql> CREATE TABLE test.select (ACCOUNT int);
   ERROR 1064 (HY000): SQL parser error: You have an error in your SQL syntax; check the manual that corresponds to your OmniFabric server version for the right syntax to use. syntax error at line 1 column 24 near "select (ACCOUNT int)";
   ```

The following list shows reserved and non-reserved keywords in OmniFabric, where those that are not keywords in MySQL are marked with **(M)**.

## Reserve Keywords

### A

- ADD
- ALL
- ALTER
- ANALYZE
- AND
- AS
- ASC

### B

- BEGIN
- BETWEEN
- BINARY
- BOTH
- BY

### C

- CALL
- CASE
- CHANGE
- CHAR
- CHARACTER
- CHECK
- COLLATE
- COLUMN
- CONFIG **(M)**
- CONSTRAINT
- CONVERT
- CREATE
- CROSS
- CURRENT_DATE
- CURRENT_ROLE **(M)**
- CURRENT_TIME
- CURRENT_TIMESTAMP
- CURRENT_USER

### D

- DATABASE
- DATABASES
- DAY_HOUR
- DAY_MICROSECOND
- DAY_MINUTE
- DAY_SECOND
- DECLARE
- DEFAULT
- DELAYED
- DELETE
- DENSE_RANK
- DESC
- DESCRIBE
- DISTINCT
- DIV
- DROP

### E

- ELSE
- ELSEIF
- ENCLOSED
- END
- ESCAPE
- ESCAPED
- EXCEPT
- EXISTS
- EXPLAIN

### F

- FALSE **(M)**
- FOR
- FORCE
- FOREIGN
- FROM
- FULLTEXT
- FUNCTION

### G

- GROUP
- GROUPS

### H

- HAVING
- HIGH_PRIORITY
- HOUR_MICROSECOND
- HOUR_MINUTE
- HOUR_SECOND

### I

- IF
- IGNORE
- ILIKE **(M)**
- IN
- INDEX
- INFILE
- INNER
- INOUT
- INSERT
- INT1
- INT2
- INT3
- INT4
- INT8
- INTERSECT
- INTERVAL
- INTO
- IS
- ITERATE

### J

- JOIN

### K

- KEY
- KILL

### L

- LEADING
- LEAVE
- LEFT
- LIKE
- LIMIT
- LINES
- LOAD
- LOCALTIME
- LOCALTIMESTAMP
- LOCK
- LOOP
- LOW_PRIORITY

### M

- MATCH
- MAXVALUE
- MINUS **(M)**
- MINUTE_MICROSECOND
- MINUTE_SECOND
- MOD

### N

- NATURAL
- NOT
- NULL

### O

- ON
- OPTIONALLY
- OR
- ORDER
- OUT
- OUTER
- OUTFILE
- OVER

### P

- PARTITION
- PRIMARY

### Q

- QUICK

### R

- RANK
- RECURSIVE
- REFERENCES
- REGEXP
- RENAME
- REPEAT
- REPLACE
- REQUIRE
- RIGHT
- RLIKE
- ROW
- ROW_NUMBER
- ROWS

### S

- SCHEMA
- SCHEMAS
- SECOND_MICROSECOND
- SELECT
- SEPARATOR
- SET
- SHOW
- SQL_BIG_RESULT
- SQL_BUFFER_RESULT
- SQL_SMALL_RESULT
- SSL
- STARTING
- STRAIGHT_JOIN

### T

- TABLE
- TEMPORARY
- TERMINATED
- THEN
- TO
- TRAILING
- TRUE **(M)**

### U

- UNION
- UNIQUE
- UNTIL
- UPDATE
- USAGE
- USE
- USING
- UTC_DATE
- UTC_TIME
- UTC_TIMESTAMP

### V

- VALUES

### W

- WHEN
- WHERE
- WHILE
- WITH

### X

- XOR

### Y

- YEAR_MONTH

### _

- _BINARY **(M)**

## Non-Reserved Keywords

### A

- ACCOUNT
- ACCOUNTS **(M)**
- ACTION
- ADMIN_NAME **(M)**
- AFTER
- AGAINST
- ALGORITHM
- ANY
- ASCII
- ATTRIBUTE
- AUTO_INCREMENT
- AUTO_RANDOM **(M)**
- AUTOEXTEND_SIZE
- AVG_ROW_LENGTH

### B

- BACKEND **(M)**
- BACKUP
- BIGINT
- BINDINGS **(M)**
- BIT
- BLOB
- BOOL
- BOOLEAN
- BSI **(M)**
- BTREE

### C

- CANCEL **(M)**
- CASCADE
- CASCADED
- CHAIN
- CHARSET
- CHECKSUM
- CIPHER
- CLIENT
- CLUSTER **(M)**
- COALESCE
- COLLATION
- COLUMN_FORMAT
- COLUMN_NUMBER **(M)**
- COLUMNS
- COMMENT
- COMMIT
- COMMITTED
- COMPACT
- COMPRESSED
- COMPRESSION
- CONNECT **(M)**
- CONNECTION
- CONNECTOR **(M)**
- CONNECTORS **(M)**
- CONSISTENT
- COPY **(M)**
- CREDENTIALS **(M)**
- CURRENT
- CYCLE **(M)**

### D

- DAEMON **(M)**
- DATA
- DATE
- DATETIME
- DAY
- DEALLOCATE
- DECIMAL
- DEFINER
- DELAY_KEY_WRITE
- DIRECTORY
- DISABLE
- DISCARD
- DISK
- DO
- DOUBLE
- DRAINER **(M)**
- DUPLICATE
- DYNAMIC

### E

- ENABLE
- ENCRYPTION
- ENFORCED
- ENGINE
- ENGINE_ATTRIBUTE
- ENGINES
- ENUM
- ERRORS
- EVENT
- EVENTS
- EXCLUSIVE **(M)**
- EXECUTE
- EXPANSION **(M)**
- EXPIRE
- EXTENDED
- EXTENSION
- EXTERNAL **(M)**

### F

- FAILED_LOGIN_ATTEMPTS
- FIELDS
- FILE
- FILESYSTEM **(M)**
- FILL **(M)**
- FIRST
- FIXED
- FLOAT
- FOLLOWING
- FORCE_QUOTE **(M)**
- FORMAT
- FULL

### G

- GEOMETRY
- GEOMETRYCOLLECTION
- GLOBAL
- GRANT
- GRANTS

### H

- HANDLER
- HASH
- HEADER **(M)**
- HISTORY
- HOUR

### I

- IDENTIFIED
- IMPORT
- INCREMENT **(M)**
- INDEXES
- INLINE **(M)**
- INPLACE **(M)**
- INSERT_METHOD
- INSTANT **(M)**
- INT
- INTEGER
- INVISIBLE
- INVOKER
- ISOLATION
- ISSUER
- IVFFLAT **(M)**

### J

- JSON
- JSONTYPE **(M)**

### K

- KEY_BLOCK_SIZE
- KEYS

### L

- LANGUAGE
- LAST
- LESS
- LEVEL
- LINEAR
- LINESTRING
- LIST
- LISTS **(M)**
- LOCAL
- LOCKS
- LONGBLOB
- LONGTEXT
- LOW_CARDINALITY **(M)**

### M

- MANAGE **(M)**
- MASTER
- MAX_CONNECTIONS_PER_HOUR
- MAX_FILE_SIZE **(M)**
- MAX_QUERIES_PER_HOUR
- MAX_ROWS
- MAX_UPDATE_PER_HOUR **(M)**
- MAX_USER_CONNECTIONS
- MEDIAN **(M)**
- MEDIUMBLOB
- MEDIUMINT
- MEDIUMTEXT
- MEMORY
- MERGE
- MICROSECOND
- MIN_ROWS
- MINUTE
- MINVALUE **(M)**
- MODE
- MODIFY
- MODUMP **(M)**
- MONTH
- MULTILINESTRING
- MULTIPOINT
- MULTIPOLYGON
- MYSQL_COMPATIBILITY_MODE **(M)**

### N

- NAMES
- NCHAR
- NEVER
- NEXT
- NO
- NODE **(M)**
- NONE
- NULLS
- NUMERIC

### O

- OFFSET
- ONLY
- OP_TYPE **(M)**
- OPEN
- OPTIMIZE
- OPTION
- OPTIONAL
- OWNERSHIP **(M)**

### P

- PACK_KEYS
- PARALLEL **(M)**
- PARALLELISM **(M)**
- PARSER
- PARTIAL
- PARTITIONS
- PASSWORD
- PASSWORD_LOCK_TIME
- PAUSE **(M)**
- PERCENT **(M)**
- PERSIST
- PLUGINS
- POINT
- POLYGON
- PRECEDING
- PREPARE
- PREV
- PRIVILEGES
- PROCEDURE
- PROCESSLIST
- PROFILES
- PROPERTIES **(M)**
- PROXY
- PUBLICATION **(M)**
- PUBLICATIONS **(M)**
- PUMP **(M)**

### Q

- QUARTER
- QUERY
- QUERY_RESULT **(M)**

### R

- RANDOM
- RANGE
- READ
- REAL
- REDUNDANT
- REFERENCE
- RELEASE
- RELOAD
- REORGANIZE
- REPAIR
- REPEATABLE
- REPLICATION
- RESET
- RESTRICT
- RESTRICTED **(M)**
- RESUME
- RETURNS
- REUSE
- REVERSE
- REVOKE
- ROLE
- ROLES **(M)**
- ROLLBACK
- ROUTINE
- ROW_COUNT
- ROW_FORMAT
- RTREE

### S

- S3OPTION **(M)**
- SAMPLE **(M)**
- SAN **(M)**
- SECOND
- SECONDARY
- SECONDARY_ENGINE_ATTRIBUTE
- SECURITY
- SEQUENCE **(M)**
- SEQUENCES **(M)**
- SERIALIZABLE
- SERVERS **(M)**
- SESSION
- SHARE
- SHARED **(M)**
- SHUTDOWN
- SIGNED
- SIMPLE
- SLAVE
- SLIDING **(M)**
- SMALLINT
- SNAPSHOT
- SOME
- SOURCE
- SPATIAL
- SQL
- SQL_CACHE
- SQL_NO_CACHE
- SQL_TSI_DAY
- SQL_TSI_HOUR
- SQL_TSI_MINUTE
- SQL_TSI_MONTH
- SQL_TSI_QUARTER
- SQL_TSI_SECOND
- SQL_TSI_WEEK
- SQL_TSI_YEAR
- STAGE **(M)**
- STAGEOPTION **(M)**
- STAGES **(M)**
- START
- STATS_AUTO_RECALC
- STATS_PERSISTENT
- STATS_SAMPLE_PAGES
- STATUS
- STORAGE
- STREAM
- SUBJECT
- SUBPARTITION
- SUBPARTITIONS
- SUBSCRIPTIONS **(M)**
- SUPER
- SUSPEND

### T

- TABLE_NUMBER **(M)**
- TABLE_SIZE **(M)**
- TABLE_VALUES **(M)**
- TABLES
- TABLESPACE
- TASK **(M)**
- TEMPTABLE
- TEXT
- THAN
- TIME
- TIMESTAMP
- TINYBLOB
- TINYINT
- TINYTEXT
- TRANSACTION
- TRIGGER
- TRIGGERS
- TRUNCATE
- TYPE

### U

- UNBOUNDED
- UNCOMMITTED
- UNDEFINED
- UNKNOWN
- UNLOCK
- UNSIGNED
- URL
- USER
- UUID **(M)**

### V

- VALIDATION
- VALUE
- VARBINARY
- VARCHAR
- VARIABLES
- VECF32 **(M)**
- VECF64 **(M)**
- VERBOSE **(M)**
- VIEW
- VISIBLE

### W

- WARNINGS
- WEEK
- WITHOUT
- WORK
- WRITE

### X

- X509

### Y

- YEAR

### Z

- ZEROFILL
- ZONEMAP **(M)**
