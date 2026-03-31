# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

[A thread is a smaller unit of execution within the same process that shares its resources, whereas a process is an independent program with its own memory space. Because they don't need separate memory allocation, threads are lighter and may be created more quickly than processes.

Because the simulation must do several activities at once without incurring significant costs, we chose threads rather than processes in this project. The output shows that some processes, such as P1, P2, and P3, are scheduled frequently and rapidly, which would be inefficient if we used actual processes.]

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

[A process in Round-Robin scheduling is pushed back to the end of the ready queue if it does not complete within its time quantum. This guarantees equity since every process has an opportunity to run.]

Example from my output:
```
P1 executing quantum [4000ms]
P1 completed quantum 4000ms
Remaining time: 4642ms
P1 yields CPU for context switch

P1 added to ready queue

Explanation of example:
In this case, P1 did not complete execution because it had 4642 milliseconds left. It was therefore put back in the ready queue rather than continuing. Round-Robin ensures that all processes are fair by giving it another turn once other processes have finished.
```

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:
We can track the lifecycle of P1 using the simulation output:

New:

P1 is in the New state when it is first created before entering the system. This is shown when:
P1 added to ready queue
Runnable:

After being added to the ready queue, P1 becomes Runnable and waits for CPU scheduling. For example:
Ready Queue: [P2 … P16 ? P1]
Running:

P1 enters the Running state when it starts executing on the CPU:
P1 executing quantum [4000ms]

Waiting:
P1 effectively enters a waiting-like state after yielding the CPU and waiting for its next turn:
P1 yields CPU for context switch
P1 added to ready queue

Here it is not running but waiting in the queue.

Terminated:
Finally, P1 finishes execution when its remaining time becomes 0:
P1 completed quantum 642ms
Remaining time: 0ms
P1 finished execution

This shows the full lifecycle of P1 from creation until completion.**




---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Web Servers]

**Description**:
Web servers manage several client requests concurrently, such as loading webpages for various users.

**Why Round-Robin works well here**: 
[Every request is guaranteed CPU time without starvation thanks to Round-Robin. Because no single request may prevent others from being blocked for an extended period of time, it increases responsiveness.]

### Example 2: [Operating System Task Scheduling]

**Description**: 
[Several programs can run concurrently on modern operating systems.]

**Why Round-Robin works well here**: 
[By allocating equal CPU time to each process, it promotes fairness. This maintains the system responsive for users and stops any application from controlling the CPU.]

---

## Summary

Key concepts I understood through these questions:

1- The distinction between a thread and a process and how it affects efficiency
2- The Round-Robin algorithm's time distribution mechanism
3- The duration of a thread's life cycle

**Concepts I need to study more:**
1. advanced thread synchronization
2. deadlocks and how to avoid them
