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




Got it 👍
I’ll give you **detailed interview-style answers** with **examples** for each question.

---

## 1. **What is `<!DOCTYPE html>` in HTML5?**

* The `<!DOCTYPE>` declaration defines the **document type** and tells the browser **which version of HTML** the page is written in.
* In **HTML5**, it’s simplified to:

  ```html
  <!DOCTYPE html>
  ```
* This ensures the browser renders the page in **standards mode** instead of **quirks mode** (which mimics old browsers).

✅ Example:

```html
<!DOCTYPE html>
<html>
<head>
  <title>My HTML5 Page</title>
</head>
<body>
  <h1>Hello HTML5</h1>
</body>
</html>
```

---

## 2. **What is the difference between `<div>` and `<span>` in HTML?**

* **`<div>`**

  * Block-level element.
  * Used to group **larger sections** of content.
  * Starts on a new line by default.
* **`<span>`**

  * Inline element.
  * Used to style or group **small pieces of text** inside a line.

✅ Example:

```html
<div style="background: lightblue;">
  <h2>Title</h2>
  <p>This is a paragraph inside a div.</p>
</div>

<p>This is <span style="color:red;">important</span> text.</p>
```

---

## 3. **What are semantic and non-semantic tags in HTML?**

* **Semantic tags**: Clearly describe their meaning to both browser and developer.

  * Examples: `<header>`, `<footer>`, `<article>`, `<section>`, `<nav>`, `<main>`.
* **Non-semantic tags**: Do not describe content meaning, only structure.

  * Examples: `<div>`, `<span>`.

✅ Example:

```html
<!-- Semantic -->
<header>Website Header</header>
<article>Blog Content</article>
<footer>Contact Info</footer>

<!-- Non-semantic -->
<div class="header">Website Header</div>
<div class="content">Blog Content</div>
<div class="footer">Contact Info</div>
```

---

## 4. **What is the difference between HTML and HTML5?**

* **HTML (older versions)**:

  * Limited multimedia support (needed Flash, Silverlight, etc.).
  * No semantic tags.
  * No local storage or offline features.
* **HTML5**:

  * Supports **audio**, **video**, and **canvas** without plugins.
  * Introduces **semantic elements** (`<article>`, `<section>`, `<nav>`, etc.).
  * Provides **local storage** (`localStorage`, `sessionStorage`).
  * Supports **Geolocation API**, **offline caching**.
  * Supports new form input types (`email`, `date`, `number`, etc.).

✅ Example:

```html
<!-- HTML (old) -->
<object data="song.mp3"></object>

<!-- HTML5 -->
<audio controls>
  <source src="song.mp3" type="audio/mpeg">
</audio>
```

---

## 5. **What is the `<iframe>` tag in HTML5?**

* `<iframe>` stands for **Inline Frame**.
* It is used to embed another webpage/document inside the current webpage.

✅ Example:

```html
<iframe src="https://www.wikipedia.org" width="600" height="400"></iframe>
```

---

## 6. **What are the formatting tags in HTML?**

Formatting tags change the **appearance of text**.
Some common ones:

* `<b>` → Bold
* `<strong>` → Important (semantic)
* `<i>` → Italic
* `<em>` → Emphasized (semantic italic)
* `<u>` → Underlined
* `<mark>` → Highlighted
* `<small>` → Smaller text
* `<del>` → Deleted text (strikethrough)
* `<ins>` → Inserted text (underlined)

✅ Example:

```html
<p>This is <b>bold</b>, <strong>important</strong>, <i>italic</i>, <u>underlined</u>, <mark>highlighted</mark>.</p>
```

---

## 7. **What is the difference between `<b>` and `<strong>` in HTML?**

* `<b>` → Makes text **bold**, but has **no semantic meaning**.
* `<strong>` → Makes text **bold** AND conveys **importance** to browsers and screen readers.

✅ Example:

```html
<p>This is <b>just bold</b>.</p>
<p>This is <strong>important text</strong>.</p>
```

---

## 8. **What is the viewport attribute in HTML?**

