# SQL

# PostgreSQL Database Documentation

---

## Database: `sample`
---

### Common Table Expressions (CTEs)

- **`WITH OrderSummary AS (...)`**  
    Creates a temporary named result set.  
    Aggregates total orders and total spending per customer.  
    The main query joins customers with `OrderSummary`.

---
### Recursive Query Explanation

1. **Base Case (`manager_id IS NULL`)**  
   - Selects the top-level employee in the hierarchy.  
   - Example: Alice (CEO) is selected because she has no manager (`manager_id IS NULL`).

2. **Recursive Query (`JOIN ON manager_id`)**  
   - Iteratively fetches employees reporting to the previous level.  
   - Example: Finds employees whose `manager_id` matches the `employee_id` of the previous level.

3. **`hierarchy_level + 1`**  
   - Tracks the depth of each employee in the hierarchy.  
   - Example: Alice is at level 1, her direct reports are at level 2, and so on.