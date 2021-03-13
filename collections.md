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
  * ArrayBlockingQueue
  * ConcurrentLinkedQueue
  * DelayQueue
  * LinkedBlockingQueue
  * PriorityBlockingQueue
  * SynchronousQueue
  * LinkedBlockingDeque
  * ConcurrentLinkedDeque
  * LinkedTransferQueue

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
### ArrayBlockingQueue
### ConcurrentLinkedQueue
### DelayQueue
### LinkedBlockingQueue
### PriorityBlockingQueue
### SynchronousQueue
### LinkedBlockingDeque
### ConcurrentLinkedDeque
### LinkedTransferQueue
