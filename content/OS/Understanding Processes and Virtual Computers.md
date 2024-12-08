

# What is a Process?

  - A process is simply a program that is running (being executed) on a computer.

# Which Computer Runs the Process?

  - A process doesn’t directly run on the physical hardware. 
  - Instead, it runs on an *illusory "virtual computer"* provided by the operating system.

# What Does the Virtual Computer Provide?

  - The operating system gives each process its own virtual environment to make it feel like it's running on its own computer.

# Key Components of the Virtual Computer:

## 1. Virtual CPU(s): 

- The process gets one or more "threads of execution," which are like virtual CPUs.
- The OS shares the real CPU between processes.

## 2. Virtual Memory:
- Each process has its own "private" memory space, called an address space.
- It can't directly see or interfere with other processes' memory.

## 3. Virtual Storage:

- Files on disk appear as if they're part of the process's own storage.

## 4. Virtual Network:

-  Sockets allow processes to communicate as if they each have their own network.

## 5. Other Virtual Devices:

- Examples include:
- **Screen/Keyboard**: Processes might think they control their own terminal or window.
- **Windows**: A process might have its own graphical interface (like an app window).

# Why Use a Virtual Computer?

- It keeps processes isolated for security and stability.
- It allows multiple programs to run on one physical computer without interfering with each other.
