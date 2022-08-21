# State and Props

> Understanding the work flow increases your ability to work on complix project and increases your confidence level in addition, well understanding the work flow will reduce the errors and will ease the act of debugging.
---
---

**Based off the diagram, what happens first, the ‘render’ or the ‘componentDidMount’?**

According to the work flow diagram **_render_** occurs first followed by React updates DOM and refs then at the end **_componentDidMount_** takes action. 

**What is the very first thing to happen in the lifecycle of React?**

There are three phases in React lifecycle; Mounting, Updating and Unmounting. Mounting occurs the first thing as soon as an instance of a component is being created and inserted into the DOM. Saying that, the order in which React calls its methods are as follows:

1. constructor ( )
2. getDerivedStateFromProps( )
3. render( )
4. componentDidMount( )

concluding that the action of calling the constructor is the first thing that happens.

**Put the following things in the order that they happen: componentDidMount, render, constructor, componentWillUnmount, React Updates**

- For the Mounting Stage:

_constructor_ --> _render_ --> _React Updates_  --> _componentDidMount_

- For the Unmounting Stage:

 _componentWillUnmount_

**What does componentDidMount do?**

It is a place where you can load anything if needed using either network request or initialize the DOM.[1] In another words, it is a place where you can run statements that requires that the component is already placed in the DOM.[2]

**What types of things can you pass in the props?**

Anything that is going to be passed from the parent and will not be changed inside the component, such as titles or names or description of something, instead of hard coding it we use props to make it dynamic, for example if you waht to render multiple cards each of contains a name of an animal, a picture, and a description, instead of hard coding them, we can use an api to fetch the values and pass each as a prop to the component.

**What is the big difference between props and state?**

Props are like an arguments that you pass to a component like the args passed to a functions, while State is something inside of a component and handled inside the component and props are handles outside of the component.

**When do we re-render our application?**

when a state inside our application is changed.

**What are some examples of things that we could store in state?**

A count, such as a score or time. It is basically something we want to update.

---
---

## Things I want to know more about

- Why is there props and states, why when developing react they did not just develop one thing which can be used as either a prop or a state. Is the reason for it to increase the rendering, rerendering time and refreshing?

 ---

## References

[1] Blankenship, Joshua 2018, _React: Component Lifecycle Events_, medium.com, accessed 22 August 2022, <<https://medium.com/@joshuablankenshipnola/react-component-lifecycle-events-cb77e670a093>>.

[2] _React Lifecycle_, w3schools, accessed 22 August 2022, <<https://www.w3schools.com/react/react_lifecycle.asp>>.
