# React JS 💻✔

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
---
### 2. Difference between Virtual DOM, Shallow DOM, and Real DOM

DOM: Tree structure representing the UI in browsers.

Virtual DOM: A lightweight copy of the real DOM in memory. React updates only the changed parts, improving performance.

Shallow DOM: Not a React concept, but in testing (like Enzyme) "shallow rendering" means rendering a component without its child components.

Real DOM: Direct representation in the browser; expensive to update.

---

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
---

### 4. What are Hooks in React.js?

Functions introduced in React 16.8 to use state and lifecycle features inside functional components.

Examples: useState, useEffect, useMemo, useCallback, useRef, useContext.

---

### 5. What is JSX, Babel, Webpack?

JSX: JavaScript XML, syntax extension that allows writing HTML inside JS.

Babel: JavaScript compiler that transpiles JSX and ES6+ to browser-compatible JavaScript.

Webpack: Module bundler that bundles all files (JS, CSS, images) into one optimized file.

---

## 📌 Redux & State Management


### 6. What is Redux?

A state management library for JavaScript apps.
Manages global state with a predictable flow using store, action, reducer.

---

### 7. Reducer, Action, Store in Redux

Action: Object describing what to do ({type: "ADD_TODO", payload: "Task"}).

Reducer: Pure function that takes current state + action, and returns new state.

Store: Centralized object holding application state.

---

### 8. What is Middleware in Redux?

Functions that run between dispatching an action and reaching the reducer.

Used for logging, async calls, or modifying actions.

---

### 9. Explain Data Flow in Redux

UI dispatches an action.

Action goes through middleware.

Reducer processes it → returns new state.

Store updates state.

React components re-render with new state.


---
### 10. What is Redux-Thunk?

A middleware for handling async logic in Redux (like API calls).
Allows actions to return a function instead of an object.

---


### 11. What is Redux-Saga? Difference vs Redux-Thunk

Redux-Saga: Middleware for handling async logic using ES6 generators.

Thunk vs Saga:

Thunk → Simpler, function-based async.

Saga → More powerful, good for handling complex async flows, retries, parallel tasks.


---

## 📌 React Components & Lifecycle



### 12. Class vs Function Component

Class: Uses class, lifecycle methods (componentDidMount), this.state.
Function: Uses plain functions with hooks (useState, useEffect), simpler syntax.

---

### 13. How to Implement componentWillUnmount in Function Component

Use useEffect cleanup:
```js
useEffect(() => {
  return () => {
    console.log("Component will unmount");
  };
}, []);

```
---

### 14. useEffect, useState, useMemo, useCallback

useState: Manage state in function components.

useEffect: Side effects (API calls, subscriptions, cleanup).

useMemo: Memoize expensive calculations.

useCallback: Memoize function references to prevent re-renders.

---
### 15. Explain Lifecycle Methods in React.js

For class components:

Mounting: constructor, render, componentDidMount

Updating: shouldComponentUpdate, componentDidUpdate

Unmounting: componentWillUnmount

---

### 16. Export Default vs Export

default export: One per file.
```js
export default App;

```
named export: Many per file, must be imported with {}.

```js
export const add = () => {};


```


---

### 17. What is Portal in React.js

A way to render children into a DOM node outside the parent component’s hierarchy.
Example: Modals, Tooltips.

---

### 18. What is Reconciliation in React.js

Process where React compares new virtual DOM with old virtual DOM using diffing algorithm to update only changed nodes.


---

### 19. What is useRef in React.js

Hook to store mutable values or access DOM elements directly.
```js
const inputRef = useRef();

```
---

### 20. What is Server-Side Rendering (SSR) in React.js

Rendering React components on the server before sending HTML to client.

Benefits: Faster initial load, better SEO.

Example: Next.js uses SSR.

---

### 21. What is useStrict in React.js

It’s actually StrictMode (not hook) in React.

Helps highlight potential problems (deprecated APIs, unsafe lifecycles).


---

### 22. What is Fragment in React.js

Lets you return multiple elements without adding extra DOM nodes.
```js
<></>

```



---

### 23. What is React Router

A library for routing in React apps.
Provides <BrowserRouter>, <Route>, <Link>.

---

### 24. What is Node Module in React.js

The node_modules folder contains all installed dependencies for your project.


---

### 25. Default Localhost Port in React.js

Default: 3000.

To change: Run PORT=4000 npm start (Linux/Mac) or set in .env.

---
### 26. What is Higher Order Component (HOC)

