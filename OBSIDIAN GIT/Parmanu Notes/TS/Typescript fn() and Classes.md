`function add(x: number, y: number): number {`
	`if ( x ==  0 ) {`
		`return "invalid"`
	`}`
	`return x + y`
`}`
`const result = add(1, 2);`  ==output should be mandatory a number type==
# Good logic fn() :
`function applyFunc(` 
	`funcs: ((a: number, b: number) => number) [],` 
	`values: [number, number] []` 
`): number[] {` 
	`const results = [] as number[];` 
	`for (let i=0; i < funcs.length; i++) {` 
		`const args = values[i];` 
		`const result = funcs [i] (args[0], args[1]);` 
		`results.push(result);` 
	`}`
	`return results;` 
`}` 
`applyFunc(` 
	`[mul, div],` 
	`[` 
		`[1, 2],` 
		`[4, 5],` 
	`]` 
`);`
# Adv Function types :
`function sum( ...numbers: number[]) {}` ==takes as many numbers as needed==
# Interfaces : 

`interface Person {` 
	`name: string;` 
	`age: number;` 
	`height?: number;` 
`}` 
`const person: Person {` 
	`name: "tim",` 
	`age: 23` 
`}`

# Classes and Access modifiers :
*classes are blueprint for creating new objects!*
`class Person {` 
	`private name: string;` 
	`constructor(name: string) {` 
		`this.name = name;` 
`}` 
	`greet() {` 
		`console.log('Hello, my name is ${this.name));` 
	`}` 
`}` 
`const p1 = new Person("Tim");` *won't work as name is ==private==*

# Objects :
An instance of a class or a literal value that conforms to a type or interface, holding actual data.

# Key difference bw CLASS, OBJECT & INTERFACE :

| Aspect         | ==Interface==                             | ==Class==                                    | ==Object==                           |
| -------------- | ----------------------------------------- | -------------------------------------------- | ------------------------------------ |
| Purpose        | Defines type/shape without implementation | Blueprint with structure and behavior        | Instance or literal with actual data |
| Implementation | No (only signatures)                      | Yes (methods, constructors)                  | Yes (data and methods at runtime)    |
| Instantiation  | Cannot be instantiated                    | Can be instantiated with ==new==             | Is the instantiated result           |
| Inheritance    | No, but can extend other Interfaces       | Yes, supports ==extends== and ==implements== | N/A (objects don't inherit directly) |
| Use Case       | Type-checking, contracts                  | Encapsulation, inheritance, reusable code    | Runtime data manipulation            |
# Summary :
- Use ==interfaces== to define types or contracts for objects or classes without implementation.
- Use ==classes== to create blueprints with structure and behavior, which can be instantiated.
- ==Objects== are the actual instances (from classes or literals) that hold data and behavior at runtime.
# Abstract Classes :
`abstract class Vehicle {`
  `// Normal method with code that all vehicles can use`
  `startEngine() {`
    `return "Engine started!";`
  `}`

  `// Abstract method (just a placeholder, no code)`
  `abstract move(): string; // No code here, child classes must define it`
`}`
`class Car extends Vehicle {`
  `// Must provide code for the abstract method 'move'`
  `move() {`
    `return "Car drives on the road!";`
  `}`
`}`

`class Boat extends Vehicle {`
  `// Must provide code for the abstract method 'move'`
  `move() {`
    `return "Boat sails on water!";`
  `}`
`}`
`const myCar = new Car();`
`console.log(myCar.startEngine()); // Output: Engine started!`
`console.log(myCar.move());        // Output: Car drives on the road!`

`const myBoat = new Boat();`
`console.log(myBoat.startEngine()); // Output: Engine started!`
`console.log(myBoat.move());        // Output: Boat sails on water!`
# Static & its attributes with interface, class, object example :
`// Interface defining the structure of a Book`
`interface Book {`
  `title: string;`
  `author: string;`
  `pages: number;`
  `getSummary(): string;`
`}`


`// Class implementing the Book interface`
`class LibraryBook implements Book {`
  `// Static attribute to track total number of books created`
  `static totalBooks: number = 0;`

  `// Instance properties`
  `title: string;`
  `author: string;`
  `pages: number;`

  `// Constructor`
  `constructor(title: string, author: string, pages: number) {`
    `this.title = title;`
    `this.author = author;`
    `this.pages = pages;`
    `// Increment static counter when a new book is created`
    `LibraryBook.totalBooks++;`
  `}`

  `// Instance method required by the Book interface`
  `getSummary(): string {`
    `return ${this.title} by ${this.author}, ${this.pages} pages;`
  `}`

  `// Static method to get the total number of books`
  `static getTotalBooks(): string {`
    `return Total books in library: ${LibraryBook.totalBooks};`
  `}`
`}`

`// Creating objects (instances) of the class`
`const book1 = new LibraryBook("The Hobbit", "J.R.R. Tolkien", 310);`
`const book2 = new LibraryBook("1984", "George Orwell", 328);`

`// Using instance methods and properties`
`console.log(book1.getSummary()); // Output: The Hobbit by J.R.R. Tolkien, 310 pages`
`console.log(book2.getSummary()); // Output: 1984 by George Orwell, 328 pages`

`// Using static attribute and method`
`console.log(LibraryBook.getTotalBooks()); // Output: Total books in library: 2`
# Generics :
`function getValue<K, V>(key: K, valuel: V, value2: V): V {` 
	`if (key) {` 
		`return valuel;` 
	`}` 
	`return value2` 
`}` 
`const n1: number = 1;` 
`Const n2: number = 2` 
`getValue<string, number>("hello", n1, n2)`

# Types Aliases :
`type Coordinate = [number, number]` 
	`function compareCoords(` 
	`pl: Coordinate,` 
	`p2: Coordinate` 
`): Coordinate {` 
	`return [p1[0], p2[1]]` 
`}` 
`const coords: [number, number] [] = [];`


