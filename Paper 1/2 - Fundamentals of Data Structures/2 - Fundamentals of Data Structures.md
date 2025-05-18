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
| Enqueue    | Push a new value to the end of the queue                        |
| Dequeue    | Remove one item from the front of the queue                     |
| Peek (Top) | Look at, but don't remove, one time from the front of the queue |
| isEmpty    | Check if the queue is empy                                      |
| isFull     | Check if the queue is full                                      |
The last two actions are needed as the program could crash if an attempt is made to enqueue an item when the queue is full, or dequeue an item when the queue is empty.

There are several types of queue:
- Linear queue
- Circular queue
- Priority queue

### Linear queues

In a linear queue, a front pointer is not needed.

The first item in the array always represents the front of the queue. When an item is enqueued, every single item in the queue must be moved forwards in the array. This can be inefficient, especially for larger queues.

### Circular queues

A circular queue uses a front pointer and a rear pointer.

When an item is 





