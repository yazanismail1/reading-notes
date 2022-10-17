# Linkedlist

A linked list is a sequence of data structures, which are connected together via links.

**Advantages of Linked Lists**

- Because of the chain-like system of linked lists, you can add and remove elements quickly. This also doesn't require reorganizing the data structure unlike arrays or lists. Linear data structures are often easier to implement using linked lists.

- Linked lists also don't require a fixed size or initial size due to their chainlike structure.

**Disadvantages of a Linked Lists**

- More memory is required when compared to an array. This is because you need a pointer (which takes up its own memory) to point you to the next element.

- Search operations on a linked list are very slow. Unlike an array, you don't have the option of random access.

**When Should You Use a Linked List?**

You should use a linked list over an array when:

- You don't know how many items will be in the list (that is one of the advantages - ease of adding items).

- You don't need random access to any elements (unlike an array, you cannot access an element at a particular index in a linked list).

- You want to be able to insert items in the middle of the list.

- You need constant time insertion/deletion from the list (unlike an array, you don't have to shift every other item in the list first).

Linked List is a sequence of links which contains items. Each link contains a connection to another link. Linked list is the second most-used data structure after array.

- **Link** − Each link of a linked list can store a data called an element.

- **Next** − Each link of a linked list contains a link to the next link called Next.

- **LinkedList** − A Linked List contains the connection link to the first link called First.

![Linked List](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list.jpg)

- Linked List contains a link element called first.

- Each link carries a data field(s) and a link field called next.

- Each link is linked with its next link using its next link.

- Last link carries a link as null to mark the end of the list.

**Types of Linked List**

- Simple Linked List − Item navigation is forward only.

- Doubly Linked List − Items can be navigated forward and backward.

- Circular Linked List − Last item contains link of the first element as next and the first element has a link to the last element as previous.

**Basic Operations**

- Insertion − Adds an element at the beginning of the list.

- Deletion − Deletes an element at the beginning of the list.

- Display − Displays the complete list.

- Search − Searches an element using the given key.

- Delete − Deletes an element using the given key.

**Insertion Operation**

![Linked List](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_insertion_0.jpg)

![Linked List](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_insertion_1.jpg)

![Linked List](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_insertion_3.jpg)

**Deletion Operation**

![Linked List](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_deletion_0.jpg)

![Linked List](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_deletion_1.jpg)

![Linked List](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_deletion_2.jpg)

![Linked List](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_deletion_3.jpg)

**Reverse Operation**

![Linked List](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_reverse_0.jpg)

![Linked List](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_reverse_1.jpg)

![Linked List](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_reverse_2.jpg)

![Linked List](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_reverse_3.jpg)

![Linked List](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_reverse_4.jpg)

---
---

## Things I want to know more about

- DSA

---
---

## References

[1] Tutorialspoint, accessed 17 October 2022, <https://www.tutorialspoint.com/data_structures_algorithms/linked_list_algorithms.htm#>

[2] Fakorede Damilola, Sep 22, 2022 _Linked Lists in Python – Explained with Examples_, accessed 17 October 2022, <https://www.freecodecamp.org/news/introduction-to-linked-lists-in-python/#:~:text=Linked%20Lists%20are%20a%20data,list%20is%20called%20a%20node.>
