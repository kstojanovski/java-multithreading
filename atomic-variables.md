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
* Atomic*.lazySet - is a performance win for single writers.
  * Reference: https://psy-lob-saw.blogspot.com/2012/12/atomiclazyset-is-performance-win-for.html
* Atomic*.weakCompareAndSet - weakCompareAndSet is not a good choice for implementing locks, semaphores, initialization flags. It does not provide ordering guarantees. This provides weaker memory visibility guarantees than compareAndSet.  If you have any doubt whether you should be using weakCompareAndSet or compareAndSet, then use compareAndSet.
  * Reference: http://jsr166-concurrency.10961.n7.nabble.com/AtomicReference-weakCompareAndSet-quot-May-fail-spuriously-quot-td918.html

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

Examples: https://www.logicbig.com/tutorials/core-java-tutorial/java-multi-threading/atomic-field-updater.html

## Atomic special reference variables
In this group following classes belong:
* AtomicMarkableReference\<V\>
  * Example: https://www.logicbig.com/tutorials/core-java-tutorial/java-multi-threading/atomic-markable-reference.html
  * Example: https://www.baeldung.com/java-atomicmarkablereference
* AtomicStampedReference\<V\>
  * Example: https://www.logicbig.com/tutorials/core-java-tutorial/java-multi-threading/atomic-stamped-reference.html
  * Example: https://www.baeldung.com/java-atomicstampedreference

## Accumulators
This class is usually preferable to alternatives when multiple threads update a common value that is used for purposes such as summary statistics that are frequently updated but less frequently read.
The order of accumulation within or across threads is not guaranteed and cannot be depended upon, so this class is only applicable to functions for which the order of accumulation does not matter.

In this group following classes belong:
* DoubleAccumulator
  * Example: https://www.geeksforgeeks.org/doubleaccumulator-get-method-in-java-with-examples/
  * Example: https://www.geeksforgeeks.org/doubleaccumulator-doublevalue-method-in-java-with-examples/ 
* LongAccumulator
  * Example: https://www.geeksforgeeks.org/doubleadder-doublevalue-method-in-java-with-examples/
  * Example: https://www.geeksforgeeks.org/doubleadder-sum-method-in-java-with-examples/

## Adders
This class is usually preferable to alternatives when multiple threads update a common value that is used for purposes such as summary statistics that are frequently updated but less frequently read.
The order of accumulation within or across threads is not guaranteed and cannot be depended upon, so this class is only applicable to functions for which the order of accumulation does not matter.

In this group following classes belong:
* DoubleAdder
  * Example: https://www.geeksforgeeks.org/longaccumulator-accumulate-method-in-java-with-examples/
  * Example: https://www.geeksforgeeks.org/longaccumulator-get-method-in-java-with-examples/
* LongAdder
  * Example: https://www.geeksforgeeks.org/longadder-sum-method-in-java-with-examples/
  * Example: https://www.baeldung.com/java-longadder-and-longaccumulator



