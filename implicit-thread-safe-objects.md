# Objects which have implicit thread safe logic
## Introduction
In this section all objects have implicit thread safe logic which is part of the low level multithreading.
## java.util.Hashtable
### Introduction
* This class implements a hash table, which maps keys to values. Any non-null object can be used as a key or as a value.
* To successfully store and retrieve objects from a hashtable, the objects used as keys must implement the hashCode method and the equals method.
* As of the Java 2 platform v1.2, this class was retrofitted to implement the Map interface, making it a member of the Java Collections Framework. 
* Unlike the new collection implementations, Hashtable is synchronized. 
* If a thread-safe implementation is not needed, it is recommended to use HashMap in place of Hashtable. 
* If a thread-safe highly-concurrent implementation is desired, then it is recommended to use ConcurrentHashMap in place of Hashtable.
* HashTable is thread-safe with implementation based on blocking therefore not perfomrant enough but the invocation of size is much more realable than the ConcurrentHashMap.
### Structure
* It is structured as same as more used HashMap.
### Sources
* https://docs.oracle.com/javase/8/docs/api/java/util/Hashtable.html
## java.lang.StringBuffer
### Introduction
* A thread-safe, mutable sequence of characters. A string buffer is like a String, but can be modified. At any point in time it contains some particular sequence of characters, but the length and content of the sequence can be changed through certain method calls.
* String buffers are safe for use by multiple threads. The methods are synchronized where necessary so that all the operations on any particular instance behave as if they occur in some serial order that is consistent with the order of the method calls made by each of the individual threads involved.
  * The order of the calls need o be in the desired order.
* As of release JDK 5, this class has been supplemented with an equivalent class designed for use by a single thread, StringBuilder. The StringBuilder class should generally be used in preference to this one, as it supports all of the same operations but it is faster, as it performs no synchronization.
### Structure
* It is structured as same as more used StringBuilder.
### Sources
https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuffer.html
