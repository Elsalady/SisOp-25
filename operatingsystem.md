# Operating System

Name: Elsa Lady Dia Fatma

NRP: 3124521025

Class: 1 TI A 

## Practice Exercises
#### 1.1 What are the three main purposes of an operating system?

Answer:

The three main puropses are:

• To provide an environment for a computer user to execute programs
on computer hardware in a convenient and efficient manner.

• To allocate the separate resources of the computer as needed to
solve the problem given. The allocation process should be as fair
and efficient as possible.

• As a control program it serves two major functions: (1) supervision
of the execution of user programs to prevent errors and improper use
of the computer, and (2) management of the operation and control
of I/O devices.

#### 1.2 We have stressed the need for an operating system to make efficient use of the computing hardware. When is it appropriate for the operating system to forsake this principle and to “waste” resources? Why is such a system not really wasteful?

Answer:

Single-user systems should maximize use of the system for the user. A
GUI might “waste” CPU cycles, but it optimizes the user’s interaction
with the system.

#### 1.3 What is the main difficulty that a programmer must overcome in writing an operating system for a real-time environment?

Answer:

The main difficulty is keeping the operating system within the fixed time
constraints of a real-time system. If the system does not complete a task
in a certain time frame, it may cause a breakdown of the entire system it
is running. Therefore when writing an operating system for a real-time
system, the writer must be sure that his scheduling schemes don’t allow
response time to exceed the time constraint.

#### 1.4 Keeping in mind the various definitions of operating system, consider whether the operating system should include applications such as Web browsers and mail programs. Argue both that it should and that it should not, and support your answers.

Answer:

An argument in favor of including popular applications with the
operating system is that if the application is embedded within the
operating system, it is likely to be better able to take advantage of
features in the kernel and therefore have performance advantages
over an application that runs outside of the kernel. Arguments against
embedding applications within the operating system typically dominate
however: 

(1) the applications are applications - and not part of an
operating system 

(2) any performance benefits of running within the
kernel are offset by security vulnerabilities

(3) it leads to a bloated
operating system.

#### 1.5 How does the distinction between kernel mode and user mode function as a rudimentary form of protection (security) system?

Answer:

The distinction between kernel mode and user mode provides a rudimentary
form of protection in the following manner. Certain instructions
could be executed only when the CPU is in kernel mode. Similarly,
hardware devices could be accessed only when the program is executing in
kernel mode. Control over when interrupts could be enabled or disabled
is also possible only when the CPU is in kernel mode. Consequently, the
CPU has very limited capability when executing in user mode, thereby
enforcing protection of critical resources.

#### 1.6 Which of the following instructions should be privileged?

a. Set value of timer.

b. Read the clock.

c. Clear memory.

d. Issue a trap instruction.

e. Turn off interrupts.

f. Modify entries in device-status table.

g. Switch from user to kernel mode.

h. Access I/O device.

Answer:

The following operations need to be privileged: Set value of timer, clear
memory, turn off interrupts, modify entries in device-status table, access
I/O device. The rest can be performed in user mode.

#### 1.7 Some early computers protected the operating system by placing it in a memory partition that could not be modified by either the user job or the operating system itself. Describe two difficulties that you think could arise with such a scheme.

Answer:

The data required by the operating system (passwords, access controls,
accounting information, and so on) would have to be stored in or passed
through unprotected memory and thus be accessible to unauthorized
users.

#### 1.8 Some CPUs provide for more than two modes of operation. What are two possible uses of these multiple modes?

Answer:

Although most systems only distinguish between user and kernel
modes, some CPUs have supported multiple modes. Multiple modes
could be used to provide a finer-grained security policy. For example,
rather than distinguishing between just user and kernel mode, you
could distinguish between different types of user mode. Perhaps users
belonging to the same group could execute each other’s code. The
machine would go into a specified mode when one of these users was
running code. When the machine was in this mode, a member of the
group could run code belonging to anyone else in the group.

Another possibility would be to provide different distinctions within
kernel code. For example, a specific mode could allow USB device drivers
to run. This would mean that USB devices could be serviced without
having to switch to kernel mode, thereby essentially allowing USB device
drivers to run in a quasi-user/kernel mode.

#### 1.9 Timers could be used to compute the current time. Provide a short description of how this could be accomplished.

Answer:

A program could use the following approach to compute the current
time using timer interrupts. The program could set a timer for some
time in the future and go to sleep. When it is awakened by the interrupt,
it could update its local state, which it is using to keep track of the
number of interrupts it has received thus far. It could then repeat this
process of continually setting timer interrupts and updating its local
state when the interrupts are actually raised.

#### 1.10 Give two reasons why caches are useful. What problems do they solve? What problems do they cause? If a cache can be made as large as the device for which it is caching (for instance, a cache as large as a disk), why not make it that large and eliminate the device?

