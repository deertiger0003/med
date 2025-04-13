# DBMS Project Documentation

## Project Overview
This project implements a web-based interface for performing basic database operations (INSERT, UPDATE, DELETE, SELECT) through a user-friendly form interface.

## Features Implemented
1. **Form-based SQL Query Generation**
   - INSERT operation form
   - UPDATE operation form
   - DELETE operation form
   - SELECT operation form

2. **User Interface Components**
   - Tabbed interface for different operations
   - Input validation
   - Success/error notifications
   - Loading states
   - Form reset functionality

3. **Query Generation**
   - Dynamic SQL query generation based on form inputs
   - Proper SQL syntax handling
   - Support for optional clauses (WHERE, ORDER BY)

## Database Schema
The forms are designed to work with any database table structure. For demonstration purposes, here's an example schema:

```sql
-- Example Table: customers
CREATE TABLE customers (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    email VARCHAR(100),
    phone VARCHAR(20),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## Form Fields and SQL Mapping

### INSERT Operation
- Table Name: Specifies target table
- Columns: Comma-separated column names
- Values: Comma-separated values matching columns
```sql
-- Example Generated Query
INSERT INTO customers (name, email, phone) VALUES ('John Doe', 'john@example.com', '1234567890');
```

### UPDATE Operation
- Table Name: Specifies target table
- SET Clause: Column-value pairs to update
- WHERE Clause: Condition for update
```sql
-- Example Generated Query
UPDATE customers SET name = 'John Smith', email = 'john.smith@example.com' WHERE id = 1;
```

### DELETE Operation
- Table Name: Specifies target table
- WHERE Clause: Condition for deletion
```sql
-- Example Generated Query
DELETE FROM customers WHERE id = 1;
```

### SELECT Operation
- Columns: Columns to select (* for all)
- Table Name: Source table
- WHERE Clause: Filter condition (optional)
- ORDER BY: Sorting criteria (optional)
```sql
-- Example Generated Query
SELECT * FROM customers WHERE name LIKE '%John%' ORDER BY created_at DESC;
```

## Implementation Details
1. **Frontend**
   - Built with Next.js and React
   - Uses shadcn/ui components for UI
   - Implements form validation and error handling
   - Shows real-time feedback for operations

2. **Query Generation**
   - Dynamically constructs SQL queries
   - Handles optional clauses
   - Validates input before query generation

## Future Enhancements
1. Database connection implementation
2. Query execution and results display
3. Advanced query building (JOINs, subqueries)
4. Query history and favorites
5. Export functionality for generated queries

## Demo Instructions
1. Navigate to the Database Operations page
2. Select an operation type (INSERT, UPDATE, DELETE, SELECT)
3. Fill in the required fields
4. Submit the form to generate the SQL query
5. View the generated query in the success notification

## Technical Requirements
- Node.js
- Next.js
- React
- shadcn/ui components
- SQL database (for future implementation) 