# Components of OS

<aside>
💡 Interrupts - System call - Virtual machines-  Symmetric multiprocessing - Microkernel

</aside>

## Interrupts

Interrupt is defined as an event that alters the sequence of instructions executed by the process. It changes the flow of the program.

- Devices can interrupt the CPU at anytime asynchronously.
- When interrupt arrives, kernel saves its current process and jumps to service the interrupt.
- Based on the interrupt priority, interrupts are processed.
- Once the interrupt process is completed, the control is transferred back to the previous process.

- The amount of time between the generation of an interrupt and its handling is known as **interrupt latency.** When the device generating the interrupt needs a specific length of time to generate the interrupt, interrupt latency is required. For instance, if a printer is printing paper, the computer needs to stop the printing program and wait for the document to finish printing. The interrupt latency is the amount of time the computer has to stop the program from operating.

The interrupts are classified into two types : 

1. **Hardware Interrupt  :** A sort of interrupt called a hardware interrupt is one that is produced by hardware or a device. Traps and exceptions are other names for software interruptions.
    1. Example : Division of a number by zero throws an exception that results in the software interrupt.
2. **Software Interrupt :** A sort of interrupt called a software interrupt is one that is produced by software or a system.

---

## System Call

A system call is a way for programs to interact with the operating system. A computer program makes a system call when it makes a request to the operating system’s kernel. System call provides the services of the operating system to the user programs via *Application Program Interface(API)*. It provides an interface between a process and an operating system to allow user-level processes to request services of the operating system. System calls are the only entry points into the kernel system. All programs needing resources must use system calls.

A system call can be written in high-level languages like **C or Pascal** or in assembly language. If a high-level language is used, the operating system may directly invoke system calls, which are predefined functions. System calls are essential for the proper functioning of an operating system, as they provide a standardized way for programs to access system resources. Without system calls, each program would need to implement its own methods for accessing hardware and system services, leading to inconsistent and error-prone behavior.
<img width="597" alt="system-call" src="https://github.com/Rajendran2201/operating-systems/assets/137254223/23952218-48a9-4037-816d-10a9097bdfbe">

```c
// the following functions can be used to make system calls 
open(), wait(), read(), close(), write(), exit()

//example using open
//this will link to C runtime library
open(filename, buffer, mode)
```

**open():** Accessing a file on a file system is possible with the open() system call. It gives the file resources it needs and a handle the process can use. A file can be opened by multiple processes simultaneously or just one process. Everything is based on the structure and file system.

**read():** Data from a file on the file system is retrieved using it. In general, it accepts three arguments:

1. A description of a file.
2. A buffer for read data storage.
3. How many bytes should be read from the fileBefore reading, the file to be read could be identified by its file descriptor and opened using the open() function.

**wait():** In some systems, a process might need to hold off until another process has finished running before continuing. When a parent process creates a child process, the execution of the parent process is halted until the child process is complete. The parent process is stopped using the wait() system call. The parent process regains control once the child process has finished running.

**write():** Data from a user buffer is written using it to a device like a file. A program can produce data in one way by using this **system call**. generally, there are three arguments:

1. A description of a file.
2. A reference to the buffer where data is stored.
3. The amount of data that will be written from the buffer in bytes.

**fork():** The fork() system call is used by processes to create copies of themselves. It is one of the methods used the most frequently in operating systems to create processes. When a parent process creates a child process, the parent process’s execution is suspended until the child process is finished. The parent process regains control once the child process has finished running.

**exit():** A system call called exit() is used to terminate a program. In environments with multiple threads, this call indicates that the thread execution is finished. After using the exit() system function, the operating system recovers the resources used by the process.

### Working of System Call

Here is the detailed explanation step by step how system call work:

- **User need special resources :** Sometimes programs need to do some special things which can’t be done without the permission of OS like reading from a file, writing to a file , getting any information from the hardware or requesting a space in memory.
- **Program makes a system call request :** There are special predefined instruction to make a request to the operating system. These instruction are nothing but just a “system call”. The program uses these system calls in its code when needed.
- **Operating system sees the system call :** When the OS sees the system call then it recongnises that the program need help at this time so it temporarily stop the program execution and give all the control to special part of itself called ‘Kernel’ . Now ‘Kernel’ solve the need of program.
- **Operating system performs the operations :**Now the operating system perform the operation which is requested by program . Example : reading content from a file etc.
- **Operating system give control back to the program :** After performing the special operation, OS give control back to the program for further execution of program .

