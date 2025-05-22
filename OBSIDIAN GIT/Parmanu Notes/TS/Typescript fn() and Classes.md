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