* The **viewport** controls how a web page is displayed on mobile devices.
* Defined inside the `<meta>` tag.
* Common usage:

  ```html
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  ```

  * `width=device-width` → matches screen width.
  * `initial-scale=1.0` → sets zoom level.

Without this, mobile sites may look **zoomed out**.

---

## 9. **What is an attribute in HTML?**

* An **attribute** gives additional information about an element.
* Written inside the **opening tag** in `name="value"` format.

✅ Example:

```html
<a href="https://google.com" target="_blank">Visit Google</a>
```

Here:

* `href` = attribute (link destination)
* `target="_blank"` = attribute (open in new tab)

---

## 10. **What are block-level and inline elements in HTML?**

* **Block-level elements**:

  * Take up the full width.
  * Start on a new line.
  * Examples: `<div>`, `<p>`, `<h1>–<h6>`, `<section>`, `<article>`.
* **Inline elements**:

  * Take up only as much width as needed.
  * Do **not** start on a new line.
  * Examples: `<span>`, `<a>`, `<b>`, `<i>`, `<img>`.

✅ Example:

```html
<p>This is a block element</p>
<span>This is inline</span>
<span>and stays on same line</span>
```

---

## 11. **What is the difference between HTML and HTML5?**

(Same as Q4, but if asked again you can keep it short in an interview.)

* **HTML**: Basic structure, no built-in multimedia or semantic tags.
* **HTML5**: Latest version, supports multimedia, semantic tags, APIs (Geo, Storage), better form controls.

✅ Quick Example:

```html
<!-- HTML (old) -->
<input type="text">

<!-- HTML5 -->
<input type="email">
<input type="date">
```

---

✨ That covers **all 11 questions with examples**.



# CSS 


Perfect 👍 Let’s build a **list of CSS interview questions from basic → intermediate → advanced** with answers and examples.
This way you can **revise quickly** and also give **detailed explanations in interviews**.

---

# 🌱 **Basic CSS Questions**

### 1. What is CSS?

* **CSS (Cascading Style Sheets)** is used to style HTML elements (colors, fonts, spacing, layout).
  ✅ Example:

```css
p {
  color: blue;
  font-size: 16px;
}
```

---

### 2. What are the different types of CSS?

1. **Inline CSS** – inside the element.

   ```html
   <p style="color: red;">Hello</p>
   ```
2. **Internal CSS** – inside `<style>` in `<head>`.

   ```html
   <style> p { color: red; } </style>
   ```
3. **External CSS** – in a `.css` file linked via `<link>`.

   ```html
   <link rel="stylesheet" href="style.css">
   ```

---

### 3. Difference between `id` and `class` in CSS?

* `id` → unique, used for **one element**. (`#idName`)
* `class` → reusable, used for **multiple elements**. (`.className`)

✅ Example:

```css
#main { color: red; }
.btn { color: blue; }
```

---

### 4. What are pseudo-classes in CSS?

* Special states of an element.
  ✅ Example:

```css
a:hover { color: red; }   /* when mouse hovers */
input:focus { border: 2px solid blue; }
```

---

### 5. What is the difference between relative, absolute, fixed, and sticky positioning?

* `relative`: positioned relative to itself.
* `absolute`: positioned relative to nearest positioned ancestor.
* `fixed`: positioned relative to **viewport**.
* `sticky`: switches between relative and fixed depending on scroll.

✅ Example:

```css
div { position: absolute; top: 50px; left: 100px; }
```

---

# 🌿 **Intermediate CSS Questions**

### 6. What is the difference between `inline`, `inline-block`, and `block`?

* `inline`: No line break, width/height ignored.
* `block`: Takes full width, new line.
* `inline-block`: Behaves like inline but accepts width/height.

---

### 7. What is the difference between relative units (`em`, `rem`, `%`) and absolute units (`px`, `cm`)?

* `px` = fixed size.
* `em` = relative to **parent element’s font size**.
* `rem` = relative to **root element’s font size**.
* `%` = relative to **parent container**.

✅ Example:

```css
p { font-size: 2em; }   /* 2x parent size */
p { font-size: 2rem; }  /* 2x root size */
```

