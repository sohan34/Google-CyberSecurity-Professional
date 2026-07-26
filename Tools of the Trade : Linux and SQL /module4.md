# Course 4 — Module 4

## Linux vs. SQL Filtering

In this reading, you'll explore the differences between Linux and SQL as they relate to filtering. You'll also learn that one way to access SQL is through the Linux command line.

## Accessing SQL

There are many interfaces for accessing SQL and many different versions of SQL. One way to access SQL is through the Linux command line.

To access SQL from Linux, type in a command for the version of SQL you want to use. For example, if you want to access SQLite, you can enter:

    sqlite3

After this, any commands typed in the command line will be directed to SQL instead of Linux commands.

## Differences Between Linux and SQL Filtering

Although both Linux and SQL allow you to filter through data, there are some differences that affect which one you should choose.

### Purpose

- Linux filters data in the context of files and directories on a computer system.
  - Used for tasks like searching for specific files, manipulating file permissions, or managing processes.
- SQL filters data within a database management system.
  - Used for querying and manipulating data stored in tables and retrieving specific information based on defined criteria.

### Syntax

- Linux uses various commands and command-line options specific to each filtering tool.
  - Examples: find, sed, cut, grep
- SQL uses Structured Query Language with specific keywords and clauses for filtering data across different databases.
  - Examples: WHERE, SELECT, JOIN

### Structure

SQL offers more structure than Linux, which is more free-form and not as tidy.

For example, if you wanted to access a log of employee login attempts:

- SQL would have each record separated into columns.
- Linux would print the data as a line of text without this organization.

As a result, selecting a specific column to analyze is easier and more efficient in SQL.

### Joining Tables

Some security-related decisions require information from different tables.

- SQL allows the analyst to join multiple tables together when returning data.
- Linux does not have that same functionality; it does not allow data to be connected to other information on your computer.

This is more restrictive for an analyst going through security logs.

### Best Uses

As a security analyst, it is important to understand when you can use which tool.

- A lot of cybersecurity data will be stored in a database format that works with SQL.
- Other logs might be in a format that is not compatible with SQL.
- If the data is stored in a text file, you cannot search through it with SQL.

In those cases, it is useful to know how to filter in Linux.

### Key Takeaways

- Linux filtering focuses on managing files and directories on a system.
- SQL filtering focuses on structured data manipulation within databases.
- To work with SQL, you can access it from multiple interfaces, including the Linux command line.
- Both SQL and Linux allow you to filter for specific data, but SQL offers the advantages of structuring the data and joining data from multiple tables.

---

## Why We Use a Ready-Made Database

Creating your own database from scratch is like building a car instead of just learning how to drive one.

It is difficult because you would need to manually set up:

- How information is stored
- How to keep it from getting lost
- How to make sure the computer can find specific data quickly

Instead of spending weeks building that complicated engine, this course uses the Chinook database so you can focus on learning how to ask questions and get answers from data.

---

## Basic SQL Query

There are two essential keywords in any SQL query:

- SELECT
- FROM

You will use these keywords every time you want to query a SQL database.

Using them together helps SQL identify:

- What data you need from a database
- What table you are returning it from

Example query:

    SELECT employee_id, device_id
    FROM employees;

The Chinook database is used in readings and quizzes for this course. It includes data that might be created at a digital media company.

The database contains eleven tables, including:

- employees
- customers
- invoices

These tables include data such as names and addresses.

Example query using the customers table:

    SELECT customerid, city, country
    FROM customers;

### SELECT

The SELECT keyword indicates which columns to return.

Examples:

    SELECT customerid

    SELECT customerid, city

If you want to return all columns in a table, you can use an asterisk:

    SELECT *

**Note:** Although the tables in this course are relatively small, using SELECT * may not be advisable when working with large databases and tables because the output may be difficult to understand and might be slow to run.

### FROM

The FROM keyword indicates which table to query.

Example:

    SELECT *
    FROM customers;

A semicolon (;) tells SQL that the query is complete.

**Note:** Line breaks are not required in SQL, but they are often used to make queries easier to understand. You can also write the query on one line as:

    SELECT * FROM customers;

### ORDER BY

Database tables are often very complicated, and ORDER BY helps organize the data you extract from a table.

ORDER BY sequences the records returned by a query based on a specified column or columns.

It can sort in either:

- Ascending order
- Descending order

#### Sorting in Ascending Order

By default, ORDER BY sorts in ascending order.

