# 5 - Scheduling

1. **What is the diference between preemptive and non-preemptive (cooperative scheduling)?**

    Preemptive scheduling allows a process to be interrupted in the midst of its execution, taking the CPU away and      allocating it to another process. Nonpreemptive scheduling ensures that a process relinquishes control of the CPU     only when it finishes with its current CPU burst.
<br>
<br>
<br>
2. **Compare the waiting time, turnaround time, and response time scheduling criteria.**

  1. **Waiting Time**: Amount of time a process has been waiting in the ready queue.
  2. **Turnaround Time**: Amount of time to execute a particular process (includes waiting time in memory, and ready queue, executing in CPU, and doing IO).
  3. **Response Time**: Amount of time from when a request has been submitted until the first response is produced.
<br>
<br>
<br>
3. **Consider an FCFS scheduler for P1, P2, P3 as shown (arrived in this order). Draw the Gantt chart and calculate the average waiting time.**

    | Process | Burst Time |
    | ------- | ---------- |
    | P1      | 24         |
    | P2      | 3          |
    | P3      | 3          |
    
    ![Gantt Chart 3](http://i.imgur.com/7ySuPae.png)
    
    **Average Waiting Time** = [ 0 + 24 + 27 ] / 3 = **17**
<br>
<br>
<br>
4. **Draw the Gantt charts for the FCFS, SJF, and RR schedulers.**

    | Process | Burst Time |
    | ------- | ---------- |
    | P1      | 10         |
    | P2      | 29         |
    | P3      | 3          |
    | P4      | 7          |
    | P5      | 12         |
    
    #### FCFS
    ![Gantt Chart 4.1](http://i.imgur.com/09pJCGa.png)

    #### SJF
    ![Gantt Chart 4.2](http://i.imgur.com/0Tij42M.png)
    
    #### RR
    Not going to do because it's trivial and subjective.
<br>
<br>
<br>
5. **What is the difference between SJF and preemptive SJF?**

    With regular SJF, once a process has been scheduled for the CPU, it will execute until it's burst is over, or it voluntarily gives up the CPU. With preemptive SJF, another process can take the place of the currently executing process if it has a smaller remaining CPU burst time.
<br>
<br>
<br>
6. **What are the two types of latencies that affect the real-time scheduling performance?**

    * Interrupt Latency
    * Dispatch Latency
<br>
<br>
<br>
7. **Explain how completely fair scheduler (CFS) works in Linux.**
    
    It is a new scheduler that is used in Linux versions 2.6.23+. Rather than having a quantum-based scheduler that works on fixed time allotments, the CFS prioritizes based on proportion of CPU time. It always schedules the highest priority task in the highest priority class. Each runnable task is placed in a red-black tree, whose key is based on the value of it's virtual run time. Tasks that have been given less processing time have a smaller virtual run time, and are moved to the left side of the tree. The scheduler will always pick the left-most node in the tree because it has the smallest virtual run time.
