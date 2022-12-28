# Intro to Next.js & Tailwind CSS

## What is Next.js

Next.js is a React framework that enables several extra features, including server-side rendering and generating static websites. Next.js is an open-source web development framework created by Vercel enabling React-based web applications with server-side rendering and generating static websites.

**How to Create a Next app**

```
npx create-next-app@latest <name>
```

**app Directory**

improving the routing and layouts experience in Next.js and aligning with the future of React with the introduction of the app directory. This is a follow-up to the Layouts RFC previously published for community feedback.

The app directory is currently in beta and we do not recommend using it in production yet. You can use Next.js 13 with the pages directory with stable features like the improved next/image and next/link components, and opt into the app directory at your own pace. The pages directory will continue to be supported for the foreseeable future.

The app directory includes support for:

- **Layouts:** Easily share UI between routes while preserving state and avoiding expensive re-renders.
- **Server Components:** Making server-first the default for the most dynamic applications.
- **Streaming:** Display instant loading states and stream in units of UI as they are rendered.
- **Support for Data Fetching:** async Server Components and extended fetch API enables component-level fetching.

**Layouts**

The app/ directory makes it easy to lay out complex interfaces that maintain state across navigations, avoid expensive re-renders, and enable advanced routing patterns. Further, you can nest layouts, and colocate application code with your routes, like components, tests, and styles.

Creating routes inside `app/` requires a single file, `page.js`:

```
// app/page.js
// This file maps to the index route (/)
export default function Page() {
  return <h1>Hello, Next.js!</h1>;
}
```

You can then define layouts through the file system. Layouts share UI between multiple pages. On navigation, layouts preserve state, remain interactive, and do not re-render.

```
// app/blog/layout.js
export default function BlogLayout({ children }) {
  return <section>{children}</section>;
}
```

**Server Components**

The app/ directory introduces support for React's new Server Components architecture. Server and Client Components use the server and the client each for what they're best at - allowing you to build fast, highly-interactive apps with a single programming model that provides a great developer experience.

With Server Components, we're laying the foundations to build complex interfaces while reducing the amount of JavaScript sent to the client, enabling faster initial page loads.

When a route is loaded, the Next.js and React runtime will be loaded, which is cacheable and predictable in size. This runtime does not increase in size as your application grows. Further, the runtime is asynchronously loaded, enabling your HTML from the server to be progressively enhanced on the client.

**Streaming**

The app/ directory introduces the ability to progressively render and incrementally stream rendered units of the UI to the client.

With Server Components and nested layouts in Next.js, you're able instantly render parts of the page that do not specifically require data, and show a loading state for parts of the page that are fetching data. With this approach, the user does not have to wait for the entire page to load before they can start interacting with it.

When deployed to Vercel, Next.js 13 applications that use the app/ directory will stream responses by default in both the Node.js and Edge runtimes for improved performance.

**Data Fetching**

React's recent Support for Promises RFC introduces a powerful new way to fetch data and handle promises inside components

## What is tailwindcss

### Why use tailwindcss

Traditionally, whenever you need to style something on the web, you write CSS. With Tailwind, you style elements by applying pre-existing classes directly in your HTML.

Example:

- Tailwind’s flexbox and padding utilities (flex, shrink-0, and p-6) to control the overall card layout
- The max-width and margin utilities (max-w-sm and mx-auto) to constrain the card width and center it horizontally
- The background color, border radius, and box-shadow utilities (bg-white, rounded-xl, and shadow-lg) to style the card’s appearance
- The width and height utilities (w-12 and h-12) to size the logo image
- The space-between utilities (space-x-4) to handle the spacing between the logo and the text
- The font size, text color, and font-weight utilities (text-xl, text-black, font-medium, etc.) to style the card text
- This approach allows us to implement a completely custom component design without writing a single line of custom CSS.

Why not just use inline styles?
A common reaction to this approach is wondering, “isn’t this just inline styles?” and in some ways it is — you’re applying styles directly to elements instead of assigning them a class name and then styling that class.

But using utility classes has a few important advantages over inline styles:

- Designing with constraints. Using inline styles, every value is a magic number. With utilities, you’re choosing styles from a predefined design system, which makes it much easier to build visually consistent UIs.
- Responsive design. You can’t use media queries in inline styles, but you can use Tailwind’s responsive utilities to build fully responsive interfaces easily.
- Hover, focus, and other states. Inline styles can’t target states like hover or focus, but Tailwind’s state variants make it easy to style those states with utility classes.

### Maintainability concerns

The biggest maintainability concern when using a utility-first approach is managing commonly repeated utility combinations.

This is easily solved by extracting components and partials, and using editor and language features like multi-cursor editing and simple loops.

Aside from that, maintaining a utility-first CSS project turns out to be a lot easier than maintaining a large CSS codebase, simply because HTML is so much easier to maintain than CSS. Large companies like GitHub, Netflix, Heroku, Kickstarter, Twitch, Segment, and more are using this approach with great success.









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
