# A Beginner's Guide to Big O Notation

![Big O Notation Chart](https://cdn-media-1.freecodecamp.org/images/1*KfZYFUT2OKfjekJlCeYvuQ.jpeg)

Big O notation is used in Computer Science to describe the performance or complexity of an algorithm. Big O specifically describes the worst-case scenario, and can be used to describe the execution time required or the space used (e.g. in memory or on disk) by an algorithm. 

Big O notation tells us how a certain code is effecient and how scalable is it using a growth rate, in terms of how much operation (time) will a certain algorithm needs with accordance to the data size.below are some common orders of growth along with descriptions and examples where possible.

1. **O(1) --> Constant Time**

Describes an algorithm that will always execute in the same time (or space) regardless of the size of the input data set.

```
def return_first_element(list):
    return list[0]
```

2. **O(n) --> Linear Time**

Describes an algorithm performance will grow linearly and in direct proportion to the size of the input data set.

```
def return_all_element(list):
    for i in list:
        return i
```

3. **O(n^2) --> Quadratic Time**

Describes an algorithm performance will grow is directly proportional to the square of the size of the input data set. This is common with algorithms that involve nested iterations over the data set.

```
def return_pairs(items):
    for i in items:
        for j in items:
            return (i, j)
```

4. **O(2^n)**

Describes an algorithm performance will growth doubles with each addition to the input data set. The growth curve of an O(2^N) function is exponential — starting off very shallow, then rising meteorically. 

```
def fibonacci(n: int):
    if n <= 1:
        return n
    else:
        return fibonacci(n-2) + fibonacci(n-1)
```

5. **Logarithms**

Describes an algorithm performance will growth in a logarithmatic shape, where as the data unput increases the operational time becomes more constant where at the begining it increases dramatically with small amount of data then reaches a point where in is almost constant. An example of Logarithmatic Big O notation is "Binary Search"; where binary search is a technique used to search sorted data sets. It works by selecting the middle element of the data set, essentially the median, and compares it against a target value. If the values match, it will return success. If the target value is higher than the value of the probe element, it will take the upper half of the data set and perform the same operation against it. Likewise, if the target value is lower than the value of the probe element, it will perform the operation against the lower half. It will continue to halve the data set with each iteration until the value has been found or until it can no longer split the data set.

---
---

## Things I want to know more about

- How to optimize the Big O notation of an algorithm using Data Structures.

---
---

## References

[1]  Rob Bell, Jun, 2009, _A beginner's guide to Big O Notation_, rob-bell.com, accessed 05 October 2022, <https://rob-bell.net/2009/06/a-beginners-guide-to-big-o-notation>
