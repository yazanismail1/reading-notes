# Authentication

## Beginner’s Guide to SWR: Data Fetching in React

SWR stands for stale-while-revalidate, a HTTP cache invalidation strategy popularized by HTTP RFC 5861. It basically means that it performs data fetching in 3 steps:

1. Returns cached data first (stale)

2. Sends the fetch request (revalidate)

3. Returns the up-to-date data

SWR is created by Vercel and one of its advantages is that it is a fast and lightweight package. It is a layer built on top of Fetch API and therefore provides additional features on top of just data fetching. These features include caching, pagination, auto revalidation and more.

### Why use SWR?

1. **Built-in Cache + Real-Time Experience**

    When we use Fetch or Axios for data fetching in React, we usually need to show the user some loading message or spinner while data is being fetched. Using SWR’s strategy, the user sees the cached (stale) data first and requests are automatically being cached. Components will always be constantly updated with the most recent data, ensuring UI will always be fast and reactive.

2. **Auto Revalidation**

    SWR ensures that the user sees the most up-to-date data. So even with multiple tabs or windows, the data is always fresh and in sync when the window/tab is refocused.

    Instead of just revalidating data on focus, SWR can also revalidate data on interval, to make sure multiple sessions will render the same components based on the data.

    Finally, there’s revalidation on reconnect. In the event the user disconnects from the internet, SWR will automatically revalidates data once the user is online again.

3. **Pagination**

    One of the most useful features of SWR is that it supports pagination and infinite loading of data.

    Instead of having to write your own logic with Fetch or Axios to paginate data or create an infinite loading UI for your app, SWR provides a simple Hook called useSWRInfinite to handle this for you.

4. **More Features + Benefits of SWR**

    There are many more reasons why you should use SWR in your React apps. Some of them are:

    - Local mutation

    - Dependent fetching

    - Smart error retry

    - Supports fetching from both REST and GraphQL APIs

    - Typescript and React Native ready

### How to use SWR?

1. **Install Package**

```
npm install swr
```

2. **Import useSWR**

```
import useSWR from 'swr'

const { data, error } = useSWR('/api/123', fetcher)

// The useSWR Hook returns 2 values: data and error. It accepts a key as its first parameter, usually the URL or graphQL query of the request. The second parameter is a fetcher function.
```

3. **Write the fetcher function**

```
import axios from 'axios'

const fetcher = url => axios.get(url).then(res => res.data)
```

**Recap**

```
import useSWR from "swr";
import "./App.css";
function App() {
  const fetcher = (...args) => fetch(...args).then((res) => res.json());
  // fetch data
  const { data, error } = useSWR(
    "https://jsonplaceholder.typicode.com/todos/1",
    fetcher
  );
  if (error) return <div>failed to load</div>;
  
  if (!data) return <div>loading...</div>;
  // render data
  return (
    <div className="App">
      <h2>{data.title}</h2>
      <p>UserId: {data.userId}</p>
      <p>Id: {data.id}</p>
      {data.completed? <p>Completed</p> : <p>Not Completed</p>}
    </div>
  );
}
export default App;
```

## Summary

he name “SWR” is derived from stale-while-revalidate, a HTTP cache invalidation strategy popularized by HTTP RFC 5861. SWR is a strategy to first return the data from cache (stale), then send the fetch request (revalidate), and finally come with the up-to-date data.

With SWR, components will get a stream of data updates constantly and automatically.
And the UI will be always fast and reactive.

### Features

With just one single line of code, you can simplify the logic of data fetching in your project, and also have all these amazing features out-of-the-box:

- Fast, lightweight and reusable data fetching

- Built-in cache and request deduplication

- Real-time experience

- Transport and protocol agnostic

- SSR / ISR / SSG support

- TypeScript ready

- React Native

SWR has you covered in all aspects of speed, correctness, and stability to help you build better experiences:

- Fast page navigation

- Polling on interval

- Data dependency

- Revalidation on focus

- Revalidation on network recovery

- Local mutation (Optimistic UI)

- Smart error retry

- Pagination and scroll position recovery

- React Suspense

# Things I want to know more about

- React Hooks
- React UseEffect
- React UseState
- React UseRef
- React Native
- Next JS
- Redux

# References

[1] <https://blog.openreplay.com/beginner-s-guide-to-swr-data-fetching-in-react>

[2] <https://swr.vercel.app/>
