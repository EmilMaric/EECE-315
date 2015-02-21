# 3 - Processes

1. **Explain the notion of a process. How is it different from the program stored on the hard disk?**
<br>
A process is a program that is currently being executed. It is not a program; a program is a passive entity (a file on a disk), 
whereas a process is an active entity.
<br>
<br>
<br>
2. **Explain the different parts of a process in memory.**
<br>
A process in memory consists of the following:
  * __Text Section__: The program code that is being executed
  * __Data Section__: Initialized static variables such as global variables and static local variables
  * __Heap__: Dynamically allocated memory at run-time
  * __Stack__: Temporary data, such as function parameters and return addresses
<br>
<br>
<br>
3. **What are the different process states?**
<br>
  * New
  * Ready
  * Running
  * Waiting
  * Terminated
<br>
<br>
<br>
4. **How does the OS keep the info for each process?**
<br>
In a Process Control Block.
<br>
<br>
<br>
5. **What is the role of the process scheduler?**
<br>
To select an available process for execution.
<br>
<br>
<br>
6. **Explain the concept of context switch. Is context-switch time overhead?**
<br>
A context switch is when a CPU switches to running another process, and in the meantime saves the state of the old process,
and loads the saved state of the new process. A context-switch is time overhead because the CPU is is idle while this is happening.
<br>
<br>
<br>
7. **Explain how many processes (_INCLUDING THE ORIGINAL PROCESS_) are created in this code segment. Assume fork() is successful.**
<br>
```c
#include <stdio.h>
#include <unistd.h>

int main(void)
{
    pid_t pid1, pid2, pid3;
    
    pid1 = fork();
    
    pid2 = fork();
    
    pid3 = fork();
    
    //...
    
    return 0;
}
```
![Process Drawing](http://i.imgur.com/VWxGykc.png)
