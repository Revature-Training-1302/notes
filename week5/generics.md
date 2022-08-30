## Generics
- Sometimes when we're defining a class, we don't know what the data type is ahead of time
- In the case of lists, we can store any type of data in our list
    - We can't define our list based on one single data type (ex: string, integer), we have to keep it "generic" where it's applicable to any data type that we pass in
- syntax:
```java
class CustomList <T> {
    // anywhere we see the T, it's going to reger to that type that we assigned
}