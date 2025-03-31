# SQL

# PostgreSQL Database Documentation

---

## Database: `sample`

---
## Date and Time Functions

### Common Date and Time Functions

1. **CURRENT_DATE**  
    Returns the current date.  
    Example:  
    ```sql
    SELECT CURRENT_DATE;
    ```

2. **CURRENT_TIME**  
    Returns the current time.  
    Example:  
    ```sql
    SELECT CURRENT_TIME;
    ```

3. **NOW()**  
    Returns the current date and time (timestamp).  
    Example:  
    ```sql
    SELECT NOW();
    ```

4. **AGE(timestamp, timestamp)**  
    Calculates the difference between two timestamps.  
    Example:  
    ```sql
    SELECT AGE('2023-01-01', '2022-01-01');
    ```

5. **DATE_PART(field, source)**  
    Extracts a specific part of a date/time value (e.g., year, month, day).  
    Example:  
    ```sql
    SELECT DATE_PART('year', NOW());
    ```

6. **TO_CHAR(timestamp, format)**  
    Formats a timestamp into a string based on a specified format.  
    Example:  
    ```sql
    SELECT TO_CHAR(NOW(), 'YYYY-MM-DD');
    ```

### Example Usage

```sql
-- Get the current date and time
SELECT CURRENT_DATE AS today, CURRENT_TIME AS current_time;

-- Calculate the age difference between two dates
SELECT AGE('2023-12-31', '2000-01-01') AS age_difference;

-- Extract the month from the current date
SELECT DATE_PART('month', NOW()) AS current_month;

-- Format the current timestamp
SELECT TO_CHAR(NOW(), 'DD Mon YYYY HH24:MI:SS') AS formatted_date;
```
