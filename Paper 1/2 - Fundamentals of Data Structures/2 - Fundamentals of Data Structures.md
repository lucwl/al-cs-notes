### Units
- [[2.1. Data Structures and Abstract Data Types]]

## Arrays

An *array* is a fixed-size collection of values, all of the same data type. Each element is given an index, which can start with either 0 or 1.

Arrays can be created in multiple dimensions, for example to represent tabular data.

## Fields, records and files

Information is stored on computers as a series of *files*. Each file is made up of *records* which are composed of a number of *fields*.

Files are a way of permanently storing data, which can later be accessed when the program or subroutine has finished running.

Text files store data in a text encoding, such as ASCII or Unicode. Binary files represent items using binary values.

## Abstract data types/data structures

Abstract data structures do not exist as data structures in their own right, they are implemented from other data structures.

They enable programmers to perform high-level operations without having to worry about the underlying implementation.

Some data structures are *static*, meaning the memory allocated to them is fixed and cannot be changed, such as arrays.

Other are *dynamic*, meaning the memory allocated to them can change at runtime, such as in the case of linked lists.

## Queues

A *queue* is an abstract data structure based on an array.

Items are retrieved from the front of the queue and new items are added at the rear of the queue. This can be described as first in, first out (FIFO).

Common uses of queues include:
- Buffering, storing data as it arrives until it can be processed
- Simulating a card game
- Performing breadth-first search (BFS)

A queue can be implemented using a single dimensional array and two integer variables, designated Front Pointer (FP) and Rear Pointer (RP).

The following actions can be performed on a queue:

| Action     | Description                                                     |
| ---------- | --------------------------------------------------------------- |
| Enqueue    | Add a new item to the end of the queue                          |
| Dequeue    | Remove one item from the front of the queue                     |
| Peek (Top) | Look at, but don't remove, one item from the front of the queue |
| isEmpty    | Check if the queue is empty                                     |
| isFull     | Check if the queue is full                                      |
The last two actions are needed as the program could crash if an attempt is made to enqueue an item when the queue is full, or dequeue an item when the queue is empty.

There are several types of queue:
- Linear queue
- Circular queue
- Priority queue

### Linear queue

In a *linear queue*, a front pointer is not needed.

The first item in the array always represents the front of the queue. When an item is enqueued, every single item in the queue must be moved forwards in the array. This can be inefficient, especially for larger queues.

### Circular queue

A *circular queue* uses a front pointer and a rear pointer.

When an item is enqueued, the rear pointer is incremented by one. When an item is dequeued, the front pointer is incremented by one.

When a pointer reaches the end of an array, it wraps back around to the start.

This is much more efficient than a linear queue when the queue is large as it avoids having to move every single item down when a new value is enqueued.

However, it comes with more implementation complexity. A linear queue may be more appropriate for a smaller queue.

### Priority queue

A *priority queue* enqueues items to the rear of a queue alongside a priority level.

Items with the highest priority are always dequeued first, so when a value is enqueued the new item's priority is compared to every priority in the list, starting at the back.

An example of where this is used is applications on a computer system, which are assigned priorities. Applications being used by the user are prioritised over background applications, allowing for a faster user experience.

## Stacks

A *stack* is another abstract data structure based on an array.

It is a last in, first out (LIFO) data structure as items are pushed and retrieved from the top of the stack.

Common uses of a stack include:
- Reversing a list of values
- Keeping track of and performing undo operations
- A call stack for keeping track of subroutine calls
- Evaluating RPN expressions

A stack can be implemented using a single-dimensional array and an integer variable to point at the top of the stack.

The following actions can be performed on a stack:

| **Action** | **Description**                                               |
| ---------- | ------------------------------------------------------------- |
| Push       | Add a new item to the top of the stack                        |
| Pop        | Remove one item from the top of the stack                     |
| Peek (Top) | Look at, but don't remove, one item from the top of the stack |
| isEmpty    | Check if the queue is empty                                   |
| isFull     | Check if the queue is full                                    |

## Graphs

A *graph* is an abstract data structure designed to represent more complex relationships between items in datasets.

Uses of graphs include:
- Route finding
- Representing relationships on social networks
- Computer networks
- Project management
- Game theory

There are several types of graph:
- Unweighted and undirected graphs
- Weighted graphs
- Directed graphs
- Disconnected graphs 

#### Unweighted and undirected graphs

Simple graphs that show how two or more items are connected.

#### Weighted graphs

A *weighted* graph is used where the connection between two nodes has a cost or value, e.g. distance or time.

#### Directed graphs

In a *directed graph*, one or more edges has an arrow which indicates that the edge can only be traversed in one direction. For example, a one-way road. Not every edge needs to be one-directional. 

#### Disconnected graphs

