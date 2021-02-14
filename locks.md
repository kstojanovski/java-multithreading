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

### Lock
* java.util.concurrent.locks.Lock
  * has a java.util.concurrent.locks.Condition

### ReadWriteLock
* java.util.concurrent.locks.ReadWriteLock

## Class Group

### LockSupport
* java.util.concurrent.locks.LockSupport

### ReentrantLock
* java.util.concurrent.locks.ReentrantLock
  * is a java.util.concurrent.locks.Lock
  * has a java.util.concurrent.locks.Condition

### ReentrantReadWriteLock
* java.util.concurrent.locks.ReentrantReadWriteLock
  * is a java.util.concurrent.locks.ReadWriteLock
* java.util.concurrent.locks.ReentrantReadWriteLock.ReadLock
* java.util.concurrent.locks.ReentrantReadWriteLock.WriteLock

### StampedLock
* Class: java.util.concurrent.locks.StampedLock
  * has a java.util.concurrent.locks.Lock

### Synchronizer
* java.util.concurrent.AbstractOwnableSynchronizer
* java.util.concurrent.AbstractQueuedLongSynchronizer is a java.util.concurrent.AbstractOwnableSynchronizer
* java.util.concurrent.AbstractQueuedSynchronizer is a java.util.concurrent.AbstractOwnableSynchronizer

