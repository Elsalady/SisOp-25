# CPU Scheduling

Nama: Elsa Lady Dia Fatma

NRP: 3124521025

Kelas: 1 TI A 

## Chapter 5 Exercises
5. 17. Consider the following set of processes, with the length of the CPU burst given in milliseconds:
    
    | Process    | Burst Time | Priority |
    |------------|------------|----------|
    |    P1      |     5      |     4    |
    |    P2      |     3      |     1    |
    |    P3      |     1      |     2    |
    |    P4      |     7      |     2    |
    |    P5      |     4      |     3    |

    The processes are assumed to have arrived in the order P_{v} P_{2}*r P3, P_{4r} all at time 0.

    a. Draw four Gantt charts that illustrate the execution of these pro-cesses using the following scheduling algorithms: FCFS, SJF, non-preemptive priority (a larger priority number implies a higher priority), and RR (quantum = 2).

    b. What is the turnaround time of each process for each of the scheduling algorithms in part a?

    c. What is the waiting time of each process for each of these schedul ing algorithms?

    d. Which of the algorithms results in the minimum average waiting time (over all processes)?

Answer:

a. four Gantt charts illustrating process execution using the FCFS, SJF (non-preemptive), Priority (non-preemptive), and RR (quantum = 2) algorithms:
 
   1. first-come, first-served (FCFS)
      |----P1----|---P2---|--P3--|------P4------|----P5----|
      0         5        8      9            16        20

   2. Shortest-job-first(SJF) (non-preemptive)
      |--P3--|---P2---|----P5----|----P1----|-------P4-------|
      0     1        4         8        13              20

   3. Priority (non-preemptive)
      |---P2---|--P3--|-------P4-------|----P5----|----P1----|
      0      3      4              11        15        20

   4. Round robin (RR) (Quantum =2)
      |--P1--|--P2--|--P3--|--P4--|--P5--|--P1--|--P4--|--P5--|--P1--|--P4--|--P4--|
      0     2     4     5     7     9    11    13    15    17    19         19    20

b. Turnaround Time

    | Process    | FCFS (ms) | SJF (ms) | Priority (ms) | Round Robin (ms)  |
    |------------|-----------|----------|---------------|-------------------|
    |    P1      |     5     |     13   |       20      |        19         |
    |    P2      |     8     |     4    |        3      |         4         |
    |    P3      |     9     |     1    |        4      |         5         |
    |    P4      |     16    |     20   |       11      |        20         |
    |    P5      |     20    |     8    |       15      |        13         |

c. Waiting Time

    | Process    | FCFS (ms) | SJF (ms) | Priority (ms) | Round Robin (ms)  |
    |------------|-----------|----------|---------------|-------------------|
    |    P1      |     0     |     8    |       15      |        14         |
    |    P2      |     5     |     1    |        0      |         1         |
    |    P3      |     8     |     0    |        3      |         4         |
    |    P4      |     9     |     13   |        4      |        13         |
    |    P5      |     16    |     4    |       11      |         9         |
    |    Average |     7.6   |     5.2  |       6.6     |        8.2        |

d. Algorithm with minimum average waiting time:

Based on the calculated average waiting times, the Shortest-Job-First (SJF) algorithm yields the minimum average waiting time of 5.2 ms. This is attributed to SJF's strategy of prioritizing the execution of processes with the shortest burst times, thereby reducing the overall waiting time for other processes in the system.

However, it is important to note that the practical implementation of SJF can be challenging due to the requirement of knowing the burst time of processes in advance. Furthermore, non-preemptive SJF can potentially lead to starvation for processes with longer burst times if there is a continuous influx of shorter processes. 

5. 18. The following processes are being scheduled using a preemptive, priority-based, round-robin scheduling algorithm..

    | Process    | Priority   | Burst    | Arrival  |
    |------------|------------|----------|----------|
    |    P1      |     8      |     15   |     0    |
    |    P2      |     3      |     20   |     0    |
    |    P3      |     4      |     20   |     20   |
    |    P4      |     4      |     20   |     25   |
    |    P5      |     5      |     5    |     45   |
    |    P6      |     5      |     15   |     55   |

    Each process is assigned a numerical priority, with a higher number indi-cating a higher relative priority. The scheduler will execute the highest-priority process. For processes with the same priority, a round-robin scheduler will be used with a time quantum of 10 units. If a process is preempted by a higher-priority process, the preempted process is placed at the end of the queue.

    a. Show the scheduling order of the processes using a Gantt chart.

    b. What is the turnaround time for each process?

    c. What is the waiting time for each process?

Answer:

a. Ah, Anda benar sekali! Mohon maaf atas kesalahan dalam membaca soal sebelumnya. Mari kita kerjakan soal 5.18 dengan data proses yang lengkap hingga P6.

Problem 5.18: Preemptive Priority-Based Round-Robin Scheduling

The following processes are being scheduled using a preemptive, priority-based, round-robin scheduling algorithm.

Process	Priority	Burst	Arrival
P_1	8	15	0
P_2	3	20	0
P_3	4	20	20
P_4	4	20	25
P_5	5	5	45
P_6	5	15	55

Ekspor ke Spreadsheet
Each process is assigned a numerical priority, with a higher number indicating a higher relative priority. The scheduler will execute the highest-priority process. For processes with the same priority, a round-robin scheduler will be used with a time quantum of 10 units. If a process is preempted by a higher-priority process, the preempted process is placed at the end of the queue.

Questions:

a. Show the scheduling order of the processes using a Gantt chart.

b. What is the turnaround time for each process?

c. What is the waiting time for each process?

Answers:

a. Below is a Gantt chart illustrating process execution using the Preemptive Priority-Based Round-Robin algorithm:

   |----P2----|----P2----|----P3----|----P4----|----P3----|----P4----|--P5--|----P6----|----P1----|----P1----|--P6--|
   0         10        20        30        40        50        60        70    75        85        95       105   110

b. Turnaround Time:

- P1: Finish Time - Arrival Time = 105 - 0 = 105

- P2: Finish Time - Arrival Time = 30 - 0 = 30

- P3: Finish Time - Arrival Time = 60 - 20 = 40

- P4: Finish Time - Arrival Time = 70 - 25 = 45

- P5: Finish Time - Arrival Time = 75 - 45 = 30

- P6: Finish Time - Arrival Time = 110 - 55 = 55

c. Waiting Time:

Waiting Time = Turnaround Time - Burst Time

- P1: 105 - 15 = 90

- P2: 30 - 20 = 10

- P3: 40 - 20 = 20

- P4: 45 - 20 = 25

- P5: 30 - 5 = 25

- P6: 55 - 15 = 40