In a *disconnected graph*, two or more vertices are not connected to the rest of the graph.

### Graph representation

There are two ways to represent a graph on a computer system: using an *adjacency list* or using an *adjacency matrix*.

#### Adjacency lists

An *adjacency list* uses a list for each node to store details about adjacent nodes.

For example:

| **Vertex** | **Adjacent vertices** |
| ---------- | --------------------- |
| A          | B, C                  |
| B          | A, C, E               |
| C          | A, B, D               |
| D          | C, E                  |
| E          | B, D                  |

This is efficient for *sparse graphs*, which have many vertices but few edges. An adjacency list only records existing connections in a graph, unlike an adjacency matrix which can store edges that do not exist.

#### Adjacency matrices

An *adjacency matrix* uses a grid to store details of adjacent nodes. For an unweighted graph, the adjacency matrix uses a binary number to show the presence or lack of an edge. For a weighted graph, this value represents the weight of that edge.

This is efficient for *dense graphs*, with few vertices but many edges.

In an undirected graph, adjacency matrices form a diagonal line of symmetry. Directed graphs are asymmetrical. Where nodes are not adjacent, the cost of traversing them is infinite.

For example:

|       | **A**    | **B**    | **C**    | **D**    | **E**    |
| ----- | -------- | -------- | -------- | -------- | -------- |
| **A** | $\infty$ | 20       | 30       | $\infty$ | $\infty$ |
| **B** | 20       | $\infty$ | 30       | $\infty$ | 25       |
| **C** | 30       | 30       | $\infty$ | 35       | $\infty$ |
| **D** | $\infty$ | $\infty$ | 35       | $\infty$ | 40       |
| **E** | $\infty$ | 25       | $\infty$ | 40       | $\infty$ |

#### Comparing an adjacency matrix to an adjacency list

| **Adjacency matrix**                                                                            | **Adjacency list**                                                 |
| ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| Suited to dense graphs                                                                          | Suited to sparse graphs                                            |
| Memory inefficient, as all possible edges in the graph are stored, even those that do not exist | Memory efficient, as only edges that exist in the graph are stored |
| Fast to query, edge can be fetched via row and column                                           | Slow to query, each item in a list must be searched sequentially   |

## Trees

A *tree* is a connected, undirected graph with no cycles.

Uses of a tree:
- Creating binary search trees
- Creating minimum spanning trees for a graph
- File systems

### Binary Trees

A *binary tree* is a rooted tree in which each node has at most two child nodes.

They consist of:

| Feature | Description                                                     |
| ------- | --------------------------------------------------------------- |
| Root    | the node that is the starting point of the tree                 |
| Branch  | a node that comes after the root and has one or two child nodes |
| Leaf    | a node that does not have any child nodes                       |

*Binary search trees* can be used to quickly and easily search through data.

The following process is followed when adding a node to a binary tree:
1. Set the current node to the root node
2. Compare the item to the value of the current node: if the item is less than the value, set the current node to the current node's left child, if the item is greater than the value, set hte current node to the current node's right child
3. If that child does not exist, create a new child node with the item's value, otherwise go back to step 2

A binary search tree will always be able to produce a perfectly ordered list of the values.

## Hash tables

A *hash table* is a data structure in which values are indexed with keys, determined by a hashing algorithm. This enables $O(1)$ lookup times.

A *hashing algorithm* takes in a value and returns a hash. A hash is unique to its input and the hash cannot be reversed to find the value. The same hash is always returned for each input.

A hash table stores key-value pairs. When an element is looked up, the key is hashed and the position in the table related to that hash is queried and the value returned. 

Sometimes different values can produce the same hash, this is known as a *hash collision*. This could result in data being overwritten in a poorly designed system.

A simple solution to a collision is storing the value in the next available index.

A better solution is to use *rehashing*, using a new hashing algorithm that will provide more possible values and recalculating the hashes for each existing value.

Uses of hashing algorithms include:
- Checksums
- Storing passwords in databases
- Encryption

## Dictionaries

A *dictionary* is a collection of key-value pairs, in which the value is found by looking up the key.

They are used for information retrieval, such as in frequency analysis or dictionary-based compression.

## Vectors

While *scalars* in mathematics represent a single value, a *vector* has both a magnitude and an associated direction. They are often used to describe a position.

Vectors can be represented in the list representation, such as $[3, 5]$. The first value represents the horizontal position and the second value represents the vertical position.

A two-dimensional vector is known as a *2-vector*. A two-dimensional vector made up of real numbers exists in a two-dimensional space known as $\mathbb{R}2$.

Using function representation, the vector $[3, 5]$ could be written as:

$$\Large 0 \to 3$$
$$\Large 1 \to 5$$

### Vector manipulation