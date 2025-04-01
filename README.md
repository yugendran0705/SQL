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

### Window Functions

- **`LAG(price, 1)`**  
    Retrieves the previous order's price for the customer.

- **`LEAD(price, 1)`**  
    Retrieves the next order's price for the customer.

- **`PARTITION BY customer_id`**  
    Ranks orders per customer separately. Orders for each customer are sorted by `price DESC`.
