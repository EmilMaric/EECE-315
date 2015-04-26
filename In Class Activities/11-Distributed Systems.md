# 11 - Distributed Systems

1. **What is a distributed system (for computation)?**

    A collection of loosely coupled nodes interconnected by a communications network.
<br>
<br>
<br>
2. **Explain the four reasons for building distributed systems.**

    * Resource Sharing
    * Computation Speedup
    * Reliability
    * Communication
<br>
<br>
<br>
3. **Consider Windows, iOS, Sun Microsystems NFS file system. Based on the definitions provided in the textbook, are they network operating systems or distributed operating systems?**

    Network operating systems.
<br>
<br>
<br>
4. **The World Wide Web has many aspects of a distributed computing environment. Explain whether it provides data migration, computation migration, and/or process migration?**

    All 3 are provided by the World Wide Web.

    * **Data Migration** - Downloading/uploading files
    * **Computation Migration** -
    * **Process Migration** - 
<br>
<br>
<br>
5. **In the Internet, how do we uniquely identify a process?**

    An IP address plus a port number.
<br>
<br>
<br>
6. **State the layers of the Internet protocol stack. In which layer is TCP and IP? Explain the roles of the transport and network layers.**

    * Application
    * Transport - deals with process-to-process data transfer, includes TCP
    * Network - deals with the routing of datagrams from source to destination, includes IP
    * Link
    * Physical
<br>
<br>
<br>
7. **What is a distributed file system?**

    A distributed implementation of a file system, where multiple users share files and sotrage resources.
<br>
<br>
<br>
8. **In a distributed file system, explain the two concepts of location transparency and location independence.**

    * **Location transparency** - file name does not reveal the files physical storage location
    * **Location independence** - file name does not need to be changed when the files physical storage location changes
