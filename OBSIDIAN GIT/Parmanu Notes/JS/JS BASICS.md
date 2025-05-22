**JavaScript Revision Notes**

---

### 1. **Basics of JavaScript**

- **JavaScript (JS)** is a high-level, interpreted, dynamic scripting language used primarily for web development.
    
- It is **single-threaded** and uses the **event loop** to handle asynchronous operations.
    
- Runs in browser and server environments (Node.js).
    

---

### 2. **Data Types**

#### **Primitive Types** (Immutable)

- **Number**: Includes integers and floating-point numbers.
    
- **String**: Textual data, enclosed in `""`, `''`, or backticks for template literals.
    
- **Boolean**: `true` or `false`.
    
- **Undefined**: A variable declared but not assigned a value.
    
- **Null**: Intentional absence of value.
    
- **Symbol**: Unique and immutable value (ES6).
    
- **BigInt**: For arbitrarily large integers (ES11).
    

#### **Reference Types** (Mutable)

- **Object**: Collection of key-value pairs.
    
- **Array**: List-like objects.
    
- **Function**: First-class objects.
    
- **Date, RegExp, Map, Set, WeakMap, WeakSet**: Built-in reference types.
    

---

### 3. **Variables**

- `var`: Function-scoped, hoisted.
    
- `let`: Block-scoped, not hoisted.
    
- `const`: Block-scoped, cannot be reassigned.
    

---

### 4. **Operators**

- Arithmetic: `+`, `-`, `*`, `/`, `%`, `**`
    
- Comparison: `==`, `===`, `!=`, `!==`, `>`, `<`, `>=`, `<=`
    
- Logical: `&&`, `||`, `!`
    
- Assignment: `=`, `+=`, `-=`, `*=`, `/=`, etc.
    
- Type: `typeof`, `instanceof`
    

---

### 5. **Control Structures**

- Conditional: `if`, `else if`, `else`, `switch`
    
- Loops: `for`, `while`, `do...while`, `for...in`, `for...of`
    
- Jump: `break`, `continue`, `return`
    

---

### 6. **Functions**

- Function Declaration: `function name() {}`
    
- Function Expression: `const fn = function() {}`
    
- Arrow Functions: `const fn = () => {}`
    
- Parameters vs Arguments, Rest `...args`, Default Params
    
- Callback functions
    

---

### 7. **Objects**

- Created via literals or constructors.
    
- Properties can be added, modified, or deleted.
    
- Nested objects, `this` keyword.
    
- Object methods: `Object.keys()`, `Object.values()`, `Object.entries()`, `Object.assign()`, `Object.freeze()`
    

---

### 8. **Arrays**

- Methods: `push()`, `pop()`, `shift()`, `unshift()`, `splice()`, `slice()`, `forEach()`, `map()`, `filter()`, `reduce()`, `find()`, `includes()`
    
- Destructuring and Spread syntax `[...arr]`
    

---

### 9. **ES6+ Features**

- `let`, `const`
    
- Arrow functions `()=>{}`
    
- Template literals `` `Hello ${name}` ``
    
- Destructuring assignment
    
- Spread and Rest `...`
    
- Default parameters
    
- Modules: `import`, `export`
    
- Classes: `class`, `constructor`, `extends`, `super`
    
- Promises, `async/await`
    
- Optional chaining `?.`, Nullish coalescing `??`
    

---

### 10. **Asynchronous JavaScript**

- **Callbacks**: Functions passed as arguments.
    
- **Promises**: `.then()`, `.catch()`, `.finally()`
    
- **Async/Await**: Syntactic sugar for promises.
    
- **Event Loop**: Handles async via call stack + task queue.
    

---

### 11. **DOM Manipulation**

- `document.getElementById()`, `querySelector()`
    
- `innerHTML`, `textContent`, `value`
    
- `addEventListener()`, `removeEventListener()`
    
- Creating elements: `createElement`, `appendChild`
    

---

### 12. **Events**

- Event types: `click`, `submit`, `keydown`, etc.
    
- Event propagation: Bubbling vs Capturing
    
- `event.target`, `event.preventDefault()`
    

---

### 13. **Error Handling**

- `try...catch`, `finally`
    
- `throw new Error()`
    

---

### 14. **JavaScript Facts**

- Loosely typed, dynamic typing.
    
- Prototypes: JS uses prototype-based inheritance.
    
- Everything is an object (except primitives).
    
- Hoisting: Declarations are moved to the top of scope.
    
- Closures: Functions retain access to their lexical scope.
    
- IIFE: Immediately Invoked Function Expression.
    

---

### 15. **Advanced Topics**

- Closures, Currying, Memoization
    
- Debouncing, Throttling
    
- Event Loop, Microtasks vs Macrotasks
    
- `this`, `call`, `apply`, `bind`
    
- Module Systems: CommonJS, ES Modules
    
- Garbage Collection
    

---

### 16. **Browser APIs**

- `localStorage`, `sessionStorage`
    
- `fetch`, `XMLHttpRequest`
    
- `setTimeout`, `setInterval`
    
- `navigator`, `location`, `history`
    

---

### 17. **Node.js Basics**

- JavaScript runtime for backend.
    
- Modules: `require`, `module.exports`
    
- Built-in modules: `fs`, `path`, `http`
    
- NPM (Node Package Manager)
    

---

### 18. **Tools & Frameworks**

- Transpilers: Babel
    
- Bundlers: Webpack, Vite
    
- Frameworks: React, Vue, Angular
    
- Linters: ESLint
    

---

### 19. **Best Practices**

- Use `const` and `let` over `var`
    
- Write modular and reusable code
    
- Avoid global variables
    
- Use strict equality `===`
    
- Comment and document code
    

---

### 20. **Common Patterns**

- Module Pattern
    
- Singleton Pattern
    
- Observer Pattern
    
- Factory Pattern
    
- Revealing Module Pattern