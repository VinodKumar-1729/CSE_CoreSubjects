

### 1. **Primary, Secondary, and Tertiary Storage**
- **Primary Storage**:
  - Refers to volatile memory directly accessible by the CPU, such as RAM.
  - Used for storing data currently being processed.
  - **Advantages**: High speed, low access time.
  - **Disadvantages**: Expensive and volatile.
- **Secondary Storage**:
  - Non-volatile storage such as HDDs and SSDs.
  - Used for long-term storage of data.
  - **Advantages**: Larger capacity, persistent.
  - **Disadvantages**: Slower access compared to primary storage.
- **Tertiary Storage**:
  - Used for archival and backup purposes.
  - Includes optical discs (CD/DVD) and magnetic tapes.
  - **Advantages**: High durability, cost-effective for large volumes of data.
  - **Disadvantages**: Slow access speeds and typically offline.

---

### 2. **Heap Files and Sequential Files**
- **Heap Files**:
  - Unordered storage structure where records are placed wherever space is available.
  - **Advantages**: Simple to implement, efficient for small data retrieval.
  - **Disadvantages**: Slow for large searches as no indexing is used.
- **Sequential Files**:
  - Records are stored in a specific order based on a key.
  - **Advantages**: Efficient for range queries and sequential access.
  - **Disadvantages**: Requires reorganization for insertions and deletions.

---

### 3. **Clustered Index vs. Non-Clustered Index**
- **Clustered Index**:
  - The physical order of data in the table matches the index order.
  - Each table can have only one clustered index.
  - **Advantages**: Faster retrieval for range queries.
  - **Disadvantages**: Slower updates and inserts due to data reordering.
- **Non-Clustered Index**:
  - The index stores pointers to the actual data, and the physical order is independent of the index order.
  - A table can have multiple non-clustered indexes.
  - **Advantages**: Flexible for various queries.
  - **Disadvantages**: Slower lookups compared to clustered indexes due to pointer traversal.

---

### 4. **RAID (Redundant Array of Independent Disks)**
- **Definition**: RAID is a storage technology that combines multiple physical disk drives into a single logical unit for improved performance, fault tolerance, or both.
- **Levels of RAID**:
  - **RAID 0 (Striping)**:
    - Data is split across multiple drives for high performance.
    - No redundancy, so failure of one disk results in data loss.
  - **RAID 1 (Mirroring)**:
    - Data is duplicated on two disks.
    - Provides redundancy and fault tolerance.
  - **RAID 5 (Striping with Parity)**:
    - Data and parity (error-checking information) are distributed across all disks.
    - Can tolerate one disk failure.
  - **RAID 6**:
    - Similar to RAID 5 but can handle two disk failures.
  - **RAID 10 (1+0)**:
    - Combines RAID 1 (mirroring) and RAID 0 (striping).
    - Provides high performance and fault tolerance.

---