---

### 8. Explain z-index in CSS.

* Controls the **stacking order** of elements.
* Higher `z-index` → appears on top.

✅ Example:

```css
.box1 { position: absolute; z-index: 1; }
.box2 { position: absolute; z-index: 2; }
```

---

### 9. What is the difference between relative and absolute paths in CSS `url()`?

* **Relative path**: based on file location.
* **Absolute path**: full URL.

✅ Example:

```css
/* Relative */
background: url("images/bg.png");

/* Absolute */
background: url("https://example.com/bg.png");
```

---

### 10. What is the difference between `relative` and `inherit` in CSS values?

* `relative`: modifies the value relative to its current one.
* `inherit`: takes value from parent element.

✅ Example:

```css
p { font-size: inherit; }
```

---

# 🌳 **Advanced CSS Questions**

### 11. What is the difference between CSS Grid and Flexbox?

* **Flexbox**: 1D (row OR column).
* **Grid**: 2D (row AND column).

✅ Example (Grid):

```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr;
}
```

✅ Example (Flexbox):

```css
.container {
  display: flex;
  justify-content: space-between;
}
```

---

### 12. Explain CSS specificity.

* Order of priority:

  1. Inline styles (`style="..."`) → **1000**
  2. ID selectors (`#id`) → **100**
  3. Class/attribute/pseudo-class (`.class`, `:hover`) → **10**
  4. Element/pseudo-element (`p`, `::after`) → **1**

✅ Example:

```css
p { color: blue; }          /* 1 */
p.intro { color: green; }   /* 10 */
#main p { color: red; }     /* 100 */
```

➡️ Final color = red.

---

### 13. What are CSS variables (custom properties)?

* Introduced in **CSS3**, reusable values.

✅ Example:

```css
:root {
  --main-color: #3498db;
}
p {
  color: var(--main-color);
}
```

---

### 14. What is the difference between absolute, relative, fixed, and fluid layouts?

* **Absolute**: fixed pixel values.
* **Relative**: relative to container.
* **Fixed**: based on viewport.
* **Fluid/Responsive**: uses `%`, `vh`, `vw` for flexibility.

---

### 15. What is the difference between `inline-style`, `internal-style`, and `external-style` in terms of performance?

* **Inline** → highest priority, but **bad for maintainability**.
* **Internal** → good for single-page styles.
* **External** → best practice, allows **caching** and reuse.

---

### 16. Explain CSS transitions and animations.

* **Transitions**: animate property changes on event.
* **Animations**: keyframe-based, continuous.

✅ Transition Example:

```css
button {
  background: blue;
  transition: background 0.3s;
}
button:hover { background: red; }
```

✅ Animation Example:

```css
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}
div {
  animation: fadeIn 2s ease-in;
}
```

---

### 17. Difference between relative length units: `%`, `em`, `rem`, `vh`, `vw`.

* `%` → relative to parent.
* `em` → relative to parent font size.
* `rem` → relative to root font size.
* `vh` → relative to viewport height.
* `vw` → relative to viewport width.

---

### 18. Explain difference between `absolute` units (px, pt) and `responsive` units.

* `px`, `pt` → fixed, not responsive.
* `vh`, `vw`, `%`, `em`, `rem` → responsive, scale based on device.

---

### 19. Difference between relative import (`@import`) and `<link>` for CSS.

* `<link>` → better performance, loads in parallel.
* `@import` → slower, loads sequentially.

✅ Example:

```html
<link rel="stylesheet" href="style.css">
```

```css
@import url("style.css");
```

---

### 20. What are media queries in CSS?

* Used to make **responsive designs**.

✅ Example:

```css
@media (max-width: 768px) {
  body { background: lightblue; }
}
```

---

## 🔥 CSS advance -:


---

## 1. **What is difference between CSS and CSS3?**

* **CSS**: The earlier version used for styling HTML.
* **CSS3**: Latest standard, divided into **modules** with new features like:

  * **Media Queries** (responsive design)
  * **Flexbox & Grid** (advanced layout)
  * **Animations & Transitions**
  * **Rounded corners, gradients, shadows**

