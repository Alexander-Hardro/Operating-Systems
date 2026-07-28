<h1>Operating Systems</h1>

Contains Operating System related projects involving Processes, Threads, Synchronization, CPU scheduling, Memory Management, Input/Output operations, Interrupts, and File Systems
<h1>Projects</h1>

<b>Thread Mailboxes</b>

This project implements a multithreaded message-passing system in C++ using POSIX threads (pthreads) and semaphores. Each worker thread owns a private mailbox that receives messages from the main thread. Workers process incoming integer values by accumulating their sum and, upon termination, return statistics back to the main thread.

The program supports both <b>blocking</b> and <b>non-blocking</b> mailbox communication, demonstrating synchronization, concurrency, and inter-thread communication using semaphores.
