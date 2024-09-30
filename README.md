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