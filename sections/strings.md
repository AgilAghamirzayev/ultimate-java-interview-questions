# Java String interview Question

**1. What is a String in Java?**

In Java, a String is an object that represents a sequence of characters. The String class is part of the java.lang
package. Strings are immutable, meaning once created, they cannot be modified. Any operation on a String results in a
new String object.

**2. What is the difference between String, StringBuffer, and StringBuilder?**

* String: Immutable, meaning once a String object is created, it cannot be changed. Any modification creates a new
  String.
* StringBuffer: Mutable, and thread-safe. It can be modified without creating a new object. It uses synchronized
  methods, which makes it slower than StringBuilder.
* StringBuilder: Mutable and not synchronized, which makes it faster than StringBuffer but not thread-safe.
