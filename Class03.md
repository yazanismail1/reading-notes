# Passing Functions as Props

> General Props and states are very strong and can be widely used, however, passing functions as props is next level, it allows you to control events for example the way you want.

---
---

**What does .map() return?**

.map( ) return an array.

**If I want to loop through an array and display each value in JSX, how do I do that in React?**

You can return each element as a HTML element and then wrap the whole new list outputted from map with another HTML element, for example, you can return each element as HTML li tag and wrap the whole new list with ul tag in the place you want to render your output.

**Each list item needs a unique** _key_

**What is the purpose of a key?**

Keys help React identify which items have changed, are added, or are removed.[1]


**What is the spread operator?**

The spread operator is a useful and quick syntax for adding items to arrays, combining arrays or objects, and spreading an array out into a function’s arguments.[2]

**List 4 things that the spread operator can do.**

You can add items to an array, combine arrays, combine objects and spreading an array out into a function’s arguments.[2]


**Give an example of using the spread operator to combine two arrays.**

> ``const myArray = [`🤪`,`🐻`,`🎌`]``  
> ``const yourArray = [`🙂`,`🤗`,`🤩`]``  
> ``const ourArray = [...myArray,...yourArray]``  
>``console.log(...ourArray) // 🤪 🐻 🎌 🙂 🤗 🤩"🍌" ]``

**Give an example of using the spread operator to add a new item to an array.**

> ``const fewFruit = ['🍏','🍊','🍌'];``  
> ``const fewMoreFruit = ['🍉', '🍍', ...fewFruit];``  
> ``console.log(fewMoreFruit); //  Array(5) [ "🍉", "🍍", "🍏", "🍊", "🍌" ]``  


**Give an example of using the spread operator to combine two objects into one.**

>``const objectOne = {hello: "🤪"}``  
>``const objectTwo = {world: "🐻"}``  
>``const objectThree = {...objectOne, ...objectTwo, laugh: "😂"}``  
>``console.log(objectThree) // Object { hello: "🤪", world: "🐻", laugh: "😂" }``  
>``const objectFour = {...objectOne, ...objectTwo, laugh: () => {console.log("😂".repeat(5))}}``  
>``objectFour.laugh() // 😂😂😂😂😂``


**In the video, what is the first step that the developer does to pass functions between components?**

Create a function where ever the state exists.


**In your own words, what does the increment function do?**

It takes a name, loop through an array of objects and increase the count for a specific object when triggered.

**How can you pass a method from a parent component into a child component?**

It is as easy as passing props. The same way of passing props. For example => increment={this.increment}.

**How does the child component invoke a method that was passed to it from a parent component?**

By calling the method as a props inside a method in the child component.

---
---

## Things I want to know more about

- Passing functions and methods. It sounds interesting and for sure it needs a lot of practice to fully grasp it.

 ---

## References

[1]  _List and Keys_, reactjs.org, accessed 23 August 2022, <<https://reactjs.org/docs/lists-and-keys.html>>.

[2] Dr.Derek Austin, 4 Oct 2019 _How to Use the Spread Operator (…) in JavaScript_, medium, accessed 23 August 2022, <<https://medium.com/coding-at-dawn/how-to-use-the-spread-operator-in-javascript-b9e4a8b06fab>>.
