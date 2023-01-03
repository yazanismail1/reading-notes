# Next- Forms and Conditional Rendering 

React is, in our opinion, the premier way to build big, fast Web apps with JavaScript. It has scaled very well for us at Facebook and Instagram.

One of the many great parts of React is how it makes you think about apps as you build them. In this document, we’ll walk you through the thought process of building a searchable product data table using React.

## React Hooks and Custom Hooks

Hooks are a new addition in React 16.8. They let you use state and other React features without writing a class.

### Custom Hooks
When we want to share logic between two JavaScript functions, we extract it to a third function. Both components and Hooks are functions, so this works for them too!

A custom Hook is a JavaScript function whose name starts with ”use” and that may call other Hooks. For example, useFriendStatus

```
import { useState, useEffect } from 'react';

function useFriendStatus(friendID) {
  const [isOnline, setIsOnline] = useState(null);

  useEffect(() => {
    function handleStatusChange(status) {
      setIsOnline(status.isOnline);
    }

    ChatAPI.subscribeToFriendStatus(friendID, handleStatusChange);
    return () => {
      ChatAPI.unsubscribeFromFriendStatus(friendID, handleStatusChange);
    };
  });

  return isOnline;
}
```

Unlike a React component, a custom Hook doesn’t need to have a specific signature. We can decide what it takes as arguments, and what, if anything, it should return. In other words, it’s just like a normal function. Its name should always start with use so that you can tell at a glance that the rules of Hooks apply to it.

#### Things to consider when working with custom hooks

**Is this code equivalent to the original examples?**

Yes, it works in exactly the same way. If you look closely, you’ll notice we didn’t make any changes to the behavior. All we did was to extract some common code between two functions into a separate function. Custom Hooks are a convention that naturally follows from the design of Hooks, rather than a React feature.

**Do I have to name my custom Hooks starting with “use”?**

Please do. This convention is very important. Without it, we wouldn’t be able to automatically check for violations of rules of Hooks because we couldn’t tell if a certain function contains calls to Hooks inside of it.

**Do two components using the same Hook share state?** 

No. Custom Hooks are a mechanism to reuse stateful logic (such as setting up a subscription and remembering the current value), but every time you use a custom Hook, all state and effects inside of it are fully isolated.

**How does a custom Hook get isolated state?** 

Each call to a Hook gets isolated state. Because we call useFriendStatus directly, from React’s point of view our component just calls useState and useEffect. And as we learned earlier, we can call useState and useEffect many times in one component, and they will be completely independent.

## Lifting State Up

In React, sharing state is accomplished by moving it up to the closest common ancestor of the components that need it. This is called “lifting state up”. We will remove the local state from the TemperatureInput and move it into the Calculator instead.

If the Calculator owns the shared state, it becomes the “source of truth” for the current temperature in both inputs. It can instruct them both to have values that are consistent with each other. Since the props of both TemperatureInput components are coming from the same parent Calculator component, the two inputs will always be in sync.

### Summary

There should be a single “source of truth” for any data that changes in a React application. Usually, the state is first added to the component that needs it for rendering. Then, if other components also need it, you can lift it up to their closest common ancestor. Instead of trying to sync the state between different components, you should rely on the top-down data flow.

Lifting state involves writing more “boilerplate” code than two-way binding approaches, but as a benefit, it takes less work to find and isolate bugs. Since any state “lives” in some component and that component alone can change it, the surface area for bugs is greatly reduced.

If something can be derived from either props or state, it probably shouldn’t be in the state. For example, instead of storing both celsiusValue and fahrenheitValue, we store just the last edited temperature and its scale. The value of the other input can always be calculated from them in the render() method. This lets us clear or apply rounding to the other field without losing any precision in the user input.

## React Memoization

There are some times when re-rendering of the component results in performance issues. To overcome this, React provides us with a performance feature known as memoization.

Memoization is an optimization technique that allows an increase in the performance of a program by storing the results of some expensive function so that we don’t need to call that function when the same inputs are given.

### How to Implement Memoization in React

React has the features PureComponent and memo hook which allow us to implement memoization in React.
PureComponent allows us to perform optimization. It depends on the shouldComponentUpdate() lifecycle method but it can only be used with the class component.
React also gives us a memo() hook to apply memoization for functional components.
If we need a function component that gives the same result for the same props and we don’t want to re-render it, we can use memoization to skip the re-render of the component by storing and reusing the last rendered result.

### Memoization using purecomponent

PureComponent is similar to Components in React except that PureComponent implements shouldComponentUpdate() with shallow prop and state comparison and Components does not.
In some cases, if our component re-renders the same result with the same given props and state which results in performance issues, then we can use PureComponent to increase performance. PureComponent’s shouldComponentUpdate() only shallowly compares the object.
But we should make sure that props and state are simple. If they contain any complex data structures then PureComponent may produce wrong results. Also, we should make sure that all the children components of PureComponent are also PureComponent since PureComponent’s shouldComponentUpdate() skips prop updates for the full component subtree.

### Memoization using Memo

In React, the memo is the higher-order component in short HOC (HOC are functions that take a component and return a new component). Memo allows us to implement memoization in functional components since PureComponents can only be used in class components. In other words, we wrap the function with the memo key word.

### Memoization usinf useMemo

If you are a Hook fan then you can use useMemo for implementing memoization. To utilize useMemo we need to pass a create function and an array of dependencies. useMemo optimizes performance by recomputing the memoized value only when one of the passed dependencies changes.

We should only implement useMemo for performance optimization and for that we should first write our code such that it works without useMemo and then add useMemo to optimize it. Also, we should know that useMemo runs during rendering so we need to make sure that we do not use anything that is not used during rendering, like side effects.

### When to use Memoization

Memoization can increase performance for some functions. But, if we use it for every component rendering, it might decrease performance since it stores results that increase memory used for the program. We should only use memoization when there is a clear benefit for doing so.

### Summary

Memoization is an optimization feature in React which, when used in the right place, increases the performance of the program. React gives us PureComponent and memo to implement memoization. PureComponent is used with the class component and memo is used with the function component. Memoization increases performance by storing results for functions when the same prop is passed, hence reducing the number of re-renderings. But, overuse of memoization in places where there are not performance issues can result in reduction of performance.


# Things I want to know more about

- React Hooks
- React UseEffect
- React UseState
- React UseRef
- React Native
- Next JS

# References

[1] <https://www.youtube.com/watch?v=__mSgDEOyv8&ab_channel=BeyondFireship>

[2] <https://nextjs.org/blog/next-13>

[3] <https://tailwindcss.com/docs/utility-first>
