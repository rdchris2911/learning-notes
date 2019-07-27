# ACID

See:

- [ACID (computer science)](https://en.wikipedia.org/wiki/ACID_(computer_science))

ACID = acronym describing four properties that transactions in relational database must have

Also provided to some extent by some NoSQL or NewSQL databases

The four ACID properties:

- *Atomicity*: 
  - A transaction is treated as a single unit that either succeeds completely or fails completely. If some operation fails as part of a transaction, the entire transaction is rolled back, including the changes that other operations may have performed in the same transaction. The system must guarantee this in every situation, even if the system crashes right after a transaction is successfully committed.
- *Consistency*: 
  - The execution of the transaction must bring the database to a valid state, respecting the database’s schema
  - Example: no matter how many concurrent transactions are executing, you will never be able to set a foreign key from a row to another row that does not exist (but maybe did exist when you retrieved your data)
- *Isolation*: 
  - Although multiple transactions may be running concurrently, their effects on each other’s execution are limited. 
  - Relational database systems typically provide multiple isolation levels, where higher levels protect against more concurrency-induced phenomena than lower levels. For more details, see [transaction isolation levels](./Transaction-isolation-levels).
- *Durability*: 
  - Once a transaction has been successfully committed, it will remain so, even if the system crashes, power is shut off, etc. right after the transaction has completed.