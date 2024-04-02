# Distributed Systems

A distributed system is basically a collection of autonomous (independent by function) computer systems which co-operate with one another through their hardware and software interconnections. In distributed systems, the processors cannot share memory or time, each processor has its own local memory. 

The processors communicate with one another through various communication lines such as high speed buses. These systems are also called as "**Loosely Coupled systems**".

```fortran
Distributed system = Network + Transparency(Invisible)
```

### Types of Distributed Systems:

There are many models and architectures of distributed systems in use today.

- **Client-server systems** involve a multitude of networked computers that interact with a central server for data storage, processing or other common goal.
- **Peer-to-peer networks** distribute workloads among hundreds or thousands of computers all running the same software.
- **Cell phone networks** are an advanced distributed system, sharing workloads among handsets, switching systems and internet-based devices.

<img width="392" alt="08" src="https://github.com/Rajendran2201/operating-systems/assets/137254223/01112ed6-a7fa-472c-a581-2901fb81fdc7">


## Advantages of Distributed Systems

Two main advantages of Distributed Systems are as follows : 

1. **Resource sharing:** If a number of sites connected by a high speed communication lines, it is possible to share the resources from one site to another site.
For example, S, and S are two sites, these are connected by some communication lines, the site
S, having the printer, but S₂ does not having the printer. Then the system can use the printer at S, without moving from 5 to 5,. Therefore resource sharing is possible in distributed systems.
2. **Computation speedup:** A big computation is partitioned into number of partitions, these sub- partitions run concurrently in distributed systems.
For example, site S, need to execute a big computation, this computation is divided into sub computations and these are executed by some other machines in different sites.
