# Patterns

Diverse patterns with concurrency exists like:
* Producer-Consumer
* Distributed Locking
* Object pool

## Producer-Consumer

This is one of the main pattern which is used for explaining the thread approach. It can be implemneted in different ways like:
* Low-Level API - wait-notify methods of the Object class.
* High-Level API - BlockingQueue class.

## Distributed Locking

This kind of pattern is needed when you have different groups of threads which are bound to one lock.
Acctualy I wish this culd be a part of the high level API of the concurrency package.
One possible solution using the low level api with wait and notify can be found in the next example.

Discussion and Example: https://stackoverflow.com/questions/21286831/managing-multiple-locks


## Object pool

Object pool is not a classic multithreading pattern. It is listed here because for implementig it concurrency proramming needs to be used.
