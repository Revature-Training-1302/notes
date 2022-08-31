## Strings
- Strings are immutable, we can't change them after we create them
We can't take a string "cat" and turn into "bat"
```java
String s = "cat";
s[0] = 'b';
```
- We can reassign strings
```java
String s = "cat";
s = "bat";
```
Even this is technically not changing the string, we're creating a new string and assigning it to the variable
```java
String result = "";
result += "a";
```
- We'll learn a way to change the string itself

## String Builder and String Buffer Class
- String Builder/Buffer class are similar in that they have same methods
    - replace - replacing a sub string with something else
    - reverse - reversing the string
    - insert - insert a string into the middle
    - append - adding something else to the end
    - find more methods here: https://docs.oracle.com/javase/7/docs/api/java/lang/StringBuilder.html#
    - https://docs.oracle.com/javase/7/docs/api/java/lang/StringBuffer.html




### Difference between String Builder and String Buffer:
- Thread safety and synchronization
- Threads allow us to run different methods at the same time
- Multithreading, in general, allows for the program to run faster
- String Buffer is thread-safe synchronized which means if we use the String Buffer in a multi-threading program, we are assured that the values will be consistent, they won't be changed due to inconsistencies in the thread
    - Usually this means only one thread can alter it at a given time
    - Slower, because we might have to pause threads to make sure that it stays synchronized
- String Builder not thread-safe so therefore it is faster