### Importance of System Call

*System calls are necessary for several reasons:*

***Access to privileged operations:*** Many operations, such as managing hardware devices or modifying system configurations, require higher privileges that are only accessible through system calls.

***Resource management:*** System calls provide a standardized interface for allocating and managing system resources like memory, files, and devices, ensuring fair and controlled access by different processes.

***Abstraction:*** System calls abstract the underlying complexities of the operating system, allowing application developers to interact with the system in a higher-level, platform-independent manner.

***Security and protection:*** System calls enforce access control and security policies, preventing unauthorized access to sensitive resources and protecting the integrity of the system.

**1. Passing parameters in registers.**

- It is the simplest method among the three
- Here we directly pass the parameters to registers.
- But it will it is limited when, number of parameters are greater than the number of registers.
- Here is the C program code:

```c
// Passing parameters in registers. 

#include <fcntl.h>
#include <stdio.h>

int main()
{
	const char* pathname = "example.txt";
	int flags = O_RDONLY;
	mode_t mode = 0644;

	int fd = open(pathname, flags, mode);
// in function call open(), we passed the parameters pathanme,flags,mode to the kernal directly

	if (fd == -1) {
		perror("Error opening file");
		return 1;
	}

	// File operations here...

	close(fd);
	return 0;
}

```

**2.Address of the block is passed as parameters**

- It can be applied when the number of parameters are greater than the number of registers.
- Parameters are stored in blocks or table.
- The address of the block is passed to a register as a parameter.
- Most commonly used in Linux and Solaris.
- Here is the C program code:

```c
//Address of the block is passed as parameters

#include <stdio.h>
#include <fcntl.h>

int main() {
	const char *pathname = "example.txt";
	int flags = O_RDONLY;
	mode_t mode = 0644;

	int params[3];
		// Block of data(parameters) in array
	params[0] = (int)pathname;
	params[1] = flags;
	params[2] = mode;

	int fd = syscall(SYS_open, params);
		// system call

	if (fd == -1) {
		perror("Error opening file");
		return 1;
	}

	// File operations here...

	close(fd);
	return 0;
}

```

---

### **Types of System Calls**

1. Process control
2. File management
3. Device management
4. Information maintenance
5. Communications

---

## Virtual Machine

<aside>
💡 **A virtual machine is “an isolated and efficient duplicate of an actual computer machine**."

</aside>

Virtualization is an abstraction layer that decouples the physical hardware from the operating system to deliver greater resource utilization and flexibility. Virtual machine is a component which has its own virtual hardware upon which the operating system and applications are loaded. In a virtual machine architecture, the operating system gives each process the illusion that it is the only process on the machine. Each user directs the virtual machine to perform different commands. These commands are then executed on the physical machine in a multiprogramming environments. Virtual machines tend to be less efficient than real machines because they access the hardware indirectly. The Java Virtual Machine (JVM) is one of the most widely used virtual machine. 

**Characteristics of virtual machines**

The characteristics of the virtual machines are as follows −

- Multiple OS systems use the same hardware and partition resources between virtual computers.
- Separate Security and configuration identity.
- Ability to move the virtual computers between the physical host computers as holistically integrated files.

**Types of Virtual Machines**

- **System virtual machines:** These types of virtual machines are also termed as full **virtualization VMs**. It facilitates a replacement for an actual machine. These VMs offers the functionality required for executing the whole operating system (OS). A hypervisor applies native execution for managing and sharing hardware. It permits for more than one environment that is separated from each other while exists on a similar physical machine. Novel hypervisor applies virtualization-specific hardware and hardware-assisted virtualization from various host CPUs primarily.
- **Process virtual machines:** These Virtual Machines are created for executing several programs of the computer within the platform-independent environment.

