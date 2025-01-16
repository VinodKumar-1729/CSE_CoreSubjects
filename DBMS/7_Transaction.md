
### 1. **Transaction in DBMS**
- **Definition**: A transaction is a sequence of one or more operations performed as a single logical unit of work, which must satisfy certain properties (ACID) to ensure database consistency.
- **Example**: Transferring money between bank accounts involves debit from one account and credit to another.

---

### 2. **ACID Properties**
- **Atomicity**: Ensures that a transaction is completed entirely or not at all.
- **Consistency**: Guarantees that a transaction brings the database from one valid state to another.
- **Isolation**: Ensures that transactions execute independently without interfering with each other.
- **Durability**: Ensures that the results of a committed transaction are permanent, even in case of a system failure.

---

### 3. **Commit and Rollback**
- **Commit**:
  - A command used to save all the changes made by a transaction permanently to the database.
  - Example: `COMMIT;`
- **Rollback**:
  - A command used to undo all changes made by a transaction.
  - Example: `ROLLBACK;`

---

### 4. **Serializability and Its Importance**
- **Definition**: Serializability is a property of a transaction schedule (sequence) ensuring it is equivalent to a serial schedule, where transactions execute one after another without overlapping.
- **Importance**:
  - Prevents inconsistencies in the database.
  - Guarantees the correctness of concurrent transactions.

---

### 5. **Deadlock**
- **Definition**: A deadlock occurs when two or more transactions wait indefinitely for each other to release resources.
- **Prevention Methods**:
  - **Deadlock Avoidance**:
    - Allocate resources only if they won’t lead to a deadlock.
    - Example: Banker’s Algorithm.
  - **Deadlock Detection**:
    - Regularly check for cycles in the resource allocation graph.
  - **Deadlock Recovery**:
    - Abort one or more transactions to break the cycle.
  - **Timeouts**:
    - Abort a transaction if it waits too long.

---

### 6. **Concurrency Control Protocols**
- **Lock-Based Protocols**:
  - Use locks (shared or exclusive) to manage concurrent access to data.
  - Types:
    - **Shared Lock (S)**: Allows reading.
    - **Exclusive Lock (X)**: Allows reading and writing.
- **Timestamp-Based Protocols**:
  - Assign timestamps to transactions and ensure older transactions are executed first.

---

### 7. **Two-Phase Locking (2PL)**
- **Definition**: A concurrency control protocol that ensures serializability by dividing the transaction execution into two phases:
  - **Growing Phase**: Locks are acquired, and no locks are released.
  - **Shrinking Phase**: Locks are released, and no new locks are acquired.
- **Types**:
  - **Strict 2PL**:
    - All exclusive locks are held until the transaction commits or aborts.
  - **Rigorous 2PL**:
    - All locks (shared and exclusive) are held until the transaction commits or aborts.

---
