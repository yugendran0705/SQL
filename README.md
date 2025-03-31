# SQL

# PostgreSQL Database Documentation

---

## Database: `sample`

---

### Nested Queries

Nested queries, also known as subqueries, are queries embedded within another SQL query. They are used to perform operations that depend on the results of another query. A nested query is enclosed in parentheses and can be used in SELECT, INSERT, UPDATE, or DELETE statements.

#### Example:

```sql
-- Find customers who have placed more than one order
SELECT name, email
FROM customers
WHERE id IN (
    SELECT customer_id
    FROM orders
    GROUP BY customer_id
    HAVING COUNT(*) > 1
);
```

#### Key Points:
- Subqueries can return a single value (scalar), a list of values, or a table.
- They can be used in various clauses like WHERE, HAVING, or FROM.
- Proper indexing can improve the performance of queries involving subqueries.

Nested queries are a powerful tool for solving complex problems in SQL.
