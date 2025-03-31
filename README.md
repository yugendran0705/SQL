# SQL

# PostgreSQL Database Documentation

---

## Database: `sample`

### Users Table
| Column Name  | Data Type      | Constraints               | Description                   |
|--------------|----------------|----------------------------|-------------------------------|
| `id`         | `SERIAL`       | `PRIMARY KEY`              | Unique identifier for each user |
| `name`       | `VARCHAR(100)` | `NOT NULL`                 | Name of the user              |
| `email`      | `VARCHAR(100)` | `UNIQUE NOT NULL`          | Email address (unique)        |
| `age`        | `INT`          |                            | Age of the user               |
| `created_at` | `TIMESTAMP`    | `DEFAULT CURRENT_TIMESTAMP` | Timestamp of record creation  |

---

## Sample Data
```sql
-- Inserting sample data
INSERT INTO users (name, email, age)  
VALUES  
    ('y1', 'y1@gmail.com', 30),  
    ('y2', 'y2@gmail.com', 35),  
    ('y3', 'y3@gmail.com', 28);  
