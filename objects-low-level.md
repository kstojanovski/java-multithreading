# Objects of low level mulithreading programing in Java
## Introduction
In this section all objects are involed which are an part of the low level mulithreading programing in Java.
## Object
### Introduction
The object class which is the parent of any othe class in java
### Structure
In multithreading context the following methods are used:
* wait()
  * Causes the current thread to wait until another thread invokes the notify() method or the notifyAll() method for this object.
* wait(long timeout)
  * Causes the current thread to wait until either another thread invokes the notify() method or the notifyAll() method for this object, or a specified amount of time has elapsed.
* wait(long timeout, int nanos)
  * Causes the current thread to wait until another thread invokes the notify() method or the notifyAll() method for this object, or some other thread interrupts the current thread, or a certain amount of real time has elapsed.
* notify()
  * Wakes up a single thread that is waiting on this object's monitor.
* notifyAll()
  * Wakes up all threads that are waiting on this object's monitor.
### Sources
* https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html
## Runnable
### Introduction
* Type: Interface
### Structure
* run
### Note
Derivate class on this interface include:
* Thread
* TimerTask
* etc.
### Sources
* https://docs.oracle.com/javase/8/docs/api/java/lang/Runnable.html
## Thread
### Introduction
* Type: Class start
### Structure
* void start()
  * Causes this thread to begin execution; the Java Virtual Machine calls the run method of this thread.
* void run()
  * Starts the run method where the main logic is placed. Should be invoked directly but only via tha start method if used as multithreading method.
* static void yield()
  * A hint to the scheduler that the current thread is willing to yield its current use of a processor.
    * Thread which is using this method gives advantage in the processing to the other threads but doesnt stops!
* void join()
  * Waits for this thread to die.
* void	join(long millis)
  * Waits at most millis milliseconds for this thread to die.
* void	join(long millis, int nanos)
  * Waits at most millis milliseconds plus nanos nanoseconds for this thread to die.
* static void sleep(long millis)
  * Causes the currently executing thread to sleep (temporarily cease execution) for the specified number of milliseconds, subject to the precision and accuracy of system timers and schedulers.
* static void sleep(long millis, int nanos)
  * Causes the currently executing thread to sleep (temporarily cease execution) for the specified number of milliseconds plus the specified number of nanoseconds, subject to the precision and accuracy of system timers and schedulers.
* void interrupt()
  * Interrupts this thread.
* static boolean interrupted()
  * Tests whether the current thread has been interrupted.
### Sources
* https://docs.oracle.com/javase/8/docs/api/java/lang/Thread.html
