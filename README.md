# SQL

# PostgreSQL Database Documentation

---

## Database: `sample`

---

### Ranking Functions

- **`RANK()`**  
    Assigns a rank to each row in a result set. Skips ranking for duplicate values.  
    **Example Output:** `1, 2, 2, 4`

- **`DENSE_RANK()`**  
    Assigns a rank to each row without gaps in ranking.  
    **Example Output:** `1, 2, 2, 3`

- **`ROW_NUMBER()`**  
    Assigns a unique rank to each row, ignoring duplicates.  
    **Example Output:** `1, 2, 3, 4`

---

### Common Table Expressions (CTEs)

- **`WITH OrderSummary AS (...)`**  
    Creates a temporary named result set.  
    Aggregates total orders and total spending per customer.  
    The main query joins customers with `OrderSummary`.