# Locks

All classes from the package java.util.concurrent.Locks are part of this description here. There are three interfaces which are used by the classes:
* Condition
* Lock
* ReadWriteLock

The are classes separated into several groups:
* LockSupport
* ReentrantLock
* ReentrantReadWriteLock
* StampedLock
* Synchronizer

Interfaces and classes providing a framework for locking and waiting for conditions that is distinct from built-in synchronization and monitors. The framework permits much greater flexibility in the use of locks and conditions, at the expense of more awkward syntax.

Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/locks/package-summary.html

## Interfaces

### Condition
* java.util.concurrent.locks.Condition
* Reference and Example: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/locks/Condition.html
* This interface is used in the Lock Interface.

### Lock
* java.util.concurrent.locks.Lock
  * has a java.util.concurrent.locks.Condition
* Reference and Example: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/locks/Lock.html
* This interface is used in the classes ReentrantLock and StampedLock.

### ReadWriteLock
* java.util.concurrent.locks.ReadWriteLock
  * has a java.util.concurrent.locks.Lock
* Reference and Example: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/locks/ReadWriteLock.html
* This interface is used in the classes ReentrantReadWriteLock and StampedLock.

## Class Group

### LockSupport
* java.util.concurrent.locks.LockSupport
* Reference and Example: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/locks/LockSupport.html
* On given thread "permits" are used which are set and get with park() and unpark() and managed in the sense of the Semaphore class.
* This approach should not be used on threads with code where locking and blocking are used.
* Since the permit approach works on related threads, it is not flexible as the approach with blocking and locking where relation to the threads is irrelevant, therefore not useful for most concurrency control applications. 
* For manging the threads some concurrency collection can be used like ConcurrentLinkedQueue.
* Discussions:
  * https://stackoverflow.com/questions/37789051/why-is-locksupport-provided-by-java-but-not-useful
  * https://stackoverflow.com/questions/39415636/can-locksupport-park-replace-object-wait 

### ReentrantLock
* java.util.concurrent.locks.ReentrantLock
  * is a java.util.concurrent.locks.Lock (has a java.util.concurrent.locks.Condition)
* Reference and Example: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/locks/ReentrantLock.html
* ReentrantLock doesn't means it behaved differently from instrict lock but with the extended capabilites it is possible to implement reentrance. 
* The name ReentrantLock is misleading and it shoule be called AdvancedLock.
* Reasons why ReentrantLock exists:
  * Polled and Timed Lock Acquisition - the methods tryLock() and unlock() are used here.
  * Interruptible Lock Acquisition - can be implemented with lockInterruptibly().
  * Non-block Structured Locking - no need to be aquired and released in the same code block. Using this techinquie as Lock Strapping in ConcurrentHashMap which has 16 lock on it.
  * Fairness - through paremter in the constructor. Fairness means locks favor granting access to the longest-waiting thread for but this is not meant of thread scheduling.
* ReentrantLock should be used when the advance features are needed: timed, polled or interruptible lock aquisition, fair queueing or non-block-structured locking. Otherwise synchronized (intristics locking) is prefered.
* Examples:
  * https://dzone.com/articles/what-are-reentrant-locks
  * https://javarevisited.blogspot.com/2013/03/reentrantlock-example-in-java-synchronized-difference-vs-lock.html#axzz6nmsBwnaK
  * https://www.netjstech.com/2016/02/difference-between-reentrantlock-and-synchronized-java.html
  * https://www.netjstech.com/2016/05/lock-striping-in-java-concurrency.html?showComment=1541399122082&m=0  
* Controversy:
  * Several stackoverflow discussions and also some tutorial sites are mentioning that the reentrant locking is ReentrantLock exclusive feature.
    * But the instristic locks also have this behavour - Book Java concurerncy in practice, Chapter 2.3.2.

### ReentrantReadWriteLock
* java.util.concurrent.locks.ReentrantReadWriteLock
  * is a java.util.concurrent.locks.ReadWriteLock
* java.util.concurrent.locks.ReentrantReadWriteLock.ReadLock
* java.util.concurrent.locks.ReentrantReadWriteLock.WriteLock

### StampedLock
* Class: java.util.concurrent.locks.StampedLock
  * has a java.util.concurrent.locks.Lock (has a java.util.concurrent.locks.Condition)
  * has a java.util.concurrent.locks.ReadWriteLock

### Synchronizer
* java.util.concurrent.AbstractOwnableSynchronizer
* java.util.concurrent.AbstractQueuedLongSynchronizer is a java.util.concurrent.AbstractOwnableSynchronizer
* java.util.concurrent.AbstractQueuedSynchronizer is a java.util.concurrent.AbstractOwnableSynchronizer