<img width="637" alt="JVM" src="https://github.com/Rajendran2201/operating-systems/assets/137254223/e2a8cb17-43b3-4f16-be60-6fe9b794876a">


**Advantages of VM**

- Virtual Machine facilitates compatibility of the software to that software which is executing on it. Hence, each software specified for a virtualized host would also execute on the VM.
- It offers isolation among distinct types of processors and OSes. Hence, the processor OS executing on a single virtual machine can't change the host of any other host systems and virtual machines.
- Virtual Machine facilitates encapsulation. Various software present over the VM could be controlled and modified.
- Virtual machines give several features such as the addition of **new operating system.** An error in a single operating system will not affect any other operating system available on the host. It offers the transfer of many files between VMs, and no dual booting for the multi-OS host.
- VM provides better management of software because VM can execute a complete stack of software of the run legacy operating system, host machine, etc.
- It can be possible to distribute hardware resources to software stacks independently. The VM could be transferred to distinct computers for balancing the load.

---

## Symmetric Multiprocessing

The multiprocessing system, in which multiple processors work together on the same task, is
known as Symmetric Multiprocessing System. In this system, each processor can perform all
types of tasks. All processors are treated equally as peers and no master-slave relationship exists
between the processors.

For example, different processors in the system can communicate with each other. Similarly, an
I/O can be processed on any processor. However, I/O must be controlled to ensure that the data
reaches the appropriate processor. Because all the processors share the same memory, so the
input data given to the processors and their results must be separately controlled. 

Today all modern operating systems including Windows and Linux provide support for SMP.
It must be noted that in the same computer system, the asymmetric multiprocessing and
symmetric multiprocessing technique can be used through different operating systems.

![symmetric-multiprocessing](https://github.com/Rajendran2201/operating-systems/assets/137254223/e7441e08-5b29-44eb-ab89-84e487e948c9)


## Kernel

The kernel is a software code that resides in the central core of a operating system. It has complete control over the system. The kernel does not interact directly with the user. But it interacts with the shell, other programs and hardware. When the operating system boots, kernel is the first part of the operating system to load into memory. Kernel remains in memory for the entire duration of the computer session. The kernel code is usually loaded into a protected area memory. 

When a computer crashes, it actually means the kernel has crashed. The kernel provides services for process management, memory management, file management and I/O management. 

A kernel includes the following components, 

1. Scheduler
2. Supervisor
3. Interrupt handler
4. Memory manager

**Objectives of Kernel :**

- To establish communication between user level application and hardware.
- To decide state of incoming processes.
- To control disk management.
- To control memory management.
- To control task management.

**Types of Kernel** 

1. Monolithic kernel
2. Microkernel 
3. Hybrid kernel
4. Exo-kernel

**Advantages** 

- Simple to design and implement
- Simplicity provides speed on simple hardware
- It can be expanded using module system
- Time tested and design well known

**Disadvantages** 

- Runtime loading and unloading is not possible because of module system
- If the code base size increases, maintainance is difficult
- Fault tolerance is low

### MicroKernel

It is kernel types which has minimalist approach. It has virtual memory and thread scheduling. It is more stable with less services in kernel space. It puts rest in user space.

The function of a microkernel is to provide a communication facility between the client programs. It also provides facility to various services which are running in user space. 

It is use in small os.

Example : Mach, L4, AmigaOS, Minix, K42 etc.

Micro-kernel  structure designs the operating system by removing all non-essential components from the kernel and implementing them as system and user programs. This results in a smaller kernel called the micro-kernel. Advantages of this structure are that all new services need to be added to user space and does not require the kernel to be modified. Thus it is more secure and reliable as if a service fails, then rest of the operating system remains untouched. Mac OS is an example of this type of OS.

**Advantages of Micro-kernel structure**

- It makes the operating system portable to various platforms.
- As microkernels are small so these can be tested effectively.
- Uniform interface on request made by a process.
- Supports flexibility. User can add or subtract services according to their requirements

**Disadvantages of Micro-kernel structure**

- Increased level of inter module communication degrades system performance.

## Operating System Services

[Operating System Services](https://github.com/Rajendran2201/operating-systems/blob/main/02-Components%20of%20OS/operating%20system%20services.md)
