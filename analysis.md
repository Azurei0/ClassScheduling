# Introduction

For the solution of the Class Scheduling, we have decided to use 
non-preemptive **Shortest Job First** (**SJF**) algorithm
AND
non-preemptive **Priority Scheduling** algorithm
to schedule the classes.

# Consideration

We consider that the class:
1.  Cannot be interfered or stopped halfway

_Thus, the reason for why non-preemptive methods of the algorithms are chosen_

# Analysis

## First Come First Serve (FCFS)

 > In FCFS algorithm, the classes are sorted depending on their respective: </br>
 1. preferred ***Arrival time*** </br>
 **IF** two or more classes have the same arrival time </br>
 2. whichever classes that is earlier in the queue will execute first

Output:

Order in which process gets executed </br>
2201    3401    1103

Processes   Burst time   Waiting time   Turn around time </br>
   1            3           0             3 </br>
   2            2           3             5 </br>
   3            1           5             6 </br>
   
Average waiting time = 2.66667 </br>
Average turn around time = 4.66667

## Non-Preemptive Shortest Job First (SJF)

> In non-preemptive SJF algortihm, classes are sorted depending on their:
1. shortest burst time *OR* duration </br>
**IF** two or more classes have the same arrival time </br>
2. classes is sorted based on its preferred **Arrival Time**

// in non-preemptive SJF algorithm, all arrival time is considered as 0

Output:

Order in which process gets executed </br>
1103 3401 2201

Processes  Burst time  Waiting time  Turn around time </br>
 1103           1        0               1 </br>
 3401           2        1               3 </br>
 2201           3        3               6 </br>

Average waiting time = 1.33333 </br>
Average turn around time = 3.33333

## Non-Preemptive Priority Scheduling

> In non-preemptive Priority Scheduling, classes are sorted depending on:
1. The class **Priority level** </br>
**IF** two or more classes have the same priority </br>
2. classes is sorted depending on its **Arrival Time**

//because it is non-preemptive most of the time arrival time is considered 0

Output:

Order in which processes gets executed </br>
3401 2201 1103

Processes   Burst time   Waiting time   Turn around time </br>
   3401         2           0             2 </br>
   2201         3           2             5 </br>
   1103         1           5             6 </br>

Average waiting time = 2.33333 </br>
Average turn around time = 4.33333
