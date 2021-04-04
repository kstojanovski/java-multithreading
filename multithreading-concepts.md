# Multithreading concepts

To the multithreading concepts follwoing classes belong:
* Semaphore
* CountDownLatch
* CyclicBarrier
* Phaser
* Exchanger

## Semaphore
* java.util.concurrent.Semaphore
* Reference and Example: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/Semaphore.html
* A counting semaphore. Conceptually, a semaphore maintains a set of permits.
* Semaphores are often used to restrict the number of threads than can access some (physical or logical) resource.
* A semaphore initialized to one, and which is used such that it only has at most one permit available, can serve as a mutual exclusion lock and its named binary semaphore.

## CountDownLatch
* java.util.concurrent.CountDownLatch
* Reference and Example: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CountDownLatch.html
* A synchronization aid that allows one or more threads to wait until a set of operations being performed in other threads completes.

## CyclicBarrier
* java.util.concurrent.CyclicBarrier
* Refernce and Example: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CyclicBarrier.html
* A synchronization aid that allows a set of threads to all wait for each other to reach a common barrier point.
* CyclicBarriers are useful in programs involving a fixed sized party of threads that must occasionally wait for each other. 
* The barrier is called cyclic because it can be re-used after the waiting threads are released.

## Phaser
* java.util.concurrent.Phaser
* Reference and Example: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/Phaser.html
* A reusable synchronization barrier, similar in functionality to CyclicBarrier and CountDownLatch but supporting more flexible usage.
* This approach is prefered than the CyclicBarrier or CountDownLatch.

## Exchanger
* java.util.concurrent.Exchanger<V>
* Reference and Example: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/Exchanger.html
* A synchronization point at which threads can pair and swap elements within pairs.
* Exchangers may be useful in applications such as genetic algorithms and pipeline designs.
