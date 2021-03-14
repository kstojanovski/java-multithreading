# Collections

Particular collections are thread safe. They can be separated in several groups:
* Sets
  * CopyOnWriteArraySet
  * ConcurrentSkipListSet
* Lists
  * CopyOnWriteArrayList
* Maps
  * ConcurrentHashMap
  * ConcurrentHashMap.KeySetView
  * ConcurrentSkipListMap
* Queues
  * ConcurrentLinkedQueue
  * ConcurrentLinkedDeque
* Blocking Queues
  * ArrayBlockingQueue  
  * LinkedBlockingQueue
  * PriorityBlockingQueue
  * SynchronousQueue
  * LinkedTransferQueue
  * DelayQueue 
  * LinkedBlockingDeque 

## Sets
### CopyOnWriteArraySet
* java.util.concurrent.CopyOnWriteArraySet
* Reference and Examples: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArraySet.html
* A thread-safe variant of HashSet.
### ConcurrentSkipListSet
* java.util.concurrent.ConcurrentSkipListSet
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html
* A thread-safe variant of TreeSet.
## Lists
### CopyOnWriteArrayList
* java.util.concurrent.CopyOnWriteArrayList
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html 
* A thread-safe variant of ArrayList.
## Maps
### ConcurrentHashMap
* java.util.concurrent.ConcurrentHashMap
  * has a ConcurrentHashMap.KeySetView
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentHashMap.html
* A thread-safe variant of HashMap.
#### ConcurrentHashMap.KeySetView
* java.util.concurrent.ConcurrentHashMap.KeySetView
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentHashMap.KeySetView.html
* Collection of Key values pairs of a ConcurrentHashMap.
* Example: https://www.geeksforgeeks.org/concurrentlinkedqueue-in-java-with-examples/
### ConcurrentSkipListMap
* java.util.concurrent.ConcurrentSkipListMap
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListMap.html
* A thread-safe variant of TreeMap.
* Example: https://www.geeksforgeeks.org/concurrentlinkeddeque-in-java-with-examples/
## Queues
### ConcurrentLinkedQueue
* java.util.concurrent.ConcurrentLinkedQueue
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedQueue.html 
* A thread-safe implementation of LinkedQueue.
### ConcurrentLinkedDeque
* java.util.concurrent.ConcurrentLinkedDeque
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html
* An unbounded concurrent deque based on linked nodes. 
* Concurrent insertion, removal, and access operations execute safely across multiple threads.
## Blocking Queues
### ArrayBlockingQueue  
* java.util.concurrent.ArrayBlockingQueue
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ArrayBlockingQueue.html
* A bounded blocking queue backed by an array. 
* This queue orders elements FIFO (first-in-first-out). 
* This is a classic "bounded buffer", in which a fixed-sized array holds elements inserted by producers and extracted by consumers. Once created, the capacity cannot be changed. Attempts to put an element into a full queue will result in the operation blocking; attempts to take an element from an empty queue will similarly block.
### LinkedBlockingQueue
* java.util.concurrent.LinkedBlockingQueue
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html
* An optionally-bounded blocking queue based on linked nodes. 
* This queue orders elements FIFO (first-in-first-out). 
* Linked queues typically have higher throughput than array-based queues but less predictable performance in most concurrent applications.
### PriorityBlockingQueue
* java.util.concurrent.PriorityBlockingQueue
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/PriorityBlockingQueue.html
* A thread-safe variant of PriorityQueue.
* A priority queue relying on natural ordering also does not permit insertion of non-comparable objects (doing so results in ClassCastException).
### SynchronousQueue
* java.util.concurrent.SynchronousQueue
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/SynchronousQueue.html
* A blocking queue in which each insert operation must wait for a corresponding remove operation by another thread, and vice versa.
### LinkedTransferQueue
* java.util.concurrent.LinkedTransferQueue
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedTransferQueue.html
* A BlockingQueue in which producers may wait for consumers to receive elements.
* It is based on the TransferQueue interface which means it uses the transfer methods to transfers the element to a consumer.
### DelayQueue
* java.util.concurrent.DelayQueue
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/DelayQueue.html
* An unbounded blocking queue of Delayed elements, in which an element can only be taken when its delay has expired. 
### LinkedBlockingDeque
* java.util.concurrent.LinkedBlockingDeque
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html
* An optionally-bounded blocking deque based on linked nodes of of delayed elements.

