<h1>Operating Systems</h1>

Contains Operating System related projects involving Processes, Threads, Synchronization, CPU scheduling, Memory Management, Input/Output operations, Interrupts, and File Systems
<h1>Projects</h1>

<b>Thread Mailboxes</b>



<pre>
<b>Input</b>
  
10 1
5 2
7 1
12 3
3 2

<b>Output</b>

The result from thread 1 is 17 from 2 operations during 2 seconds.
The result from thread 2 is 8 from 2 operations during 2 seconds.
The result from thread 3 is 12 from 1 operations during 1 seconds.
</pre>

This project implements a multithreaded message-passing system in C++ using POSIX threads (pthreads) and semaphores. Each worker thread owns a private mailbox that receives messages from the main thread. Workers process incoming integer values by accumulating their sum and, upon termination, return statistics back to the main thread.

The program supports both <b>blocking</b> and <b>non-blocking</b> mailbox communication, demonstrating synchronization, concurrency, and inter-thread communication using semaphores.
