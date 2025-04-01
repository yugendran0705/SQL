# SQL

# PostgreSQL Database Documentation

---

## Database: `sample`
---

### Stored Procedures and Functions

Procedures and functions are reusable database objects that encapsulate logic to perform specific tasks or calculations. They help in maintaining modularity and reusability within the database.

- **Procedures**: Typically used to perform actions such as `INSERT`, `UPDATE`, or `DELETE` operations. They can also include complex business logic and support OUT parameters to return values.

- **Functions**: Designed to return a value and are often used in `SELECT` queries. Functions are ideal for calculations, data transformations, or validations.

#### Procedures (CALL)
- Perform actions such as `INSERT`, `UPDATE`, and `DELETE`.

#### Functions (SELECT)
- Return values and can be used in queries.

#### OUT Parameters
- Enable procedures to return values.