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
