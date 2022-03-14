# Stacks and Queues

1. # What is a Stack ?

A stack is a datastructure that is formed by multiple nodes, where each node references the next node, but unlike the doubly-linked list; it can't reference the previous node.

common methodologies for stack are:

- Push - Nodes or items that are put into the stack are pushed
- Pop - Nodes or items that are removed from the stack are popped. When you attempt to pop an empty stack an exception will be raised.
- Top - This is the top of the stack, same as the head in linked lists, only difference that the top will be the last added node.
- Peek - When you peek you will view the value of the top Node in the stack. When you attempt to peek an empty stack an exception will be raised.
- IsEmpty - returns true when stack is empty otherwise returns false.

Stacks behave by the following concepts:

- FILO (First In Last Out)
  This means that the first item added in the stack will be the last item popped out of the stack.

- LIFO (Last In First Out)
  This means that the last item added to the stack will be the first item popped out of the stack.

### Push O(1)

Pushing a Node onto a stack will always be an O(1) operation. This is because it takes the same amount of time no matter how many Nodes (n) you have in the stack.

When adding a Node, you push it into the stack by assigning it as the new top, with its next property equal to the original top.

### Pop O(1)

Popping a Node off a stack is the action of removing a Node from the top. When conducting a pop, the top Node will be re-assigned to the Node that lives below and the top Node is returned to the user.

Typically, you would check isEmpty before conducting a pop. This will ensure that an exception is not raised. Alternately, you can wrap the call in a try/catch block.

### Peek O(1)

When conducting a peek, you will only be inspecting the top Node of the stack.

Typically, you would check isEmpty before conducting a peek. This will ensure that an exception is not raised. Alternately, you can wrap the call in a try/catch block.

Here is the pseudocode for a peek

ALGORITHM peek()<br>
// INPUT <-- none<br>
// OUTPUT <-- value of top Node in stack<br>
// EXCEPTION if stack is empty<br>
return top.value

### IsEmpty O(1)

Here is the pseudocode for isEmpty

ALGORITHM isEmpty()<br>
// INPUT <-- none<br>
// OUTPUT <-- boolean<br>

return top = NULL

2. # What is a Queue?

Common terminology for a queue is

- Enqueue - Nodes or items that are added to the queue.
- Dequeue - Nodes or items that are removed from the queue. If called when the queue is empty an exception will be raised.
- Front - This is the front/first Node of the queue.
- Rear - This is the rear/last Node of the queue.
- Peek - When you peek you will view the value of the front Node in the queue. If called when the queue is empty an exception will be raised.
- IsEmpty - returns true when queue is empty otherwise returns false.

Queues follow these concepts:

FIFO
First In First Out

This means that the first item in the queue will be the first item out of the queue.

LILO
Last In Last Out

This means that the last item in the queue will be the last item out of the queue.

### Enqueue O(1)

When you add an item to a queue, you use the enqueue action. This is done with an O(1) operation in time because it does not matter how many other items live in the queue (n); it takes the same amount of time to perform the operation.

Here is the pseudocode for the enqueue method:

ALGORITHM enqueue(value)<rb>
// INPUT <-- value to add to queue (will be wrapped in Node internally)<br>
// OUTPUT <-- none<br>
node = new Node(value)<br>
rear.next <-- node<br>
rear <-- node

### Dequeue O(1)

When you remove an item from a queue, you use the dequeue action. This is done with an O(1) operation in time because it doesn’t matter how many other items are in the queue, you are always just removing the front Node of the queue.

Typically, you would check isEmpty before conducting a dequeue. This will ensure that an exception is not raised. Alternately, you can wrap the call in a try/catch block.

Here is the pseudocode for the dequeue method:

ALGORITHM dequeue()<br>
// INPUT <-- none<br>
// OUTPUT <-- value of the removed Node<br>
// EXCEPTION if queue is empty<br>

Node temp <-- front<br>
front <-- front.next<br>
temp.next <-- null<br>

return temp.value

### Peek O(1)

When conducting a peek, you will only be inspecting the front Node of the queue.

Typically, you want to check isEmpty before conducting a peek. This will ensure that an exception is not raised. Alternately, you can wrap the call in a try/catch block.

Here is the pseudocode for a peek

ALGORITHM peek()<br>
// INPUT <-- none<br>
// OUTPUT <-- value of the front Node in Queue<br>
// EXCEPTION if Queue is empty<br>

return front.value

### IsEmpty O(1)

Here is the pseudocode for isEmpty

ALGORITHM isEmpty()<br>
// INPUT <-- none<br>
// OUTPUT <-- boolean<br>

return front = NULL
