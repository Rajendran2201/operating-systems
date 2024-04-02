# Batch Processing Systems

A batch Processing  System is a type of operating system that is used to improve the efficiency  by allowing to run multiple tasks at the same time. Therefore the processor of the operating system is utilised in its maximum efficiency. Many tasks can be done at the same time without having to wait for each one to finish. By scheduling and processing jobs in batches, the system can maximize the utilization of the available resources such as CPU time, memory, and storage.

In batch processing operating systems, users submit their jobs to the system, which are then added to a queue for processing. The system processes each job in turn, without any user intervention, until all jobs have been completed. The jobs in queue are group into batches based on their similarity. The scheduling of jobs is based on the batches.

<img width="642" alt="03" src="https://github.com/Rajendran2201/operating-systems/assets/137254223/859e53d7-9c6a-4ebc-bc92-098210656111">

The Batch Processing System can be analysed in terms of two point of views namely monitor point of view and processor point of view.

### Monitor Point of View

The batch processing system contains a piece of software called as monitor. The monitor is used to control the sequence of events. The major part of the monitor is used for memory management which is called as resident monitor. The remaining part of the monitor is used for processing the user programs. 

- The jobs are given by the user are added to the queue for processing.
- The monitor prepares a job control file (also called as batch script) which contains the instructions for the processor on how to execute each job in the batch.
- Once the batch is submitted, the control is transferred from the monitor to the batch. The monitor waits for the processor to complete all the jobs before receiving any output or results.
- As soon as the process is done, the control is transferred back to the monitor.

### Processor Point of View

- When a batch of jobs are received, the processor reads the job control file or batch script prepared by the monitor.
- The processor then executes each job in the batch sequentially, following the instructions provided in the job control file.
- Only when the job of the processor is complete, it instructs the monitor to start its program execution.
- The program is then executed till the end or till an error is occurred.

### Job Control Language (JCL)

JCL is a special type of programming language. The instructions to the monitor are written in Job Control Language (JCL).  Here's an example:

```fortran
$Job
$FIN
.
.
// FORTRAN instructions
.
.
$LOAD
$RUN
.
.
// Data 
.
.
$END

```

When the program is executed, the appropriate language compiler is loaded from the mass storage(known as tape) and converts it into object code.
