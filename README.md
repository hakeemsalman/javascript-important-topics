# Javascript Important Quesetions 

&nbsp; <button onclick="toggleDarkMode()">Toggle Dark Mode</button>

> *Click &#9733; if you like the project. Your contributions are heartily ♡ welcome.*

<br/>

- [Javascript Important Quesetions](#javascript-important-quesetions)
  - [Q 1. What is Execution Context?](#q-1-what-is-execution-context)
  - [Q 2. What is Memory component?](#q-2-what-is-memory-component)
  - [Q 3. What is Code component?](#q-3-what-is-code-component)
  - [Q 4. What is Javascript?](#q-4-what-is-javascript)
  - [Q 5. In which mechanisms Javascript runs the code?](#q-5-in-which-mechanisms-javascript-runs-the-code)
  - [Q 6. What is Hoisting?](#q-6-what-is-hoisting)
  - [Q 8. What is window?](#q-8-what-is-window)
  - [Q 9. What is **this**?](#q-9-what-is-this)


## Q 1. What is Execution Context?

1. Everything in JS happens inside the `execution context`.
2. Imagine a sealed-off container inside which JS runs.
3. It is an abstract concept that hold info about the environment.
4. Within the current code is being executed.

## Q 2. What is Memory component?

- Memory component has all the variables and functions in key value pairs.
- It is also called **Variable environment**.

## Q 3. What is Code component?

- Code component is the place where code is executed one line at a time.
- It is also called the **Thread of Execution**.


<div align="right">
    <b><a href="#javascript-important-quesetions">↥ back to top</a></b>
</div>

## Q 4. What is Javascript?

- JS is a **synchronous**, **single-threaded language**
  - *Synchronous*:- In a specific synchronous order.
  - *Single-threaded*:- One command at a time.
  
## Q 5. In which mechanisms Javascript runs the code?

- Javascript manages code execution context creation and deletion with the the help of **Call Stack**.
- **Call Stack** is a mechanism to keep track of its place in script that calls multiple function.
- Call Stack maintains the order of execution of execution contexts.
- It is also known as *Program Stack*, *Control Stack*, *Runtime stack*, *Machine Stack*, *Execution context stack*.

## Q 6. What is Hoisting?

- **Hoisting** is a concept which enables us to extract values of variables and functions even before initialising/assigning value without getting error.
- This is happening due to the 1st phase (memory creation phase) of the Execution Context.
- ```js
  getName(); // Hello World!
  console.log(x); // undefined
  var x = 7;
  function getName() {
    console.log("Hello World!");
  }

  // xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

  getName(); // Hello World!
  console.log(x); // Uncaught Reference: x is not defined.
  console.log(getName); // f getName(){ console.log("Hello World!"); }
  function getName() {
    console.log("Hello World!");
  }

  // xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

  getName(); // Uncaught TypeError: getName is not a function
  console.log(getName);
  var getName = function () {
    console.log("Hello World!");
  };
  // The code won't execute as the first line itself throws an TypeError.
  ```


<div align="right">
    <b><a href="#javascript-important-quesetions">↥ back to top</a></b>
</div>

## Q 7. What is a Functions?

- A JavaScript function is a block of code designed to perform a particular task.
- A JavaScript function is executed when "something" invokes it (calls it).
- ```js
  var x = 1;
  a();
  b(); // we are calling the functions before defining them. This will work properly, as seen in Hoisting.
  console.log(x);

  function a() {
    var x = 10; // local scope because of separate execution context
    console.log(x);
  }

  function b() {
    var x = 100;
    console.log(x);
  }

  /*
  * Outputs:
    10
    100
    1
  */
  ```

## Q 8. What is window?

- It is an **object**, which is created in the global space.
- It contains lots of functions and variables.
- These functions and variables can be accessed from anywhere in the program.

## Q 9. What is **this**?

- JS engine also creates a **this** keyword, which points to the **window** object at the global level.

```js
var x = 10;
console.log(x); // 10
console.log(this.x); // 10
console.log(window.x); // 10
```

<div align="right">
    <b><a href="#javascript-important-quesetions">↥ back to top</a></b>
</div>
