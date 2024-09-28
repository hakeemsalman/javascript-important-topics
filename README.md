# Javascript Important Quesetions 

<!-- &nbsp; <button onclick="toggleDarkMode()">Toggle Dark Mode</button> -->

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
  - [Q 9. What is **this** keyword?](#q-9-what-is-this-keyword)
  - [Q 10. When variable is assigned as a **undefined**?](#q-10-when-variable-is-assigned-as-a-undefined)
  - [Q 10. When variable is assigned as a **NOT defined**?](#q-10-when-variable-is-assigned-as-a-not-defined)
  - [Q 11. Difference b/w **undefined** and **NOT defined**](#q-11-difference-bw-undefined-and-not-defined)
  - [Q 13. What is Global Scope?](#q-13-what-is-global-scope)
  - [q 14. What is Local Scope?](#q-14-what-is-local-scope)
  - [Q 15. What is Function scope?](#q-15-what-is-function-scope)
  - [Q 16. What is Block Scope?](#q-16-what-is-block-scope)
  - [Q 14. What is Lexical Environment?](#q-14-what-is-lexical-environment)
  - [Q 14. What is scope chain?](#q-14-what-is-scope-chain)


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
  - JS is a **loosely typed** / **weakly typed** language. 
  
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
- If we create any variable in the global scope, then the variables get attached to the global object.

## Q 9. What is **this** keyword?

- JS engine also creates a **this** keyword, which points to the **window** object at the global level.
- At global level, `this` `===` `window`

```js
var x = 10;
console.log(x); // 10
console.log(this.x); // 10
console.log(window.x); // 10
```

<div align="right">
    <b><a href="#javascript-important-quesetions">↥ back to top</a></b>
</div>

## Q 10. When variable is assigned as a **undefined**?

- In first phase (memory allocation) JS assigns each variable a placeholder called **undefined**.
- **undefined** is when memory is allocated for the variable, but no value is assigned yet.

## Q 10. When variable is assigned as a **NOT defined**?

- If an object/variable is not even declared/found in memory allocation phase, and tried to access it then it is **Not defined**
- `Not Defined !== Undefined`


## Q 11. Difference b/w **undefined** and **NOT defined**

- When variable is declared but not assigned value, its current value is undefined.
- But when the variable itself is not declared but called in code, then it is not defined.
- ```js
  console.log(x); // undefined
  var x = 25;
  console.log(x); // 25
  console.log(a); // Uncaught ReferenceError: a is not defined
  ```

> **Never** assign `undefined` to a variable *manually*. Let it happen on it's own accord.

<div align="right">
    <b><a href="#javascript-important-quesetions">↥ back to top</a></b>
</div>


## Q 12. What is Scope?

- **Scope** in Javascript is directly related to **Lexical Environment**.
- ```js
  function a() {
    console.log(b); // 10
    // Instead of printing undefined it prints 10, So somehow this a function could access the variable b outside the function scope.
  }
  var b = 10;
  a();

  // xxxxxxxxxxxxxxxxxxxxxxxxxx

  function a() {
    var b = 10;
    c();
    function c() {
      console.log(b); // 10
    }
  }
  a();
  console.log(b); // Error, Not Defined
  // A function can access a global variable, but the global execution context can't access any local variable.
  ```

## Q 13. What is Global Scope?

- When a variable is declared outside any function, it belongs to the Global Scope.
- This means it can be accessed and modified from any other part of the code,
  
<details>
<summary>SHOW CODE</summary>

```js
var globalVar = "I am a global variable";

function accessGlobalVar() {
    // Accessing the global variable within a function
    console.log(globalVar);
}

accessGlobalVar(); // Output: I am a global variable
console.log(globalVar); // Output: I am a global variable
```

</details>

## q 14. What is Local Scope?

- It refers to variables declared within a **function** or a **block** (in case of `let` and `const` in ES6)
- These variables are only accessible within that function or block, making them hidden from the rest of the program.

## Q 15. What is Function scope?

- Variables declared within a function using `var`, `let`, or `const` are scoped to the function.

<details>
<summary>SHOW CODE</summary>

```js
function localFunctionScope() {
     var functionScopedVar = "I am a local variable";
     // Output: I am a local variable
     console.log(functionScopedVar);
}

localFunctionScope(); // Output: I am a local variable
// Uncaught ReferenceError: functionScopedVar is not defined
console.log(localVar);
```

</details>

## Q 16. What is Block Scope?

- Introduced in ES6 with `let` and `const`, variables declared inside a block `{}` are only accessible within that block.

```js
if (true) {
     let blockScopedVar = "I am block-scoped";
     const anotherBlockScopedVar = "So am I";
     var globalVar = "I am global!!!";
     console.log(blockScopedVar); // Accessible here
     console.log(anotherBlockScopedVar); // Accessible here
}

// Uncaught ReferenceError: blockScopedVar is not defined
console.log(blockScopedVar);
// Uncaught ReferenceError: anotherBlockScopedVar
// is not defined
console.log(anotherBlockScopedVar);
// Output: I am global!!!
console.log(globalVar);
```


## Q 14. What is Lexical Environment?

- JavaScript engines during the runtime to manage and access the variables based on the Lexical Scope.
- `Lexical Environment` = `local memory` `+` `lexical env of its parent`.
- Hence, Lexical Environement is the local memory along with the lexical environment of its parent
- Whenever an Execution Context is created, a Lexical environment(LE) is also created and is referenced in the local Execution Context(in memory space).

> **Lexical**: In hierarchy, In order

## Q 14. What is scope chain?

- The process of going one by one to parent and checking for values is called scope chain or Lexcial environment chain.

<div align="right">
    <b><a href="#javascript-important-quesetions">↥ back to top</a></b>
</div>

