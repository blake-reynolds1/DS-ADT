# Abstract Data Types
## Outline
* ADT concept
* Stack, Queue, List
* Contiguous Implementation of List
* Linked Implementation of List
## Introduction
* In C++, when declare a variable
  - we need to specify the data type
  - e.g., int n, bool b, for basic types
  - e.g., Stack<int> stack, for structured types
* For structured types
  - There could be different implementations
    - But share the same data fields and operations (same interface) ---- decided by the nature of the structure
  - The clients don't need to know the detailed implementations
    - Do you need to know the details of cout in iostream?
  - Shared sense of these structures: standard way to use
* Abstract Data Types (ADT)
  - Abstract
    - Implementation details are not specified by the data type
  - The definition of any ADT involves two parts
    - A description of the nature of the ADT, e.g., the way in which the components of the ADT are related to each other
    - A statement of the operations that can be performed on values of the ADT
## ADT of Stacks
* A Stack contains elements of the same type T arranged in sequential order
* All operations take place at a single end that is top of the stack
* Following operations can be performed:
  - Create the stack, leaving it empty
  - Test whether the stack is Empty
  - Push a new entry onto the top of the stack, provided the stack is not full
  - Pop the entry off the top of the stack, provided the stack is not empty
  - Retrieve the Top entry from the stack, provided the stack is not empty
## ADT of Queues
* A Queue contains elements of the same type T arranged in sequential order
* Operations take place at both ends, insertion is done at the end and deletion is done at the front
* Following operations can be performed
  - Create the queue, leaving it empty
  - Test whether the stack is Empty
  - Enqueue: insert a new entry onto the end of the queue, provided the queue is not full
  - Dequeue: remove the entry off the beginning of the queue, provided the queue is not empty
  - Retrieve the first entry (at the beginning) from the queue, provided the queue is not empty
## ADT of Lists
* A list of elements of type T is a finite sequence of elements of T with the following operations:
  - Construct the list, leaving it empty.
  - Determine whether the list is empty or not.
  - Determine whether the list is full or not.
  - Find the size of the list.
  - Clear the list to make it empty.
  - Insert an entry at a specified position of the list.
  - Remove an entry from a specified position in the list.
  - Retrieve the entry from a specified position in the list.
  - Replace the entry at a specified position in the list.
  - Traverse the list, performing a given operation on each entry.
## Implementation Issues
