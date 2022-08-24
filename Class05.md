# Putting it all together

> Understanding the concepts and developing a mindset is the most important thing to be a fully fledged programmer, writing the code without fully understanding the concepts will result in an unreadable, complex code.

---
---

**What is the single responsibility principle and how does it apply to components?**

It mans that each component should be responsible for doing only one thing same as functions or objects.

**What does it mean to build a ‘static’ version of your application?**

It means that it displays the UI but it is not interactive.

**Once you have a static application, what do you need to add?**

We need to add functionality by passing states.

**What are the three questions you can ask to determine if something is state?**

- Is it passed in from a parent via props? If so, it probably isn’t state.  
- Does it remain unchanged over time? If so, it probably isn’t state.  
- Can you compute it based on any other state or props in your component? If so, it isn’t state.

**How can you identify where state needs to live?**

- Identify every component that renders something based on that state.
- Find a common owner component (a single component above all the components that need the state in the hierarchy).
- Either the common owner or another component higher up in the hierarchy should own the state.
- If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.

**What is a “higher-order function”?**

Functions that operate on other functions, either by taking them as arguments or by returning them.

**Explore the `greaterThan` function as defined in the reading. In your own words, what is line 2 of this function doing?**

It returns a new function if the arg passed to the function in smaller than the arg in the to be returned function.

**Explain how either map or reduce operates, with regards to higher-order functions.**
  
`.map()` loops through an array and take a `callBackFn` as an argument to execute something or mutable the data in the original array. It returns a new array of the returned data from the `callBackFn` without modifying the original array.

---
---

## Things I want to know more about

- webpack

 ---

## References

1. <https://eloquentjavascript.net/05_higher_order.html#h_xxCc98lOBK> 
2. <https://reactjs.org/docs/thinking-in-react.html>
