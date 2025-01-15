**Process Management**

### 1. Process vs Program
- **Program:** A passive entity, consisting of a set of instructions stored on disk. It is not executing and does not have resources allocated.
- **Process:** An active entity, representing an executing program. It includes the program code, a program counter, stack, data section, and allocated resources.

| Feature              | Program            | Process            |
|----------------------|--------------------|--------------------|
| Nature              | Static, passive    | Dynamic, active    |
| Stored In           | Disk (storage)     | RAM (memory)       |
| Lifecycle           | Does not have one  | Created, executes, terminates |
| Resources           | None allocated     | Allocates CPU, memory, I/O |

### 2. Process States and State Transition Diagram
A process goes through various states during its lifecycle:
- **New:** Process is created.
- **Ready:** Process is waiting to be assigned to the CPU.
- **Running:** Process is being executed by the CPU.
- **Waiting:** Process is waiting for an event (e.g., I/O completion).
- **Terminated:** Process has finished execution.

#### State Transition Diagram:
1. **New → Ready:** Admission by the operating system.
2. **Ready → Running:** CPU scheduler dispatches the process.
3. **Running → Waiting:** Process requests I/O or an event.
4. **Waiting → Ready:** Event or I/O completion.
5. **Running → Terminated:** Process completes execution.
6. **Running → Ready:** Preempted due to higher priority processes or time slice expiry.

### 3. Process Control Block (PCB)
The PCB is a data structure used by the OS to store all information about a process. Key components include:
- **Process ID (PID):** Unique identifier for the process.
- **Process State:** Current state (New, Ready, Running, etc.).
- **Program Counter:** Address of the next instruction.
- **CPU Registers:** Saved values of CPU registers.
- **Memory Management Info:** Base and limit registers, page tables.
- **I/O Status Info:** I/O devices allocated.
- **Scheduling Info:** Priority, scheduling queue.

### 4. Context Switching
- **Definition:** The process of saving the state of a currently running process and loading the state of a new process.
- **Steps:**
  1. Save the state of the current process (PCB updated).
  2. Load the state of the next process to be executed.
- **Overhead:** Increases CPU scheduling time as no useful work is done during switching.
- **Triggers:** Preemption, I/O, interrupts.

### 5. Threads
#### Types of Threads
1. **User-Level Threads (ULT):**
   - Managed by user-level libraries.
   - Faster creation and management.
   - No kernel support; relies on application.
   - Issues: Blocking system calls block the entire process.
2. **Kernel-Level Threads (KLT):**
   - Managed directly by the operating system.
   - Slower but allows better multitasking.
   - Blocking system calls do not block other threads in the process.

#### 6. Multithreading Models
1. **Many-to-One:**
   - Many user threads map to one kernel thread.
   - Simple, but one blocking thread blocks all.
2. **One-to-One:**
   - Each user thread maps to a kernel thread.
   - Provides concurrency but requires more overhead.
3. **Many-to-Many:**
   - Many user threads map to many kernel threads.
   - Combines benefits of both models, with efficient resource utilization.

### 7. Process Scheduling
#### Types of Schedulers
1. **Long-Term Scheduler:**
   - Decides which processes are admitted to the ready queue.
   - Controls the degree of multiprogramming.
   - Invoked infrequently.
2. **Medium-Term Scheduler:**
   - Temporarily removes processes from memory to reduce load (swapping).
   - Balances CPU and I/O-bound processes.
3. **Short-Term Scheduler (CPU Scheduler):**
   - Decides which process in the ready queue gets the CPU next.
   - Invoked frequently for efficient CPU utilization.

#### Types of Scheduling
1. **Preemptive Scheduling:**
   - Allows the process to be preempted and moved back to the ready queue.
   - Examples: Round Robin, Priority Scheduling.
2. **Non-Preemptive Scheduling:**
   - Process runs to completion or until it voluntarily enters a waiting state.
   - Examples: First Come First Serve (FCFS), Shortest Job Next (SJN).
