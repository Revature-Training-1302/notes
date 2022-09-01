## Data Structures and Algorithms
- Data Structures - 
    - a way to organize variables
    - how data is organized in memory
- Algorithms - 
    - a way to get to a solution
    - series of steps to get to a solution
    - formula, equation
    - usually have some input and some output

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


### Data Structures

#### Interfaces and Classes that are NOT in Collections Framework:

##### Map Interface
- key and value pairs
- keys must be unique and they "point to" a specific value
- Methods
    - clear - clear out the map
    - get - instead of an index, we pass in a key and get the corresponding value
    - keySet - return the set of all keys in the map
    - put - given a key and a value, associate the key to that value in the map
    - remove - given just a key or a key and value, remove that entry in the map
    - replace - replace the value for the specified key
    - size - return how many mappings there are
    - values - returns a collection of the value

##### HashMap and HashTable
- both implementations of the map interface
- HashMap is not synchronized and HashTable is
- HashMap is faster
- Null is allowed in HashMap but not in HashTable


### Algorithms
#### Searching
- Given some data structure, find the location of a specific value
- ex: Find the letter R in the alphabet, we would return 17 (0-based index)
- Given a list of id's or numbers, find the specified number

##### Linear Search
- Checking every single item in the data structure and return the index once we find it
- Worst Case - item is at the end of the array or not in the array, O(N)
    - If you double the array size, it would double the time to search, but it would still have the same big O notation
- Best Case - item is the first element, O(1)
- Average Case - element is right in the middle of the array O(N/2) => O(N)
- Linear search has linear time

##### Binary Search
- Requirement is that the array is sorted
- Way more efficient way to search because the array is sorted
- Looking at the middle number, seeing if the target is greater or less than the middle and look at the half the number could be in. Repeat this until you've found the number or until there's no possible place the number could be.
```
target = 9
[1, 2, 3, 4, 5, 6, 7, 8, 9,10]
First start in the middle, so in this case 5. Is target greater than or less than 9?
Since 9 is bigger than 5, we can eliminate half of the array. 
[6,7,8,9,10]
In one step, we've shrunk our array in half (got ride of 5 elements):
Is target greater or less than the middle number (8). 9 is bigger than 8
So we can shrink the array again and get rid of 6-8 because all numbers to the left of 8 are guarenteed to be less than 8, and therefore less than 9
[9,10]
Look at 9 and we see that that's our number
On the other hand, if we looked at 10, we would see that 10 is not the number so then we would just look at 9 and say that that's our number
```
3-4 steps (binary search)vs 9 (linear search)