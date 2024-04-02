# Multiprogramming System

Multiprogramming in an operating system in which more than one program can executed at the same time. The objective of multiprogramming is to maximise the utilization of resources. 

The system’s job scheduler selects and loads several jobs into the memory simultaneously, allowing the CPU to switch between them as needed.

Consider Two processes namely A and B are scheduled to the system. Initially the system startes with executing A and encounters a part where user input is required. While A is waiting for the input, the CPU can switch to B which is ready to execute. This overlapping of I/O and CPU operations helps to keep the CPU busy and improve overall system efficiency.

Therefore, Multiprogramming systems can execute multiple jobs concurrently.


<img width="652" alt="04" src="https://github.com/Rajendran2201/operating-systems/assets/137254223/0ce91b95-a846-4090-881c-2d835e2ba3ad">


- The operating system keeps several jobs in memory simultaneously.Since, in general, main memory is too small to accommodate all jobs,the jobs are kept initially on the disk in the job pool.
- This pool consists of all processes residing on disk awaiting allocation of main memory.
- Job scheduler takes a set of jobs from this pool and brings it into memory based on scheduling algorithms.
- Multiprogrammed systems provide an environment in which the various system resources (for example, CPU, memory, and peripheral devices) are utilized effectively, but they do not provide for user interaction with the computer system.
- When a process has to wait (for I/O for example), OS switches to another job.

Multiprogramming is broadly classified into two types namely 

## Multi-user operating system

- A multi-user operating system allows many users to share processing time on a powerful central computer on different terminals.
- The operating system does this by quickly switching between terminals, each receiving a limited amount of CPU time on the central computer.
- Operating systems change so rapidly between terminals that each user appears to have constant access to the central computer.
- If there are many users on such a system, the time it takes for the central computer to respond may become more apparent.

## **Multitasking operating system**

- Multitasking is a method that is divided into two types:
    - *Preemptive Scheduling algorithm:* In the preemptive scheduling algorithm if more than one process wants to enter into the critical section then it will be allowed and it can enter into the critical section without any interruption only if no other progress is in the critical section.
    - *Non-Preemptive scheduling algorithm:* If a process gets a critical section then it will not leave the critical section until or unless it works gets done.
    
    <aside>
    
    The main principle of multiprogramming system is to maximise the processor usage.
    
    </aside>
