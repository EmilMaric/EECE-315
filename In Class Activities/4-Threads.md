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