✅ Example:

```css
/* CSS2 way (basic) */
div {
  background: red;
}

/* CSS3 new features */
div {
  border-radius: 10px;
  box-shadow: 2px 2px 10px gray;
  transition: all 0.3s ease;
}
```

---

## 2. **What are the selectors in CSS?**

Selectors define **which HTML elements** to style.

### Types of selectors:

1. **Universal** – `* { margin: 0; }`
2. **Type** – `p { color: red; }`
3. **Class** – `.title { font-size: 20px; }`
4. **ID** – `#main { background: yellow; }`
5. **Group** – `h1, h2, p { color: blue; }`
6. **Descendant** – `div p { color: green; }`
7. **Child** – `div > p { color: red; }`
8. **Attribute** – `input[type="text"] { border: 1px solid black; }`
9. **Pseudo-class** – `a:hover { color: red; }`
10. **Pseudo-element** – `p::first-letter { font-size: 30px; }`

---

## 3. **What is media query in CSS?**

* Media queries help make a website **responsive** by applying CSS rules **based on device width, height, or orientation**.

✅ Example:

```css
@media (max-width: 768px) {
  body { background: lightblue; }
}
```

---

## 4. **What are different positions in CSS?**

* **static** → Default, no special positioning.
* **relative** → Positioned relative to itself.
* **absolute** → Positioned relative to nearest positioned ancestor.
* **fixed** → Positioned relative to viewport (stays even on scroll).
* **sticky** → Acts like relative, but sticks when scrolling.

✅ Example:

```css
div {
  position: absolute;
  top: 50px;
  left: 100px;
}
```

---

## 5. **What is BOM in CSS?**

⚠️ Trick question → **BOM (Browser Object Model)** is actually a **JavaScript concept**, not CSS.

* It refers to browser objects like `window`, `document`, `navigator`.
  👉 If asked in CSS context → clarify that **BOM is not related to CSS**.

---

## 6. **What is difference between PX, %, em, rem in CSS?**

* `px`: Absolute fixed unit. (not responsive)
* `%`: Relative to **parent container**.
* `em`: Relative to **parent element’s font size**.
* `rem`: Relative to **root (`html`) font size**.

✅ Example:

```css
html { font-size: 16px; }
p { font-size: 2em; }   /* 32px if parent is 16px */
p { font-size: 2rem; }  /* 32px (root font size) */
```

---

## 7. **What is flexbox in CSS?**

* Flexbox (**Flexible Box Layout**) is a 1D layout model to arrange elements in **rows or columns**.
* Provides **alignment, spacing, and ordering** of items.

✅ Example:

```css
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

---

## 8. **What is pseudo selector in CSS?**

* Pseudo-selectors define styles for **special states or parts** of elements.

### Types:

* **Pseudo-classes**: `:hover`, `:focus`, `:nth-child()`.
* **Pseudo-elements**: `::before`, `::after`, `::first-letter`.

✅ Example:

```css
a:hover { color: red; }
p::first-letter { font-size: 30px; }
```

---

## 9. **How to make a website responsive?**

1. Use **relative units** (`%`, `em`, `rem`, `vh`, `vw`).
2. Apply **media queries**.
3. Use **flexbox or grid** for layout.
4. Set **viewport meta tag**:

   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   ```

---

## 10. **What are breakpoints for responsive devices?**

Common breakpoints:

* Extra small devices (mobiles): `max-width: 576px`
* Small devices (tablets): `max-width: 768px`
* Medium devices (laptops): `max-width: 992px`
* Large devices (desktops): `max-width: 1200px`
* Extra large: `max-width: 1400px`

✅ Example:

```css
@media (max-width: 768px) {
  .menu { display: none; }
}
```

---

## 11. **Why do we use box-sizing in CSS?**

* The `box-sizing` property defines how the **width & height** of an element are calculated.

* **content-box** (default): width = only content. Padding & border are extra.

* **border-box**: width = content + padding + border.

✅ Example:

```css
* {
  box-sizing: border-box;  /* easier responsive layouts */
}
```

---

✨ 






