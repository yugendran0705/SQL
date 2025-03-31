# SQL

# PostgreSQL Database Documentation

---

## Database: `sample`

---

## **What is a Join?**
- A **JOIN** in SQL is used to combine rows from two or more tables based on a **related column** between them.  
- It allows you to retrieve data from multiple tables in a **single query**.  
--
## **Key Differences**

| **Join Type**     | **Includes**                       | **NULL Values in Missing Matches** |
|-------------------|-----------------------------------|----------------------------------|
| `INNER JOIN`      | Only matching rows                | No NULL values                  |
| `LEFT JOIN`       | All rows from the left table      | NULL for missing right table rows |
| `RIGHT JOIN`      | All rows from the right table     | NULL for missing left table rows  |
| `FULL OUTER JOIN` | All rows from both tables         | NULL for missing matches         |


