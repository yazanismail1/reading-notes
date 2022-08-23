# React and Forms

> Forms are a powerful thing you can store users data and send them to the server to check the values, fetching data and send Emails and way more.

---
---

**What is a ‘Controlled Component’?**

Is a component that holds its own state and been mutable its state using react, this component is called a controlled component such as a HTML input element. 

**Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why?**

From my understanding, we should update the state. to keep it sync with the input’s value, meaning that changing the input will update the state, and updating the state will change the input.

**How do we target what the user is entering if we have an event handler on an input field?** 

By setting a state for it in the constructor to make the react state the source of truth.

**Why would we use a ternary operator?**

to shorten our if statements into one line of code with the conditional operator.

**Rewrite the following statement using a ternary statement:**
>`if(x===y){`
>   `console.log(true);`
>`} else {`
>   `console.log(false);`
>`}`

`(x === y) ? console.log(true) : console.log(false)`

---
---

## Things I want to know more about

- Does it have any requirements or when not to use it, such as the arrow functions?

 ---

## References

