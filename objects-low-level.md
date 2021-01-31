# Objects of low level mulithreading programing in Java
## Introduction
In this section all objects are involed which are an part of the low level mulithreading programing in Java.
## java.lang.Object
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
## java.lang.Runnable
### Introduction
* Type: Interface
* The Runnable interface should be implemented by any class whose instances are intended to be executed by a thread. 
* The class must define a method of no arguments called run.
* This interface is designed to provide a common protocol for objects that wish to execute code while they are active. For example, Runnable is implemented by class Thread. Being active simply means that a thread has been started and has not yet been stopped.
* In addition, Runnable provides the means for a class to be active while not subclassing Thread. A class that implements Runnable can run without subclassing Thread by instantiating a Thread instance and passing itself in as the target. In most cases, the Runnable interface should be used if you are only planning to override the run() method and no other Thread methods. This is important because classes should not be subclassed unless the programmer intends on modifying or enhancing the fundamental behavior of the class.
### Structure
* void run()
  * When an object implementing interface Runnable is used to create a thread, starting the thread causes the object's run method to be called in that separately executing thread.
### Note
Derivate class on this interface:
* AsyncBoxView.ChildState, ForkJoinWorkerThread, FutureTask, RenderableImageProducer, SwingWorker, Thread, TimerTask.
### Sources
* https://docs.oracle.com/javase/8/docs/api/java/lang/Runnable.html
## java.lang.Thread
### Introduction
* Type: Class
* A thread is a thread of execution in a program. The Java Virtual Machine allows an application to have multiple threads of execution running concurrently.
* Every thread has a priority. Threads with higher priority are executed in preference to threads with lower priority. Each thread may or may not also be marked as a daemon. When code running in some thread creates a new Thread object, the new thread has its priority initially set equal to the priority of the creating thread, and is a daemon thread if and only if the creating thread is a daemon.
* When a Java Virtual Machine starts up, there is usually a single non-daemon thread (which typically calls the method named main of some designated class). The Java Virtual Machine continues to execute threads until either of the following occurs:
  * The exit method of class Runtime has been called and the security manager has permitted the exit operation to take place.
  * All threads that are not daemon threads have died, either by returning from the call to the run method or by throwing an exception that propagates beyond the run method.
### Structure
* void start()
  * Causes this thread to begin execution; the Java Virtual Machine calls the run method of this thread.
* void run()
  * Starts the run method where the main logic is placed. Should be invoked directly but only via tha start method if used as multithreading method.
* static void yield()
  * A hint to the scheduler that the current thread is willing to yield its current use of a processor.
    * Thread which is using this method gives advantage in the processing to the other threads but it doesnt stops!
    * https://www.tutorialspoint.com/java/lang/thread_yield.htm
* void join()
  * Waits for this thread to die.
    * The current thread where `t.join` (`t` for some thread object reference) is invoked waits for the thread (for the process which was started in the run method) `t` to finish.
    * https://www.tutorialspoint.com/java/lang/thread_join.htm
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
    * From the java docs - the interrupted status of the thread is cleared by this method! This leads to confusion, therefore I would suggest the other method to be used for checking purposes.
    * https://www.tutorialspoint.com/javaexamples/thread_interrupt.htm
* boolean	isInterrupted()
  * Tests whether this thread has been interrupted.
* void	setPriority(int newPriority)  
  * Changes the priority of this thread.
    * The priorities are platform dependent, means they behave differenty on diffrent platforms.
    * https://www.tutorialspoint.com/java-thread-priority-in-multithreading
* void	setName(String name)
  * Changes the name of this thread to be equal to the argument name.
* void	setDaemon(boolean on)
  * Marks this thread as either a daemon thread or a user thread.
* Thread.State	getState()
  * Returns the state of this thread.
* static void	setDefaultUncaughtExceptionHandler(Thread.UncaughtExceptionHandler eh)
  * Set the default handler invoked when a thread abruptly terminates due to an uncaught exception, and no other handler has been defined for that thread.
* void	setContextClassLoader(ClassLoader cl)
  * Sets the context ClassLoader for this Thread.
### Sources
* https://docs.oracle.com/javase/8/docs/api/java/lang/Thread.html
## java.lang.ThreadLocal
### Introduction
* Type: Class
* This class provides thread-local variables.
* These variables differ from their normal counterparts in that each thread that accesses one (via its get or set method) has its own, independently initialized copy of the variable.
* ThreadLocal instances are typically private static fields in classes that wish to associate state with a thread.
* Each thread holds an implicit reference to its copy of a thread-local variable as long as the thread is alive and the ThreadLocal instance is accessible; after a thread goes away, all of its copies of thread-local instances are subject to garbage collection (unless other references to these copies exist).
   * Each thread has is accessing own copy of the variable, means each thread has own variable even if the syntax does not show that explicitly.
* **Note**: Shouldn't be abused as storage and should be used as less as possible because of memory reasons. Creating an high amount of threads multiplies the memory allocation. 
### Structure
* T	get()
  * Returns the value in the current thread's copy of this thread-local variable.
* protected T	initialValue()
  * Returns the current thread's "initial value" for this thread-local variable.
* void	remove()
  * Removes the current thread's value for this thread-local variable.
* void	set(T value)
  * Sets the current thread's copy of this thread-local variable to the specified value.
* static \<S\> ThreadLocal\<S\>	withInitial(Supplier<? extends S> supplier)
  * Creates a thread local variable.
### Sources
* https://docs.oracle.com/javase/8/docs/api/java/lang/ThreadLocal.html
