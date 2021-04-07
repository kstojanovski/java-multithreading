# Patterns

Diverse patterns with concurrency exists like:
* Producer-Consumer
* Distributed Locking
* Object pool

## Producer-Consumer

This is one of the main pattern which is used for explaining the thread approach. It can be implemneted in different ways like:

### Object-Class

Low-Level API implementation. This pattern is implemented without any concurrency collections or special objects. Only the methods of the Object-class are used like wait, notify and notifyAll.

* Examples:
  * https://docs.oracle.com/javase/tutorial/essential/concurrency/guardmeth.html
  * https://www.geeksforgeeks.org/producer-consumer-solution-using-threads-java
  * https://www.tutorialspoint.com/javaexamples/thread_procon.htm
  * https://www.tutorialride.com/java-multithreading-programs/producer-consumer-problem-java-program.htm
  * https://www.java-success.com/producer-and-consumer-java-multi-threading-code

### BlockingQueue-Class

High-Level API implementation. This pattern is implemented with BlockingQueue which are thead safe and are part of the java.util.concurrent package.

* Examples: 
  * https://stackoverflow.com/questions/2332537/producer-consumer-threads-using-a-queue
  * https://howtodoinjava.com/java/multi-threading/producer-consumer-problem-using-blockingqueue
  * https://www.geeksforgeeks.org/producer-consumer-solution-using-blockingqueue-in-java-thread
  * https://www.codejava.net/java-core/collections/java-producer-consumer-examples-using-blockingqueue
  * https://codepumpkin.com/producer-consumer-using-blockingqueue

## Distributed Locking

This kind of pattern is needed when you have different groups of threads which are bound to one lock. One use case is when many requests are inbound through in a HTTPServlet but the requests contain parameters which can be seen as unique id and only one of them should run a particular piece of code while the other requests with the same id should wait.

This approach is a candidate for an extra implementation as part of the of the concurrency package.

One possible solution using the low level api with wait and notify can be found in the next example:
* https://stackoverflow.com/questions/21286831/managing-multiple-locks


## Object pool

Object pool is not a classic multithreading pattern. It is listed here because for implementing it, concurrency proramming needs to be used. This approach was listed in the project about software design patterns:
* https://github.com/kstojanovski/software-design-patterns/blob/main/creational-patterns.md#object-pool