Example:

    SELECT customerid, city, country
    FROM customers
    ORDER BY city;

This means:

- If the column contains numeric data, the output is sorted from smallest to largest.
- If the column contains alphabetic data, the records are ordered from A to Z.

#### Sorting in Descending Order

You can use DESC with ORDER BY to sort in descending order.

- DESC stands for descending.
- It sorts numbers from largest to smallest.
- It sorts alphabetically from Z to A.

Example:

    SELECT customerid, city, country
    FROM customers
    ORDER BY city DESC;

Now, cities at the end of the alphabet are listed first.

#### Sorting Based on Multiple Columns

You can also choose multiple columns to order by.

Example:

    SELECT customerid, city, country
    FROM customers
    ORDER BY country, city;

This sorts first by country and then by city for rows with the same country.

### Key Takeaways

- SELECT indicates which columns to return.
- FROM indicates which table to query.
- ORDER BY organizes query output.
- These foundational SQL skills support more advanced queries.

---

## Filtering with WHERE, LIKE, and Wildcards

Previously, you explored how to refine SQL queries using the WHERE clause to filter results. In this reading, you'll further explore how to use WHERE, the LIKE operator, the percentage sign (%) wildcard, and the underscore (_) wildcard.

### How Filtering Helps

As a security analyst, you will often work with very large and complicated security logs. To find the information you need, you will often need to use SQL to filter logs.

In a cybersecurity context, you might use filters to find:

- Login attempts of a specific user
- Login attempts made at the time of a security issue
- Devices running a specific version of an application

### WHERE

To create a filter in SQL, you need to use the keyword WHERE.

WHERE indicates the condition for a filter.

Example:

    SELECT firstname, lastname, title, email
    FROM employees
    WHERE title = 'IT Staff';

Rather than returning all records in the employees table, this clause returns only those with IT Staff in the title column.

WHERE uses the equals sign (=) to set the condition.

**Note:** Place the semicolon where the query ends. When you add a filter to a basic query, the semicolon goes after the filter.

### Filtering for Patterns

You can also filter based on a pattern.

Filtering for a pattern requires:

- A wildcard
- The LIKE operator

### Wildcards

A wildcard is a special character that can be substituted with any other character.

Two useful wildcards are:

- % — substitutes for any number of other characters
- _ — substitutes for one other character

Wildcards can be placed:

- After a string
- Before a string
- In both locations

Examples using the string a:

| Pattern | Possible Results |
|---|---|
| a% | apple123, art, a |
| a_ | as, an, a7 |
| a__ | ant, add, a1c |
| %a | pizza, Z6ra, a |
| _a | ma, 1a, Ha |
| %a% | Again, back, a |
| _a_ | Car, ban, ea7 |

### LIKE

To apply wildcards to a filter, you use the LIKE operator instead of =.

LIKE is used with WHERE to search for a pattern in a column.

Example:

    SELECT lastname, firstname, title, email
    FROM employees
    WHERE title LIKE 'IT%';

This returns records where the title column starts with IT, such as:

- IT Staff
- IT Manager

Another example:

    SELECT firstname, lastname, state, country
    FROM customers
    WHERE state LIKE 'N_';

This returns records with state abbreviations that follow the pattern N_, such as:

- NY
- NV
- NS
- NT

### Key Takeaways

- WHERE is an essential keyword for adding a filter to a query.
- You can filter for patterns by combining LIKE with wildcards.
- % matches any number of characters.
- _ matches one character.

---

## Logical Operators: AND, OR, and NOT

Previously, you explored how to add filters containing the AND, OR, and NOT operators to SQL queries. These are all logical operators.

### AND

AND is used to filter on two conditions.

Both conditions must be met simultaneously.

Example:

    SELECT firstname, lastname, email, country, supportrepid
    FROM customers
    WHERE supportrepid = 5 AND country = 'USA';

This returns customers who are both:

- Handled by support representative 5
- Located in the USA

### OR

OR connects two conditions, and either condition can be met.

It returns results where:

- The first condition is true
- The second condition is true
- Or both are true

Example:

    SELECT firstname, lastname, email, country
    FROM customers
    WHERE country = 'Canada' OR country = 'USA';

This returns all customers in either Canada or the USA.

**Note:** Even if both conditions are based on the same column, you still need to write both full conditions.

### NOT

NOT works on a single condition and negates it.

SQL returns all records that do not match the condition.

