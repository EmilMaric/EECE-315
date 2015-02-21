# 1 - Introduction


1. **Explain two of the main purposes of an operating system.**
  1. Execute user programs and make solving user problems easier
  2. Make the computer system convenient to use
  3. Use the computer hardware in an efficient manner
<br>
<br>
<br>
2. **What is the main difficulty that a programmer must overcome in writing an operating system for a real-time environment?**<br>
Real-time systems have strictly defined time constraints, and processing must be done within that time constraint. **_Hard_** real-time systems have complete system failure if these time constraints are not met, while **_soft_** real-time systems have their quality-of-service diminish if the time constraints are not met.
<br>
<br>
<br>
3. **Keeping in mind the various definitions of operating system, consider whether the operating system should include applications such as Web browsers and mail programs. Argue both that it should and that it should not, and support your answer.**<br>
The answer to this question depends on what you define as the _operating system_. In 1998, there was a lawsuit by the United States Federal department against Microsoft, where one of the main accusations revovled around Microsoft bundling it's own broswer, _Internet Explorer (IE)_, into it's operating system. 
<br>
<br>
Microsoft argued that it acted on consumer expectations of having a default Web Broswer that comes with the operating system. This gave the user the convenience of having something that works out of the box, and allowed Microsoft to integrate additional integration features that wouldn't be possible if the browser was not part of the operating system.
<br>
<br>
However that case against having these sorts of user applications in the operating system is that it adds to the complexity of the kernel, and introduces many security holes due to how the Web Browser services and handles web pages, which is not native to the kernel. Additionaly, having this sort of integration means that if the Web Browser were to crash, it would take down the entire Operating System with it.
<br>
<br>
<br>
4. **How does the distinction between kernel mode and user mode function as a rudimentary form of protection (security) system.**<br>
This seperation allows for user applications to run in user-mode, which prevents them from accessing the hardware or memory. They must make a system call in order to do this, which causes the CPU to switch to kernel mode to execute the instruction. This means that user-programs are isolated, and the system can recover if a crash occurs in user-mode.
<br>
<br>
<br>
5. **Explain why memory caches are usueful.**<br>
Caches are designed for fast access and are useful for storing memory blocks that need to be accessed frequently.
<br>
<br>
<br>
6. **Distinguish between the client-server and peer-to-peer models of distributed systems**<br>
In a client-server model, a system will either act as a client or server. The client sends requests to the server, and the server will respond to the requests. The servers main job is to handle and respond to client requests. Clients do not generally communicate with one another. An example is a web server that handles request to some web page.
<br>
<br>
In a peer-to-peer model, each node is considered a peer, and each peer can either act as a client, server, or both. An example of this is uTorrent, where you can download and upload chunks of files within your P2P network.
