Let's delve deeper into querying data in SQL, focusing on the SELECT statement, WHERE clause, and ORDER BY clause, which are fundamental for retrieving and organizing data from databases.

### SELECT Statement

The SELECT statement is used to select data from a database. The data returned is stored in a result table, sometimes called the result-set.

- **Syntax**: 
```sql
SELECT column1, column2, ...
FROM table_name;
```
- **Select All Columns**: 
```sql
SELECT * FROM table_name;
```
  - The asterisk (*) is a wildcard that selects all columns from the table.

- **Example**: 
```sql
SELECT first_name, last_name FROM employees;
```
  - This query selects the `first_name` and `last_name` columns from the `employees` table.

### WHERE Clause

The WHERE clause is used to filter records. It is used to extract only those records that fulfill a specified condition.

- **Syntax**: 
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```
- **Example**: 
```sql
SELECT * FROM employees WHERE department = 'Sales';
```
  - This query selects all columns from the `employees` table where the `department` column has the value 'Sales'.

### ORDER BY Clause

The ORDER BY clause is used to sort the result set in ascending or descending order.

- **Syntax**: 
```sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column1 [ASC|DESC], column2 [ASC|DESC], ...;
```
  - The `ASC` keyword specifies an ascending order (which is the default if no keyword is specified), and `DESC` specifies a descending order.

- **Example**: 
```sql
SELECT first_name, last_name, department FROM employees
ORDER BY department ASC, last_name DESC;
```
  - This query selects the `first_name`, `last_name`, and `department` from the `employees` table, sorting the results first by `department` in ascending order, and then by `last_name` in descending order within each department.

These elements form the basis for retrieving data from SQL databases. Through SELECT statements, you can specify exactly what data you want. The WHERE clause allows for filtering this data based on conditions, and the ORDER BY clause provides a means to sort the results according to specific columns, enhancing the readability and utility of the data retrieved.