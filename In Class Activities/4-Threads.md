# 4 - Thread

1. **What is a thread? Give an example of a multithread application.**
<br>
A thread is a basic unit of CPU utilization. An example of a multithread solution is a chat server that has one thread 
handling new client connections, and it has a seperate thread for each client currently connected on the server.
<br>
<br>
<br>
2. **Why threads? That is why not always using the process-creation method?**
<br>
Threads are less time-consuming for the CPU, and less resource-intensive. They also provide a simpler model for sharing memory.
<br>
<br>
<br>
3. **Explain two benefits of multithreaded programming.**
<br>
  1. Threads share resources of the process, which is easier to work with than the shared memory and message passing models in inter-process communication.
  2. Allow for continued execution if part of a process is blocked.
<br>
<br>
<br>
4. **What is the difference between user and kernel threads?**
<br>
User threads are supported above the kernel and are managed by the by a user-level thread library, without any kernel support. Kernel threads are supported and directly managed by the OS.
<br>
<br>
<br>
5. **Explain the three multithreading models.**
<br>
  1. **Many-to-one**: In this model, many user-level threads are mapped to a single kernel thread. This model is efficient because all thread management is done in user-space by the thread library, thus freeing up the kernel. It can also work on an OS that doesn't support multithreading as thread management is done in user-space, not kernel-space. They are innefficient because the entire process will block if a thread makes a blocking call. This model is used in Solaris Green Threads and GNU Portable Threads.
  2. **One-to-one**: In this model, one user-level thread is mapped to one kernel thread. This model provides more concurrency because if a thread makes a blocking call, it will only block that specific thread, and the rest of the threads from the process can continue executing. It's disadvantage lies in the fact that the kernel has to be notified when a new thread is created in user-space so that the corresponding state can be created in the kernel. This setup cost is overhead that must be paid each time a thread is created and there is an upper bound on the number of threads and thread state that the kernel can track before performance begins to degrade. This model is used in Windows, Linux, and Solaris 9.
  3. **Many-to-Many**: In this model, many user-level threads are mapped to a smaller or equal number of kernel threads. It avoids the shortcomings of the previous two models by letting the developer createa as many user threads as necessary. The corresponding kernel threads can run in parallel on a multiprocessor and when a thread performs a blocking system call, the kernel can schedule another thread for execution. It's disadvantages are that it needs the scheduler in user-land and in kernel to work with each other, threads doing blocking I/O operations will block all other threads sharing the same kernel thread, and it's difficult to write, maintain and debug code using this model. Examples include Solariis prior to version 9, and Windows NT/2000 with the Thread Fiber Package.
<br>
<br>
<br>
6. **How can we use threads in Linux?**
<br>
We can make use of some of the APIs that are provided to us such as the Pthreads library or the Java Threads API.
<br>
<br>
<br>
7. **Explain how sockets (client-server) and pipes are used in inter-process comunications.**
<br>
In a network with remote nodes, we can open up a pair of sockets on each end and communicate between the sockets through TCP or IP. Pipes allow for local processes to communicate with each other. One end will write to the pipe, while the other end reads from the pipe.
<br>
<br>
<br>
8. **Explain how many processes (including the original process) are created in this code segment. Assume `fork()` is successful.**
```c
#include <stdio.h>
#include <unistd.h>

int main (void)
{
    pid_t pid1, pid2, pid3;
    
    pid1 = fork();
    
    pid2 = fork();
    
    if (pid1 && pid2) {
        pid3 = fork();
    }
    
    //...
    
    return 0;
}
```
5 processes.
