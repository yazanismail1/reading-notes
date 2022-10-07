# Reading and Writing Files in Python

A file is a contiguous set of bytes used to store data. This data is organized in a specific format and can be anything as simple as a text file, csv file or as complicated as a program executable.

**Files Structure**

- Header: metadata about the contents of the file (file name, size, type, and so on)
- Data: contents of the file as written by the creator or editor
- End of file (EOF): special character that indicates the end of the file

**File Path**

When you access a file on an operating system, a file path is required. The file path is a string that represents the location of a file. It’s broken up into three major parts:

- Folder Path: the file folder location on the file system where subsequent folders are separated by a forward slash / (Unix) or backslash \ (Windows)
- File Name: the actual name of the file
- Extension: the end of the file path pre-pended with a period (.) used to indicate the file type

**WHAT CAN BE DONE WITH FILES IN PYTHON | Selected Examples**

**Opening and Closing a File in Python**

Python has a built-in method called open() that allows you to open file, there are two ways to open file in Python:

1. Assignment -->

```
file = open('example.txt')
```

Opening a file in this way you must close the file manually after executing you code using;

```
file.close()
```

2. with open -->

```
with open("example.txt") as file:
    # do something...
```  

Opening a file in this way, it will ensure that the file is closed as soon as the block of code indented is executed.

When a file is opened, by defualt it is opened with as read; to change it:

```
## Opening a file in a read only mode: ##

with open("example.txt", "r") as file:
    # do something...

## Opening a file in a write only mode: ##

with open("example.txt", "w") as file:
    # do something...

## Opening a file in a binary mode (read/write): ##

- Used when you want to work with byte files, all of the same methods for the file object apply. However, each of the methods expect and return a bytes object instead:

with open("example.txt", "rb") as file:
    # do something...

with open("example.txt", "wb") as file:
    # do something...
```
**Operations can be done on a file**

- Read and print out the whole document.

```
with open('example.txt', r) as f:
    print(f.read()) 

>> Example Output:
Hi there,
this is a test file to test the file reading in python.
this is so much fun.
have a nice day.
bye..
```

- Readline and print.

```
# Reading and printing only the first line 

with open('example.txt', r) as f:
    print(f.readline()) 

>> Example Output:
Hi there,
---------------------------------
# Reading and printing only the first two lines 

with open('example.txt', r) as f:
    print(f.readline())
    print(f.readline()) 

>> Example Output:
Hi there,
this is a test file to test the file reading in python.
---------------------------------
# Reading and printing only the five char in the first line 

with open('example.txt', r) as f:
    print(f.readline(5))

>> Example Output:
Hi th
---------------------------------
# Reading and printing only the five char in the first line, then breaks to a new line and continue reading from the place it stopped until the end of the line "even if it is less than 5 chars".

with open('example.txt', r) as f:
    print(f.readline(5))
    print(f.readline(5))

>> Example Output:
Hi th
ere,
```

- Readlines and print.

```
# It returnes the whole document in a list

with open('example.txt', r) as f:
    print(f.readlines()) 

>> Example Output:
['Hi there,\n', 'this is a test file to test the file reading in python.\n', 'this is so much fun.\n', 'have a nice day.\n', 'bye..']

with open('example.txt', r) as f:
    print(list(f)) 

>> Example Output:
['Hi there,\n', 'this is a test file to test the file reading in python.\n', 'this is so much fun.\n', 'have a nice day.\n', 'bye..']
```

- ReIterating over each line in the file

```
with open('example.txt', 'r') as reader:
    # Read and print the entire file line by line
    line = reader.readline()
    while line != '':  # The EOF char is an empty string
        print(line, end='')
           line = reader.readline()

>> Example Output:
Hi there,
this is a test file to test the file reading in python.
this is so much fun.
have a nice day.
bye..
---------------------------------------------------------
with open('example.txt', 'r') as reader:
    for line in reader.readlines():
        print(line, end='')

>> Example Output:
Hi there,
this is a test file to test the file reading in python.
this is so much fun.
have a nice day.
bye..
---------------------------------------------------------
with open('example.txt', 'r') as reader:
    # Read and print the entire file line by line
    for line in reader:
        print(line, end='')

>> Example Output:
Hi there,
this is a test file to test the file reading in python.
this is so much fun.
have a nice day.
bye..
```

- Writing to a file

```
with open('example.txt', 'a') as a_writer:
    a_writer.write('\nI'm newly added')

with open('example.txt', 'r') as f:
    print(f.read()) 

>> Example Output:
Hi there,
this is a test file to test the file reading in python.
this is so much fun.
have a nice day.
bye..
I'm newly added
```

