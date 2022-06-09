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
* In ADTs
  - No specification of how ADTs are represented
  - No specification of how the operations are carried out
* The List ADT can be implemented
  - Arrays
  - Or singly linked list
  - Or doubly linked list
* Similarly, Stack ADT and Queue ADT can be implemented using arrays or linked lists
  - We will focus on List ADT
* Two ways to implement a list 
  - Contiguous implementation
    - Contiguous: Elements are next to each other
    - A list implemented using an array is a contiguous list
    - A list implemented using a vector is also a contiguous list
  - Linked implementation
    - Linked list is a list in which each entry contains a pointer giving the location of the next entry
    - Pointer: An object, often a variable, that stores the location (that is the memory address) of some other object
* Which implementation do we use?
  - depends on the predicted usage
    - E.g., can we predict the size of the list?
    - In array implementation: an array has fixed size, so “resizing” is expensive, but access to single element is very fast
      - Suitable for cases when the size is relatively stable and for random access
    - In linked list implementation: size is dynamic, so resizing won’t be a problem, but random access to an element could be expensive: we can only sequentially access along the links
      - Suitable for cases when the size is unstable or unpredictable and for sequential access
  - Let’s look at the detailed implementati
## Contiguous Implementation
* <img width="462" alt="Screen Shot 2022-06-09 at 4 56 29 PM" src="https://user-images.githubusercontent.com/89602311/172952012-b254f551-5ee3-455e-bc22-63b229d0bb9d.png">
* Denote 
  - List_class
    - A name for the generic type: recall the review of function template and class template in the previous lecture
  - void transverse(void (*visit)(List_entry &))
    -  void (*visit)(List_entry &): *visit is a function pointer - address of a function takes a List_entry as input without output (void)
    - Pass the function pointer to another function: leaving details to the clients
  - Error_code
* Insertion method
*<img width="429" alt="Screen Shot 2022-06-09 at 5 10 12 PM" src="https://user-images.githubusercontent.com/89602311/172953719-9ace7263-265b-48e8-ab37-b71afe14e531.png">
* Transversal 
* <img width="424" alt="Screen Shot 2022-06-09 at 5 19 56 PM" src="https://user-images.githubusercontent.com/89602311/172954755-64c6c9eb-a764-4432-b3a6-f5254fc3df89.png">
* Discussion 
  - In processing a contiguous list with n entries:
    - Insert and remove operate in time approximately proportional to n 
        -  (0 + 1 + 2 + ... + (n-1) + n) / (n + 1)
     - How to resize the list if count reach its capacity?
        - E.g., double the value of max_list, and copy all the values
        - Very expensive
     - List, clear, empty, full, sizez, replace and retrieve operate in constant time
## Singly Linked Implementation
* <img width="383" alt="Screen Shot 2022-06-09 at 5 25 44 PM" src="https://user-images.githubusercontent.com/89602311/172955405-f67b5d50-6cf8-4a76-812e-c96cfbe60b56.png">
* How to create the nodes?
* How to link them together?

