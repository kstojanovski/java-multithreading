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
* Should be used on much more elements because it takes the time for spitting and merging the partial results.
* It is advisable to use parallel streams in cases where no matter what is the order of execution, the result is unaffected and the state of one element does not affect the other as well as the source of the data also remains unaffected.
* Examples:
  * https://java-8-tips.readthedocs.io/en/stable/parallelization.html
  * https://www.geeksforgeeks.org/what-is-java-parallel-streams/
  * https://docs.oracle.com/javase/tutorial/collections/streams/parallelism.html
  * https://mkyong.com/java8/java-8-parallel-streams-examples/
