# Real-Time Systems

Real-time operating systems (RTOS) are used in environments where a large number of events, must be accepted and processed in a short time or within certain deadlines. such applications are industrial control, telephone switching equipment, flight control, and real-time simulations. With an RTOS, the processing time is measured in tenths of seconds. This system is time-bound and has a fixed deadline. The processing in this type of system must occur within the specified constraints. Otherwise, This will lead to system failure.

Examples of real-time operating systems are airline traffic control systems, Command Control Systems, airline reservation systems, Heart pacemakers, Network Multimedia Systems, robots, etc.

### Types of Real-Time Systems

<img width="626" alt="09" src="https://github.com/Rajendran2201/operating-systems/assets/137254223/c01d245a-66b3-4099-b9d9-78f37c94da87">


- Hard Real-Time Operating System: These operating systems guarantee that critical tasks are completed within a range of time.
    - For example, a robot is hired to weld a car body. If the robot welds too early or too late, the car cannot be sold, so it is a hard real-time system that requires complete car welding by the robot hardly on time., scientific experiments, medical imaging systems, industrial control systems, weapon systems, robots, air traffic control systems, etc.
- Soft real-time operating system: This operating system provides some relaxation in the time limit.
    - For example – Multimedia systems, digital audio systems, etc. Explicit, programmer-defined, and controlled processes are encountered in real-time systems. A separate process is changed by handling a single external event. The process is activated upon the occurrence of the related event signaled by an interrupt.
- Firm Real-time Operating System: RTOS of this type have to follow deadlines as well. In spite of its small impact, missing a deadline can have unintended consequences, including a reduction in the quality of the product.
    - Example: Multimedia applications.
