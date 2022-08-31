## Data Structures and Algorithms


### Time and Space Complexity
- When dealing with operations/algorithms in our programs, we usually think of them in terms of n, our data size
- O(1) - doesn't depend on size at all, constant time no matter what
    - 1 + 1 = 2
    - arraylist.get(i) - constant time because we're just looking up the value at that index
- O(N) - directly correlate with how big our data size
    - Usually means going through our data set and doing something to each value
    - Printing everything in a list
    - Inserting onto the end of a single-linked list because we have to iterate all the way through until we get to the end
    - Imagine we have to go through a list twice
        - O(2 * N) - simplified to O(N) because in the grand scheme of things, if we have thousands or millions of data, one more run through of the list isn't going to drastically change the run-time