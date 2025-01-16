

### 1. **Indexing in DBMS**
- **Definition**: Indexing is a data structure technique to efficiently retrieve records from a database based on a search key. It reduces the amount of data scanned during query execution.
- **Purpose**: Speeds up search operations by minimizing disk I/O.
- **Types**:
  - **Single-Level Index**: Contains a single layer of indexes pointing directly to the data.
  - **Multi-Level Index**: Contains multiple levels where higher levels point to the next level of indexes until the data is reached.

---

### 2. **Single-Level Index vs. Multi-Level Index**
- **Single-Level Index**:
  - Has only one level of indexes.
  - Efficient for small databases but not scalable.
  - Example: A single list of key-value pairs.
- **Multi-Level Index**:
  - Indexes are organized in a hierarchy (e.g., first-level indexes point to second-level indexes).
  - Suitable for large databases.
  - Reduces disk I/O by narrowing down the search space.

---

### 3. **Dense Index vs. Sparse Index**
- **Dense Index**:
  - Contains an entry for every record in the data file.
  - Provides faster lookup but requires more storage.
- **Sparse Index**:
  - Contains entries only for some records (e.g., one entry per block or page).
  - Saves space but increases lookup time since additional block scanning may be required.

---

### 4. **B-Tree and B+ Tree Indexing**
- **B-Tree Indexing**:
  - A self-balancing tree where nodes represent keys and pointers to data or other nodes.
  - Keys are stored at all levels of the tree.
  - Supports both sequential and random access.
  - Example: Used in file systems.
- **B+ Tree Indexing**:
  - A variant of the B-Tree where all keys are stored in the leaf nodes.
  - Internal nodes only store keys and pointers to child nodes.
  - Better for range queries as leaf nodes are linked.
  - Example: Commonly used in database indexing.

---

### 5. **Hashing in DBMS**
- **Definition**: Hashing is a technique used to map a large set of keys into a smaller address space using a hash function.
- **Purpose**: Efficiently retrieve records using a hash key.
- **Advantages**: Constant-time access in average cases for key-based lookups.

---

### 6. **Static Hashing vs. Dynamic Hashing**
- **Static Hashing**:
  - The hash table size is fixed.
  - Collisions are handled using methods like chaining or open addressing.
  - Suitable for systems with a relatively stable number of records.
- **Dynamic Hashing**:
  - The hash table size grows or shrinks dynamically as records are inserted or deleted.
  - Example: Extendible hashing and linear hashing.
  - Suitable for databases where the size can vary significantly.

---

