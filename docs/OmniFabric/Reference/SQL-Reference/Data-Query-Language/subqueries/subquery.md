# **SUBQUERY**

A subquery is a ``SELECT`` statement within another statement. is a SQL query nested inside a larger query.

Here is an example of a subquery:

```
SELECT * FROM t1 WHERE column1 = (SELECT column1 FROM t2);
```

In this example, `SELECT * FROM t1 ...` is the outer query (or outer statement), and `(SELECT column1 FROM t2)` is the subquery. We say that the subquery is nested within the outer query, and in fact it is possible to nest subqueries within other subqueries, to a considerable depth. A subquery must always appear within parentheses.

The main advantages of subqueries are:

- They allow queries that are structured so that it is possible to isolate each part of a statement.

- They provide alternative ways to perform operations that would otherwise require complex joins and unions.

- Many people find subqueries more readable than complex joins or unions.

A subquery may occur in:

- A SELECT clause
- A FROM clause
- A WHERE clause

For more information, see the reference below:

- [Derived Tables](derived-tables.md)
- [Comparisons Using Subqueries](comparisons-using-subqueries.md)
- [SUBQUERY WITH ANY or SOME](subquery-with-any-some.md)
- [SUBQUERY WITH ALL](subquery-with-all.md)
- [SUBQUERY WITH EXISTS](subquery-with-exists.md)
- [SUBQUERY WITH IN](subquery-with-in.md)

## **Constraints**

OmniFabric does not support selecting multiple columns for the subquery.
