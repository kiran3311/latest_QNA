# React JS

### 1: What is React.js?

Definition: React.js is a JavaScript library for building user interfaces.

Key Features:

Component-based architecture

Virtual DOM for performance

One-way data binding

Reusable UI components
```js
function App() {
  return <h1>Hello, React!</h1>;
}
```

### 2. Difference between Virtual DOM, Shallow DOM, and Real DOM

DOM: Tree structure representing the UI in browsers.

Virtual DOM: A lightweight copy of the real DOM in memory. React updates only the changed parts, improving performance.

Shallow DOM: Not a React concept, but in testing (like Enzyme) "shallow rendering" means rendering a component without its child components.

Real DOM: Direct representation in the browser; expensive to update.



### 3. Controlled vs Uncontrolled Components

Controlled: Input values are controlled by React state.
```js
const [name, setName] = useState("");
<input value={name} onChange={(e) => setName(e.target.value)} />

```
Uncontrolled: Input values handled by the DOM, accessed via ref.
```js
const inputRef = useRef();
<input ref={inputRef} />

```


### 4. What are Hooks in React.js?

Functions introduced in React 16.8 to use state and lifecycle features inside functional components.

Examples: useState, useEffect, useMemo, useCallback, useRef, useContext.



### 5. What is JSX, Babel, Webpack?

JSX: JavaScript XML, syntax extension that allows writing HTML inside JS.

Babel: JavaScript compiler that transpiles JSX and ES6+ to browser-compatible JavaScript.

Webpack: Module bundler that bundles all files (JS, CSS, images) into one optimized file.



## 📌 Redux & State Management


### 6. What is Redux?

A state management library for JavaScript apps.
Manages global state with a predictable flow using store, action, reducer.

### 7. Reducer, Action, Store in Redux

Action: Object describing what to do ({type: "ADD_TODO", payload: "Task"}).

Reducer: Pure function that takes current state + action, and returns new state.

Store: Centralized object holding application state.



### 8. What is Middleware in Redux?

Functions that run between dispatching an action and reaching the reducer.

Used for logging, async calls, or modifying actions.



### 9. Explain Data Flow in Redux

UI dispatches an action.

Action goes through middleware.

Reducer processes it → returns new state.

Store updates state.

React components re-render with new state.



### 10. What is Redux-Thunk?

A middleware for handling async logic in Redux (like API calls).

Allows actions to return a function instead of an object.



### 11. What is Redux-Saga? Difference vs Redux-Thunk

Redux-Saga: Middleware for handling async logic using ES6 generators.

Thunk vs Saga:

Thunk → Simpler, function-based async.

Saga → More powerful, good for handling complex async flows, retries, parallel tasks.




## 📌 React Components & Lifecycle



### 12. Class vs Function Component

Class: Uses class, lifecycle methods (componentDidMount), this.state.

Function: Uses plain functions with hooks (useState, useEffect), simpler syntax.


### 13. How to Implement componentWillUnmount in Function Component

Use useEffect cleanup:
```js
useEffect(() => {
  return () => {
    console.log("Component will unmount");
  };
}, []);

```


### 14. useEffect, useState, useMemo, useCallback

useState: Manage state in function components.

useEffect: Side effects (API calls, subscriptions, cleanup).

useMemo: Memoize expensive calculations.

useCallback: Memoize function references to prevent re-renders.


### 15. Explain Lifecycle Methods in React.js

For class components:

Mounting: constructor, render, componentDidMount

Updating: shouldComponentUpdate, componentDidUpdate

Unmounting: componentWillUnmount



### 16. Export Default vs Export

default export: One per file.
```js
export default App;

```
named export: Many per file, must be imported with {}.

```js
export const add = () => {};


```




### 17. What is Portal in React.js

A way to render children into a DOM node outside the parent component’s hierarchy.
Example: Modals, Tooltips.



### 18. What is Reconciliation in React.js

Process where React compares new virtual DOM with old virtual DOM using diffing algorithm to update only changed nodes.




### 19. What is useRef in React.js

Hook to store mutable values or access DOM elements directly.
```js
const inputRef = useRef();

```


### 20. What is Server-Side Rendering (SSR) in React.js

Rendering React components on the server before sending HTML to client.

Benefits: Faster initial load, better SEO.

Example: Next.js uses SSR.



### 21. What is useStrict in React.js

It’s actually StrictMode (not hook) in React.

Helps highlight potential problems (deprecated APIs, unsafe lifecycles).




### 22. What is Fragment in React.js

Lets you return multiple elements without adding extra DOM nodes.
```js
<></>

```




### 23. What is React Router

A library for routing in React apps.

Provides <BrowserRouter>, <Route>, <Link>.



### 24. What is Node Module in React.js

The node_modules folder contains all installed dependencies for your project.




### 25. Default Localhost Port in React.js

Default: 3000.

To change: Run PORT=4000 npm start (Linux/Mac) or set in .env.


### 26. What is Higher Order Component (HOC)

Function that takes a component and returns a new component with added features.
```js
const withLogger = (Component) => (props) => {
  console.log(props);
  return <Component {...props} />;
};

```

### 27. What is Pure Component

React component that does a shallow comparison of props & state to avoid unnecessary re-renders.


### 28. Difference Between State and Props

State: Internal, mutable data owned by component.

Props: External, immutable data passed from parent.



### 29. How to Optimize React.js App

Use React.memo

Use useMemo, useCallback

Code-splitting with React.lazy

Avoid unnecessary re-renders

Virtualization (react-window)



### 30. React.js vs Angular.js

React: Library, Virtual DOM, unidirectional data flow, JSX.

Angular: Framework, Real DOM + Incremental DOM, two-way binding, TypeScript-based.


### 31. What is Prop Drilling and How to Overcome It

Prop Drilling: Passing props down through many levels of components.

Solution: Context API, Redux, or Zustand.


### 32. What is Context API in React.js

Built-in way to manage global state without prop drilling.

Uses React.createContext + Provider + useContext.


### 33. What is Super, Constructor, Render in React.js

super: Calls parent class constructor (super(props)).

constructor: Initialize state, bind methods in class components.

render: Returns JSX (UI) to be displayed.