Answer:

Caches are useful when two or more components need to exchange
data, and the components perform transfers at differing speeds. Caches
solve the transfer problem by providing a buffer of intermediate speed
between the components. If the fast device finds the data it needs in the
cache, it need not wait for the slower device. The data in the cache must
be kept consistent with the data in the components. If a component has
a data value change, and the datum is also in the cache, the cache must
also be updated. This is especially a problem on multiprocessor systems
where more than one process may be accessing a datum. A component
may be eliminated by an equal-sized cache, but only if: (a) the cache
and the component have equivalent state-saving capacity (that is, if the
component retains its data when electricity is removed, the cache must
retain data as well), and (b) the cache is affordable, because faster storage
tends to be more expensive.

#### 1.11 Distinguish between the client–server and peer-to-peer models of distributed systems.

Answer:

The client-server model firmly distinguishes the roles of the client and
server. Under this model, the client requests services that are provided
by the server. The peer-to-peer model doesn’t have such strict roles. In
fact, all nodes in the system are considered peers and thus may act as
either clients or servers—or both. A node may request a service from
another peer, or the node may in fact provide such a service to other
peers in the system.

For example, let’s consider a system of nodes that share cooking
recipes. Under the client-server model, all recipes are stored with the
server. If a client wishes to access a recipe, it must request the recipe from
the specified server. Using the peer-to-peer model, a peer node could ask
other peer nodes for the specified recipe. The node (or perhaps nodes)
with the requested recipe could provide it to the requesting node. Notice
how each peer may act as both a client (it may request recipes) and as a
server (it may provide recipes).

#### 1.12 How do clustered systems differ from multiprocessor systems? What is required for two machines belonging to a cluster to cooperate to provide a highly available service?

Answer:

Clustered systems use multiple independent computers working together,
while multiprocessor systems have multiple CPUs within a single machine
sharing memory and resources. Clusters rely on network connections,
whereas multiprocessors use shared memory for faster communication.

For two machines in a cluster to provide high availability,
they need to share storage and use a coordination mechanism.

#### 1.13 Consider a computing cluster consisting of two nodes running a database. Describe two ways in which the cluster software can manage access to the data on the disk. Discuss the benefits and disadvantages of each.

Answer:

One way is asymmetric clustering, where one node actively handles the
database while the other stays on standby, ready to take over if the
active node fails. This improves reliability but wastes resources since
the standby node is mostly idle. Another way is symmetric clustering,
where both nodes actively process database requests, sharing the workload.
This improves performance and resource utilization but requires complex
synchronization to avoid conflicts when accessing the disk.

#### 1.14 What is the purpose of interrupts? How does an interrupt differ from a trap? Can traps be generated intentionally by a user program? If so, for what purpose?

Answer:

Interrupts signal the CPU to stop its current task and handle an
important event, like input from a keyboard or a completed I/O
operation. They help the OS manage multiple tasks efficiently.

A trap is a type of software-generated interrupt, usually triggered
by an error like division by zero or a system call. Unlike hardware
interrupts, traps come from the executing program itself. And yes,
traps can be intentionally generated by user programs, mainly to request
OS services through system calls, like reading a file or allocating memory.

#### 1.15 Explain how the Linux kernel variables HZ and jiffies can be used to determine the number of seconds the system has been running since it was booted.

Answer:

In Linux, HZ defines the number of timer ticks per second,
and jiffies is a counter that increments with each tick.
To calculate uptime, you divide jiffies by HZ. For example,
if HZ is 100 and jiffies is 500,000 means the system has been running for 5000 sec since boot. 

#### 1.16 Direct memory access is used for high-speed I/O devices in order to avoid increasing the CPU's execution load. a. How does the CPU interface with the device to coordinate the transfer? b. How does the CPU know when the memory operations are complete? c. The CPU is allowed to execute other programs while the DMA controller is transferring data. Does this process interfere with the execution of the user programs? If so, describe what forms of interference are caused.

Answer:

a.The CPU sets up the Direct Memory Access (DMA) transfer by giving the DMAcontroller details like memory addresses, transfer size, and the I/O device involved. Once configured, the DMA controller handles the transfer independently.
b.When the transfer is complete, the DMA controller sends an interrupt to the CPU, letting it know that the operation has finished.
c.Yes, DMA can interfere with user programs because it accesses the memory bus, temporarily blocking the CPU from accessing memory. This can cause minor delays in execution, especially if multiple DMA transfers happen at once. However, the performance gain from offloading data transfers usually outweighs the small interruptions.

#### 1.17 Some computer systems do not provide a privileged mode of operation in hardware. Is it possible to construct a secure operating system for these computer systems? Give arguments both that it is and that it is not possible.

Answer:

