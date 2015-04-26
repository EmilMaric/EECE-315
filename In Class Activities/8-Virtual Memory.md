# 8 - Virtual Memory

1. **Explain the advantages of using the virtual memory technique in memory management.**
    
    * Only part of a program needs to be in memory for execution, therefore the logical address space can be much larger than the physical address space
    * Files and memory can be shared by two or more processes through page sharing
<br>
<br>
<br>
2. **How does demand paging allow us to implement the virtual memory technique?**

    With demand paging, we only need to load a page into memory when it is needed. To execute a process, we swap its pages into memory. But we only swap in those pages that are needed.
<br>
<br>
<br>
3. **What causes a page fault? Explain the procedure for handling page faults.**

    A page fault is caused when a process tries to access a page that is not loaded in physical memory. A page fault causes a trap that is sent to the OS. The page is then brought into physical memory from the backing store, and the page table is reset to reflect this change. Then the original instruction is restarted.
<br>
<br>
<br>
4. **Assume that the memory access time is 200 nanoseconds and the average service time for a page fault is 8 milliseconds. Calculate the effective access time when the page fault rate is 1 out of 1000.**

#Effective Access Time = (1 - 0.001) x 200 + 0.001 x 8000000 = 8200 nanoseconds

<br>
<br>
<br>
5. **What are the two problems we must solve to implement demand paging?**

    * A frame-allocation algorithm
    * A page-replacement algorithm
<br>
<br>
<br>
6. **Explain the Beladys anomaly effect in the FIFO page replacement algorithm.**

    When we use a FIFO page replacement algorithm, sometimes with more free frames, we end up with more page faults.
<br>
<br>
<br>
7. **Why can the Optimal algorithm be used as a benchmark? What are the advantages and challenges associated with it?**

    It can be used because it has the lowest page-fault rate of all algorithms and will never suffer from Beladys anomaly. The optimal algorithm requires future knowledge of when a page will be accessed, so it is not feasible to implement.
<br>
<br>
<br>
8. **Consider the reference string 1, 2, 3, 4, 1, 2, 5, 1, 2, 3, 4, 5. Calculate how many page faults occur, assuming that an LRU page replacement algorithm is used with 4 frames.**

    8 page faults.
<br>
<br>
<br>
9. **What is thrashing? How do we prevent thrashing?**

    A process is thrashing if it spends more time paging than executing. We can prevent thrashing by using a local replacement algorithm, or a working set strategy.
<br>
<br>
<br>    
10. **Explain the working set model used in memory management.**

    * Examines the most recent page references
    * If a page is in active use, it will be in the working set model
    * If the demand for frames is higher than the number of available frames, thrashing occurs
<br>
<br>
<br>
11. **Explain the clustering technique used in the demand paging of the Windows operating system.**

    Clustering brings in pages surrounding the faulting page.
