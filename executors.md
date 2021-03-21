# Executors

Follwing classes belog to this type:
* ExecutorCompletionService
* AbstractExecutorService
* ForkJoinPool
* ScheduledThreadPoolExecutor
* ThreadPoolExecutor
  * ThreadPoolExecutor.AbortPolicy
  * ThreadPoolExecutor.CallerRunsPolicy
  * ThreadPoolExecutor.DiscardOldestPolicy
  * ThreadPoolExecutor.DiscardPolicy
* Executors

## ExecutorCompletionService
* java.util.concurrent.ExecutorCompletionService
* Reference and Examples: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ExecutorCompletionService.html
* A CompletionService that uses a supplied Executor to execute tasks.

## AbstractExecutorService
* java.util.concurrent.AbstractExecutorService
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/AbstractExecutorService.html
* Provides default implementations of ExecutorService execution methods.

## ForkJoinPool
* java.util.concurrent.ForkJoinPool
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ForkJoinPool.html
* An ExecutorService for running ForkJoinTasks. 
* A ForkJoinPool provides the entry point for submissions from non-ForkJoinTask clients, as well as management and monitoring operations.
* Examples:
  * https://www.javatpoint.com/java-forkjoinpool
  * https://java-8-tips.readthedocs.io/en/stable/forkjoin.html
  * https://howtodoinjava.com/java7/forkjoin-framework-tutorial-forkjoinpool-example/
  * https://www.baeldung.com/java-fork-join
* Discussion:
  * decorateTask
  * https://stackoverflow.com/questions/1401520/scheduledthreadpoolexecutor-schedulewithfixeddelay-and-urgent-execution

## ScheduledThreadPoolExecutor
* java.util.concurrent.ScheduledThreadPoolExecutor
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ScheduledThreadPoolExecutor.html
* A ThreadPoolExecutor that can additionally schedule commands to run after a given delay, or to execute periodically. 
* This class is preferable to Timer when multiple worker threads are needed, or when the additional flexibility or capabilities of ThreadPoolExecutor (which this class extends) are required.
* Examples:
  * https://www.tutorialspoint.com/java_concurrency/concurrency_scheduledthreadpoolexecutor.htm
  * https://howtodoinjava.com/java/multi-threading/task-scheduling-with-executors-scheduledthreadpoolexecutor-example/
  * https://www.geeksforgeeks.org/scheduledthreadpoolexecutor-class-in-java/

## ThreadPoolExecutor
* java.util.concurrent.ThreadPoolExecutor
* Reference and Example: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ThreadPoolExecutor.html
* An ExecutorService that executes each submitted task using one of possibly several pooled threads, normally configured using Executors factory methods.
* Examples:
  * https://www.journaldev.com/1069/threadpoolexecutor-java-thread-pool-example-executorservice
  * https://howtodoinjava.com/java/multi-threading/java-thread-pool-executor-example/
  * https://tutorialedge.net/python/concurrency/python-threadpoolexecutor-tutorial/

## Executors
* java.util.concurrent.Executors
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/Executors.html
* Factory for creation of any kind of executors.
