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
* Reference and Examples: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/locks/ReentrantReadWriteLock.html
* The ReadWriteLock interface similarly defines locks that may be shared among readers but are exclusive to writers.
* This class has the following properties:
  * Acquisition order
  * Reentrancy
  * Lock downgrading
  * Interruption of lock acquisition
  * Condition support
  * Instrumentation
* The explanations and the examples from the class-java-doc give much information about this class and the use cases where it can be used. Because the purpose of it existence is clear and concrete thouse information are more than ehough to understand the ReentrantReadWriteLock.

### StampedLock
* Class: java.util.concurrent.locks.StampedLock
  * has a java.util.concurrent.locks.Lock (has a java.util.concurrent.locks.Condition)
  * has a java.util.concurrent.locks.ReadWriteLock
* Reference and Examples: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/locks/StampedLock.html
* The StampedLock can be seen as improvement over the ReentrantReadWriteLock. It has not the startvation problem of the ReentrantReadWriteLock when many writers are operating on the shared data while the readers are waiting.
* It does not support reentrance, but can "simulate" it by using the stamps.
* Writer locks doesn't have advantage over the read locks.
* Optimistic locking is very recommented to be used.
* Better performance over the ReentrantReadWriteLock.
* Documentation and Examples:
  * http://javaspecialists.eu/talks/jfokus13/PhaserAndStampedLock.pdf
  * https://dzone.com/articles/a-look-at-stampedlock
  * https://www.netjstech.com/2016/08/stampedlock-in-java.html

### Synchronizer
* java.util.concurrent.AbstractOwnableSynchronizer
* java.util.concurrent.AbstractQueuedLongSynchronizer is a java.util.concurrent.AbstractOwnableSynchronizer
* java.util.concurrent.AbstractQueuedSynchronizer is a java.util.concurrent.AbstractOwnableSynchronizer
* Reference and Example: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/locks/AbstractQueuedSynchronizer.html
* AbstractQueuedSynchronizer and AbstractQueuedLongSynchronizer are similar, the only difference is the type of the stored state whch is int in the AbstractQueuedSynchronizer and long in the AbstractQueuedLongSynchronizer.
* This class is designed to be a useful basis for most kinds of synchronizers that rely on a single atomic int value to represent state.
* It should be defined as subclass of the class which needs to be synchronized (See the example).
* This class supports either or both, at the same time, a default exclusive mode and a shared mode. They share the same FIFO queue.
* AbstractQueuedSynchronizer.ConditionObject is a Condition implementation for a AbstractQueuedSynchronizer serving as the basis of a Lock implementation.
* Typical subclasses requiring serializability will define a readObject method that restores this to a known initial state upon deserialization.
