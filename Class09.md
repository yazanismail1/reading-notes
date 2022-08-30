# Functional Programming

> When writing a complex code it is better to split it into modules, it is easier to debug and more readable and this goes for functions also, it is better to have many functions that each do one thing. 

---
---

**What is functional programming?**

means using functions to the best effect for creating clean and maintainable software.

**What is a pure function and how do we know if something is a pure function?**

A pure function is a function which, given the same input, will always return the same output and produces no side effects

**What are the benefits of a pure function?**

Pure functions are much easier to read and reason about. All relevant inputs and dependencies are provided as parameters, so no effects are observed that alter variables outside of the set of inputs. This means that we can quickly understand a function and its dependencies, just by reading the function's declaration.

**What is immutability?**

Immutable data cannot change its structure or the data in it.

**What is Referential transparency?**

In computer science, referential transparency and referential opacity are properties of parts of computer programs. An expression is called referentially transparent if it can be replaced with its corresponding value without changing the program's behavior.

**What is a module?**

A module in JavaScript is just a file containing related code.

**What does the word ‘require’ do?**

The require() method is used to load and cache JavaScript modules. So, if you want to load a local, relative JavaScript module into a Node. js application, you can simply use the require() method. It is like import and export.

**How do we bring another module into the file the we are working in?**

using require('path') in the place we want to use it and in the module export it using, module.exports = ####.

**What do we have to do to make a module available?**

Export the module and require it in the place you want to use.

---
---

## Things I want to know more about

- webpack

 ---

## References

[1] TK, Nov 25, 2018, _Concepts of Functional Programming in Javascript_, medium.com, accessed 30 August 2022, <https://medium.com/the-renaissance-developer/concepts-of-functional-programming-in-javascript-6bc84220d2aa>

[2] The Net Ninja, 2016, _Node JS Tutorial for Beginners #6 - Modules and require()_, youtube.com, accessed 30 August 2022, <https://www.youtube.com/watch?v=xHLd36QoS4k&ab_channel=TheNetNinja>
