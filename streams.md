# Streams

With java 8 lambda notation and stream were introduced. As part of the Streamp API several methods came with multithreading capabilites:
* Parallel Stream
* Parallel

# Parallel Stream
* java.util.Collection<E>::parallelStream()
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html#parallelStream--

# Parallel
* java.util.stream.BaseStream<T,S extends BaseStream<T,S>>::parallel()
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/stream/BaseStream.html#parallel--

---

# Parallel and Parallel Stream Explanation

* Executing Streams in Parallel
	* Aggregate operations and parallel streams enable you to implement parallelism with non-thread-safe collections provided that you do not modify the collection while you are operating on it.
* Concurrent Reduction
	* Note that parallelism is not automatically faster than performing operations serially, although it can be if you have enough data and processor cores. 
	* While aggregate operations enable you to more easily implement parallelism, it is still your responsibility to determine if your application is suitable for parallelism.
	* Should be used on much more elements because it takes the time for spitting and merging the partial results.
* Ordering
  * It is advisable to use parallel streams in cases where no matter what is the order of execution, the result is unaffected and the state of one element does not affect the other as well as the source of the data also remains unaffected.
* Side Effects
  * Laziness
    * Intermediate operations like peek, map in a lambda pipe are lazy and are one of the source of interference problems on computing parallel streams.
  * Interference
	* Processing streams lazily enables the Java compiler and runtime to optimize how they process streams. Therefore lambda expressions in stream operations should not interfere. Interference occurs when the source of a stream is modified while a pipeline processes the stream.
    * Intermediate operations like peek in a lambda pipe are lazy while the terminal operation are eager. Using them togehter in a parallel stream leads to ConcurrentModificationException.
  * Stateful Lambda Expressions
    * Avoid using stateful lambda expressions as parameters in stream operations. A stateful lambda expression is one whose result depends on any state that might change during the execution of a pipeline

## Reference 
* Tutorial:
  * https://docs.oracle.com/javase/tutorial/collections/streams/parallelism.html
* Examples:
  * https://java-8-tips.readthedocs.io/en/stable/parallelization.html
  * https://www.geeksforgeeks.org/what-is-java-parallel-streams/
  * https://mkyong.com/java8/java-8-parallel-streams-examples/
