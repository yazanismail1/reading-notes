# Context API

## What is global state with React?

In React, originally, the state is held and modified within the same React component. In most applications, different components may need to access and update the same state. This is achieved by introducing the global states in your app. The main purpose of the global state is to share a state among multiple components.

There are three ways this communication can happen:

- With a child component

- With a parent component

- With a sibling component

### State traveling down

State traveling down through the hierarchy is best managed using the mutable state at the highest level to determine immutable properties that define the lower-level components. Even when these properties are updated, the lower-level component is updated rather than fully recreated.

### State traveling up

You need to pass down a callback function for a higher-level component to know the state. In the following version, we add a global state to count the total number of button presses and update this state with a callback function called pushed, which is called whenever a button is pushed.

### State traveling sideways

Various sub-components need to communicate updates between them. This can be achieved by passing state, using callback, up to a common parent component, and then passing it back down.

## Context

Context provides a way to pass data through the component tree without having to pass props down manually at every level.

In a typical React application, data is passed top-down (parent to child) via props, but such usage can be cumbersome for certain types of props (e.g. locale preference, UI theme) that are required by many components within an application. Context provides a way to share values like these between components without having to explicitly pass a prop through every level of the tree.

### When to Use Context

Context is designed to share data that can be considered “global” for a tree of React components, such as the current authenticated user, theme, or preferred language. 

Using context, we can avoid passing props through intermediate elements.

Context is primarily used when some data needs to be accessible by many components at different nesting levels. Apply it sparingly because it makes component reuse more difficult.

If you only want to avoid passing some props through many levels, component composition is often a simpler solution than context.

It might feel redundant to pass down the user and avatarSize props through many levels if in the end only the Avatar component really needs it. It’s also annoying that whenever the Avatar component needs more props from the top, you have to add them at all the intermediate levels too.

One way to solve this issue without context is to pass down the Avatar component itself so that the intermediate components don’t need to know about the user or avatarSize props.

It might feel redundant to pass down the user and avatarSize props through many levels if in the end only the Avatar component really needs it. It’s also annoying that whenever the Avatar component needs more props from the top, you have to add them at all the intermediate levels too.

One way to solve this issue without context is to pass down the Avatar component itself so that the intermediate components don’t need to know about the user or avatarSize props

## Redux vs Context API

The simplest way to pass data from a parent to a child in a React Application is by passing it on to the child's props. But an issue arises when a deeply nested child requires data from a component higher up in the tree. If we pass on the data through the props, every single one of the children would be required to accept the data and pass it on to its child, leading to prop drilling, a terrible practice in the world of React.

To solve the prop drilling issue, we have State Management Solutions like Context API and Redux.

### What is the Context API?

Context API is a built-in React tool that does not influence the final bundle size, and is integrated by design.

### The of use Context API

1. **Create the Context**

```
const Context = createContext(MockData);
```

2. **Create a Provider for the Context**

```
const Parent = () => {
    return (
        <Context.Provider value={initialValue}>
            <Children/>
        </Context.Provider>
    )
}
```

3. **Consume the data in the Context**

```
const Child = () => {
    const contextData = useContext(Context);
    // use the data
    // ...
}
```

### What is Redux

Redux is an Open Source Library which provides a central store, and actions to modify the store. It can be used with any project using JavaScript or TypeScript.

### The of use Redux

1. **Create a Reducer**

```
import { createSlice } from "@reduxjs/toolkit";

export const slice = createSlice({
    name: "slice-name",
    initialState: {
        // ...
    },
    reducers: {
        func01: (state) => {
            // ...
        },
    }
});

export const { func01 } = slice.actions;
export default slice.reducer;
```

2. **Configure the Store**

```
import { configureStore } from "@reduxjs/toolkit";
import reducer from "./reducer";

export default configureStore({
    reducer: {
        reducer: reducer
    }
});
```

3. **Make the Store available for data consumption**

```
import React from 'react';
import ReactDOM from 'react-dom';
import { Provider } from 'react-redux';
import App from './App.jsx'
import store from './store';

ReactDOM.render(
    <Provider store={store}>
        <App />
    </Provider>,
    document.getElementById("root")
);
```

4. **Use State or Dispatch Actions**

```
import { useSelector, useDispatch } from 'react-redux';
import { func01 } from './redux/reducer';

const Component = () => {
    const reducerState = useSelector((state) => state.reducer);
    const dispatch = useDispatch();
    const doSomething = () = > dispatch(func01)  
    return (
        <>
            {/* ... */}
        </>
    );
}
export default Component;
```

### Summary

|Context API|Redux|
|---|---|
|Built-in tool that ships with React|	Additional installation Required, driving up the final bundle size|
|Specifically designed for static data, that is not often refreshed or updated|Works like a charm with both static and dynamic data|
|Adding new contexts requires creation from scratch|Easily extendible due to the ease of adding new data/actions after the initial setup|
|Debugging can be hard in highly nested React Component Structure even with Dev Tool|Incredibly powerful Redux Dev Tools to ease debugging|
|UI logic and State Management Logic are in the same component|Better code organization with separate UI logic and State Management Logic


# Things I want to know more about

- React Hooks
- React UseEffect
- React UseState
- React UseRef
- React Native
- Next JS
- Redux

# References

[1] <https://www.educative.io/answers/what-is-global-state-with-react>

[2] <https://reactjs.org/docs/context.html>

[3] <https://dev.to/ruppysuppy/redux-vs-context-api-when-to-use-them-4k3p>