Example:

    SELECT firstname, lastname, email, country
    FROM customers
    WHERE NOT country = 'USA';

This returns every entry where the customers are not from the USA.

**Pro Tip:** Another way to find values that are not equal to a certain value is by using <> or !=.

Examples:

- WHERE country <> 'USA'
- WHERE country != 'USA'

These are the same as:

    WHERE NOT country = 'USA'

### Combining Logical Operators

Logical operators can be combined in filters.

Example:

    SELECT firstname, lastname, email, country
    FROM customers
    WHERE NOT country = 'Canada' AND NOT country = 'USA';

### Key Takeaways

- AND requires both conditions to be true.
- OR requires either one or both conditions to be true.
- NOT negates a condition.
- Logical operators can be combined to create more specific queries.

---

## SQL Joins

Previously, you explored SQL joins and how to use them to join data from multiple tables when those tables share a common column. You also examined how there are different types of joins, and each returns different rows from the tables being joined.

### Inner Joins

An INNER JOIN returns rows matching on a specified column that exists in more than one table.

It only returns rows where there is a match, but like other joins, it returns all specified columns from all joined tables.

If you use SELECT *, all columns in both tables are returned.

**Note:** If a column exists in both tables, it is returned twice when SELECT * is used.

#### Syntax of an Inner Join

    SELECT *
    FROM employees
    INNER JOIN machines ON employees.device_id = machines.device_id;

You must specify:

- The first or left table after FROM
- The second or right table after INNER JOIN

After the right table, use ON and = to indicate the column used for the join.

It is important to specify both the table and column names by placing a period (.) between them.

You can also select only certain columns:

    SELECT username, operating_system, employees.device_id
    FROM employees
    INNER JOIN machines ON employees.device_id = machines.device_id;

In this example:

- username and operating_system appear in only one table, so only the column name is needed.
- device_id appears in both tables, so you need to specify the table name as well.

### Outer Joins

Outer joins expand what is returned from a join. Each type of outer join returns all rows from one or both tables.

### Left Joins

LEFT JOIN returns all records of the first table, but only returns rows of the second table that match on a specified column.

#### Syntax of a Left Join

    SELECT *
    FROM employees
    LEFT JOIN machines ON employees.device_id = machines.device_id;

Because employees is the left table, all of its records are returned. Only matching records are returned from machines.

### Right Joins

RIGHT JOIN returns all records of the second table, but only returns rows from the first table that match on a specified column.

#### Syntax of a Right Join

    SELECT *
    FROM employees
    RIGHT JOIN machines ON employees.device_id = machines.device_id;

This returns all records from machines, which is the second or right table. Only matching records are returned from employees, which is the first or left table.

**Note:** You can use LEFT JOIN and RIGHT JOIN to return the exact same results if you reverse the order of the tables.

Example:

    SELECT *
    FROM machines
    RIGHT JOIN employees ON employees.device_id = machines.device_id;

### Full Outer Joins

FULL OUTER JOIN returns all records from both tables.

You can think of it as completely merging two tables.

#### Syntax of a Full Outer Join

    SELECT *
    FROM employees
    FULL OUTER JOIN machines ON employees.device_id = machines.device_id;

The order of tables does not change the results of a FULL OUTER JOIN.

### Key Takeaways

- INNER JOIN returns only matching records.
- LEFT JOIN returns all records from the first or left table.
- RIGHT JOIN returns all records from the second or right table.
- FULL OUTER JOIN returns all records from both tables.
- Joins are useful when working with related data stored across multiple tables.

---

## Terms and Definitions — Course 4, Module 4

| Term | Definition |
|---|---|
| Database | An organized collection of information or data |
| Date and time data | Data representing a date and/or time |
| Exclusive operator | An operator that does not include the value of comparison |
| Filtering | Selecting data that match a certain condition |
| Foreign key | A column in a table that is a primary key in another table |
| Inclusive operator | An operator that includes the value of comparison |
| Log | A record of events that occur within an organization's systems |
| Numeric data | Data consisting of numbers |
| Operator | A symbol or keyword that represents an operation |
| Primary key | A column where every row has a unique entry |
| Query | A request for data from a database table or a combination of tables |
| Relational database | A structured database containing tables that are related to each other |
| String data | Data consisting of an ordered sequence of characters |
| SQL (Structured Query Language) | A programming language used to create, interact with, and request information from a database |
| Syntax | The rules that determine what is correctly structured in a computing language |
| Wildcard | A special character that can be substituted with any other character |
