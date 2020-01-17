# Reasons for concurrency and parallelism


To complete this exercise you will have to use git. Create one or several commits that adds answers to the following questions and push it to a repository to complete the task. Remember to also submit your answers to Blackboard

When answering the questions, remember to use all the resources at your disposal. Asking the internet isn't a form of "cheating", it's a way of learning.

 ### What is concurrency? What is parallelism? What's the difference?
 > *Concurrency is the ability of an algorithm or computer program to execute  multiple computations, independent of order, at the same time. Computations are executed concurrently, not sequentially.  Large computations may be divided into smaller tasks which are solved simultaneously, called parallalism. In parallel computing, the problem is typically divided into similar smaller tasks, while in concurrent computing the individual tasks don't necessarily relate to each other and some "inter-process communication" may be required.*
 
 ### Why have machines become increasingly multicore in the past decade?
 > *Computer performance have formaly been improved by frequency scaling of processors. However, when reaching a certain Hertz of processing frequency, physical constraints limits the potential for efficient further improvement. This makes multiple cores attractive, resulting in a need of parallelism.*
 
 ### What kinds of problems motivates the need for concurrent execution?
 (Or phrased differently: What problems do concurrency help in solving?)
 > *Problems were one computation can be executed without having to wait for other computations to finish. E.g. simulation of physical problems using Monte Carlo methods. Concurrency allows several Monte Carlo histories to be computed independently in different "threads". The OS on your computer also uses concurrency to execute idependent processes that uses the CPU as a computing resource, e.g. me typing specific letters while spotify playing music. The specific text editor I am using at the moment is using 11 threads.*
 
 ### Does creating concurrent programs make the programmer's life easier? Harder? Maybe both?
 (Come back to this after you have worked on part 4 of this exercise)
 > *Concurrent programs are more complex, but opens up a new world of possibilities.*
 
 ### What are the differences between processes, threads, green threads, and coroutines?
 > *Citing Greg Hewgill from stack overflow: "Both processes and threads are independent sequences of execution. The typical difference is that threads (of the same process) run in a shared memory space, while processes run in separate memory spaces". Coroutines are threads that are cooperatively multitasked, rather than preemtively multitasked. Green threads are threads that are not managed by the OS.*
 
 ### Which one of these do `pthread_create()` (C/POSIX), `threading.Thread()` (Python), `go` (Go) create?
 >  * `pthread_create()` creates a new thread.  `threading.Thread()` creates a threading object. Each of these objects represents an activity, started by an member function. The activity is run in a separate thread of control. `go` creates a "goroutine", a lightweight thread. Goroutines are managed by Go Runtime, so they are essentially green threads.* 
 
 ### How does pythons Global Interpreter Lock (GIL) influence the way a python Thread behaves?
 > *GIL allows only one thread to execute Python code at once.*
 
 ### With this in mind: What is the workaround for the GIL (Hint: it's another module)?
 > *To work around GIL you'll have to use multiprocessing or the `concurrent.futures.ProcessPoolExecutor` module.*
 
 ### What does `func GOMAXPROCS(n int) int` change? 
 > *In Golang, this function sets the maximum number of CPUs that Golang may execute simultaneously. It also returns n.*
