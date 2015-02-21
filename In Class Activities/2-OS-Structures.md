# 2 - OS Structures

1. **We discussed a number of OS services. Give two examples for services that are primarily helpful to the user, as well as two examples for services that ensure the efficient operation of a system.**
<br>
Services that are helpful for the User: A GUI, and a CLI
<br>
Servies that ensure efficient operation of a system: Resource Allocation Services, Protection and Security Services
<br>
<br>
<br>
2. **Explain what system calls are.**
<br>System calls provide a programming interface to calls that are made by the OS. They are typically available as functions written in C/C++.
<br>
<br>
<br>
3. **Provide two examples for three different system call types (either general functionality or for specific OS).**
<br>
For file manipulation on UNIX, we have: read(), write(), open()
<br>
For process control on UNIX, we have: fork(), exit(), wait()
<br>
<br>
<br>
4. **What are the three major activities of an operating system with regard to memory management?**
<br>
  1. Keeping track of which parts of memory are currently being used and by whom
  2. Deciding which processes and data to move into and out of memory
  3. Allocating and deallocating memory space as needed
<br>
<br>
<br>
5. **Explain the microkernel structure for operating systems.**<br>
In the microkernel structure, many non-essential components are stripped from the kernel and instead implemented as 
system and user-level programs. The microkernel structure must provide for a efficient means of communicating between 
client programs and various services using message passing.<br>
Some benefits of the microkernel structure:
  * easier to extend
  * easier to port to new architectures
  * less code running in kernel-mode, thus more reliable
  * more secure
  
  Some disadvantages include:
    * high performance overhead because of the large number of user-space to kernel-space communications that need to happen.
<br>
<br>
<br>
6. **What are the advantages of using loadable kernel modules?**
<br>
Each module is seperate from one another, and is loaded as needed within the kernel.
<br>
<br>
<br>
7. **Name one interactive application in your preferred OS that can be used to monitor the system and to acquire information regarding process, memory usage, and such?**
8. <br>
Mac OS X - Activity Monitor
