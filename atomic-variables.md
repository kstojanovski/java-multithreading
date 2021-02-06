# Atomic Variables
All classes from the package **java.util.concurrent.atomic** are part of this description here. They classes separated into several groups:
* Atomic single variables
* Atomic list variables
* Atomic field updaters
* Atomic special reference variables
* Accumulators
* Adders

The idea of the atomic vriable is to garantee atomicity, means changing the state of the clases from many threads leaves the state consitent for all threads before and after operating on it.

Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/package-summary.html

## Notes
* Atomic*.lazySet - is a performance win for single writers (volatile mode).

## Atomic single variables
In this group following classes belong:
* AtomicBoolean
  * Example: https://www.tutorialspoint.com/java_concurrency/concurrency_atomicboolean.htm
* AtomicInteger
  * Example: https://www.tutorialspoint.com/java_concurrency/concurrency_atomic_integer.htm
* AtomicLong
  * Example: https://www.tutorialspoint.com/java_concurrency/concurrency_atomiclong.htm 
* AtomicReference\<V\>
  * Example: https://www.tutorialspoint.com/java_concurrency/concurrency_atomicreference.htm

## Atomic list variables
In this group following classes belong:
* AtomicIntegerArray
  * Example: https://www.tutorialspoint.com/java_concurrency/concurrency_atomicintegerarray.htm
* AtomicLongArray
  * Example: https://www.tutorialspoint.com/java_concurrency/concurrency_atomiclongarray.htm
* AtomicReferenceArray\<E\>
  * Example: https://www.tutorialspoint.com/java_concurrency/concurrency_atomicreferencearray.htm

## Atomic field updaters
In this group following classes belong:
* AtomicIntegerFieldUpdater\<T\>
* AtomicLongFieldUpdater\<T\>
* AtomicReferenceFieldUpdater\<T,V\>

## Atomic special reference variables
In this group following classes belong:
* AtomicMarkableReference\<V\>
* AtomicStampedReference\<V\>

## Accumulators
In this group following classes belong:
* DoubleAccumulator
* LongAccumulator

## Adders
In this group following classes belong:
* DoubleAdder
* LongAdder



