## Collections
- A collection of data
- We've seen a few members of the Collections framework
    - ArrayList class
    - List interface
- Iterable - parent of the collection hierarchy
    - iterable means we can iterate through the different members
- List
    - https://docs.oracle.com/javase/8/docs/api/java/util/List.html
    - We've seen lists being used to store different values
    - Dynamically sized, we can add elements after it's created
    - We can give it a type to indicate what classes can be in the list
        - ex: List<Pet> pets
    - There are a few different implementations of the list
    - Unordered
    - Allows Duplicate elements
    - Some methods
        - add
        - get
        - clear
        - remove
    - Classes that implement List
        - ArrayList
            - Underlying representation is an array
            - Since the array is static sized, we have to do some resizing
            - ![Diagram of Array List](https://miro.medium.com/max/670/0*5w9-ibvGwT1EpeH9.png)
        - LinkedList
            - Comprised of nodes
            - A node has a value and a pointer to another value
            - The start of the list is the head node which points to the 2nd node and so on...
            - ![Diagram of Linked List](https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2013/03/Linkedlist.png)
        - Vector
            - Vector is like the ArrayList but it is synchronized, thread-safe
            - https://docs.oracle.com/javase/8/docs/api/java/util/Vector.html
            - https://www.geeksforgeeks.org/vector-vs-arraylist-java/
        - Stack
            - extends the vector class
            - Unlike a queue, which is FIFO (First in First Out), the stack is LIFO (Last in First Out)
            - Like a stack of pancakes, if you add a pancake to the stack, you wouldn't take one from the bottom, you would take the last one that was place on top
            - Methods
                - empty - check if the stack is empty
                - pop - remove the item on the top of the stack
                - peek - look at but don't remove the top item
                - search - returns the position on the stack
                - push - push an item onto the stack
- Queue
    - https://docs.oracle.com/javase/8/docs/api/java/util/Queue.html
    - Usually First in First Out
    - Methods
        - Throw Exception if fails:
            - add - insert an element into the queue
            - remove - retrieves and removes the head of the queue
            - element - return the head without removing it
        - Return special value (null or false) if fails
            - offer - insert an element into the queue
            - poll - remove the head, return null if empty
            - peek - return the head, return null if empty
    - Implementations
        - ArrayDeque - double-ended queue with no size limitations
            - We can add to both ends and get value from both ends
            - For every method that interacts with the front of the queue (pollFirst, PeekFirst, addFirst), we have corresponding methods that interact with the end of the queue (pollLast, PeekLast, addLast)
        - Priority Queue
            - it stores the elements in order
            - so whenever we take an element from the queue, it's guaranteed to be in whatever order we defined
- Set
    - https://docs.oracle.com/javase/8/docs/api/java/util/Set.html
    - No duplicate elements
    - Don't have a get method like list but we can use an iterator to loop through the elements in the set
    - add, remove, clear
- ![Diagram of Collections](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200811210521/Collection-Framework-1.png)

## ArrayList vs LinkedList
- Which is more efficient at inserting/adding an element?
    - Time Efficient - ArrayList usually better (unless we have to resize) because it's a matter of setting the position in the array to be that new value
        - Whereas with the linked list, we have to iterate through until we found the correct position
    - Memory Efficient - LinkedList, because instead of moving things around, resize, we just update the pointers
        - With ArrayList, you have to allocate more memory, or copy things over
- Which is more efficient at getting an element?
    - Time Efficient - ArrayList, look up the value directly using the index
        - LinkedList is slower because we have to iterate until we get there
    - Memory Efficient - irrelevant because we're not updating the structure

## HashSet vs TreeSet
- https://www.geeksforgeeks.org/hashset-vs-treeset-in-java/
1. Internal Implementation
    - HashSet - we use hash values to identify and locate the values in our set
        - insert, delete, search constant O(1)
    - TreeSet - underlying representation is a sorted tree
        - insert, delete, search O(log N) which is a little bit slower than the O(1)
    ![Hash Set Diagram](https://1.bp.blogspot.com/-hZ1zEGSDnvw/YOljOn69-tI/AAAAAAAAofI/9HHDgGQ29MU4ZOgb2NG-IIvL2lRbo4oRQCLcBGAsYHQ/w1200-h630-p-k-no-nu/How%2BHashSet%2Binternally%2Bworks%2Bin%2BJava.png)
    - https://www.youtube.com/watch?v=shs0KM3wKv8
2. Ordering - HashSet is unordered and TreeSet is ordered
3. HashSet allows null, whereas TreeSet does not allow null values

### Hashing
- Hash function - takes a value like a string or an object or whatever and produce a consistent integer value
    - ex: "cat" -> 34
    - ex: "dog" -> 56
    - In HashSets, we use the hash value (sometimes indirectly) to produce an index value in an array:

- Let's say we want to insert "cat"
- hash(cat) => 5, this means we put the "cat" in index 5
- hash(dog) => 3, means we put the "dog" in index 3
- Sometimes, because our hash values could be much bigger than the array, we have to do some math (division) to get that number down
    - Because, we can have some collisions
    - To resolve these collisions, we just take the next non-null spot
- [null, null, null, dog, null,cat, null]
- Because the hash functions are consistent (meaning, with the same input, we would get the same output), we can look up the animals very quickly by first getting the hash value and then checking if a record exists at that location

## Iterator
- points to a data structure and lets us iterate through the elements
- we have to specify a type
```Iterator<String> itr = ...```
- .hasNext to check if there is a next value
- .next return the next value and increment the iterator

## Comparator and Comparable Interfaces
- Both have to do with comparing objects in Java
- About seeing what is less than, greater than, equal to
- With primitives and Strings, it's usually easy to tell how to compare them
    - 1 < 2, "a" < "b", 56 == 56
- This gets more difficult with more complex objects
    - How do we order them?
    - Do we order by a particular field? Multiple fields?
- For example, movie:
    - Order by name?
    - Order by year?
    - Order by rating?

### Comparable Interface
- When a class implement the Comparable interface, it means that particular class is the one that we're determining how to order
- We also have to implement the compareTo method which takes in another object and returns an integer that represents the comparison between them
- compareTo method takes in only one object because the other object is the "this"
- positive - first object is greater than the other
- negative - second object is greater
- 0 - two objects are equal

### Comparator Interface
- A class that implements the comparator interface, its only purpose is to compare 2 members of (usually) a different class (like a Movie class)
    - We would have a Movie class as well as a totally separate MovieCompare class
- compare method takes in 2 objects and compares them


