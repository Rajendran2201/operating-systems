# Time Sharing Systems

A time-sharing operating system is an operating system design that allows multiple users or processes to concurrently share the same system resources, such as the CPU, memory, and peripherals. It enables each user or process to have the illusion of having dedicated access to the system while effectively sharing resources in a time-sliced manner.

In a time-sharing operating system, the CPU time is divided into small time intervals called time slices or quantum. Each user or process is allocated a time slice during which it can execute its tasks. The operating system switches between processes rapidly, giving the illusion of parallel execution.

The operating system uses scheduling algorithms, such as round-robin or priority-based scheduling, to determine which process should be allocated the CPU next. Context switching, which involves saving and restoring the execution context of each process, is performed to switch between processes.

- Active State – The user’s program is under the control of the CPU. Only one program is available in this state.
- Ready State – The user program is ready to execute but it is waiting for its turn to get the CPU. More than one user can be in a ready state at a time.
- Waiting State – The user’s program is waiting for some input/output operation. More than one user can be in a waiting state at a time.

<img width="658" alt="06" src="https://github.com/Rajendran2201/operating-systems/assets/137254223/37f20395-779a-431d-931d-5c06c6d6895a">


Example : Compatible Time Sharing System (CTSS)

<aside>

  
💡 The main principle of time sharing system is to minimise the response time.

</aside>
