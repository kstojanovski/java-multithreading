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

## ScheduledThreadPoolExecutor
* java.util.concurrent.ScheduledThreadPoolExecutor
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ScheduledThreadPoolExecutor.html
* A ThreadPoolExecutor that can additionally schedule commands to run after a given delay, or to execute periodically. 
* This class is preferable to Timer when multiple worker threads are needed, or when the additional flexibility or capabilities of ThreadPoolExecutor (which this class extends) are required.

## ThreadPoolExecutor
* java.util.concurrent.ThreadPoolExecutor
* Reference and Example: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ThreadPoolExecutor.html

## Executors
* java.util.concurrent.Executors
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/Executors.html
* Factory for creation of any kind of executors.
