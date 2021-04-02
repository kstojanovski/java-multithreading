# Futures

The following interface is the base of the features:
* Future

To the futures the following classes belong separated in two groups:
* Classes of Future Task
  * FutureTask
  * SwingWorker
  * CompletableFuture
* Classes of Fork-Join Task
  * ForkJoinTask
  * RecursiveAction
  * RecursiveTask
  * CountedCompleter

## Interface 

### Future
* java.util.concurrent.Future<V>
* Reference and Example: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/Future.html
* A Future represents the result of an asynchronous computation.

## Classes of Future Task

### FutureTask
* java.util.concurrent.FutureTask
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/FutureTask.html
* A cancellable asynchronous computation. This class provides a base implementation of Future, with methods to start and cancel a computation, query to see if the computation is complete, and retrieve the result of the computation.
* The FutureTask class is an implementation of Future that implements Runnable, and so may be executed by an Executor.

### SwingWorker
* javax.swing.SwingWorker
* Reference and Exampels: https://docs.oracle.com/javase/8/docs/api/javax/swing/SwingWorker.html
* An abstract class to perform lengthy GUI-interaction tasks in a background thread. 
* Several background threads can be used to execute such tasks. However, the exact strategy of choosing a thread for any particular SwingWorker is unspecified and should not be relied on.

### CompletableFuture
* java.util.concurrent.CompletableFuture
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CompletableFuture.html
* java.util.concurrent.CompletionStage
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CompletionStage.html
* A Future that may be explicitly completed (setting its value and status), and may be used as a CompletionStage, supporting dependent functions and actions that trigger upon its completion.
* The CompletionStage makes the future chainable to other tasks in a lamda notation way. Thouse methods are part of the CompletionStage interface.

## Classes of Fork-Join Task

### ForkJoinTask
* java.util.concurrent.ForkJoinTask
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ForkJoinTask.html
* Used when the task can be solved recursively. For any new recursion a fork is started. After the processing the  threads are joined.

### RecursiveAction
* java.util.concurrent.RecursiveAction
* Reference and Examples: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/RecursiveAction.html
* A recursive resultless ForkJoinTask. This class establishes conventions to parameterize resultless actions as Void ForkJoinTasks. Because null is the only valid value of type Void, methods such as join always return null upon completion.

### RecursiveTask
* java.util.concurrent.RecursiveTask
* Reference and Example: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/RecursiveTask.html
* A recursive result-bearing ForkJoinTask.

### CountedCompleter
* java.util.concurrent.CountedCompleter
* Reference and Examples: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CountedCompleter.html
* A ForkJoinTask with a completion action performed when triggered and there are no remaining pending actions. 
* CountedCompleters are in general more robust in the presence of subtask stalls and blockage than are other forms of ForkJoinTasks, but are less intuitive to program.
