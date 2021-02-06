# Keywords
## Keyword - volatile
### Notes
* The volatile keyword is used on veriable which share memory through threads.
* The do not block the read/write process which leads to inconsitend state trough many threads, reading the same value from emmory even when it is modified in the very moment.
  * Therefor not atomic.
* Not to use: when more than one thread is writing into the variable.
* To use: when only one thread is writing but meany are reading.
* Happens-Before Ordering is used on volatile keywords.
  * On writing: All other varibles of the method set with new values before the setting the volatile value are memorized, which means on reading the volatile it is 100% for sure that the other varibles have also the newest state.
### Sources
* https://www.baeldung.com/java-volatile
* http://tutorials.jenkov.com/java-concurrency/volatile.html
## Keyword - synchronized
### Notes
* The synchronized keyword can be used on static methods, non static method and in a mthod as static block.
* It block the execution of the code part for any other thread that the one which owns the object lock. Default is
** this on non static code part.
** class-object on static code part.
## Sources
* https://www.baeldung.com/java-synchronized
