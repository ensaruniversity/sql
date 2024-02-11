Transactions in SQL are critical for maintaining the integrity of data within relational databases. They allow multiple database operations to be executed as a single unit of work, ensuring that either all operations within the transaction are completed successfully or none of them are applied if an error occurs. This is essential for preserving the consistency and reliability of your database.

### Key Concepts of Transactions

- **Atomicity**: Ensures that all operations within a transaction block are treated as a single unit, which either completely succeeds or fails.
- **Consistency**: Guarantees that a transaction takes the database from one valid state to another valid state.
- **Isolation**: Ensures that transactions occur independently without interference. The effects of an incomplete transaction are not visible to other transactions.
- **Durability**: Ensures that the results of a transaction are permanently stored in the database, even in the event of a system failure.

### Basic SQL Transaction Commands

#### BEGIN TRANSACTION

- **Usage**: Marks the starting point of an explicit transaction.
- **Syntax**:
  ```sql
  BEGIN TRANSACTION;
  ```
- **Example**:
  ```sql
  BEGIN TRANSACTION;
  ```
  This command starts a new transaction.

#### COMMIT

- **Usage**: Used to save all changes made during the current transaction.
- **Syntax**:
  ```sql
  COMMIT;
  ```
- **Example**:
  ```sql
  COMMIT;
  ```
  This command saves the changes made during the transaction to the database.

#### ROLLBACK

- **Usage**: Used to undo all changes made during the current transaction.
- **Syntax**:
  ```sql
  ROLLBACK;
  ```
- **Example**:
  ```sql
  ROLLBACK;
  ```
  This command undoes all changes made during the current transaction, returning the database to its state before the transaction began.

### Transaction Isolation Levels

SQL standards define four levels of transaction isolation that control the degree to which the transactions are isolated from each other:
- **READ UNCOMMITTED**: Allows transactions to read uncommitted changes from other transactions.
- **READ COMMITTED**: Allows transactions to read only committed changes, preventing dirty reads.
- **REPEATABLE READ**: Ensures that if a transaction reads a record twice, it will get the same data each time, preventing non-repeatable reads.
- **SERIALIZABLE**: The highest level of isolation. Transactions are executed with full isolation from one another, preventing dirty reads, non-repeatable reads, and phantom reads.

### Practical Example

Consider a banking application where you need to transfer money from one account to another. This operation involves two steps: deducting an amount from one account and adding it to another. Using transactions ensures that both operations succeed or fail together, preserving the accuracy of account balances.

```sql
BEGIN TRANSACTION;

UPDATE accounts SET balance = balance - 100 WHERE account_id = 1;
UPDATE accounts SET balance = balance + 100 WHERE account_id = 2;

COMMIT;
```

In this example, if either `UPDATE` statement fails, the transaction can be rolled back to prevent one account from being debited without crediting the other, thus maintaining the integrity of the data.

Understanding and effectively using transactions is essential for developers working with relational databases, especially in applications requiring high levels of data integrity and consistency.