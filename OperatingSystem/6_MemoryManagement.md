### 6. Memory Management

#### **Memory Hierarchy**
- **Definition**: Memory hierarchy organizes storage systems into levels based on speed, cost, and size. Faster and costlier memory is placed closer to the CPU.
- **Levels of Memory**:
  1. **Registers**: Fastest, smallest, directly accessed by the CPU.
  2. **Cache Memory**: Small-sized, high-speed memory between CPU and main memory.
  3. **Main Memory (RAM)**: Primary storage for active processes.
  4. **Secondary Storage**: Non-volatile, slower (e.g., HDD, SSD).
  5. **Tertiary Storage**: Archival storage (e.g., magnetic tapes).

#### **Contiguous vs. Non-Contiguous Allocation**
- **Contiguous Allocation**:
  - Memory blocks are allocated in a single contiguous section.
  - **Advantages**: Simple, easy to implement.
  - **Disadvantages**: Fragmentation (internal and external), inflexible resizing.
- **Non-Contiguous Allocation**:
  - Memory blocks are allocated in scattered locations, linked logically.
  - **Advantages**: Overcomes fragmentation, flexible.
  - **Disadvantages**: Increased overhead for address translation.

#### **Paging and Page Tables**
- **Paging**: Divides physical memory into fixed-size blocks called frames and logical memory into pages of the same size.
  - Eliminates external fragmentation.
- **Page Tables**: Maps logical pages to physical frames.

##### Types of Page Tables
1. **Single-Level Page Tables**:
   - Single table maps pages to frames.
   - Efficient for small address spaces.
2. **Multi-Level Page Tables**:
   - Hierarchical structure with multiple levels of page tables.
   - Reduces memory usage for page tables but increases translation time.
3. **Inverted Page Tables**:
   - Single table for all processes, indexed by frame number.
   - Reduces memory usage but increases lookup time.

#### **Translation Lookaside Buffer (TLB)**
- **Definition**: A cache that stores recent translations of virtual addresses to physical addresses.
- **Advantages**:
  - Speeds up address translation.
  - Reduces memory access time.
- **Working**:
  - CPU checks TLB before consulting the page table.

#### **Segmentation**
- Divides memory into variable-sized segments based on logical divisions such as functions, data, etc.
- **Advantages**:
  - Supports modular programming.
  - Easy to manage growing segments.
- **Disadvantages**:
  - Suffering from external fragmentation.

#### **Virtual Memory**
- **Definition**: Allows execution of processes that may not completely reside in physical memory.
- **Key Components**:
  - **Demand Paging**: Loads pages into memory only when required.
  - **Page Faults**: Occurs when a referenced page is not in memory.

#### **Page Replacement Algorithms**
- Used to decide which page to replace when memory is full.
1. **FIFO (First-In-First-Out)**:
   - Replaces the oldest page.
   - Simple but can lead to Belady’s anomaly.
2. **Optimal**:
   - Replaces the page not needed for the longest future period.
   - Ideal but impractical as it requires future knowledge.
3. **LRU (Least Recently Used)**:
   - Replaces the least recently used page.
   - Balances performance and implementability.
4. **Clock Algorithm**:
   - Uses a circular buffer with reference bits to approximate LRU.

#### **Thrashing**
- **Definition**: High paging activity due to insufficient memory, leading to degraded performance.
- **Causes**:
  - Too many processes in memory.
  - High degree of multiprogramming.
- **Solutions**:
  - Reduce multiprogramming level.
  - Use working set model to allocate enough frames to processes.
