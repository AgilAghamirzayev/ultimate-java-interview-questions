# Java String interview Question

**1. What is a String in Java?**

In Java, a String is represented internally by an array of byte values (or char values before JDK 9). The String class
is part of the java.lang package. Strings are immutable, meaning once created, they cannot be modified. Any operation on
a String results in a new String object.

**2. What is the difference between String, StringBuffer, and StringBuilder?**

* String: Immutable, meaning once a String object is created, it cannot be changed. Any modification creates a new
  String.
* StringBuffer: Mutable, and thread-safe. It can be modified without creating a new object. It uses synchronized
  methods, which makes it slower than StringBuilder.
* StringBuilder: Mutable and not synchronized, which makes it faster than StringBuffer but not thread-safe.

**3. What is the difference between == and .equals() when comparing Strings?**

* == compares the memory reference (location) of two String objects, not the actual content.
* .equals() compares the content (value) of two String objects. It checks if the characters in both strings are the
  same.

**4. What is String Pool in Java?**

The String Pool is a special memory area in Java where Strings are stored. When a String is
created using a string literal (e.g., "hello"), Java checks if the same String already exists in the pool. If it does,
it returns a reference to the existing String, thus **saving memory**. String pool located inside heep memory.

**5. What is String immutability and why is it important?**
[Why Java Strings are Immutable?](https://www.geeksforgeeks.org/java-string-is-immutable-what-exactly-is-the-meaning/)

String immutability means that once a String object is created, its value cannot be changed. If a String is modified, a
new String object is created. This property is important because it makes Strings thread-safe, improves performance by
reusing the same object from the String Pool, and prevents accidental changes to string data.

**6. What is the String class’s intern() method?**

The intern() method ensures that a String is present in the String Pool. If the String already exists in the pool, it
returns the reference to that String; otherwise, it adds the String to the pool and returns its reference.

**7. What is the difference between String.trim() and String.strip()?**

* String.trim() removes leading and trailing whitespace (ASCII space characters).
* String.strip() removes leading and trailing whitespace, but it also handles other Unicode space characters.

  String test = "\u2001\u2001\u2001test   ";
  System.out.println(test.trim());
  System.out.println(test.strip());

  prints:
  test
  test

**8. What is the difference between String.equals() and String.compareTo() methods?**

* equals(): Compares two strings for equality, checking if both strings have the same value (content).

      "hello".equals("hello"); // true
* compareTo(): Compares two strings lexicographically (i.e., based on Unicode values). It returns:
    * 0 if the strings are equal
    * A negative integer if the first string is lexicographically less than the second
    * A positive integer if the first string is lexicographically greater than the second

          "hello".compareTo("hello"); // 0
          "hello".compareTo("world"); // Negative value

**9. What are the different string methods in Java?**

* split(): Split/divide the string at the specified regex.
* compareTo(): Compares two strings on the basis of the Unicode value of each string character.
* compareToIgnoreCase(): Similar to compareTo, but it also ignores case differences.
* length(): Returns the length of the specified string.
* substring(): Returns the substring from the specified string.
* equalsIgnoreCase(): Compares two strings ignoring case differences.
* contains(): Checks if a string contains a substring.
* trim(): Returns the substring after removing any leading and trailing whitespace from the specified string.
* charAt(): Returns the character at specified index.
* toLowerCase(): Converts string characters to lower case.
* toUpperCase(): Converts string characters to upper case.
* concat(): Concatenates two strings.

**10. What will print in below code:**

    String s1 = "abc";
    String s2 = "abc";
    String s3 = new String("abc");
    
    System.out.println("s1 == s2 ? " + (s1 == s2));
    System.out.println("s1 == s3 ? " + (s1 == s3));
    System.out.println("s1 equals s3 ? " + (s1.equals(s3)));

* true
* false
* true

**11. What will print in below code:**

    String s1 = "abc";
    String s2 = new String("abc");
    s2.intern();
    System.out.println(s1 == s2);

false

**12. What is Compact Strings**
[Compact Strings in Java 9](https://www.geeksforgeeks.org/compact-strings-in-java-9-with-examples/)


Java 9 has brought the concept of compact Strings back.

This means that whenever we create a String if all the characters of the String can be represented using a byte —
LATIN-1 representation, a byte array will be used internally, such that one byte is given for one character.

In other cases, if any character requires more than 8-bits to represent it, all the characters are stored using two
bytes for each — UTF-16 representation.

So basically, whenever possible, it’ll just use a single byte for each character.

Now, the question is – how will all the String operations work? How will it distinguish between the LATIN-1 and UTF-16
representations?

Well, to tackle this issue, another change is made to the internal implementation of the String. We have a final field
coder, that preserves this information.

**13. Why after Java 9 String internally changes from char[] to byte[]**

Pre-Java 9: String was backed by a char[], where each char takes 2 bytes (16 bits) due to UTF-16 encoding. For ASCII
characters, this resulted in unused space because ASCII characters can fit into a single byte (8 bits).
