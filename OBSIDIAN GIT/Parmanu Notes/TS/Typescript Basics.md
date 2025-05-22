`let x = 2;` is also correct but `let x: number = 2;` means explicitly defining the datatype for variable.
1st also has defined datatype but implicitly via the value's datatype.

# Primitive datatypes:
1. number
2. string
3. bool
4. null
5. undefined (used where you haven't decided the value, but will in the future)
6. void
7. never
# Array :
![[Pasted image 20250522104011.png]]
# Tuple :
![[Pasted image 20250522104136.png]]
# Tricky-mix :
**==`const coords: [number, number[]] [] = [`**==
	==**`[1, [1,2]],`**==
	==**`[-1, [3, 4]]`**==
==**`]`**==
==**`coords [0][1]` this show that `property 1: number[]`==**
***this means that a ==tuple with number and array of number is nested== within an ==array!==***
# Literal (literally just assign what you need!) :
`let direction: "north | "south" | "east" | "west" ;`
`direction = "north" ;` 

# Enum (diy string to int or vice-versa relationship) :
## Numerical enums :
`enum Size {`
	`small,`  ==*default: small = 0* ==
	`medium`  ==1==
	`large`   ==2==
`}`
`var size: Size = 0;`  ==assigns small to  size==
`if (size === Size.small {`
`}`

## String enums :
`enum dir {`
	`up = "UP",`
	`down = "DOWN",`
	`left = "LEFT",`
	`right = "RIGHT"`
`}`
# Any (ignores type checking) :
`let x: any = 1;`
`x.length;`  ==no error==
# Unknown (forces to check the type) :
If used in if, else if . The Unknown type register it to the respective type assigned in if or else if statements, but else is incorrect as it doesn't try to assign any type. ==Any== does not bothers with type, while ==Unknown== forces type checking b4 execution !
`function process Feedback(input: unknown): void {` 
	`if (typeof input 'string') {` 
		`console.log(Processing text: $(input));` 
		`// Handle string-specific logic` 
	`} else if (typeof input 'number') {` 
		`console.log('Processing rating: $(input);` 
		`// Handle number-specific logic` 
	`} else if (input instanceof Blob) {` 
		`console.log('Processing file');` 
		`// Handle Blob-specific logic` 
	`} else {` 
		`console.log('Unsupported type of input');` 
`}` 
`// This ensures that operations are safe and based on the actual type of input` 
`process Feedback("Great service!");             // Correctly identified as string` 
`processFeedback(5);          // Correctly identified as number` 
`process Feedback(new Blob());         // Correctly identified as Blob`
# Optional Chaining and Bang :
`const arr = [[{name: "tim"}]]` 
`const el arr.pop()?.pop()?.name` ==? checks for undefined then moves forward, while ! ignores undefined==
