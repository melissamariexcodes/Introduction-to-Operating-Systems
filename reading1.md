# CECS 326 Reading Assignment 01: Introduction to Operating Systems
### Name:
### Date: 

### Assignment Description
Answer the following questions from the Chapter 1 reading from your textbook. Be thorough and complete with your answers. 

1. What are the two main functions of an operating system?
An operating system serves two core purposes. First, it provides abstractions that make the hardware easier for users and programs to interact with, such as files, processes, and virtual memory. Second, it is responsible for managing the system’s resources, including the CPU, memory, storage, and I/O devices, ensuring they are allocated efficiently and safely among running programs.

2. What is the difference between timesharing and multiprogramming systems?
A timesharing system is designed to support interactive use by many users at once. Each user interacts with the system through a terminal, and the operating system rapidly switches the CPU among users so everyone experiences responsive performance.

In contrast, multiprogramming focuses on improving CPU utilization rather than interactivity. Multiple jobs are kept in memory at the same time so that when one job is waiting for I/O, the CPU can immediately switch to another job instead of sitting idle. The main goal is to keep the processor busy as much as possible.

3. The family-of-computers idea was introduced in the 1960s with the IBM System/360 mainframes. Is this idea now dead as a doornail or does it live on?
The idea is not dead. While the specific hardware and operating systems from that era have evolved, the underlying concept of a compatible family of machines still exists today. Modern systems continue this idea through architectures that support multiple models with shared instruction sets and software compatibility. The role of these systems has shifted, often appearing in large-scale computing environments such as servers, enterprise systems, and data centers rather than traditional standalone mainframes.

4. What is the difference between kernel and user mode? Explain how having two distinct modes aids in designing an operating system.
Kernel mode allows the operating system full access to the hardware and all machine instructions. This includes operations such as controlling memory, handling I/O, and managing devices.

User mode, on the other hand, restricts programs to a limited set of instructions and prevents direct access to hardware. Having these two modes improves system reliability and security because user programs cannot interfere with the operating system or other processes. Any sensitive operation must be requested through the OS, which can validate and control it.

5. On early computers, every byte of data read or written was handled by the CPU (i.e., there was no DMA). What implications does this have for multiprogramming?
Without Direct Memory Access, the CPU must be actively involved in every I/O operation. This means the processor cannot perform other useful work while data is being transferred. As a result, multiprogramming offers little benefit because the CPU remains busy handling I/O instead of switching to another job. Efficient multiprogramming depends on the ability to overlap computation with I/O, which is difficult when the CPU is responsible for every data transfer.

6. There are several design goals in building an operating system, for example, resource utilization, timeliness, robustness, and so on. Give an example of two design goals that may contradict one another.
A common conflict occurs between fairness and real-time performance. Fairness aims to give all processes an equal or balanced share of system resources. Real-time systems, however, must prioritize certain tasks to ensure deadlines are met. Giving priority to real-time tasks can result in other processes receiving fewer resources, which violates strict fairness.

7. Which of the following instructions should be allowed only in kernel mode?
(a) Disable all interrupts. Kernel mode
(b) Read the time-of-day clock. User mode allowed
(c) Set the time-of-day clock. Kernel mode
(d) Change the memory map. Kernel mode

8. Consider a system that has two CPUs, each CPU having two threads (hyperthreading). Suppose three programs, P0, P1, and P2, are started with run times of 5, 10 and 20 msec, respectively. How long will it take to complete the execution of these programs? Assume that all three programs are 100% CPU bound, do not block during execution, and do not change CPUs once assigned.
Hyperthreading allows a CPU to switch between threads quickly, but it does not provide true parallel execution for CPU-bound tasks. Since the programs do not block and cannot migrate between CPUs, they effectively execute one after another on the same processing resources. Therefore, the total completion time is the sum of their run times: 35 milliseconds.

9. What is a trap instruction? Explain its use in operating systems.
A trap instruction is a controlled mechanism that allows a user program to transfer execution to the operating system. When a trap occurs, the CPU switches from user mode to kernel mode so the OS can safely perform a requested service, such as a system call. This provides a secure way for applications to request privileged operations without direct hardware access.

10. Modern operating systems decouple a process address space from the machine’s physical memory. List two advantages of this design.
One advantage is improved memory management, as the operating system can give each process the illusion of having its own large, continuous memory space regardless of physical memory limitations.

Another advantage is better protection and flexibility, since processes are isolated from one another and memory can be swapped between RAM and disk as needed. This abstraction improves both system stability and efficient use of memory resources.
