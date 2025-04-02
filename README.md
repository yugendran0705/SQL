# SQL

# PostgreSQL Database Documentation

---

## Database: `sample`
---

## **Summary of Tables**
- `customers` → Stores customer information.  
- `products` → Stores product information.  
- `orders` → Stores order transactions.  
- `orderdetails` → Stores details of ordered products.

---
## What is Indexing?
Indexing in SQL improves the performance of queries by allowing the database to find and retrieve rows faster. Instead of scanning the entire table, indexes help locate data efficiently.

### `idx_customers_email`
```sql
CREATE INDEX idx_customers_email ON customers(email);
```
Creates an index on the email column of the customers table.

This helps speed up searches based on email, such as login lookups or customer searches.

---
## **What is a Transaction?**
A **transaction** in SQL is a sequence of one or more SQL statements executed as a **single unit of work**. Transactions ensure **data integrity** by following the **ACID** properties:
- **Atomicity**: Either all operations succeed or none are applied.
- **Consistency**: Data remains valid before and after the transaction.
- **Isolation**: Transactions do not interfere with each other.
- **Durability**: Changes persist after a successful transaction.

---

## **Transaction Breakdown**

### 1️**Start a Transaction**
```sql
BEGIN;
```
Begins a new transaction.

Any SQL commands executed after this are part of the transaction.

```sql
INSERT INTO Orders (customer_id, total_amount) 
VALUES (1, 200.00) 
RETURNING id;
```
Creates a new order with customer_id = 1 and total_amount = 200.00.

The RETURNING id; clause fetches the newly created order's id.

### Output:

``` 
id 
----
  1
(1 row)
```

The new order gets id = 1.

```sql
INSERT INTO OrderDetails (order_id, product_id, quantity, price) 
VALUES (1, 2, 1, 200.00);
```
Adds a new entry to OrderDetails:

order_id = 1 (from previous step)

product_id = 2

quantity = 1

price = 200.00

### Output:
```
INSERT 0 1
```
Confirms that one row was successfully inserted.

### Commit the Transaction
```sql
COMMIT;
```
Finalizes the transaction and permanently saves the changes.

### Output:
```
COMMIT
```
Confirms that all changes are committed.

### If an error occurs before COMMIT;, you can undo changes using:

```sql
ROLLBACK;
```
This cancels the transaction, preventing partial inserts.

## Why Use Transactions?
Ensures Data Integrity – If one part fails, no partial data remains.

Prevents Inconsistent Data – Ensures related inserts/updates happen together.

Reduces Risk of Errors – Allows rollback in case of mistakes.

## Difference Between View and Materialized View in SQL

### **View**
- A **view** is a virtual table based on the result of a SQL query.
- It does not store data physically; instead, it fetches data from the underlying tables whenever accessed.
- Views are always up-to-date with the underlying data, as they are dynamically generated.
- Performance can be slower for complex queries since the data is retrieved on demand.

#### Example:
```sql
CREATE VIEW active_customers AS
SELECT * FROM customers WHERE status = 'active';
```
Creates a view to display only active customers.

---

### **Materialized View**
- A **materialized view** is a physical copy of the result of a query stored on disk.
- It stores data physically, which can improve performance for complex queries.
- Materialized views need to be refreshed manually or automatically to reflect changes in the underlying data.
- Useful for scenarios where query performance is critical and data does not change frequently.

#### Example:
```sql
CREATE MATERIALIZED VIEW active_customers_mv AS
SELECT * FROM customers WHERE status = 'active';
```
Creates a materialized view to store active customers.

---

### **Key Differences**
| Feature               | View                        | Materialized View            |
|-----------------------|-----------------------------|------------------------------|
| **Storage**           | No physical storage         | Physically stored on disk    |
| **Performance**       | Slower for complex queries  | Faster for complex queries   |
| **Data Freshness**    | Always up-to-date           | Requires manual/auto refresh |
| **Use Case**          | Dynamic, real-time queries  | Performance-critical queries |


