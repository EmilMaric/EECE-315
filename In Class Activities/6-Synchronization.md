# 6 - Synchronization

1. **In Linux, explain the difference between `fork()`, `sys_fork()` and `do_fork()`.**

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
