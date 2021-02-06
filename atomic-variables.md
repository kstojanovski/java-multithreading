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

## Atomic single variables
In this group following classes belong:
* AtomicBoolean
* AtomicInteger
* AtomicLong
* AtomicReference\<V\>

## Atomic list variables
In this group following classes belong:
* AtomicIntegerArray
* AtomicLongArray
* AtomicReferenceArray\<E\>

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



