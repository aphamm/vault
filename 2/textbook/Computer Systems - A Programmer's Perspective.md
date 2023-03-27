---
create: 23.02.02
view: 23.02.02
update: 23.02.02
level: two
content: textbook
status: draft
rating:
aliases: []
tags: []
---
``` toc
min_depth: 1
max_depth: 2
```
---

# A Tour of Everything

### Computer Systems
- Hardware + systems software to run application programs

### Everything are Bits
- Source file → text file → sequence of bytes (8 bits)
- All information in a system → represented as bits
	- Context in which we view them distinguishes data objects

### Programs are Translated
- Compiler Driver → translate source file to executable object file stored on disk
- Assembly language → common output language for different compilers
![[Pasted image 20230202191252.png]]
- Understanding compilation → optimize program performance, understand link-time errors, avoid security holes

### Hardware Organization
- Buses → collection of electrical conduits that transfer fixed-sized chunks (words)
- I/O Device → system’s connection to external world
	- Controller (on device or motherboard) vs. Adapter (plugs into slot)
- Main memory → temporary storage device of dynamic random access memory (DRAM)
- Central Processing Unit CPU → executes instructions stored in main memory
	- Program Counter → word-size register that points to address of machine language instruction
	- Instruction Set Architecture → simple instruction execution model (effect of each machine-code instruction)
		- Microarchitecture → how processor is actually implemented
	- Arithmetic/Logic Unit → computes new data + address values

![[Pasted image 20230202192409.png]]

### Cache Matters
- Processor-Memory gap increases → easier and cheaper to make processors run faster than it is to make main memory run faster
- Cache Memories → implemented via static random access memory SRAM
	- Exploits locality → tendency for programs to access data + code in localized regions
- Memory hierarchy → devices become slower, larger, less costly per byte as we move down
	- Story at one level serves as the cache for the new level

### Operating System
- OS → layer of software between application program and hardware
	- Purpose → protect hardware and provide simple uniform mechanisms to control low-level hardware devices
- Processes → OS gives the illusion the program is the only one running on the system with exclusive access to process, main memory & I/O devices
	- Process → OS’s abstraction for running a program
	- Context Switching → keep track of all state information of a process in order to interleave processes
	- System call → passes control to OS
	- Kernel → manages transitions between processes (always resident in memory)
- Threads → multiple execution units of a single process
	- Each running in the context of the process and share same code + global data
	- More efficient that processes
- Virtual Memory → abstraction in where each process has the illusion that it has exclusive use of main memory (virtual address space)
	- Store contents of process’s virtual memory on disk + use main memory as cache for the disk

### Networks
- Modern systems often linked to other systems via networks
	- Can be viewed as just another I/O device

### Themes
- Amdahl’s Law → a speed up on one part of a system will effect the overall system based on the significance of that part and how much it sped up
- Concurrency → general concept of a system with multiple simultaneous activities
	- Parallelism → use of concurrency to make a system run faster
	- Thread-Level Concurrency
		- Multiprocessor system → integrated onto a single integrated-circuit chip
		- Hyper-threading (simultaneous multi-threading) → single CPU executing multiple flows of control
			- Decides which threads to execute on a cycle-by-cycle basis
	- Instruction-Level Parallelism → execute multiple instruction at one time
		- Pipelining → actions required to execute instruction partitioned into different steps
	- Single-Instruction, Multiple Data (SIMD) → single instruction causes multiple operations in parallel
- Abstractions
	- Instruction Set Architecture → keeping the same execution model, different processor implementations can execute the same machine code
	- Virtual Machine → abstraction for entire computer![[Pasted image 20230202194206.png]]
