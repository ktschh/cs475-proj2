# cs475-proj2

Xinu Project 2
https://ktschh.github.io/teaching/cs475/proj2/

Kate Schuh and Seung Park

The priority of the processes in the lower half of the ready queue (closer to the tail) increases by two every time resched() is called, 
until it reaches the upper half of the ready queue where the priority of the processes only increase by one every time resched() is called 
(except for the nullproc process & the old process that is being put back into the queue). This prevents starvation of processes with very 
low priority to advance in the queue at a quicker rate. After it gets scheduled, a process' priority reverts back to its original priority.

In the test cases, you can see that the threads that starve with no aging (especially PRINTER-E and the BIGARGS programs with low priority) 
no longer starve under our aging policy. Despite the fact that PRINTER-E appears many times at the bottom of the list under the aging policy,
it still get many opportunities to run thorughout the whole program's running -- and it makes sense that they should not be so prioritized 
that they supercede the high-priority threads. The low priority programs still get to run, even if they do not finish before the high-priority
ones.


