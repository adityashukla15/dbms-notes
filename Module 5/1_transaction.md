# Transaction
A Transaction is a sequence of one or more database operations that are treated as a single logical unit of work.
A transaction must be completed entirely or not executed at all.Sequence is very important in transaction.
![alt text](image.png)

## ACID PROPERTIES
ACID is a set of four properties that ensure transactions are processed reliably and correctly in a database.
A → Atomicity
C → Consistency
I → Isolation
D → Durability

### ATOMICITY
A transaction must be completed fully or not executed at all.
![alt text](image-1.png)

### CONSISTENCY
A transaction must take the database from one valid state to another valid state.
![alt text](image-2.png)

### ISOLATION
Multiple transactions executing simultaneously should not interfere with each other.
![alt text](image-3.png)

### DURABILITY
Once a transaction is COMMITTED, its changes become permanent.
![alt text](image-4.png)


## Transaction States
A transaction state represents the current status of a transaction during its execution, from the time it starts until it successfully completes or fails.

### Active State
The transaction is currently executing its read and write operations
![alt text](image-5.png)

### Partially Committed State
The transaction has executed all its operations, but the changes are not yet permanently saved in the database.
![alt text](image-6.png)

### Commited State
The transaction has completed successfully and all changes have been permanently saved in the database.
![alt text](image-7.png)

### Failed State
The transaction cannot continue because of an error, crash, hardware failure, software failure, or integrity constraint violation.
![alt text](image-8.png)

### Aborted State
The transaction has been rolled back, and all changes made by it have been undone.
![alt text](image-9.png)

### Terminated State
The transaction has finished execution and leaves the system.
A transaction reaches this state after:
Successful Commit, or
Abort/Rollback
![alt text](image-10.png)


![alt text](image-11.png)

