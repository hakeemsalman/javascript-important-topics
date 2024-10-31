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
  - [q 14. What is Local Scope?](#q-14-what-is-local-scope)
  - [Q 15. What is Function scope?](#q-15-what-is-function-scope)
  - [Q 16. What is Block Scope?](#q-16-what-is-block-scope)
  - [Q 17. What is Lexical Environment?](#q-17-what-is-lexical-environment)
  - [Q 18. Scope chain vs Lexical Environment chain?](#q-18-scope-chain-vs-lexical-environment-chain)
    - [1. **Scope Chain**:](#1-scope-chain)
    - [2. **Lexical Environment Chain**:](#2-lexical-environment-chain)
    - [Example for Lexical Environment Chain:](#example-for-lexical-environment-chain)
    - [Summary:](#summary)
  - [Q 19. How `let`, `const` and `var` behave differently in hoisting?](#q-19-how-let-const-and-var-behave-differently-in-hoisting)
    - [Hoisting of `var`](#hoisting-of-var)
  - [Q 24. What is Shadowing?](#q-24-what-is-shadowing)
    - [Shadowing with `let`:](#shadowing-with-let)
    - [Shadowing with `var`:](#shadowing-with-var)
  - [Q 25. What is illegal Shadowing?](#q-25-what-is-illegal-shadowing)
  - [Q 26. What is a Closures?](#q-26-what-is-a-closures)
  - [Q 27. Advantages of Closures?](#q-27-advantages-of-closures)
    - [1. **Encapsulation and Data Privacy**](#1-encapsulation-and-data-privacy)
    - [2. **Maintaining State**](#2-maintaining-state)
    - [3. **Partial Application and Function Currying**](#3-partial-application-and-function-currying)
    - [4. **Callback Functions and Event Handlers**](#4-callback-functions-and-event-handlers)
    - [5. **Creating Factory Functions**](#5-creating-factory-functions)
    - [6. **Avoiding Global Variables**](#6-avoiding-global-variables)
    - [7. **Memoization**](#7-memoization)
    - [8. **Improving Performance**](#8-improving-performance)
    - [Conclusion](#conclusion)
  - [Q 28. What is the output of the below code?](#q-28-what-is-the-output-of-the-below-code)
  - [Q 29. Interview Questions](#q-29-interview-questions)


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
- **Scope** in JavaScript refers to the current context of code, which determines the accessibility of variables to JavaScript.
  - The two types of scope are **local** and **global**
- ```js
  function a() {
    console.log(b); // 10
    // Instead of printing undefined it prints 10, So somehow this a function could access the variable b outside the function scope.
  }
  var b = 10;
  a();
  ```

- ```js
  function a() {
    var b = 10;
    c();
    function c() {
      console.log(b); // 10
    }
  }
  a();
  console.log(b); // Error, Not Defined
  // A function can access a global variable,
  // but the global execution context can't access any local variable.
  ```

## Q 14. What is scope chain?

- The process of going one by one to parent and checking for values is called scope chain or Lexcial environment chain.
- A scope chain is a hierarchical structure of scopes that determines the accessibility of variables and functions within a given context.
- It's like a chain of nested containers, where each container (scope) has access to the variables and functions defined within itself and its parent containers (outer scopes).

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

<div align="right">
    <b><a href="#javascript-important-quesetions">↥ back to top</a></b>
</div>

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
     console.log(functionScopedVar); // Output: I am a local variable
}

localFunctionScope(); 

console.log(functionScopedVar); // Uncaught ReferenceError: functionScopedVar is not defined
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

console.log(blockScopedVar); // Uncaught ReferenceError: blockScopedVar is not defined

console.log(anotherBlockScopedVar); // Uncaught ReferenceError: anotherBlockScopedVar is not defined

console.log(globalVar); // Output: I am global!!!
```


## Q 17. What is Lexical Environment?

- JavaScript engines during the runtime to manage and access the variables based on the Lexical Scope.
- `Lexical Environment` = `local memory` `+` `lexical env of its parent`.
- Hence, Lexical Environement is the local memory along with the lexical environment of its parent
- Whenever an Execution Context is created, a Lexical environment(LE) is also created and is referenced in the local Execution Context(in memory space).

> **Lexical**: In hierarchy, In order

## Q 18. Scope chain vs Lexical Environment chain?

The **scope chain** and the **lexical environment chain** are closely related concepts in JavaScript, both dealing with variable access and execution contexts. However, they differ in terms of their focus and how they are used within JavaScript execution. Let's break them down:
<div align="right">
    <b><a href="#javascript-important-quesetions">↥ back to top</a></b>
</div>

### 1. **Scope Chain**:
The scope chain refers to the mechanism that JavaScript uses to resolve variable names in nested functions or blocks of code. It defines how variables are searched for and accessed when code is executed.

- **Scope** refers to the current context of execution — the context in which values and expressions are "visible" or accessible.
- When a variable is referenced in some function or block, JavaScript will first look for it in the current scope. If it’s not found there, the engine will search in the next outer scope, continuing until it reaches the global scope.
- The scope chain is formed by linking all these nested scopes, allowing for variables to be accessed up the chain.

**Example**:
```javascript
function outer() {
    let a = 10;
    function inner() {
        let b = 20;
        console.log(a); // Can access 'a' from outer scope
    }
    inner();
}
outer();
```

In this case, the scope chain for the `inner` function looks like:
1. `inner` function scope (local variables, e.g., `b`)
2. `outer` function scope (variables from the parent, e.g., `a`)
3. Global scope (if no match is found in outer scopes)

### 2. **Lexical Environment Chain**:

The **lexical environment** is a more abstract concept that refers to how JavaScript handles variable environments at runtime. Each execution context (such as a function or block) is associated with a lexical environment, which consists of:
- **Environment Record**: This contains the actual bindings of variables and their values in the current scope.
- **Outer Lexical Environment Reference**: This points to the lexical environment of the outer scope, forming a chain that links to parent environments.

The **lexical environment chain** allows JavaScript to manage the relationships between different scopes, enabling the scope chain mechanism to function. Each execution context maintains a reference to its lexical environment, which holds variables and function declarations. If a variable cannot be found in the current environment, the engine refers to the outer lexical environment (this forms the lexical environment chain).

**Key Differences**:
- **Scope Chain** is a simpler, more practical concept. It describes how JavaScript resolves variable names by searching through nested scopes.
- **Lexical Environment Chain** is a lower-level, more technical concept that powers the scope chain. It deals with the data structures that JavaScript uses internally (like environment records and references) to manage variables at runtime.

### Example for Lexical Environment Chain:

```javascript
function outer() {
    let a = 10;
    return function inner() {
        let b = 20;
        console.log(a); // Can access 'a' due to lexical environment chain
    }
}
let closure = outer();
closure();  // Still has access to 'a', even after outer() finishes
```

In this case, even after `outer()` finishes executing, the `inner()` function still has access to `a` because its lexical environment was created during the `outer()` execution. This is an example of a **closure**, where the inner function "remembers" the lexical environment in which it was created.

### Summary:
- **Scope Chain**: Describes how JavaScript searches for variables in nested scopes during execution.
- **Lexical Environment Chain**: The underlying mechanism (containing environment records and outer references) that allows the scope chain to work, linking the lexical environments of nested contexts.

Both concepts are tightly connected and are essential for understanding how JavaScript handles variable resolution and closures.

<div align="right">
    <b><a href="#javascript-important-quesetions">↥ back to top</a></b>
</div>

## Q 19. How `let`, `const` and `var` behave differently in hoisting?

> Hoisting is a JavaScript mechanism where variable and function declarations are moved (hoisted) to the top of their scope before code execution.

### Hoisting of `var`

- When you declare a variable using var, it is hoisted to the top of its scope and initialized with undefined.
- So, even though the declaration is at the bottom, you can access the variable at the top, and it will return undefined before it is assigned a valu
- ```js
  console.log(b); // prints 'undefined'
  var b = 15;
  console.log(b); // prints 15
  ```

### Hoisting of `let` and `const`

- `let` and `const` are also hoisted, but they behave differently.
- They are hoisted into the **temporal dead zone** (TDZ), meaning they are hoisted but not initialized before their actual declaration in the code.

- This results in the following behavior:
  - **ReferenceError** is thrown when trying to access a let or const variable before it is initialized.
  - They are not initialized with `undefined` like `var`.
- ```js
  console.log(a); // ReferenceError: Cannot access 'a' before initialization
  let a = 10;
  console.log(a); // prints 10
  ```
  - The variable a is hoisted, but it stays in the **temporal dead zone** (TDZ) until the point in the code where it's assigned the value 10.
  - Until that line, trying to access a will throw a ReferenceError.

- ```js
  console.log(b);  // prints 'undefined'
  console.log(a);  // a is not defined
  var b = 15;
  console.log(b); // prints 15
  console.log(a); // prints 15
  ```
  - Here `a` is not defined
  
## Q 20. What is Temporal Dead Zone (TDZ)

- The **temporal dead zone** is the period between the beginning of the scope (when the variable is hoisted) and the point where the variable is declared and initialized.
- During this period, accessing the variable throws a `ReferenceError`.

## Q 21. Key Differences between `var`, `let`, and `const`
- **`var`**: 
  - Hoisted and initialized with `undefined`.
  - No temporal dead zone, so accessing it before the declaration just gives `undefined`.
  - Variables declared with `var` are attached to the `window` object in the global scope.
  
- **`let`**: 
  - Hoisted but not initialized, meaning accessing it before declaration throws a `ReferenceError` due to the temporal dead zone.
  - Not attached to the `window` object.

- **`const`**: 
  - Similar to `let` in terms of hoisting and the TDZ, but must be initialized at the time of declaration.

## Q 22. Types of Error: Syntax, Reference, and Type.

- Uncaught **ReferenceError**: x is not **defined** at...
  - This Error signifies that x has never been in the scope of the program. This literally means that x was never defined/declared and is being tried to be accesed.

- Uncaught **ReferenceError**: **cannot access** 'a' before initialization
  - This Error signifies that 'a' cannot be accessed because it is declared as 'let' and since it is not assigned a value, it is its Temporal Dead Zone. Thus, this error occurs.

- Uncaught **SyntaxError**: Identifier 'a' has **already** been **declared**
  - This Error signifies that we are redeclaring a variable that is 'let' declared. No execution will take place.

- Uncaught **SyntaxError**: **Missing initializer** in const declaration
  - This Error signifies that we haven't initialized or assigned value to a const declaration.

- Uncaught **TypeError**: **Assignment** to **constant** variable
  - This Error signifies that we are reassigning to a const variable.

> Try using const wherever possible.
> If not, use let, Avoid var.
> Declare and initialize all variables with let to the top to avoid errors to shrink temporal dead zone window to zero.

<div align="right">
    <b><a href="#javascript-important-quesetions">↥ back to top</a></b>
</div>


## Q 23. What is a Block?

- Block aka **compound statement** is used to group JS statements together into 1 group.
- Block is created by **curly braces** `{ ... }`
- ```js
  {    
    var a = 10;
    let b = 20;
    const c = 30;
    // Here let and const are hoisted in Block scope,
    // While, var is hoisted in Global scope.
  }  
      // Block 
  ```
- <details>
    <summary>QUIZ</summary>
    
    ```js
    {
      var a = 10;
      let b = 20;
      const c = 30;
    }
    console.log(a); // 10s
    console.log(b); // Uncaught ReferenceError: b is not defined
    ```

    <details>
      <summary>Reason</summary>

      
      - In the **BLOCK SCOPE**; we get b and c inside it initialized as *undefined* as a part of hoisting (in a seperate memory space called **block**)
      - While, a is stored inside a GLOBAL scope.
      - Thus we say, *let* and *const* are BLOCK SCOPED. They are stored in a separate mem space which is reserved for this block. Also, they can't be accessed outside this block. But var a can be accessed anywhere as it is in global scope. Thus, we can't access them outside the Block.
      

    </details>
  </details>

<div align="right">
    <b><a href="#javascript-important-quesetions">↥ back to top</a></b>
</div>


## Q 24. What is Shadowing?

- Shadowing in JavaScript refers to a situation where a variable in a local scope (like inside a function or block) has the same name as a variable in an outer scope.
- In such cases, the inner variable **shadows** or **hides** the outer variable within its scope, making the outer variable inaccessible until the inner scope finishes execution.

### Shadowing with `let`:

- With `let` and `const`Shadowing can happen in both **function** and **block** level/

```js
let x = 10; // outer variable

function myFunction() {
    let x = 20; // inner variable shadows the outer one
    console.log(x); // prints 20 (inner 'x' shadows the outer 'x')
}

myFunction();
console.log(x); // prints 10 (outer 'x' is still accessible)
```

### Shadowing with `var`:

- variables declared with `var` DO NOT have **block** scope. They are **function-scoped**.
- This can lead to some confusing shadowing behavior:

```js
// BLOCK LEVEL
// -------------
var y = 30;
if (true) {
    var y = 40; // This will overwrite the outer 'y' due to function scope of 'var'
    console.log(y); // 40
}
console.log(y); // 40 (the outer 'y' has been modified)



// FUNCTION LEVEL
// --------------
var x = 10; // global scope
function myFunction() {
    var x = 20; // shadows the global 'x' inside the function
    console.log(x); // 20 (local 'x' shadows global 'x' within the function)
}

myFunction();
console.log(x); // 10 (global 'x' remains unaffected)

```

<div align="right">
    <b><a href="#javascript-important-quesetions">↥ back to top</a></b>
</div>

## Q 25. What is illegal Shadowing?

- **Illegal shadowing** in JavaScript occurs when a variable declared with `let` or `const` in a global scope attempts to shadow a variable declared with `var` in the same or a broader scope, in such a way that it breaks the scope rules of JavaScript. 
- But it is **valid** to shadow a `let` using a `let`. However, we can shadow var with let.
```js
// Shadowing
var a = 20;
{
  let a = 10;
  console.log(a)  // 10
}
console.log(a)    // 20
```

```js
// Illegal shadowing
let a = 20;
{
  var a = 10;   // SyntaxError: Identifier 'a' has already been declared
  console.log(a)
}
console.log(a)
```

## Q 26. What is a Closures?

-  **Closure** is a function that has access to its outer function scope even after the function has returned.
-  A closure can remember and access variables and arguments reference of its outer function even after the function has returned.
-  ```js
  function z() {
    var b = 900;
    function x() {
      var a = 7;
      function y() {
        console.log(a, b);
      }
      y();
    }
    x();
  }
  z(); // 7 900
  ```
- ```js
  function x() {
    var a = 7;
    function y() {
      console.log(a);
    }
    return y;
  }
  var z = x();
  console.log(z); // value of z is entire code of function y.
  ```

## Q 27. Advantages of Closures?

Closures are a powerful feature in JavaScript and many other programming languages that allow a function to retain access to its lexical scope even when that function is executed outside of its original scope. Here are some key advantages of using closures:

### 1. **Encapsulation and Data Privacy**
Closures allow you to create private variables. A closure can "enclose" variables in a function scope, preventing them from being accessed directly from outside. This is useful for creating modules or libraries where you want to hide certain data from the global scope.

**Example:**
```javascript
function createCounter() {
    let count = 0; // Private variable
    return {
        increment: function() {
            count++;
            return count;
        },
        decrement: function() {
            count--;
            return count;
        },
        getCount: function() {
            return count;
        }
    };
}

const counter = createCounter();
console.log(counter.increment()); // 1
console.log(counter.increment()); // 2
console.log(counter.getCount()); // 2
console.log(counter.decrement()); // 1
```

### 2. **Maintaining State**
Closures can be used to maintain state in an asynchronous environment, such as event handlers, callbacks, or promises. This is useful in situations where you want to remember data between function calls.

**Example:**
```javascript
function makeGreeting(greeting) {
    return function(name) {
        return `${greeting}, ${name}!`;
    };
}

const sayHello = makeGreeting('Hello');
console.log(sayHello('Alice')); // "Hello, Alice!"
```

### 3. **Partial Application and Function Currying**
Closures enable partial application and currying, allowing you to create specialized versions of functions that can be reused with preset parameters.

**Example:**
```javascript
function multiply(factor) {
    return function(number) {
        return number * factor;
    };
}

const double = multiply(2);
console.log(double(5)); // 10
```

### 4. **Callback Functions and Event Handlers**
Closures are widely used in callback functions and event handlers. They allow you to retain access to variables in the scope where the callback was defined.

**Example:**
```javascript
function setTimeoutWithClosure() {
    for (var i = 0; i < 3; i++) {
        setTimeout(function() {
            console.log(i); // Outputs 3 three times due to closure capturing the loop variable
        }, 1000);
    }
}

setTimeoutWithClosure(); // Outputs 3 three times
```

To fix this issue, you can use an IIFE (Immediately Invoked Function Expression) to create a new scope:

```javascript
function setTimeoutWithIIFE() {
    for (var i = 0; i < 3; i++) {
        (function(i) {
            setTimeout(function() {
                console.log(i); // Outputs 0, 1, 2
            }, 1000);
        })(i);
    }
}

setTimeoutWithIIFE(); // Outputs 0, 1, 2
```

### 5. **Creating Factory Functions**
Closures can be used to create factory functions that generate other functions. This is helpful for creating functions with similar behavior but different configurations.

**Example:**
```javascript
function createMultiplier(factor) {
    return function(x) {
        return x * factor;
    };
}

const triple = createMultiplier(3);
console.log(triple(5)); // 15
```

### 6. **Avoiding Global Variables**
Closures can help avoid polluting the global namespace by allowing you to encapsulate variables and functions within a local scope, preventing them from being accessed globally.

**Example:**
```javascript
(function() {
    var localVariable = 'I am local!';
    
    function showLocal() {
        console.log(localVariable);
    }

    showLocal(); // Outputs: "I am local!"
})();

console.log(typeof localVariable); // undefined
```

### 7. **Memoization**
Closures can be used to implement memoization, which is an optimization technique that caches results of expensive function calls and returns the cached result when the same inputs occur again.

**Example:**
```javascript
function memoize(fn) {
    const cache = {};
    return function(...args) {
        const key = JSON.stringify(args);
        if (cache[key]) {
            return cache[key];
        }
        const result = fn(...args);
        cache[key] = result;
        return result;
    };
}

const add = (a, b) => a + b;
const memoizedAdd = memoize(add);
console.log(memoizedAdd(1, 2)); // 3 (calculated)
console.log(memoizedAdd(1, 2)); // 3 (cached)
```

### 8. **Improving Performance**
Closures can help improve performance by allowing the reuse of variables within their scope without needing to pass them around, which can reduce the overhead of creating new variables or objects in certain situations.

### Conclusion
Closures are a fundamental concept in JavaScript that offer numerous advantages, including data privacy, state maintenance, and powerful functional programming techniques. They allow for more flexible and modular code, leading to better maintainability and readability. Understanding closures is essential for becoming proficient in JavaScript and using it effectively in complex applications. If you have any further questions or need examples on specific use cases, feel free to ask!

<div align="right">
    <b><a href="#javascript-important-quesetions">↥ back to top</a></b>
</div>


## Q 28. What is the output of the below code?

```js
function x() {
  var i = 1;
  setTimeout(function () {
    console.log(i);
  }, 3000);
  console.log("Hello world");
}
x();
```

<details>
  <summary>SHOW SOLUTION</summary>

  ```console
  Hello world
  1 // after waiting 3 seconds
  ```

</details>


## Q 29. Interview Questions


```js
function x() {
  for (var i = 1; i <= 5; i++) {
    setTimeout(function () {
      console.log(i);
    }, i * 1000);
  }
  console.log("Hello world");
}
x();
```

<details>
  <summary>SHOW SOLUTION</summary>

  ```js
  // Output:
  // Hello world
  // 6
  // 6
  // 6
  // 6
  // 6
  ```

</details>

- To avoid this, we can use `let` instead of `var` as `let` has Block scope. For each iteration, the `i` is a new variable altogether(new copy of `i`).
- Everytime setTimeout is run, the inside function forms closure with new variable `i`
- But what if interviewer ask us to implement using `var` **only**?
- ```js
  function x() {
    for (var i = 1; i <= 5; i++) {
      function close(i) {
        setTimeout(function () {
          console.log(i);
        }, i * 1000);
        // put the setT function inside new function close()
      }
      close(i); // everytime you call close(i) it creates new copy of i. Only this time, it is with var itself!
    }
    console.log("Hello world");
  }
  x();
```


<div align="right">
    <b><a href="#javascript-important-quesetions">↥ back to top</a></b>
</div>