Function that takes a component and returns a new component with added features.
```js
const withLogger = (Component) => (props) => {
  console.log(props);
  return <Component {...props} />;
};

```
---
### 27. What is Pure Component

React component that does a shallow comparison of props & state to avoid unnecessary re-renders.

---
### 28. Difference Between State and Props

State: Internal, mutable data owned by component.

Props: External, immutable data passed from parent.

---

### 29. How to Optimize React.js App

Use React.memo

Use useMemo, useCallback

Code-splitting with React.lazy

Avoid unnecessary re-renders

Virtualization (react-window)


---
### 30. React.js vs Angular.js

React: Library, Virtual DOM, unidirectional data flow, JSX.
Angular: Framework, Real DOM + Incremental DOM, two-way binding, TypeScript-based.

---

### 31. What is Prop Drilling and How to Overcome It

Prop Drilling: Passing props down through many levels of components.
Solution: Context API, Redux, or Zustand.

---

### 32. What is Context API in React.js
Built-in way to manage global state without prop drilling.
Uses React.createContext + Provider + useContext.


---
### 33. What is Super, Constructor, Render in React.js

super: Calls parent class constructor (super(props)).

constructor: Initialize state, bind methods in class components.

render: Returns JSX (UI) to be displayed.




---














# 🔚🔚🔚
---
# 🆕🆕🆕





---

# 🔹 JavaScript 💻✔

#### 1. What is EcmaScript in JavaScript

* **ECMAScript (ES)** is the standardized specification of JavaScript defined by ECMA International.
* JavaScript is the implementation of ECMAScript.
* New versions (ES6, ES7, … ES2023) bring features like `let/const`, classes, async/await, modules, etc.

---

#### 2. Difference between `let`, `const`, and `var`

* **var** → function-scoped, hoisted, can be redeclared.
* **let** → block-scoped, hoisted (but in Temporal Dead Zone), cannot be redeclared in same scope.
* **const** → block-scoped, must be initialized, cannot be reassigned (but objects/arrays can be mutated).

---

#### 3. Spread operator, Rest operator, Default parameter

* **Spread (`...`)**: Expands arrays/objects.

  ```js
  const arr = [1, 2, 3];
  console.log(...arr); // 1 2 3
  ```
* **Rest (`...`)**: Collects arguments into an array.

  ```js
  function sum(...nums) { return nums.reduce((a,b)=>a+b,0); }
  ```
* **Default Parameter**: Sets default values in functions.

  ```js
  function greet(name="Guest"){ return `Hello ${name}`; }
  ```

---

#### 4. Deep copy vs Shallow copy

* **Shallow copy** → Copies only the first level; nested objects share reference.

  ```js
  let obj1 = {a:1, b:{c:2}};
  let shallow = {...obj1};
  shallow.b.c = 5; // also changes obj1
  ```
* **Deep copy** → Copies all levels.

  ```js
  let deep = JSON.parse(JSON.stringify(obj1));
  ```

---

#### 5. Promise, Callback, Async/Await

* **Callback**: Function passed as argument, executed later. Can cause “callback hell”.
* **Promise**: Object representing async operation with `.then/.catch`.
* **async/await**: Syntactic sugar over Promises for cleaner code.

---

#### 6. Difference between Promise and Callback

* **Callback**: Hard to manage, leads to nested code.
* **Promise**: Easier chaining, better error handling.

---

#### 7. Event Bubbling vs Event Capturing

* **Bubbling**: Event propagates from child → parent. (default)
* **Capturing**: Event propagates from parent → child.
* Controlled via `addEventListener("click", handler, true)`

---

#### 8. Higher Order Function

* A function that takes another function as argument or returns a function.

  ```js
  function hof(fn){ return fn(); }
  ```

---

#### 9. Different types of functions in JavaScript

* Function Declaration
* Function Expression
* Arrow Function
* Anonymous Function
* Constructor Function
* IIFE (Immediately Invoked Function Expression)
* Generator Function

---

#### 10. Arrow Function

* Short syntax, doesn’t bind its own `this`.

  ```js
  const add = (a,b)=>a+b;
  ```

---

#### 11. Call, Apply, Bind

* **call()** → Calls function with given `this` & arguments.
* **apply()** → Same but arguments as array.
* **bind()** → Returns new function with bound `this`.

---

#### 12. Ways to create objects

* Object literal `{}`
* `new Object()`
* Constructor function
* ES6 `class`
* `Object.create()`
* Singleton using Object literal

---

#### 13. Prototype Inheritance

* JS objects inherit properties/methods from prototype chain.