- Working with two file at the same time

```
d_path = 'dog_breeds.txt'
d_r_path = 'dog_breeds_reversed.txt'
with open(d_path, 'r') as reader, open(d_r_path, 'w') as writer:
    dog_breeds = reader.readlines()
    writer.writelines(reversed(dog_breeds))
```
---
---

# Python Exceptions : An Introduction

In simple words, it is a way of writing your code so if encountered a spicific error it is handled without breaking the code.

**Exceptions vs Syntax Errors**

Important Note: You can't handle syntax error..., exception errors are when a code is syntactically correct but result in an error.

```
print( 0 / 0 ))

>> Output:
  File "<stdin>", line 1
    print( 0 / 0 ))
                  ^
SyntaxError: invalid syntax

## The arrow indicates where the parser ran into the syntax error. In this example, there was one bracket too many. Remove it and run your code again:
```
```
>>> print( 0 / 0)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: integer division or modulo by zero

## This time, you ran into an exception error. This type of error occurs whenever syntactically correct Python code results in an error. The last line of the message indicated what type of exception error you ran into.

Instead of showing the message exception error, Python details what type of exception error was encountered. In this case, it was a ZeroDivisionError.
```

**Raising an Exception**

- If you want to throw an error when a certain condition occurs using raise, you could go about it like this:

```
x = 10
if x > 5:
    raise Exception('x should not exceed 5. The value of x was: {}'.format(x))
```

When you run this code, the output will be the following:

```
Traceback (most recent call last):
  File "<input>", line 4, in <module>
Exception: x should not exceed 5. The value of x was: 10
```

**The AssertionError Exception**

Instead of waiting for a program to crash midway, you can also start by making an assertion in Python. We assert that a certain condition is met. If this condition turns out to be True, then that is excellent! The program can continue. If the condition turns out to be False, you can have the program throw an AssertionError exception.

```
import sys
assert ('linux' in sys.platform), "This code runs on Linux only."
```

If you run this code on a Linux machine, the assertion passes. If you were to run this code on a Windows machine, the outcome of the assertion would be False and the result would be the following:

```
Traceback (most recent call last):
  File "<input>", line 2, in <module>
AssertionError: This code runs on Linux only.
```

**The try and except Block: Handling Exceptions**

The try and except block in Python is used to catch and handle exceptions. Python executes code following the try statement as a “normal” part of the program. The code that follows the except statement is the program’s response to any exceptions in the preceding try clause.

- try & except Clauses

```
while j < len(x):
    try:
        if dict[x[j]] >= dict[x[j+1]]:
            num += dict[x[j]]
        else:
            num = num + (dict[x[j+1]] - dict[x[j]] )
            j += 1
    except IndexError:
        if dict[x[j-1]] >= dict[x[j]]:
                num += dict[x[j]]
    j += 1

        return(num)
```
In the previous example, it is likely that we will get an index error as we will are looping over a list and we will eventually reach to the end of it and as out consition says j + 1, we will get an error, out of range (IndexError), in this case we don't want our code to break, instead we should do another type of operation...

- else Clause

```
try:
    linux_interaction()
except AssertionError as error:
    print(error)
else:
    print('Executing the else clause.')
```

If you were to run this code on a Linux system, the output would be the following:

```
Doing something.
Executing the else clause.
```

- finally Clause

The finally clause will always run, even if the code raise an error or runs smoothely

```
try:
    linux_interaction()
except AssertionError as error:
    print(error)
else:
    try:
        with open('file.log') as file:
            read_data = file.read()
    except FileNotFoundError as fnf_error:
        print(fnf_error)
finally:
    print('Cleaning up, irrespective of any exceptions.')
```

In the previous code, everything in the finally clause will be executed. It does not matter if you encounter an exception somewhere in the try or else clauses. Running the previous code on a Windows machine would output the following:

```
Function can only run on Linux systems.
Cleaning up, irrespective of any exceptions.
```


---
---

## Things I want to know more about

- How to does python work behind the sences to open a file, read from it or write to it.

---
---

## References

[1]  James Mertz, Feb 20, 2019, _Reading and Writing Files in Python (Guide)_, realpython.com, accessed 07 October 2022, <https://realpython.com/read-write-files-python/>

[2]  Said van de Klundert, Apr 30, 2018, _Python Exceptions: An Introduction_, realpython.com, accessed 07 October 2022, <https://realpython.com/python-exceptions/>