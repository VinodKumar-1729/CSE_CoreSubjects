**Deadlocks: **

### 1. **Deadlock Definition**
A deadlock is a state in a system where two or more processes are unable to proceed because each is waiting for a resource that is held by another process. This leads to a standstill where none of the processes can make progress.

### 2. **Conditions for Deadlock (Coffman’s Conditions)**
Deadlocks can occur only if all the following conditions hold simultaneously:

1. **Mutual Exclusion:** At least one resource must be held in a non-sharable mode. That is, only one process can use the resource at a time.

2. **Hold and Wait:** A process holding at least one resource is waiting to acquire additional resources held by other processes.

3. **No Preemption:** Resources cannot be forcibly removed from a process holding them until the process releases them voluntarily.

4. **Circular Wait:** A set of processes – {P1, P2, ..., Pn} – exists such that P1 is waiting for a resource held by P2, P2 is waiting for a resource held by P3, and so on, with Pn waiting for a resource held by P1.

### 3. **Resource Allocation Graph (RAG)**
- **Definition:** A Resource Allocation Graph is a directed graph used to represent the allocation of resources to processes.

#### Components of RAG:
1. **Processes:** Represented by circles (e.g., P1, P2, etc.).
2. **Resources:** Represented by rectangles (e.g., R1, R2, etc.).
3. **Assignment Edges:** A directed edge from a resource to a process (R1 → P1) indicates that the resource is allocated to the process.
4. **Request Edges:** A directed edge from a process to a resource (P1 → R1) indicates that the process is requesting the resource.

#### Deadlock Detection in RAG:
- If the graph contains a cycle and each resource in the cycle has exactly one instance, a deadlock exists.

### 4. **Deadlock Detection**

#### a) **Banker's Algorithm**
This is a deadlock avoidance algorithm based on resource allocation and the system’s safe state.

**Key Terms:**
- **Safe State:** A system state is safe if there exists a sequence of processes that can complete without leading to a deadlock.
- **Available Resources (Work):** Represents the count of available instances for each resource type.
- **Max Matrix:** Maximum demand of each process for resources.
- **Allocation Matrix:** Current allocation of resources to processes.
- **Need Matrix:** Resources still needed by each process (Need = Max - Allocation).

**Steps for Banker's Algorithm:**
1. Initialize Work = Available and Finish = False for all processes.
2. Find a process whose Need ≤ Work and Finish = False.
3. If found, update Work = Work + Allocation of that process, set Finish = True, and continue.
4. If no such process exists and Finish = False for any process, a deadlock is detected.

**Numerical Example:**
Given Available = [3, 3, 2]
- **Max Matrix:**
  | P1 | P2 | P3 | P4 | P5 |
  |----|----|----|----|----|
  | 7  | 5  | 3  | 4  | 6  |

- **Allocation Matrix:**
  | P1 | P2 | P3 | P4 | P5 |
  |----|----|----|----|----|
  | 0  | 1  | 2  | 0  | 0  |

- **Need Matrix = Max - Allocation.**
Follow the steps to check if the system is in a safe state.

#### b) **Wait-for Graph**
- A simpler representation for deadlock detection.
- Vertices represent processes, and a directed edge from P1 to P2 indicates that P1 is waiting for a resource held by P2.
- Deadlock exists if the graph contains a cycle.

### 5. **Deadlock Prevention and Avoidance**

#### **Deadlock Prevention**
- Ensure at least one of Coffman’s conditions cannot hold:
  1. **Mutual Exclusion:** Spooling (e.g., printers as shared resources).
  2. **Hold and Wait:** Processes must request all resources at once.
  3. **No Preemption:** Allow preemption of resources if necessary.
  4. **Circular Wait:** Impose an ordering on resource types.

#### **Deadlock Avoidance**
- Use algorithms like Banker’s Algorithm to avoid unsafe states.
- Requires prior knowledge of resource demands.

### 6. **Deadlock Recovery Methods**

#### **Process Termination**
- Abort one or more processes to break the circular wait.
- Two approaches:
  1. Abort all deadlocked processes.
  2. Abort one process at a time until the deadlock is resolved.

#### **Resource Preemption**
- Resources are preempted from processes and reallocated.
- Challenges:
  - Selecting the victim (process to preempt).
  - Rollback mechanisms.
  - Starvation prevention.

---
