# Intro to OOP

Object-oriented programming (OOP) is a computer programming model that organizes software design around data, or objects, rather than functions and logic.

Objects are an encapsulation of variables and functions into a single entity. Objects get their variables and functions from classes. Classes are essentially a template to create your objects.

**Why classes?**

You can create multiple different objects that are of the same class(have the same variables and functions defined). However, each object contains independent copies of the variables defined in the class. For instance, if we were to define another object with the "MyClass" class and then change the string in the variable above:

```
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()
myobjecty = MyClass()

myobjecty.variable = "yackity"

# Then print out both values
print(myobjectx.variable)
print(myobjecty.variable)

>> output:
blah
yackity
```

To access a function inside of an object you use notation similar to accessing a variable:

```
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

myobjectx.function()

>> output:
This is a message inside the class.
```

**What is init() in classes and why it is used?**

The __init__() function, is a special function that is called when the class is being initiated. It's used for assigning values in a class.


```
class NumberHolder:

   def __init__(self, number):
       self.number = number
```

---
---

# Thinking Recursively in Python

Problems (in life and also in computer science) can often seem big and scary. But if we keep chipping away at them, more often than not we can break them down into smaller chunks trivial enough to solve. This is the essence of thinking recursively.

A recursive function is a function defined in terms of itself via self-referential expressions.

This means that the function will continue to call itself and repeat its behavior until some condition is met to return a result. All recursive functions share a common structure made up of two parts: base case and recursive case.

```
def fibonacci(n: int):
    if n <= 1:
        return n
    else:
        return fibonacci(n-2) + fibonacci(n-1)
```

When dealing with recursive functions, keep in mind that each recursive call has its own execution context, so to maintain state during recursion you have to either:

- Thread the state through each recursive call so that the current state is part of the current call’s execution context.

- Keep the state in global scope.

**Recursive Data Structures in Python**

A data structure is recursive if it can be deﬁned in terms of a smaller version of itself. A list is an example of a recursive data structure.

**Notes About Recursion**

1. Python doesn’t have support for tail-call elimination. As a result, you can cause a stack overflow if you end up using more stack frames than the default call stack depth => 3000.

2. Python’s mutable data structures don’t support structural sharing, so treating them like immutable data structures is going to negatively affect your space and GC (garbage collection) efficiency because you are going to end up unnecessarily copying a lot of mutable objects.

---
---

# Python Testing with pytest: Fixtures and Coverage

**FIXTURES**

Fixtures are a combination of the pytest.fixture decorator, along with a function definition. For example, say you have a file that returns a list of lines from a file, in which each line is reversed:

```
def reverse_lines(f):
   return [one_line.rstrip()[::-1] + '\n'
           for one_line in f]
```

If you're going to test this function, you'll need to pass it a file-like object. But rather than defining global variables in your test file, you can create a fixture that'll provide your test with the appropriate object at the right time.

```
@pytest.fixture
def simple_file():
   return StringIO('\n'.join(['abc', 'def', 'ghi', 'jkl']))
```

**Why fixtures?**

- You can call it inside another test.

```
def test_reverse_lines(simple_file):
   assert reverse_lines(simple_file) == ['cba\n', 'fed\n',
 ↪'ihg\n', 'lkj\n']
```

- can be called more than once for multiple purposes.

```
@pytest.fixture(scope='module')
def simple_file():
   return StringIO('\n'.join(['abc', 'def', 'ghi', 'jkl']))
```

**COVERAGE**

Is a process to check weather the tests covers the whole aspects of a function.

```
def add_two(num):
    return num + 2

def test_add_two():
    assert add_two(2) == 4
```
in the previous example if the user enters a string the code will crash, however according to the test the function works 100%.

**How to include coverage?**

It turns out that there's a package called pytest-cov on PyPI that you can download and install. Once that's done, you can invoke pytest with the --cov option. If you don't say anything more than that, you'll get a coverage report for every part of the Python library that your program used.

```
pytest --cov=mymul
```

to retrieve the coverage test in a human readable format.

```
coverage html
```

```
def add_two(num):
    try:
        return num + 2
    expect:
        return ("Kindly enter a number")

def test_add_two():
    assert add_two(2) == 4
```

Now the function is working correctly and catches errors and the coverage is 100% now.

---
---

## Things I want to know more about

- OOP

---
---

## References

[1]  _Classes and Objects_, learnpython.org, accessed 10 October 2022, <https://www.learnpython.org/en/Classes_and_Objects>

[2]  Abhirag Awasthi, May 27, 2018, _Thinking Recursively in Python_, realpython.com, accessed 10 October 2022, <https://realpython.com/python-thinking-recursively/>

[3]   Reuven M. Lerner, Jan 14, 2019, _Python Testing with pytest: Fixtures and Coverage_, linuxjournal.com, accessed 10 October 2022, <https://www.linuxjournal.com/content/python-testing-pytest-fixtures-and-coverage>