---

#### 14. What is TypeScript

* A superset of JavaScript with **static typing**, compiled into JS.

---

#### 15. Array methods & String methods

* **Array**: `map`, `filter`, `reduce`, `push`, `pop`, `slice`, `splice`, `find`, `sort`, `forEach`.
* **String**: `charAt`, `slice`, `substring`, `split`, `replace`, `toUpperCase`, `trim`.

---

#### 16. Difference between Java and JavaScript

* **Java**: OOP language, compiled, strongly typed.
* **JavaScript**: Scripting language, interpreted, loosely typed.

---

#### 17. Throttling & Debouncing

* **Debounce**: Delays execution until after user stops triggering.
* **Throttle**: Executes at fixed intervals, ignores extra calls.

---

#### 18. Null vs Undefined

* **null**: Intentional absence of value.
* **undefined**: Variable declared but not assigned.

---

#### 19. Falsy values in JS

`false, 0, "", null, undefined, NaN`

---

#### 20. Execution Context, Event Loop, Stack, Queues

* **Execution Context**: Environment where code runs.
* **Call Stack**: Tracks function execution.
* **Event Loop**: Moves tasks from queues to stack.
* **Callback Queue**: Stores async callbacks.
* **Microtask Queue**: Stores promises/callbacks (higher priority).

---

#### 21. setTimeout vs setInterval

* **setTimeout(fn, ms)** → runs once after delay.
* **setInterval(fn, ms)** → runs repeatedly at interval.

---

#### 22. Object.seal vs Object.freeze

* **seal**: Prevent adding/removing props, but can modify values.
* **freeze**: Prevent adding/removing and modifying values.

---

#### 23. Difference between Map and Set

* **Map**: Key-value pairs (keys can be any type).
* **Set**: Unique values only.

---

#### 24. WeakMap vs WeakSet

* **WeakMap**: Keys must be objects, values can be any. Garbage collected.
* **WeakSet**: Stores only objects, garbage collected.

---

#### 25. sessionStorage, localStorage, cookie

* **localStorage**: Stores data with no expiry.
* **sessionStorage**: Stores data for session only.
* **cookie**: Small data sent with every request, can have expiry.

---

#### 26. Program to sort array

```js
let arr = [5,2,8,1];
arr.sort((a,b)=>a-b); // ascending
```

---

#### 27. JSON.stringify & JSON.parse

* **JSON.stringify(obj)** → Converts JS object to JSON string.
* **JSON.parse(str)** → Converts JSON string to JS object.

---

#### 28. map, filter, reduce

* **map()**: Transforms array.
* **filter()**: Returns matching elements.
* **reduce()**: Reduces array to single value.

---

#### 29. Generator function

* Function that can pause & resume using `yield`.

  ```js
  function* gen(){ yield 1; yield 2; }
  ```

---

#### 30. Stop event propagation

```js
event.stopPropagation();
```

---

#### 31. Closure

* Function with access to variables of its parent scope even after parent has finished executing.

---

#### 32. Hoisting in JavaScript

* Variables & functions are moved to top of scope before execution.

---

#### 33. Dead Zone in JavaScript

* The period between variable declaration and initialization where accessing gives `ReferenceError`.

---

#### 34. Function Currying

* Breaking function with multiple args into a sequence of functions.

  ```js
  const add = a=>b=>c=>a+b+c;
  ```

---

#### 35. Mutation Observer

* API to watch DOM changes.

  ```js
  const obs = new MutationObserver(cb);
  obs.observe(node, {childList:true,subtree:true});
  ```

---

#### 36. Memoization

* Caching results of expensive function calls.

  ```js
  function memo(fn){
    let cache={};
    return function(x){
      if(cache[x]) return cache[x];
      return cache[x]=fn(x);
    }
  }
  ```

---


## ▶▶▶

---

# JavaScript Practice Programs & Interview Q\&A

This file contains frequently asked **JavaScript coding interview questions** with explanations and answers.

---

## 🔹 1. Program to Find Element Occurrence in Array

```js
const arr = [1, 2, 3, 1, 2, 1, 3];
const count = {};

arr.forEach(num => {
  count[num] = (count[num] || 0) + 1;
});

console.log(count); 
// 👉 {1: 3, 2: 2, 3: 2}
```

**Explanation:** We loop over the array and keep increasing the count of each element inside an object.

---

## 🔹 2. Remove Duplicate Items from Array

### Method 1: Using Loop

