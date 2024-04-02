# Operating System Services 

<img width="594" alt="os-services" src="https://github.com/Rajendran2201/operating-systems/assets/137254223/a6be890e-6893-49b9-8174-255a5e9bc767">



1. **User interface**
a. Almost all operating systems have a user interface (UI). This interface can
take several forms.
i. Eg.1 command-line interface (CLI), which uses text commands and a
method for entering them (say, a keyboard for typing in commands in
a specific format with specific options).
ii. Eg 2 batch interface, in which commands and directives to control
those commands are entered into files, and those files are executed.
iii. Eg 3 a graphical user interface (GUI) is used.
2. **Program execution.**
a. The system must be able to load a program into memory and to run that
program. The program must be able to end its execution, either normally or
abnormally (indicating error).
3. **I/O operations**
a. A running program may require I/O, which may involve a file or an I/O device.
For specific devices, special functions may be desired (such as recording to a
CD or DVD drive or blanking a display screen).
b. For efficiency and protection, users usually cannot control I/O devices directly.
Therefore, the operating system must provide a means to do I/O.
4. **File-system manipulation**
a. The file system is of particular interest. Obviously, programs need to read and
write files and directories. They also need to create and delete them by name,
search for a given file, and list file information.
b. Finally, some operating systems include permissions management to allow or
deny access to files or directories based on file ownership.
5. **Communications**
a. There are many circumstances in which one process needs to exchange
information with another process. Such communication may occur between
processes that are executing on the same computer or between processes
that are executing on different computer systems tied together by a computer
network.
    
    b. Communications may be implemented via shared memory, in which two or
    more processes read and write to a shared section of memory, or message
    passing, in which packets of information in predefined formats are moved
    between processes by the operating system.
    
6. **Error detection**
a. The operating system needs to be detecting and correcting errors constantly.
b. Errors may occur in the CPU and memory hardware (such as a memory error
or a power failure), in I/O devices (such as a parity error on disk, a connection
failure on a network, or lack of paper in the printer), and in the user program
(such as an arithmetic overflow, an attempt to access an illegal memory
location, or a too-great use of CPU time).
c. For each type of error, the operating system should take the appropriate
action to ensure correct and consistent computing. Sometimes, it has no
choice but to halt the system. At other times, it might terminate an
error-causing process or return an error code to a process for the process to
detect and possibly correct.
7. **Resource allocation**
a. When there are multiple users or multiple jobs running at the same time,
resources must be allocated to each of them.
b. The operating system manages many different types of resources such as
CPU cycles, main memory, and file storage.
c. For instance, in determining how best to use the CPU, operating systems
have CPU-scheduling routines that take into account the speed of the CPU,
the jobs that must be executed, the number of registers available, and other
factors. There may also be routines to allocate printers, USB storage drives,
and other peripheral devices.
8. **Accounting**
a. We want to keep track of which users use how much and what kinds of
computer resources.
b. This record keeping may be used for accounting (so that users can be billed)
or simply for accumulating usage statistics.
c. Usage statistics may be a valuable tool for researchers who wish to
reconfigure the system to improve computing services.
9. **Protection and security**
a. The owners of information stored in a multiuser or networked computer
system may want to control use of that information.
b. When several separate processes execute concurrently, it should not be
possible for one process to interfere with the others or with the operating
system itself.
c. Protection involves ensuring that all access to system resources is controlled.
d. Security of the system from outsiders is also important. Such security starts
with requiring each user to authenticate himself or herself to the system,
usually by means of a password, to gain access to system resources.
