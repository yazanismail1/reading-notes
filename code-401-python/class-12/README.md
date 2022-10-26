# Stack and Queue

Stacks and Queues are types of data structure in which data are stored in a specific way.

Stack is a container of objects that are inserted and removed according to the last-in first-out (LIFO) principle.

Queue is a container of objects (a linear collection) that are inserted and removed according to the first-in first-out (FIFO) principle.

## Stack

![](https://cdn.programiz.com/sites/tutorial2program/files/stack.png)

In the pushdown stacks only two operations are allowed: push the item into the stack, and pop the item out of the stack. A stack is a limited access data structure - elements can be added and removed from the stack only at the top. push adds an item to the top of the stack, pop removes the item from the top. A helpful analogy is to think of a stack of books; you can remove only the top book, also you can add a new book on the top.

- **Basic Stack Operation**
    - Push: Add an element to the top of a stack

    - Pop: Remove an element from the top of a stack

    - IsEmpty: Check if the stack is empty

    - IsFull: Check if the stack is full

    - Peek: Get the value of the top element without removing it

- **Stack Time Complexity**:

    -Constant Time O(1)

- **Application of Stack Data Structure**

    - T**o reverse a word:** Put all the letters in a stack and pop them out. Because of the LIFO order of stack, you will get the letters in reverse order.
    
    - **In compilers:** Compilers use the stack to calculate the value of expressions like `2 + 4 / 5 * (7 - 9)` by converting the expression to prefix or postfix form.

    - **In browsers:** The back button in a browser saves all the URLs you have visited previously in a stack. Each time you visit a new page, it is added on top of the stack. When you press the back button, the current URL is removed from the stack, and the previous URL is accessed.

- **Implementing a Stack**

```
# Creating a stack
def create_stack():
    stack = []
    return stack

# Creating an empty stack
def check_empty(stack):
    return len(stack) == 0

# Adding items into the stack
def push(stack, item):
    stack.append(item)
    print("pushed item: " + item)

# Removing an element from the stack
def pop(stack):
    if (check_empty(stack)):
        return "stack is empty"

    return stack.pop()

stack = create_stack()
push(stack, str(1))
push(stack, str(2))
push(stack, str(3))
push(stack, str(4))
print("popped item: " + pop(stack))
print("stack after popping an element: " + str(stack))
```

## Queue

![](https://cdn.programiz.com/sites/tutorial2program/files/queue.png)

An excellent example of a queue is a line of students in the food court of the UC. New additions to a line made to the back of the queue, while removal (or serving) happens in the front. In the queue only two operations are allowed enqueue and dequeue. Enqueue means to insert an item into the back of the queue, dequeue means removing the front item. The picture demonstrates the FIFO access. The difference between stacks and queues is in removing. In a stack we remove the item the most recently added; in a queue, we remove the item the least recently added.

- **Basic Queue Operation**
    - Enqueue: Add an element to the end of the queue

    - Dequeue: Remove an element from the front of the queue

    - IsEmpty: Check if the queue is empty

    - IsFull: Check if the queue is full

    - Peek: Get the value of the front of the queue without removing it


- **Complexity Analysis**

    The complexity of enqueue and dequeue operations in a queue using an array is O(1). If you use pop(N) in python code, then the complexity might be O(n) depending on the position of the item to be popped.

- **Application of Queue Data Structure**

    - CPU scheduling, Disk Scheduling

    - When data is transferred asynchronously between two processes.The queue is used for synchronization. For example: IO Buffers, pipes, file IO, etc

    - Handling of interrupts in real-time systems.

    - Call Center phone systems use Queues to hold people calling them in order.

- **Type of Queues**

    - Types of Queue
    
    - Circular Queue

    - Deque Data Structure
    
    - Priority Queue

- **Implementing a Queue**

```
class Queue:

    def __init__(self):
        self.queue = []

    # Add an element
    def enqueue(self, item):
        self.queue.append(item)

    # Remove an element
    def dequeue(self):
        if len(self.queue) < 1:
            return None
        return self.queue.pop(0)

    # Display  the queue
    def display(self):
        print(self.queue)

    def size(self):
        return len(self.queue)

q = Queue()
q.enqueue(1)
q.enqueue(2)
q.enqueue(3)
q.enqueue(4)
q.enqueue(5)

q.display()

q.dequeue()

print("After removing an element")
q.display()
```

---

## Things I want to know more about

- Data Structure

---

## References

[1] <https://everythingcomputerscience.com/discrete_mathematics/Stacks_and_Queues.html>

[2] <https://www.programiz.com/dsa/queue>

[3] <https://www.programiz.com/dsa/stack>


