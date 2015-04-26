# 9 - Mass Storage Devices

1. **The random access time of a magnetic disk consists of the seek time and rotational latency. Explain these latencies.**

    * **Seek Time** - the time necessary to move the disk arm to the desired cylinder
    * **Rotational Latency** - the time for the desired sector to rotate under the disk
<br>
<br>
<br>
2. **What is a storage-area network?**

    A private network connecting servers and storage units.
<br>
<br>
<br>
3. **Assume that the disk head is initially at cylinder 53 and the total cylinder range is 0 to 199. Calculate the total disk head movement for the following disk scheduling algorithms, for a disk queue with requests for I/O blocks on cylinders as: 98, 183, 37, 122, 14, 124, 65, 67**

    1. **FCFS** : 53, 98, 183, 37, 122, 14, 124, 65, 67 = 640 cylinders
    2. **SSTF** : 53, 65, 67, 37, 14, 98, 122, 124, 183 = 236 cylinders
    3. **C-Look** : 53, 65, 67, 98, 122, 124, 183, 14, 37 = 153 cylinders (not including moving from 183 to 14)
<br>
<br>
<br>
4. **Explain the boot process in a Windows machine.**

    * boot code is in the first sector on the hard disk (called master boot record)
    * boot partition contaions the OS and device drives, its first sector is the boot sector
<br>
<br>
<br>
5. **What is the RAID disk organization? How can it improve performance and reliability of the disk?**

    RAID disk organizations are a variety of disk organization schemes that can be used to provide reliability and performance of the disk drives. It improves performance by improving the rate at which data can be read or written. Reliability is improved because redundant data is stored on multiple disks.
<br>
<br>
<br>
6. **Explain the RAID level 0, level 1, and level 5.**

    * **RAID 0** - Block-level striping across multiple disks, but no redundancy
    * **RAID 1** - Each disk is mirrored onto another disk
    * **RAID 5** - Block-level striping acorss multiple disks, with parity sectors distributed across each disk
<br>
<br>
<br>
7. **Which scheduling algorithm is likely used in solid-state disks?**

    Not sure, since SSD has no moving parts, some of the previously mentioned scheduling algorithms do not apply to an SSD. Most likely, FCFS is the one used by an SSD as it ensures some degree of fairness.