```js
const arr = [1, 2, 3, 4, 1, 2];
const b = [];

for (let i = 0; i < arr.length; i++) {
  if (b.indexOf(arr[i]) === -1) {
    b.push(arr[i]);
  }
}
console.log("removed array value", b); // 👉 [1, 2, 3, 4]
```

### Method 2: Using `filter`

```js
const arr = [1, 2, 3, 4, 1, 2];
const b = [];

arr.filter((item) => {
  if (b.indexOf(item) === -1) {
    b.push(item);
  }
});
console.log("removed array value", b); // 👉 [1, 2, 3, 4]
```

### Method 3: Using `Set`

```js
const arr = [1, 2, 3, 4, 1, 2];
const unique = [...new Set(arr)];
console.log(unique); // 👉 [1, 2, 3, 4]
```

---

## 🔹 3. What will be the Output?

```js
const firstname = fun();
let name = 'vivek';

function fun() {
  return `my is ${name} malviya`;
}

console.log(firstname);
```

**Answer:** ❌ This will throw `ReferenceError: Cannot access 'name' before initialization`.
Because `let` is hoisted but kept in **Temporal Dead Zone** until initialized.

---

## 🔹 4. Program for Output `mul(2)(4)(6)`

### Using Normal Function

```js
function mul(a) {
  return function (b) {
    return function (c) {
      return a * b * c;
    };
  };
}

console.log("output with normal function", mul(2)(4)(6)); // 👉 48
```

### Using Arrow Function

```js
const mul = (a) => (b) => (c) => a * b * c;
console.log("output with arrow function", mul(2)(4)(6)); // 👉 48
```

---

## 🔹 5. Promise Example (Resolve if Value < 7)

```js
function fun(a) {
  let myPromise = new Promise((myResolve, myReject) => {
    if (a < 7) {
      myResolve(`number is given ${a}`);
    } else {
      myReject("Error");
    }
  });

  myPromise
    .then((result) => console.log(result))
    .catch((err) => console.log(err));
}

fun(5); // 👉 number is given 5
```

---

## 🔹 6. Multiply Two Numbers Without `*`

```js
function multiply(a, b) {
  let result = 0;
  for (let i = 0; i < Math.abs(b); i++) {
    result += a;
  }
  return b < 0 ? -result : result;
}

console.log(multiply(5, 3));  // 👉 15
console.log(multiply(5, -3)); // 👉 -15
```

---

## 🔹 7. Sorting in JavaScript (Descending Order)

```js
const arr = [3, 2, 5, 4, 1, 0];

for (let i = 0; i < arr.length; i++) {
  for (let j = i + 1; j < arr.length; j++) {
    if (arr[i] < arr[j]) {
      let temp = arr[i];
      arr[i] = arr[j];
      arr[j] = temp;
    }
  }
}

console.log("Sorted in descending order:", arr); 
// 👉 [5, 4, 3, 2, 1, 0]
```

---

## 🔹 8. Object Keys with Object as Key

```js
const a = {};
const b = { key: 'b' };
const c = { key: 'c' };

a[b] = 123;
a[c] = 456;

console.log(a[b]); // 👉 456
```

**Explanation:** Objects used as keys are converted to strings (`[object Object]`), so `a[b]` and `a[c]` overwrite each other.

---

## 🔹 9. Polyfills

### Polyfill for `map`

```js
Array.prototype.myMap = function (callback) {
  let result = [];
  for (let i = 0; i < this.length; i++) {
    result.push(callback(this[i], i, this));
  }
  return result;
};

console.log([1, 2, 3].myMap(x => x * 2)); // 👉 [2, 4, 6]
```

### Polyfill for `filter`

```js
Array.prototype.myFilter = function (callback) {
  let result = [];
  for (let i = 0; i < this.length; i++) {
    if (callback(this[i], i, this)) {
      result.push(this[i]);
    }
  }
  return result;
};

console.log([1, 2, 3, 4].myFilter(x => x % 2 === 0)); // 👉 [2, 4]
```

### Polyfill for `reduce`

```js
Array.prototype.myReduce = function (callback, initialValue) {
  let accumulator = initialValue;
  for (let i = 0; i < this.length; i++) {
    accumulator = callback(accumulator, this[i], i, this);
  }
  return accumulator;
};

console.log([1, 2, 3].myReduce((acc, val) => acc + val, 0)); // 👉 6
```

---

✅ Now you have a **README-ready version** with **questions, explanations, and code**.

Do you also want me to **combine this JavaScript Q\&A + React Q\&A into a single README or PDF cheat sheet** for interviews?

