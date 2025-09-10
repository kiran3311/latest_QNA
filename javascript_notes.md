## 1. Callback
- A function passed as an argument to another function, to be executed later when the task is done.
- Used for asynchronous operations like reading files, making API call
```js
function fetchData(callback) {
  setTimeout(() => {
    callback("Data received");
  }, 2000);
}

fetchData((result) => {
  console.log(result); // "Data received"
});
```

- Problem ❌
  if chain multiple task then may caused callback hell (nasted unreadable code)
  
```js
task1(() => {
  task2(() => {
    task3(() => {
      console.log("Done!");
    });
  });
});

```

---

## 2 Promises
- A special JavaScript object representing the result of an async operation.
- Can be in one of 3 states:
  - pending → initial state
  -  fulfilled → operation successful (.then)
  -  rejected → operation failed (.catch)
 
 ✅ Example (Promise):

```javascript
function fetchData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("Data received");
    }, 2000);
  });
}

fetchData()
  .then((result) => console.log(result))  // success
  .catch((error) => console.error(error)); // failure
```

✅ Promise chaining (cleaner than nested callbacks):

```javascript
fetchData()
  .then((res) => res + " -> processed")
  .then((res) => console.log(res));
```


---

## 3 Callback Hell
“Callback hell happens when we nest too many callbacks. We can handle it by modularizing functions, using Promises with .then(), or better, using async/await which makes the code cleaner and easier to maintain. Utility libraries like async.js can also help.”
**Callback Hell** = deeply nested callbacks, hard to read/maintain/debug.
Example of **Callback Hell**:

```javascript
doTask1((result1) => {
  doTask2(result1, (result2) => {
    doTask3(result2, (result3) => {
      doTask4(result3, (result4) => {
        console.log("All tasks done:", result4);
      });
    });
  });
});
```

---

##3 ✅ Ways to Handle Callback Hell

### 1. **Modularize Functions**

Break callbacks into **named functions** instead of anonymous ones.

```javascript
function step1(result) {
  doTask2(result, step2);
}
function step2(result) {
  doTask3(result, step3);
}
function step3(result) {
  doTask4(result, (final) => console.log("Done:", final));
}

doTask1(step1);
```

👉 Cleaner, but still a callback style.

---

### 2. **Use Promises**

Convert callbacks into **Promises** for chaining.

```javascript
doTask1()
  .then(doTask2)
  .then(doTask3)
  .then(doTask4)
  .then((final) => console.log("Done:", final))
  .catch((err) => console.error(err));
```

---

### 3. **Use Async/Await**

`async/await` makes async code look like synchronous code.

```javascript
async function runTasks() {
  try {
    const result1 = await doTask1();
    const result2 = await doTask2(result1);
    const result3 = await doTask3(result2);
    const result4 = await doTask4(result3);
    console.log("Done:", result4);
  } catch (error) {
    console.error("Error:", error);
  }
}

runTasks();
```

---

### 4. **Use Utility Libraries (like `async.js`)**

Libraries like `async.js` help control flow (`series`, `parallel`, `waterfall`).

```javascript
async.waterfall([
  doTask1,
  doTask2,
  doTask3,
  doTask4
], (err, result) => {
  if (err) console.error(err);
  else console.log("Done:", result);
});
```

---
