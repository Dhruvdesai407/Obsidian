-----

# Deep JS Foundations - Course Summary

This summary provides a deep dive into JavaScript's core concepts, emphasizing understanding *how* the language works to write more effective and resilient code. It covers Type Coercion, `this` Binding, Prototypes, and Scope, reflecting the course's focus on foundational knowledge.

## Table of Contents

1.  [I. Types](https://www.google.com/search?q=%23i-types)
      * [Primitive Types](https://www.google.com/search?q=%23primitive-types)
      * [Special Values](https://www.google.com/search?q=%23special-values)
      * [Abstract Operations (Coercion)](https://www.google.com/search?q=%23abstract-operations-coercion)
      * [Equality (`==` vs. `===`)](https://www.google.com/search?q=%23equality--vs-)
      * [TypeScript, Flow, etc.](https://www.google.com/search?q=%23typescript-flow-etc)
2.  [II. Objects (Oriented)](https://www.google.com/search?q=%23ii-objects-oriented)
      * [`this` Keyword](https://www.google.com/search?q=%23this-keyword)
      * [`class { }` (ES6 Classes)](https://www.google.com/search?q=%23class--es6-classes)
      * [Prototypes](https://www.google.com/search?q=%23prototypes)
      * [OO vs. OLOO (Object-Oriented vs. Objects Linked to Other Objects)](https://www.google.com/search?q=%23oo-vs-oloo-object-oriented-vs-objects-linked-to-other-objects)
3.  [III. Scope](https://www.google.com/search?q=%23iii-scope)
      * [Nested Scope](https://www.google.com/search?q=%23nested-scope)
      * [Hoisting](https://www.google.com/search?q=%23hoisting)
      * [Closure](https://www.google.com/search?q=%23closure)
      * [Modules](https://www.google.com/search?q=%23modules)

-----

## I. Types

In JavaScript, variables do not have types; *values* do. This is a crucial distinction. JavaScript is dynamically typed, meaning type checking happens at runtime.

### Primitive Types

JavaScript has several built-in primitive types. These are immutable and not objects (except `null` which `typeof` incorrectly reports as "object").

  * **`undefined`**: Represents a variable that has been declared but has not yet been assigned a value. It's the default return value of functions that don't explicitly return anything.

    ```javascript
    var v;
    console.log(typeof v); // "undefined"
    ```

    Distinguish `undefined` from `undeclared` (never declared) and `uninitialized` (in the Temporal Dead Zone for `let`/`const`).

  * **`string`**: For textual data.

    ```javascript
    v = "Hello, World!";
    console.log(typeof v); // "string"
    ```

  * **`number`**: For numeric data, including integers and floating-point numbers.

    ```javascript
    v = 42;
    console.log(typeof v); // "number"
    v = 3.14159;
    console.log(typeof v); // "number"
    ```

  * **`boolean`**: For `true` or `false` values.

    ```javascript
    v = true;
    console.log(typeof v); // "boolean"
    ```

  * **`object`**: While `typeof` returns "object" for various complex data structures, `object` itself is not a primitive but a category for mutable, keyed collections.

    ```javascript
    v = {};             // Plain object
    console.log(typeof v); // "object"
    v = [1, 2, 3];      // Array
    console.log(typeof v); // "object"
    v = null;           // This is a long-standing bug; `null` is a primitive.
    console.log(typeof v); // "object" (incorrectly)
    ```

  * **`symbol`**: Introduced in ES6, used for unique identifiers, often for object properties that are not prone to naming collisions.

    ```javascript
    v = Symbol("unique-id");
    console.log(typeof v); // "symbol"
    ```

  * **`null`**: A primitive value representing the intentional absence of any object value. It's a "falsy" value.

  * **`bigint`**: A newer primitive (ES2020) for arbitrarily large integers.

    ```javascript
    var bigNum = 9007199254740991n; // Add 'n' for BigInt literal
    console.log(typeof bigNum);     // "bigint"
    ```

### Special Values

  * **`NaN` ("Not a Number")**:
    Represents an invalid or unrepresentable numeric value resulting from failed numeric operations.

      * **Key characteristic**: `NaN` is the *only* value in JavaScript that is not equal to itself (`NaN === NaN` is `false`).
      * **Reliable check**: Always use `Number.isNaN()` for accurate checks. The global `isNaN()` can be misleading as it coerces its argument to a number.

    <!-- end list -->

    ```javascript
    var myCatsAge = Number("n/a"); // Coerces "n/a" to NaN
    console.log(myCatsAge);        // NaN
    console.log(myCatsAge === myCatsAge); // false

    console.log(isNaN(myCatsAge));      // true (correct)
    console.log(isNaN("my son's age")); // true (incorrect, due to coercion of "my son's age" to NaN)

    console.log(Number.isNaN(myCatsAge));      // true (correct)
    console.log(Number.isNaN("my son's age")); // false (correct, "my son's age" is not the primitive NaN)
    ```

  * **`-0` (Negative Zero)**:
    A distinct numeric value from `0` in specific mathematical contexts (e.g., division by `-0` yields negative infinity). However, most equality checks treat `0` and `-0` as equal.

      * **Distinguishing them**: Use `Object.is()` for strict differentiation.

    <!-- end list -->

    ```javascript
    var trendRate = -0;
    console.log(trendRate === -0); // true
    console.log(trendRate === 0);  // true (OOPS!)
    console.log(trendRate < 0);    // false
    console.log(trendRate > 0);    // false

    console.log(Object.is(trendRate, -0)); // true
    console.log(Object.is(trendRate, 0));  // false
    ```

    `Math.sign(-0)` returns `-0`, `Math.sign(0)` returns `0`.

### Abstract Operations (Coercion)

Coercion refers to JavaScript's automatic type conversions. These are implicit (happening without explicit code) and pervasive. The course argues that understanding and intentionally leveraging coercion is key to writing robust JavaScript.

  * **`ToPrimitive(hint)`**: An internal operation that converts an object to a primitive value. It prioritizes `valueOf()` or `toString()` methods based on a "hint" (e.g., "number" or "string").

    ```javascript
    var obj = {
        valueOf: function() { return 42; },
        toString: function() { return "hello"; }
    };
    console.log(Number(obj)); // 42 (ToPrimitive with 'number' hint calls valueOf)
    console.log(String(obj)); // "hello" (ToPrimitive with 'string' hint calls toString)
    ```

  * **`ToString`**: Converts any value to its string representation.

    ```javascript
    console.log(String(null));          // "null"
    console.log(String(undefined));     // "undefined"
    console.log(String(true));          // "true"
    console.log(String(3.14));          // "3.14"
    console.log(String([]));            // "" (empty array)
    console.log(String([1, 2, 3]));     // "1,2,3"
    console.log(String({}));            // "[object Object]"
    console.log(String({ toString(){ return "Custom"; } })); // "Custom"
    ```

    **Implicit `ToString`**: Occurs in template literals and string concatenation.

    ```javascript
    var numStudents = 16;
    console.log(`There are ${numStudents} students.`);    // "There are 16 students."
    console.log("There are " + numStudents + " students."); // "There are 16 students."
    ```

  * **`ToNumber`**: Converts any value to its numeric representation.

    ```javascript
    console.log(Number(""));           // 0
    console.log(Number("   007 "));    // 7
    console.log(Number(true));          // 1
    console.log(Number(false));         // 0
    console.log(Number(null));          // 0
    console.log(Number(undefined));     // NaN
    console.log(Number([]));            // 0 (empty array)
    console.log(Number([1, 2, 3]));     // NaN (array with multiple numbers)
    console.log(Number(["42"]));        // 42 (single numeric string in array)
    ```

    **Implicit `ToNumber`**: Occurs with mathematical operators (except `+`), unary `+`.

    ```javascript
    function kickStudentOut(numStudentsInput) {
        // If numStudentsInput is "16", it's coerced to 16 before subtraction.
        return numStudentsInput - 1;
    }
    console.log(kickStudentOut("16")); // 15
    console.log(+"5"); // 5 (unary plus for explicit ToNumber)
    ```

  * **`ToBoolean`**: Converts any value to a boolean. Values are categorized as `Falsy` or `Truthy`.

      * **Falsy values**: `""` (empty string), `0`, `-0`, `null`, `NaN`, `false`, `undefined`.
      * **Truthy values**: All other values, including empty objects (`{}`) and empty arrays (`[]`).

    <!-- end list -->

    ```javascript
    console.log(Boolean(""));          // false
    console.log(Boolean(" \t\n"));     // true (string with only whitespace is truthy)
    console.log(Boolean(0));           // false
    console.log(Boolean(1));           // true
    console.log(Boolean(null));        // false
    console.log(Boolean(undefined));   // false
    console.log(Boolean({}));          // true (empty object)
    console.log(Boolean([]));          // true (empty array)
    ```

    **Implicit `ToBoolean`**: Occurs in `if` statements, `while` loops, `&&` (logical AND), `||` (logical OR), and the ternary operator (`? :`).

    ```javascript
    var username = "";
    if (username) { // username (empty string) is falsy, so block is skipped
        console.log("Welcome " + username);
    } else {
        console.log("Please enter username."); // "Please enter username."
    }

    var items = [1, 2, 3];
    while (items.length) { // items.length (e.g., 3, 2, 1) is truthy; 0 is falsy
        items.pop();
        console.log(items);
    } // [1,2], [1], []
    ```

### Equality (`==` vs. `===`)

The course advocates for understanding both operators and using them appropriately, rather than dogmatically preferring `===`.

  * **`==` (Loose Equality / Coercive Equality)**:
    Allows coercion. If operand types differ, JavaScript attempts to convert one or both to a common type before comparison.

      * If types are the same, `==` behaves identically to `===`.
      * **Special case**: `null == undefined` is `true`. This is a useful coercion indicating a "missing" value.
        ```javascript
        var workshop1 = { topic: null };
        var workshop2 = {}; // workshop2.topic is undefined
        console.log(workshop1.topic == null); // true (null == null)
        console.log(workshop2.topic == null); // true (undefined == null)
        ```
      * **Rules for `==`**:
          * `Number == String`: String is converted to Number.
          * `Boolean == Any`: Boolean is converted to Number (`true` to 1, `false` to 0).
          * `Object == Primitive`: Object is converted to Primitive (`ToPrimitive`).
      * **Benefit**: Can lead to more readable code when the expected coercions are known and intentional.

  * **`===` (Strict Equality / Non-Coercive Equality)**:
    Disallows coercion. If operand types differ, it immediately returns `false`. Only compares values if types are identical.

    ```javascript
    console.log(42 == "42");   // true (string "42" coerced to number 42)
    console.log(42 === "42");  // false (types are different)

    console.log(null == undefined); // true
    console.log(null === undefined); // false

    console.log(0 == false);   // true (false coerced to 0)
    console.log(0 === false);  // false
    ```

    For objects, both `==` and `===` check for *identity* (same reference in memory), not structural equality.

    ```javascript
    var obj1 = { id: 1 };
    var obj2 = { id: 1 };
    console.log(obj1 == obj2);  // false (different objects)
    console.log(obj1 === obj2); // false (different objects)
    ```

    **Recommendation**: Use `==` when you know the types and the coercion is helpful and predictable (e.g., `value == null`). Use `===` when you don't know or trust the types, or when you explicitly want to prevent *any* coercion. The goal is "plain and obvious" value types.

### TypeScript, Flow, etc.

These are static type checkers that add a type layer on top of JavaScript. They provide benefits like compile-time error detection, improved IDE tooling, and explicit type communication in code. However, the course posits that they can also be an "avoidance" strategy, preventing developers from deeply understanding JavaScript's native dynamic type system. It advocates for leveraging JavaScript's built-in behaviors rather than trying to mimic other languages' type systems.

-----

## II. Objects (Oriented)

JavaScript is a multi-paradigm language that supports object-oriented programming primarily through its prototype system.

### `this` Keyword

`this` refers to the *execution context* of a function call. Its value is determined *entirely by how the function was called*, not where it was defined. This dynamic binding is a powerful feature for creating reusable functions.

  * **`this` Binding Rules (in order of precedence)**:

    1.  **`new` Binding**: When a function is called with the `new` keyword (a "constructor call"), a new object is created, linked to the constructor function's prototype, and `this` inside the function is bound to this new object.

        ```javascript
        function Person(name) {
            this.name = name; // 'this' refers to the newly created object
        }
        var john = new Person("John");
        console.log(john.name); // "John"
        ```

    2.  **Explicit Binding (`call()`, `apply()`, `bind()`)**: These methods allow you to explicitly set the `this` context for a function call.

          * `call()` and `apply()`: Immediately invoke the function with `this` set to the first argument. `call()` takes arguments individually, `apply()` takes them as an array.
            ```javascript
            function sayHello(greeting) {
                console.log(`${greeting}, I'm ${this.name}`);
            }
            var user = { name: "Alice" };
            sayHello.call(user, "Hi");    // Hi, I'm Alice (explicitly sets 'this' to 'user')
            sayHello.apply(user, ["Hey"]); // Hey, I'm Alice
            ```
          * `bind()`: Creates a *new function* with `this` permanently bound to a specified object. It doesn't invoke the function immediately.
            ```javascript
            var boundSayHello = sayHello.bind(user, "Greetings");
            boundSayHello(); // Greetings, I'm Alice
            ```

    3.  **Implicit Binding**: If a function is called as a method of an object (`obj.method()`), `this` refers to the `obj` (the "context object") that owns the method.

        ```javascript
        var teacher = {
            name: "Kyle",
            greet: function() {
                console.log(`Hello, I'm ${this.name}`);
            }
        };
        teacher.greet();       // Hello, I'm Kyle ('this' is 'teacher')

        var anotherGreet = teacher.greet;
        anotherGreet();        // Hello, I'm undefined (or "Hello, I'm [global object name]").
                               // 'this' falls back to default binding because 'anotherGreet'
                               // is just a function reference, not called as a method.
        ```

    4.  **Default Binding**: If none of the above rules apply, `this` defaults to the global object (e.g., `window` in browsers, `global` in Node.js). In strict mode (`"use strict"`), `this` defaults to `undefined`.

        ```javascript
        function showThis() {
            console.log(this);
        }
        showThis(); // In non-strict mode: window (browser) / global (Node)
                    // In strict mode: undefined
        ```

  * **Arrow Functions (`=>`)**:
    Arrow functions *do not have their own `this` binding*. Instead, they lexically inherit `this` from their *enclosing scope* at the time they are defined. They are often used for callbacks to avoid `this` context issues, as they preserve the `this` from their surrounding non-arrow function.

    ```javascript
    var workshop = {
        title: "JS Foundations",
        students: ["Alice", "Bob"],
        printStudents: function() {
            // 'this' here refers to 'workshop' due to implicit binding
            this.students.forEach(student => {
                // Arrow function inherits 'this' from 'printStudents' function (which is 'workshop')
                console.log(`${student} enrolled in ${this.title}`);
            });
        }
    };
    workshop.printStudents();
    // Alice enrolled in JS Foundations
    // Bob enrolled in JS Foundations
    ```

### `class { }` (ES6 Classes)

Introduced in ES6, the `class` syntax is primarily "syntactic sugar" over JavaScript's existing prototype-based inheritance. It provides a more familiar, class-based object-oriented syntax (`constructor`, `extends`, `super`).
However, it's critical to remember that `this` inside methods of ES6 classes *still follows the dynamic binding rules*. If a class method is detached from its instance and called as a standalone function (e.g., passed as a callback without binding), its `this` context will change.

```javascript
class Teacher {
    constructor(name) {
        this.name = name;
    }
    // 'this' in `greet` will refer to the instance of Teacher when called as a method
    greet() {
        console.log(`Hello, I'm ${this.name}`);
    }
}

const kyle = new Teacher("Kyle");
kyle.greet(); // Hello, I'm Kyle (implicit binding)

const looseGreet = kyle.greet;
looseGreet(); // Hello, I'm undefined (default binding, because it's not called as a method)

// To fix:
const boundGreet = kyle.greet.bind(kyle);
boundGreet(); // Hello, I'm Kyle

// Or use an arrow function property in the class (experimental but common):
class TeacherWithBoundGreet {
    constructor(name) {
        this.name = name;
    }
    greet = () => { // Arrow function binds 'this' lexically to the instance
        console.log(`Hello, I'm ${this.name}`);
    }
}
const susan = new TeacherWithBoundGreet("Susan");
const looseGreetSusan = susan.greet;
looseGreetSusan(); // Hello, I'm Susan (due to lexical 'this' in arrow function)
```

### Prototypes

JavaScript uses a prototype chain for inheritance. Every object has a hidden `[[Prototype]]` link to another object, its prototype. When you try to access a property or method on an object, if it's not found directly on that object, JavaScript traverses up this `[[Prototype]]` chain until it finds the property or reaches the end of the chain.

  * Objects are typically created by "constructor calls" (using `new`), which sets up this prototype linkage.
  * The `Object.create()` method allows you to explicitly create a new object with a specified prototype.
    ```javascript
    // Constructor function approach
    function Animal(name) {
        this.name = name;
    }
    Animal.prototype.speak = function() {
        console.log(`${this.name} makes a noise.`);
    };

    var dog = new Animal("Dog");
    dog.speak(); // Dog makes a noise. (The 'speak' method is found on 'Animal.prototype' via the prototype chain)

    // Check prototype chain linkage
    console.log(dog.__proto__ === Animal.prototype); // true (in browsers/Node)
    console.log(Object.getPrototypeOf(dog) === Animal.prototype); // true (preferred way)

    // Object.create() approach (more direct for OLOO)
    var animalPrototype = {
        speak: function() {
            console.log(`${this.name} makes a noise.`);
        }
    };

    var cat = Object.create(animalPrototype); // 'cat' delegates to 'animalPrototype'
    cat.name = "Cat";
    cat.speak(); // Cat makes a noise.
    ```

### OO vs. OLOO (Object-Oriented vs. Objects Linked to Other Objects)

  * **Object-Oriented (OO)**: Often associated with classical, class-based inheritance paradigms found in languages like Java or C++. While JavaScript has `class` syntax, its underlying inheritance mechanism is prototypal.
  * **Objects Linked to Other Objects (OLOO)**: Also known as **Behavior Delegation**. This paradigm aligns more closely with JavaScript's natural prototypal inheritance. Instead of defining "classes" to be "instantiated," OLOO focuses on creating objects that *delegate* behavior to other existing objects (their prototypes).
      * This promotes the principle of **Composition over Inheritance**, where functionality is built by composing objects that delegate to other objects for their behavior, rather than relying on deep, rigid inheritance hierarchies.
      * OLOO often leads to simpler, more flexible, and more testable designs compared to class-centric approaches in JavaScript.
    <!-- end list -->
    ```javascript
    // OLOO / Behavior Delegation Example
    var LoginController = {
        errors: [],
        usernameInput: "",
        passwordInput: "",
        // ... (other shared behaviors)
        getLoginInfo() {
            // ... retrieve info from inputs
            this.usernameInput = "user"; // example
            this.passwordInput = "pass"; // example
        },
        displayErrors() {
            console.log("Login Errors:", this.errors.join(", "));
        }
    };

    var AuthController = Object.create(LoginController); // AuthController delegates to LoginController
    AuthController.errors = ["Invalid credentials"]; // AuthController has its own 'errors' property
    AuthController.login = function(user, pw) {
        this.getLoginInfo(); // 'this' is AuthController, which delegates to LoginController's getLoginInfo
        if (this.usernameInput === user && this.passwordInput === pw) {
            console.log("Logged in!");
        } else {
            this.errors.push("Login failed.");
            this.displayErrors(); // 'this' is AuthController, which delegates to LoginController's displayErrors
        }
    };

    AuthController.login("user", "wrong_pass");
    // Login Errors: Invalid credentials, Login failed.
    ```

-----

## III. Scope

Scope defines where variables and functions can be accessed (the "visibility" of identifiers). It determines where the JavaScript engine looks for declared names.

### Nested Scope

Scopes can be nested within each other. An inner scope has access to variables declared in its own scope and all its outer (enclosing) scopes. This is often visualized as a series of concentric circles or "marbles in buckets."

```javascript
function outer() {
    var a = 1; // 'a' is in 'outer' scope
    function inner() {
        var b = 2; // 'b' is in 'inner' scope
        console.log(a + b); // 'inner' can access 'a' from 'outer' scope
    }
    inner();
    // console.log(b); // ReferenceError: b is not defined (b is not in 'outer' scope)
}
outer(); // 3
```

  * **`ReferenceError` vs. `undefined`**:
      * **`ReferenceError`**: Occurs when you try to access a variable that has *not been declared* in any accessible scope. This means the engine cannot find any declaration for the identifier.
        ```javascript
        // console.log(undeclaredVar); // ReferenceError: undeclaredVar is not defined
        ```
      * **`undefined`**: Occurs when you access a variable that *has been declared* but has not yet been assigned a value. The variable exists, but its value is `undefined`.
        ```javascript
        var declaredVar;
        console.log(declaredVar); // undefined
        ```

### Hoisting

Hoisting is JavaScript's behavior of conceptually moving declarations (but *not* initializations or assignments) to the top of their containing scope during the compilation phase, *before* code execution.

  * **`var` declarations**: Are hoisted to the top of their *function scope*. They are automatically initialized with `undefined`.

    ```javascript
    function doSomething() {
        console.log(x); // undefined (declaration `var x` is hoisted, but assignment happens later)
        var x = 10;
        console.log(x); // 10
    }
    doSomething();
    ```

    This is effectively interpreted as:

    ```javascript
    function doSomething() {
        var x; // declaration hoisted and initialized to undefined
        console.log(x);
        x = 10;
        console.log(x);
    }
    ```

  * **`let` and `const` declarations**: Are also "hoisted" to the top of their *block scope*, but unlike `var`, they are *not* initialized. Instead, they enter a "Temporal Dead Zone" (TDZ) from the beginning of their block until their declaration statement is executed. Attempting to access them within the TDZ results in a `ReferenceError`.

    ```javascript
    function anotherThing() {
        // console.log(y); // ReferenceError: Cannot access 'y' before initialization (y is in TDZ)
        let y = 20;
        console.log(y); // 20
    }
    anotherThing();
    ```

### Closure

Closure is a fundamental concept where a function "remembers" (or "closes over") and can access its lexical (outer) scope, *even when that function is executed outside of that lexical scope*. This allows functions to maintain persistent, private state.

```javascript
function createCounter() {
    var count = 0; // 'count' is in the lexical scope of createCounter
    return function increment() { // This inner function forms a closure over 'count'
        count++;
        console.log(count);
    };
}

var counter1 = createCounter(); // createCounter finishes, but increment function still "remembers" count
counter1(); // 1
counter1(); // 2

var counter2 = createCounter(); // A new closure is created for counter2
counter2(); // 1
counter1(); // 3 (counter1's 'count' is independent)
```

Closures are powerful for creating private variables, implementing module patterns, and handling callbacks in asynchronous operations.

### Modules

Modules are mechanisms for organizing and encapsulating code, promoting better code organization, reusability, and maintainability. They provide a way to create private scope for variables and functions, exposing only what is intended to be public. The "state" (data) of a module is typically held by its methods via closure.

  * **Classic/Revealing Module Pattern**: An older pattern using Immediately Invoked Function Expressions (IIFEs) and closures to create private scope.

    ```javascript
    var MyModule = (function() {
        var privateVar = "I'm private"; // private due to closure
        function privateMethod() {
            console.log(privateVar);
        }
        function publicMethod() { // This method is exposed
            privateMethod();
        }
        return { // Revealing the public interface
            publicMethod: publicMethod
        };
    })();

    MyModule.publicMethod(); // "I'm private"
    // console.log(MyModule.privateVar); // undefined (not accessible from outside)
    ```

  * **ES6 Modules**: The standardized module system in JavaScript, using `import` and `export` keywords. Each JavaScript file becomes its own module with its own private scope by default. Only explicitly `export`ed members are accessible from outside.

    ```javascript
    // myModule.js (file 1)
    const privateValue = 10; // Private to this module
    export function publicFunction() {
        return privateValue * 2;
    }
    export const publicConstant = "Hello";

    // main.js (file 2)
    import { publicFunction, publicConstant } from './myModule.js'; // Import specific exports

    console.log(publicFunction());   // 20
    console.log(publicConstant);     // "Hello"
    // console.log(privateValue);     // ReferenceError (private to myModule)
    ```

    ES6 Modules are the preferred way to organize JavaScript code in modern applications.

-----

This summary has aimed to cover all the essential technical content from the "Deep JS Foundations" course, including detailed explanations and relevant code examples. It is designed to be a standalone resource for learning and revision, suitable for direct integration into a GitHub repository.
