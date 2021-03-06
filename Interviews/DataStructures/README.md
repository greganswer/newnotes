# Data structures

- [How computers store data](#how-computers-store-data)
- [Arrays](#arrays)
- [Hash tables](#hash-tables)
- [Stacks and queues](#stacks-and-queues)
- [Performance](#performance)

A Data Structure is a collection of values used by an algorithm.

Examples:
- Task list
- Directory tree structure

## How computers store data

- Random Access Memory (RAM) is a high speed storage area (data structure) where other data structures can be stored
- RAM has numbered shelves known as addresses
- Each address in memory can store 8 bits (1 byte) of data
- Each bit is an electrical switch that is stored as a 1 (on) or a 0 (off)
- The Central Processing Unit (CPU) is connected to a memory controller, which is responsible for reading/writing from RAM
- An integer is a 32 bit (4 bytes) data structure. 4 bytes requires 4 memory addresses. Can also be 64 bits.

## Arrays

- A collection of items, grouped sequentially, identified by index or key
- A one dimensional array is just a list of items
- A two dimensional array is a list of lists of items
- With a static array you have to declare the amount of items that will be in the array
- When you insert an item into the array anywhere other than the end, the indexes have to be recalculated causing O(n)
- With a dynamic array, if you add a 5th item to a 4 slot array, the interpreter will copy the array into a new memory address that is 8 slots (double the original size)

## Hash tables

- A.k.a: dictionary, hash, hash maps, maps, associative arrays
- It maps keys to their associated values
- The `key` is used as the index of where to find the value in memory
- Hash functions
    - a function that generates a value of fixed length for each input that it gets
    - are one way and it's idempotent (same output for the same output)
    - gives really fast data access
    - in a hash table the key is passed through the hash function which generates a hash that points to the address in memory where the data will be stored

Advantages

- Key-value mappings are unique
- They're typically faster than any other structure, especially with a large data set

Disadvantages

- For small data sets, arrays are usually faster
- Hash tables order is not predictable
- A collision can occur when the hashed key points to a memory location that already contains a value
    - A Linked Lists is created and the list will be traversed until the correct value is found

```python
hash = {"a": 1, "b": 2}
print(hash)  #=> {'a': 1, 'b': 2}

hash["c"] = "three"
print(hash)  #=> {'a': 1, 'b': 2, 'c': 'three'}

for key, val in hash.items():
    print(f'Key: {key}, Value {val}')
```

## Stacks and queues

- Linear data structures that can be traversed sequentially
- Best for when you only care about the beginning/end of the data structure

Stack

- Think of a stack of plates, take plates off the top
- Some languages have built in data types to represent this structure
- Collection that supports push and pop operations
- The last item pushed is the first one popped. Last In, First Out (LIFO)
- Main functions of a stack: `pop`, `push`, `peek` which all have a O(1)
- Examples:
    - Processing a mathematical expression
    - Backtracking: browser back button

```python
# Add to stack
stack = []
stack.append(1)
stack.append(2)
stack.append(3)
print(stack)  #=> [1, 2, 3]

# Pop off stack
item = stack.pop
print(stack)  #=> [1, 2]
```

Queue

- Think of a line at the grocery store, FIFO
- Some languages have built in data types to represent this structure
- Collection that supports adding and removing
- The first item pushed is the first one popped. First In, First Out (FIFO)
- **Never make a queue using an array because enqueueing/dequeueing is slower**
- Main functions of a queue: `enqueue`, `dequeue`, `peek` which all have a O(1)
- Examples:
    - Order processing
    - Message processing

```python
from collections import deque

# Add to queue
queue = deque()
queue.append(1)
queue.append(2)
queue.append(3)
print(queue)  #=> deque([1, 2, 3])

# Pop off queue
item = queue.popleft()
print(queue)  #=> deque([2, 3])
```

## Performance

Lookups in `lists` are O(n), lookups in `hash` are amortized O(1), with regard to the number of items in the data structure. If you don't need to associate values, use `sets`.
Prefer `sets` or `hash` instead of `lists` in cases where:

- The collection will contain a large number of items
- You will be repeatedly searching for items in the collection
- You do not have duplicate items.

| Operation | Array | Hash | Linked List | Biary Search Tree |
| --------- | ----- | ---- | ----------- | ----------------- |
| Insert    | O(n)  | O(1) | O(n)        | O(log n)          |
| Prepend   | O(n)  | O(1) | O(1)        |                   |
| Append    | O(1)* | O(1) | O(1)**      |                   |
| Lookup    | O(1)  | O(1) | O(n)        | O(log n)          |
| Delete    | O(n)  | O(1) | O(n)        | O(log n)          |
| Search    | O(n)  | O(1) | O(n)        | O(log n)          |
| Space     | O(1)  | O(n) | O(n)        |                   |

\* Can be O(n) on expanding memory 
\** Can be O(n) if tail is not stored in the `LinkList` object 