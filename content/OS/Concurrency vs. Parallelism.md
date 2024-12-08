

- **Concurrency and Single CPU**:
  - Even with only one CPU, an operating system can run multiple programs *concurrently*.
  - How? By switching between programs very quickly.
    - Example: A typical "time-slice" for each program is about 10 milliseconds.
  - To the user, it feels like the programs are running at the same time.

- **Are Programs Really Concurrent on One CPU?**
  - Yes! Even if they don’t run at the exact same physical time.
  - Why? Because:
    - Programs don’t control when the OS switches between them.
    - They must handle interactions without knowing the exact order of execution.

- **What is Concurrency?**
  - Concurrency is about managing multiple tasks and their interactions.
  - It’s not about *physical time* but about how tasks interact with each other, often unpredictably.

- **What is Parallelism?**
  - Parallelism refers to multiple tasks running at the *exact same time* on different CPUs or cores.
  - Example:
    - Two programs running on two separate CPU cores are parallel.
    - Parallelism is a type of "true concurrency."

- **Concurrency vs. Parallelism**:
  - **Concurrency**:
    - Focuses on managing tasks that interact, regardless of whether they run at the same physical time.
    - Happens even on a single CPU.
  
  - **Parallelism**:
    - Focuses on tasks running simultaneously on multiple CPUs or cores.
    - Requires hardware support (e.g., multiple CPUs).

- **Key Insight**:
  - **Concurrency isn’t the same as parallelism, but it enables parallelism.**
    - Quote from Rob Pike: "Concurrency is not parallelism, but it enables parallelism."

- **Why Concurrency is Complicated**:
  - The challenge is in managing *interactions* between tasks.
  - Example:
    - If two tasks share data or resources, ensuring they don’t conflict is tricky.
  
- **Why Parallelism is Easier Without Interaction**:
  - If two physically parallel tasks don’t interact, they’re straightforward to manage.
  - Interaction (shared resources, communication) introduces complexity.
