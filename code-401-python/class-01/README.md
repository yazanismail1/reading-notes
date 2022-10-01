# Intro to Big O Notation 

**Big O Notation** is a way of evaluating how effecient something is/how will does an algorithm and/or data structure perform in terms of time and space it needs to complete a certain thing.

**Types of Big O Notation:** 

![Stack Example](https://cdn-media-1.freecodecamp.org/images/1*KfZYFUT2OKfjekJlCeYvuQ.jpeg)


One of the best Big O complexity is having O(1) aka constant time complexity to an algorithm and/or data structure. i.e. Adding a node to the begining of a linked list.

One of the worst Big O complexity is having O(n^2) aka quadratic time complexity to an algorithm and/or data structure. 

**What is the use of the Big O Notation?**

Evaluating data structure based on what we want to do and choose a data structure. i.e. Logging user history, the best thing is to use a stack as it is best to add to the top and we will always add to the top.

---
---

# Names and Values in Python

1. **Names in Python are reassigned independently**, this means if you assign x to 12 and y to x, this means you assigned y to 12 as names can only be assigned to values to names, hence if you changed x to 24, y will still be assigned to 12.

2. **Assignments never copies data**, as in names if you assign x to a list of [1, 2, 3] and assigned y to x, this means you assigned y to the same [1, 2, 3] list, hence, if x list is **modified** not **reassigned** to [1, 2, 3, 4] y is also will recieve the changes as there were never an individual list for y.

3. **Mutable Aliasing**, lists have methods on them that when called they are modified in-place, however, strings, int, floats and tuples have no methods on them, making them immutable, so when saying x = "Hello", and y = x, then modifying x = x + "there", you are making a new variable, hence, y will remain hello.

4. **Refrences can be more than names**, it can be Object attributes, list elements and dictionary keys and values, anything on the left side of an operation is considered an assignment.

5. **Names has no type but a scope**, you can assign x to an int, then to a float and after that to a string. However, they do have a scope, they come and go with a function for example.

6. **Values have no scope but a type**, unlike Names, values to have a type, it could be an int, float or a string, but no scope.

7. Python is neither "Call By value" nor "Call By Reference", it's "Call by Assignment"!

---

## Things I want to know more about

- How to Evaluate algorithms and data structures.
- How does Python work under the hood.
 ---

## References

[1]  Vaidehi joshi and Saron Yitbarek, Nov 29, 2017, _A friendly intro to Big O Notation_, codenewbie.org, accessed 01 October 2022, <https://www.codenewbie.org/basecs/8>

[2]  Paul Rail, Jun 11, 2018, _All you need to know about “Big O Notation” to crack your next coding interview_, freecodecamp.org, accessed 01 October 2022, <https://www.freecodecamp.org/news/all-you-need-to-know-about-big-o-notation-to-crack-your-next-coding-interview-9d575e7eec4/>

[3]  Ned Batchelder, Apr 11, 2015, _Ned Batchelder - Facts and Myths about Python names and values - PyCon 2015_, youtube.com, accessed 01 October 2022, <https://www.youtube.com/watch?v=_AEJHKGk9ns>
