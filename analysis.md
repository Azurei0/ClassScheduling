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

## Non-Preemptive Shortest Job First (SJF)

> In non-preemptive SJF algortihm, classes are sorted depending on their:
1. shortest burst time *OR* duration </br>
**IF** two or more classes have the same arrival time </br>
2. classes is sorted based on its preferred **Arrival Time**

// in non-preemptive SJF algorithm, all arrival time is considered as 0

## Non-Preemptive Priority Scheduling

> In non-preemptive Priority Scheduling, classes are sorted depending on:
1. The class **Priority level** </br>
**IF** two or more classes have the same priority </br>
2. classes is sorted depending on its **Arrival Time**

//because it is non-preemptive most of the time arrival time is considered 0
