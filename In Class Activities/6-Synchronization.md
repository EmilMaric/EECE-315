# 6 - Synchronization

1. **In Linux, explain the difference between `fork()`, `sys_fork()` and `do_fork()`.**
    
    * fork() is a system call to the kernel to initate creating a new process.
    * sys_fork() calls do_fork() and returns the PID.
    * do_fork()
        * creates a new process
        * assigns a new PCB
        * copies the PCB of the parent to the new PCB with some bit changes depending on the context.
<br>
<br>
<br>
2. **What is the difference between independent and cooperating processes? Explain two of the reasons for having cooperating processes.**

    Independent processes are processes that do not communicate with each other, and generally do not know of each other's existance. Cooperating processes are processes that communicate with each by sharing a logical address or sharing data through files and messages. Two possible reasons for having cooperating processes include:
    * Provides for the option to seperate tasks into different _modules_. 
    * Processes can share information with one another as well as common data.
<br>
<br>
<br>
3. **Compare the two implementations of consumer-producer problem in Chapters 3 and 5.**

    In Chapter 5, we introduce a `counter` variable that allows us to fill up the ring buffer to it's maximum capacity. In Chapter 3, we didn't have this variable, and therefore we were only allowed to have `BUFFER_SIZE - 1` filled entries in the ring buffer in order to distinguish between an empty and full buffer.
<br>
<br>
<br>
4. **Explain the critical section problem. What is the general structure for a process in regards to critical section?**

    The critical section problem is when we have multiple processes/threads that have access to some shared variable, and there exists the possibility that there could be more than 1 process/thread that could modify the variable at the same time. The general structure for a process with a critical section is shown below.
    ![Critical Section](http://i.imgur.com/QVRU0NF.png)
<br>
<br>
<br>
5. **What are the three requirements that a solution to the critical section problem must satisfy?**

    1. **Mutual Exclusion** - If process `Pi` is executing in its critical section, then no other processes can be executing in their critical sections
    2. **Progress** - If no process is executing in its critical section and there exist some processes that wish to enter their critical section, then the selection of the processes that will enter the critical section next cannot be postponed indefinitely
    3. **Bounded Waiting** - A bound must exist on the number of times that other processes are allowed to enter their critical sections after a process has made a request to enter its critical section and before that request is granted
<br>
<br>
<br>
6. **Do the discussed Swap and TestAndSet algorithms satisfy all the critical section solution requirements?**

    They satisfy the _Mutual Exclusion_ and _Progress_ requirements, but they do not satisfy the _Bounded Waiting_ requirement because it is possible that a process/thread waits forever while other waiting processes/threads take turns acquiring the lock. We must introduce some sort of mechanism to order the processes/threads and select them in round-robin fashion so that every process/thread has a chance to acquire the lock.
<br>
<br>
<br>
7. **What are the two types of semaphores? What is a spinlock?**

    1. **Binary Semaphores**: Values range from 0 to 1
    2. **Counting Semaphores**: Values have an unrestricted integer domain
    
    A type of semaphore implementation where if a process/thread is waiting to acquire a lock, it spins inside a while-loop until the lock is freed, wasting CPU cycles. They are useful in situations where a lock is expected to be released quickly because no context switch is required when the process waits on a lock.
<br>
<br>
<br>
8. **What are the four conditions that must exist for a deadlock to occur?**

    1. **Mutual Exclusion**: only one process at a time can use a resource
    2. **Hold and Wait**: a process holding at least one resource is waiting to acquire additional resources held by other processes
    3. **No preemption**: a resource can be released only voluntarily by the process holding it, after that process has completed its task
    4. **Circular Wait**: there exists a set `{P0, P1, ..., Pn}` of waiting processes such that `P0` is waiting for a resource that is held by `P1`, `P1` is waiting for a resource that is held by `Pn`, and `Pn` is waiting for a resource that is held by `P0`
<br>
<br>
<br>
9. **Is deadlock a possibility in the discussed solution for the dining-philosophers problem?**

    Yes, all four conditions are met for a deadlock to occur. There must be an additional constraint that is added to the solution in order to prevent deadlock.
<br>
<br>
<br>    
10. **Explain whether Peterson's solution is correct.**

    Assuming that the solution acts on two processes, then yes, Peterson's solution is correct as it satisfies all three conditions for the prevention of race conditions.
