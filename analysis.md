# Introduction

For the solution of the Class Scheduling, we have decided to use **First Come, First Serve (FCFS)** algorithm,
non-preemptive **Shortest Job First** (**SJF**) algorithm
AND,
non-preemptive **Priority Scheduling** algorithm
to schedule the classes.

The **First Come, First Serve (FCFS)** scheduling algorithm is just like its name, processes will be allocated or schedules according to their arrival time or which one comes first. Process which comes first in the ready queue will get the CPU first. The lesser the arrival time, the sooner will the process gets the CPU. The FCFS scheduling algorithm is non-preemptive algorithm which means the process priority does not matter. If a process with very least priority is being executed and suddenly there is another higher priority process arrives, the higher priority process will have to wait.

**Shortest Job First (SJF) scheduling** is an algorithm where processes are executed in ascending order based on the burst time. The process with the shortest burst time is will be executed first and the order will go until the longest burst time. SJF can be divided to pre-emptive or non-preemptive. In **non-preemptive Shortest Job First (SJF),** once a process has been allocated to the CPU, the process keeps the CPU until the process has finished its execution.

In the **non-preemptive Priority Scheduling,** processes are scheduled according to the priority number assigned to them. Once the process gets scheduled, it will run till the completion. The lower the priority number, the higher the priority of the process. If a new process arrives with a higher priority than the current running process, the incoming process is put at the head of the ready queue, which means after the execution of the current process it will be processed.

# Consideration

We consider that the class:
1.  Cannot be interfered or stopped halfway

_Thus, the reason for why non-preemptive methods of the algorithms are chosen_

# Analysis

#### Input:

```
struct Process
{
   int ccode;          // course code
   int duration;       // class duration
   int priority;       //priority
   int arrival_time;   //prefered arrival time
};

Process proc[] = {{2201, 3, 2, 1},
                  {3401, 2, 3, 2},
                  {1103, 1, 1, 3}};
```
 
## First Come First Serve (FCFS)

 > In FCFS algorithm, the classes are sorted depending on their respective: </br>
 1. preferred ***Arrival time*** </br>
 **IF** two or more classes have the same arrival time </br>
 2. whichever classes that is earlier in the queue will execute first

#### Output:
```
Order in which process gets executed
2201    3401   1103

| Processes | Burst time | Waiting time | Turn around time |
|-----------|------------|--------------|------------------|
|    2201   |     3      |      0       |        3         |
|    3401   |     2      |      3       |        5         |
|    1103   |     1      |      5       |        6         |
   
Average waiting time = 2.66667
Average turn around time = 4.66667
```

#### Analysis of First Come First Serve (FCFS) scheduling algorithm
- It is worst than the Non-Preemptive Shortest Job First (SJF) and Non-Preemptive Priority Scheduling because it has the slowest average waiting and turn around time between the 3 scheduling algorithms.

## Non-Preemptive Shortest Job First (SJF)

> In non-preemptive SJF algortihm, classes are sorted depending on their:
1. shortest burst time *OR* duration </br>
**IF** two or more classes have the same arrival time </br>
2. classes is sorted based on its preferred **Arrival Time**

// in non-preemptive SJF algorithm, all arrival time is considered as 0

#### Output:
```
Order in which process gets executed
1103  3401  2201

| Processes | Burst time | Waiting time | Turn around time |
|-----------|------------|--------------|------------------|
|    1103   |      1     |       0      |         1        |
|    3401   |      2     |       1      |         3        |
|    1103   |      3     |       3      |         6        |

Average waiting time = 1.33333
Average turn around time = 3.33333
```

#### Analysis of Non-Preemptive Shortest Job First (SJF) scheduling algorithm
- It is better than First Come First Serve (FCFS) and Non-Preemptive Priority Scheduling because it has the fastest average waiting and turn around time between the 3 scheduling algorithms.

## Non-Preemptive Priority Scheduling

> In non-preemptive Priority Scheduling, classes are sorted depending on:
1. The class **Priority level** </br>
**IF** two or more classes have the same priority </br>
2. classes is sorted depending on its **Arrival Time**

//because it is non-preemptive most of the time arrival time is considered 0

#### Output:
```
Order in which processes gets executed
3401  2201  1103

| Processes | Burst time | Waiting time | Turn around time |
|-----------|------------|--------------|------------------|
|    3401   |      2     |       0      |         2        |
|    2201   |      3     |       2      |         5        |
|    1103   |      1     |       5      |         6        |

Average waiting time = 2.33333
Average turn around time = 4.33333
```

#### Analysis of Non-Preemptive Priority scheduling algorithm
- It is better than First Come First Serve (FCFS) scheduling but worst than Non-Preemptive Shortest Job First (SJF) scheduling because the average waiting and turn around time are faster than First Come First Serve (FCFS) but slower than Shortest Job First (SJF).
