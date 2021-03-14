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
### ConcurrentSkipListMap
* java.util.concurrent.ConcurrentSkipListMap
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListMap.html
* A thread-safe variant of TreeMap.
## Queues
### ConcurrentLinkedQueue
* java.util.concurrent.ConcurrentLinkedQueue
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedQueue.html 
* A thread-safe implementation of LinkedQueue.
* Example: https://www.geeksforgeeks.org/concurrentlinkedqueue-in-java-with-examples/
### ConcurrentLinkedDeque
* java.util.concurrent.ConcurrentLinkedDeque
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html
* Deque (Doubly Ended Queue)
* An unbounded concurrent deque based on linked nodes. 
* Concurrent insertion, removal, and access operations execute safely across multiple threads.
* Example: https://www.geeksforgeeks.org/concurrentlinkeddeque-in-java-with-examples/
## Blocking Queues
### ArrayBlockingQueue  
* java.util.concurrent.ArrayBlockingQueue
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ArrayBlockingQueue.html
* A bounded blocking queue backed by an array. 
* This queue orders elements FIFO (first-in-first-out). 
* This is a classic "bounded buffer", in which a fixed-sized array holds elements inserted by producers and extracted by consumers. Once created, the capacity cannot be changed. Attempts to put an element into a full queue will result in the operation blocking; attempts to take an element from an empty queue will similarly block.
* Examples: https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/
### LinkedBlockingQueue
* java.util.concurrent.LinkedBlockingQueue
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html
* An optionally-bounded blocking queue based on linked nodes. 
* This queue orders elements FIFO (first-in-first-out). 
* Linked queues typically have higher throughput than array-based queues but less predictable performance in most concurrent applications.
* The LinkedBlockingQueue is an optionally-bounded blocking queue based on linked nodes.
* It means that the LinkedBlockingQueue can be bounded, if its capacity is given, else the LinkedBlockingQueue will be unbounded.
* The capacity, if unspecified, is equal to Integer.MAX_VALUE.
* Examples: https://www.geeksforgeeks.org/linkedblockingqueue-class-in-java/
### PriorityBlockingQueue
* java.util.concurrent.PriorityBlockingQueue
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/PriorityBlockingQueue.html
* A thread-safe variant of PriorityQueue.
* A priority queue relying on natural ordering also does not permit insertion of non-comparable objects (doing so results in ClassCastException).
* The elements of the priority queue are ordered according to the natural ordering, or by a Comparator provided at queue construction time, depending on which constructor is used. 
* The PriorityQueue is based on the priority heap. Printing the order as array confused because it is actually a heap (tree) presentation of the order.
* Examples:
  * https://www.geeksforgeeks.org/priority-queue-using-binary-heap/
  * https://www.geeksforgeeks.org/priorityblockingqueue-class-in-java/
### SynchronousQueue
* java.util.concurrent.SynchronousQueue
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/SynchronousQueue.html
* A blocking queue in which each insert operation must wait for a corresponding remove operation by another thread, and vice versa.
* A blocking queue in which each insert operation must wait for a corresponding remove operation by another thread, and vice versa.
* Examples:
  * https://www.geeksforgeeks.org/java-program-to-implement-synchronousqueue-api/
  * https://www.baeldung.com/java-synchronous-queue
  * https://javapapers.com/java/java-synchronousqueue/
### LinkedTransferQueue
* java.util.concurrent.LinkedTransferQueue
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedTransferQueue.html
* A BlockingQueue in which producers may wait for consumers to receive elements.
* It is based on the TransferQueue interface which means it uses the transfer methods to transfers the element to a consumer.
* A transfer() waits for one or more recipient threads.
* The threads where the LinkedTransferQueue is not finishing as long alelement are set with the transfer method on it.
* Exampels: https://www.geeksforgeeks.org/linkedtransferqueue-in-java-with-examples/
### DelayQueue
* java.util.concurrent.DelayQueue
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/DelayQueue.html
* An unbounded blocking queue of Delayed elements, in which an element can only be taken when its delay has expired.
* DelayQueue is a specialized Blocking Queue that orders elements based on their delay time. It means that only those elements can be taken from the queue whose time has expired. 
* DelayQueue head contains the element that has expired in the least time. 
* If no delay has expired, then there is no head and the poll will return null. 
* DelayQueue accepts only those elements that belong to a class of type Delayed or those implement java.util.concurrent.Delayed interface.
* Delayed Object have:
  * (from java.lang.Comparable) compareTo - for comparing with other delayed object.
  * getDelay(TimeUnit unit) - Returns the remaining delay associated with this object, in the given time unit - the remaining delay; zero or negative values indicate that the delay has already elapsed.
* Examples: https://www.geeksforgeeks.org/delayqueue-class-in-java-with-example/
### LinkedBlockingDeque
* java.util.concurrent.LinkedBlockingDeque
* Reference: https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingDeque.html
* Deque (Doubly Ended Queue)
* An optionally-bounded blocking deque based on linked nodes.
* It implements the BlockingDeque and provides an optionally-bounded functionality based on linked nodes.
* When unspecified, the capacity is by default taken as Integer.MAX_VALUE
* A thread-safe variant of LinkedList.
* Examples: https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/
