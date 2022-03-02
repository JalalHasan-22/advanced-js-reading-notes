# Linked lists

linked lists are a sort of data structure, data structures can be thought of as data containers that sorts different types of values, for example, a variable or an array are a form of data structures.

We have two types of data structures, a. **linear data structures** b. **non-linear data structures**.
in linear data structures (such as an array), we have to pass by each value in sequence until we reach the last entry, whereas in non-linear data structures (such as a tree) we can start at random point as our entry and traverse in different paths to reach our target entry.

Linked lists are somehow similar to arrays, but one of the main differences is that if we have an array of 10 integers; the array will reserve a 10 contiguous locations in the memory to store the value of it's entries. but in the linked lists things are different, linked lists contains nodes, where each node has a pointer to the next node in the list, the nodes can be stored in random locations in the memory as we already have a reference pointer that tells us where is the next node stored in the memory.

The first node of the list is called head and the last node will be pointing to a null value indicating the end of the list.

We have three types of linked lists:

1. Singly linked lists: which is the type that we aforementioned talked about.
2. Doubly linked lists: in doubly linked lists, we have two reference pointers, one pointing to the next node as usual, the next reference will be pointing to the previous node, which means that every node knows what node is preceding and what node comes next, this enables us to traverse the list bi-directionaly, forward and backwards.
3. Circular linked lists: in this type of lists, it is the same as the singly linked one; except that the last node (we call it the tail) instead of pointing to null; it will be pointing to the first node in the list (the head).

### differences between array and linked list:

| Array                                                          | Linked List                                                      |
| -------------------------------------------------------------- | ---------------------------------------------------------------- |
| takes a lot of time to insert or delelte                       | fast to insert or delete entries                                 |
| searching is fast                                              | Searching is slow                                                |
| static size (allocated at the time of creation)                | Dynamic in size (can grow or shrink easily)                      |
| Allocates a contigueous chunck of data at the time of creation | Non-contiguous locations, only allocates as much space as needed |
| Helpful if you know the size of the of the list                | helpful if the size is unknown                                   |

#### Resources

[Linked lists part |](https://medium.com/basecs/whats-a-linked-list-anyway-part-1-d8b7e6508b9d)

[linked lists part ||](https://medium.com/basecs/whats-a-linked-list-anyway-part-2-131d96f71996)
