### Getting Started

ECMAScript (ES) is specification that javascript follows.
Based on ECMAScript specification version of javascript is determine. e.g., (ES6) is newer version of javascript.

Every browser have javascript engine to javavscript.
Node is c++ program with embedded chrome "V8" javascript engine. 


### Basics

Variable: 
	declaring variable: `let name;`  or `let name = 'sachin';`
	default value for any uninitialized variable is `undefined`. 
	 declaring multiple variable: `let name, age, marks=10;`
Constants:
	using constant: `const name = "value";`  (its compulsory to initialize while declaration)
	
Primitive Types:
```javascript
let name = 'sachin'; // String literal
let mark = 100; // Number literal
let isApproved = true; // Boolean literal
let firstName = undefined;
let selectedColor = null;
```
Dynamic Typing: Variable can change its type during runtime & store different type of values.

Objects: 
	defining object: `let person = {name: 'sachin', 'marks': 100};`
	 accessing element: 
		 dot notation: `person.name = 'ajay';`
		 bracket notation: `person['name'] = 'ajay';`
Arrays:
	defining array: `let color = ['red', 'green', 'blue'];`
	javascript array are 
		dynamic in length: meaning we can set value beyond current its limit of index. 
		e.g., `color[5]='orange';`	outputs: `['red','green','blue',<2 empty items>,'orange']`
		dynamic in content: meaning we can set value of different types.	 
		e.g., `color[0]=1;`
	type of array is object in javascript. (so we can use all method of objects).
Functions:
	defining function:  `function greet(name) { console.log("hello " + name); }`
	calling function: `greet('sachin');`   output:  `hello sachin`
	if we don't pass argument to function, default value for parameter is `undefined`. 
	e.g., `greet();`  output:  `hello undefined`
	Any additional argument to function are ignored.


### Operators

arithemetic operators:  `+, -, *, /, %, **, ++, --`
assignment operators:  `=, +=, -=, -=, *=, /=, **=`
comparsion operators:  `<, >, <=, =>, ==, ===, !==`
ternary operators: `(condition)? exp1 : exp2;`
logical operator:  `&&, ||, !`
bitwise operator:  `&, |`

`===` (strict equality) vs `==` (loose equality): 
	`===` compairs both **value & type**
	`==` compairs  only **value**.

local operator with non-boolean:
	`&&` :  return last non falsy value.
	`||` :   return first non falsy value. 
	 ! : return `true` false falsy value & `false` for other values.
	where falsy values are  `NaN, null, undefined, 0, false, ''`


### Control Flow 

#### conditional statements

if...else:   
```javascript
if(condition1) {} else if(condition2) {} else {}
```
Switch..case: 
```javascript
switch(value) {
	case(value1):
		break;
	case(value2):
		break;
	default:
		break;
}
```

#### Loops

for: 
- initialization: execute only once at start of loop
- loop-condition: execute at start of every iteration
- expression: execute at end of every iteration
```javascript
for(let i=0; i<5; i++) {}
// for(initialization; loop-condition; expression) {}
```
while:
```javascript
while(condition) {}  // execute only when condition is true
```
do..while:
```javascript
do {} while(condition) // execute at least once
```
for..in: iterate over all indexes in object or array
```javascript
let colors = ['red', 'green', 'blue'];
for(let i in colors) console.log(i);
// outputs: 0, 1, 2
```
for..of: iterate over all values in object or array
```javascript
let colors = ['red', 'green', 'blue'];
for(let i of colors) console.log(i);
// outputs: red green blue
```
