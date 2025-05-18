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

### Queues

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

#### Linear queue

In a *linear queue*, a front pointer is not needed.

The first item in the array always represents the front of the queue. When an item is enqueued, every single item in the queue must be moved forwards in the array. This can be inefficient, especially for larger queues.

#### Circular queue

A *circular queue* uses a front pointer and a rear pointer.

When an item is enqueued, the rear pointer is incremented by one. When an item is dequeued, the front pointer is incremented by one.

When a pointer reaches the end of an array, it wraps back around to the start.

This is much more efficient than a linear queue when the queue is large as it avoids having to move every single item down when a new value is enqueued.

However, it comes with more implementation complexity. A linear queue may be more appropriate for a smaller queue.

#### Priority queue

A *priority queue* enqueues items to the rear of a queue alongside a priority level.

Items with the highest priority are always dequeued first, so when a value is enqueued the new item's priority is compared to every priority in the list, starting at the back.

An example of where this is used is applications on a computer system, which are assigned priorities. Applications being used by the user are prioritised over background applications, allowing for a faster user experience.

### Stacks

A *stack* is another abstract data structure based on an array.

It is a last in, first out (LIFO) data structure as items are pushed and retrieved from the top of the stack.

Common uses of a stack include:
- Reversing a list of values
- Keeping track of and performing undo operations
- A call stack for keeping track of subroutine calls
- Evaluating RPN expressions

A stack can be implemented using a single-dimensional array and an integer variable to point at the top of the stack.

The following actions can be performed on a stack:

| Action     | Description                                                   |
| ---------- | ------------------------------------------------------------- |
| Push       | Add a new item to the top of the stack                        |
| Pop        | Remove one item from the top of the stack                     |
| Peek (Top) | Look at, but don't remove, one item from the top of the stack |
| isEmpty    | Check if the queue is empty                                   |
| isFull     | Check if the queue is full                                    |

### Graphs

A *graph* is an abstract data structure designed to represent more complex relationships between items in datasets.

Uses of graphs include:
- Route finding
- Representing relationships on social networks
- Computer networks
- Project management
- Game theory


