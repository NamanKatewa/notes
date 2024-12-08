# Operating Systems and Virtualization:

- The OS creates an *illusory "virtual computer"* for each program (as explained earlier).
- But this is not all the OS does! 

# Virtual Machines vs. Operating Systems:

- A program that *only* provides virtual hardware is called a **Virtual Machine Monitor (VMM)** or **Hypervisor**.
- Operating systems do much more than just virtualizing hardware.

## Other Key Roles of an Operating System:

## 1. Communication:

- Programs often need to interact with each other or share data.
- Example:
 - If one program creates a document, another program might need to open or edit it.
- The OS provides ways for programs to communicate safely and efficiently.
- Users might also want to combine programs for more complex tasks (e.g., using pipelines in the command line).

## 2. Abstraction:

- Programmers prefer working with simple, high-level concepts rather than raw hardware details.
- The OS offers **abstractions** that make this easier:
- Instead of managing raw blocks of data on disk, you work with **files** and **folders**.
- Instead of directly accessing hardware, you use APIs or system calls.

## 3. Control and Inspection:

- The OS provides tools and services to manage running programs:
- **Starting/Stopping**: Launch programs and stop them when needed.
- **Inspecting/Debugging**: Check how a program is running or find and fix problems in it.
- **Performance Monitoring**: See how much CPU, memory, or disk a program is using.

# Why These Features Matter:

  They make the computer more useful and efficient for:
- **Users**: Easier interaction with programs and hardware.
- **Developers**: Simplified tools for creating and debugging software.
- **System Administrators**: Better control over the system and its resources.