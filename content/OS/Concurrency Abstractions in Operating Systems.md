
# What is Concurrency?

  - Concurrency means multiple things happening at the same time.
  - In operating systems, it refers to the ability to run multiple processes or threads simultaneously.

# Modern Concurrency Features in Operating Systems:

## 1. Multiple Processes:

- Users can create and run multiple processes at the same time.
- Each process has its own virtual environment (CPU, memory, etc.).
  
## 2. Multiple Threads:

- A single process can have multiple threads, each capable of doing different tasks simultaneously.
  
## 3. Shared Resources:

- Processes and threads can share resources like:
 - Memory
 - Files
 - Devices (e.g., printers)
 - This enables communication and cooperation but requires careful management to avoid conflicts (e.g., race conditions).

# What About Early Operating Systems?

  - Early systems in the 1950s (batch operating systems):
    - Each submitted job ran one at a time (independently) until it finished.
    - Internally, the system could keep multiple jobs in memory at once (multiprogramming), but they didn’t interact.

# Why Multiprogramming Was Useful:

  - Even in batch systems, multiprogramming was efficient because:
    - While one process waited (e.g., for a slow disk operation), the CPU could work on another process.
    - This made better use of system resources.

# The Shift to Time-Sharing Systems (1960s):

  1. **What Changed?**
     - Systems evolved to support **time-sharing**:
       - Multiple users could use the system interactively at the same time.
       - Example: Connecting via multiple teletypes (early terminals).

  2. **New Features**:
     - Users could run commands interactively, not just batch jobs.
     - Communication between users and processes became possible.

  3. **Why Shared Resources Matter**:
     - Communication requires sharing:
       - Memory: Shared data for collaboration.
       - Files: Access to shared documents.
       - Devices: Shared use of printers, terminals, etc.
     - Operating systems introduced mechanisms to manage shared resources safely.

# Impact of Concurrency:

  - Concurrency made modern computing more interactive, efficient, and collaborative.
  - It required solving new challenges, like managing shared resources and ensuring processes don’t interfere with each other.
