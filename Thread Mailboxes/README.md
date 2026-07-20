<h1>Thread Mailboxes with POSIX Threads</h1>

<b>Description</b>

This project implements a multithreaded message-passing system in C++ using POSIX threads (pthreads) and semaphores. Each worker thread owns a private mailbox that receives messages from the main thread. Workers process incoming integer values by accumulating their sum and, upon termination, return statistics back to the main thread.

The program supports both <b>blocking</b> and <b>non-blocking</b> mailbox communication, demonstrating synchronization, concurrency, and inter-thread communication using semaphores. :contentReference[oaicite:0]{index=0} :contentReference[oaicite:1]{index=1}

<b>Features</b>

<ul>
    <li>Implements mailbox-based communication between threads.</li>
    <li>Uses POSIX threads (pthreads) for concurrent execution.</li>
    <li>Synchronizes access with POSIX semaphores.</li>
    <li>Supports both blocking and non-blocking message sending.</li>
    <li>Queues undelivered messages in non-blocking mode until mailboxes become available.</li>
    <li>Each worker thread tracks the sum, number of operations, and total processing time.</li>
    <li>Gracefully terminates all worker threads using termination messages.</li>
</ul>

<h2>Example Run</h2>

<b>Input</b>

<pre>
10 1
5 2
7 1
12 3
3 2
</pre>

<b>Output</b>

<pre>
The result from thread 1 is 17 from 2 operations during 2 seconds.
The result from thread 2 is 8 from 2 operations during 2 seconds.
The result from thread 3 is 12 from 1 operations during 1 seconds.
</pre>

<h2>Compilation</h2>

Compile using the provided Makefile.

<pre>
make
</pre>

Or compile manually:

<pre>
g++ main.cpp mailbox.cpp adder.cpp -pthread -o mailbox
</pre>

<h2>Usage</h2>

<b>Blocking Mode</b>

<pre>
./mailbox 3
</pre>

<b>Non-Blocking Mode</b>

<pre>
./mailbox 3 nb
</pre>

The program reads pairs of integers from standard input:

<pre>
&lt;value&gt; &lt;thread_number&gt;
</pre>

Each value is sent to the specified worker thread's mailbox. Enter EOF (Ctrl+D on Linux/macOS or Ctrl+Z on Windows) to finish processing.

<h2>Output</h2>

For every worker thread, the program reports:

<ul>
    <li>Total sum of all received values.</li>
    <li>Number of values processed.</li>
    <li>Total processing time.</li>
    <li>Results collected through mailbox-based message passing.</li>
</ul>

The project demonstrates core operating system concepts including thread synchronization, semaphore-based communication, producer-consumer coordination, and concurrent programming with POSIX threads.