Possible: A secure OS can still be built using software-based protection mechanisms like virtualization, sandboxing, and access control policies. The OS can enforce strict execution rules and limit what user programs can do, reducing security risks.
Not possible: Without hardware-enforced privilege levels, user programs could directly access system resources, making it easier for malware or faulty programs to corrupt memory, modify system settings, or interfere with critical operations. Software-based protections alone may not be strong enough to prevent all security threats.

#### 1.18 Many SMP systems have different levels of caches; one level is local to each processing core, and another level is shared among all processing cores. Why are caching systems designed this way?

Answer:

Caching is designed this way to balance speed and efficiency.
1.Local (per-core) caches provide fast access to frequently used data, reducing latency since each core can retrieve data without waiting on others.
2.Shared caches allow cores to exchange data efficiently and help maintain consistency, reducing the need for expensive memory access.

#### 1.19 Rank the following storage systems from slowest to fastest: a.Hard-disk drivers b.Registers c.Optical disk d.Main memory e.Nonvolatile memory f.Magnetic tapes g.Cache

Answer:

Magnetic tapes → Optical disk → Hard-disk drives → Non-volatile memory → Main memory → Cache → Registers

#### 1.20 Consider an SMP system similar to the one shown in figure 1.8. Illustrate with an example how data residing in memory could in fact have a different value in each of the local caches.

Answer:

In an SMP system, each core has its own local cache, which can lead to cache inconsistency if proper synchronization isn’t maintained.

For Example: 
1.Core 1 loads J = 10 into its local cache and updates it to J = 20.
2.Core 2, unaware of Core 1’s update, loads J = 10 into its own cache.
3.Now, memory still has J= 10, but Core 1’s cache has J = 20, and Core 2’s cache has J = 10, which causing inconsistency.

#### 1.21 Discuss, with examples, how the problem of maintaining coherence of cached data manifests itself in the following processing environments: a.Single-processor systems b.Multiprocessor systems c.Distributed systems

Answer:

a.Single-processor systems: Issues arise when external devices likeDMA update memory, but the CPU still reads old cached data.
b.Multiprocessor systems: Each core has its own cache, leading to outdated values if changes aren’t synchronized. Solved using cache coherence protocols like MESI.
c.Distributed systems: Different computers may store outdated copies of shared data. Solved using consistency models like write-through caching or distributed locking.

#### 1.22 Describe a mechanism for enforcing memory protection in order to prevent a program from modifying the memory associated with other programs.

Answer:

Memory protection is enforced using an MMU with base and limit registers.
The base register sets the program’s memory start, and the limit register
defines its range. If a program accesses memory outside this range, the OS
blocks it, preventing interference with other programs.

#### 1.23 Which network configuration (LAN or WAN) would best suit with other programs. a.A campus students union b.Several campus location across a statewide university system c.A neighborhood

Answer:

a.Campus student union = LAN, Covers a small area with high-speed connectivity.
b.Several campus locations across a statewide university system = WAN, Connects multiple distant locations.
c.A neighborhood = LAN, If within a small area, like a community network.

#### 1.24 Describe some of the challenges of designing operating systems for mobile devices compared with designing operating systems for traditional PCs.

Answer:

a.Limited resources, Mobile devices have less CPU power, memory, and battery life, requiring efficient resource management.
b.Touch interface, Unlike PCs with keyboards and mice, mobile OS must be optimized for touch gestures.
c.Connectivity, Mobile OS needs to handle frequent network changes (Wi-Fi, cellular) and power-efficient communication.
d.App restrictions, Security and sandboxing are stricter to prevent malicious apps from affecting the system.
e.Energy efficiency, Power management is crucial since mobile devices rely on batteries.

#### 1.25 What are some advantages of peer-to-peer systems over client-server systems?

Answer:

a.No single point of failure, Since there’s no central server, the system is more resilient.
b.Scalability, More devices can join without overloading a central server.
c.Cost-effective, No need for expensive server hardware or maintenance.
d.Better resource utilization, Each device contributes computing power and storage.

#### 1.26 Describe some distributed applications that would be appropriate for a peer-to-peer system.

Answer:

a.File-sharing networks, Users share files directly without a central server.
b.Blockchain and cryptocurrencies, Transactions are verified by multiple peers instead of a central authority.
c.Video conferencing, Calls can be routed directly between users.
d.Online gaming, Some multiplayer games use P2P to reduce server load and latency.

#### 1.27 Identify several advantages and several disadvantages of open-source operating systems. Identify the types of people who would find each aspect to be an advantage or a disadvantage.

Answer: 

Open-source OS is free, customizable, and has strong community support,
making it great for developers, researchers, and tech enthusiasts.
It also offers better security through transparency. However,
it can be less user-friendly, lacks official support, and may have compatibility issues,
which can be a drawback for casual users and businesses