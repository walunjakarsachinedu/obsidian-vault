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
let name = `sachin`; // Template literal
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



#### Objects

##### constructing object:
1. factory function  e.g., `function student(name, age) { return {"name": name, "age": age} };`
2. constructor function 
	- first letter must be capital & generally pascal naming convention is followed.
	- e.g., `function Student(name, age) { this.name = name, this.age = age; }`
	- each object has constructor property which store reference function use to construct that object.

object are **dynamic** in javascript meaning we can add remove property at runtime.

**Function are object**. e.g., `const Student= new Function('name', 'age', "this.name=name; this.age=age;"); 

object is **reference type** means **variable stores address of memory location** where value is stored. so when we compare equality of object reference are compary instead of value.

**Enumerating object**: 
use `for..in` to loop through keys & `for..of` to loop through values
`Object.keys` & `Object.entries` use to get key & key-value entries in object.

`in operator` is use check for presence of key in object.

Private method & property : local, variable function inside constructor function
	because of **closure** this private member always remain in memory.

use object in javascript: `Math, String, Date`


#### Array

adding element: `push, unshift, splice`
finding element: 
- primitive type element: `indexOf`, 
- reference type element: `find`
removing element: `pop, shift, splice`
removing all element: set length to zero as  `arr.length = 0`
combining array: `concat(second_array)`
slicing array: `slice(start_index, end_index)`
spread operator: `const copyArr = [...arr];`
iterating array: 
	iterating through values: `for(let value of arr) console.log(value);`
	iterating through index: `for(let index in arr) console.log(index);`
	iterating use forEach: `arr.forEach((value, index) {});`
joining array to string: `arr.join(sperator_string)` 
string spliting array: `str.join(sperator_string)` 
sorting array: 
- array containing primitive type element: `sort`
- array containing reference type element: `sort((a,b) {});`
	value are swap if negative value is comparison function return negative value
testing element of array: `every(v => {}) & some(v => {})`
filtering element of array: `filter(v => {})`
mapping element of array: `map(v => {})`  (function passed to map should return updated value of `v` )
reducing array (summarization): `reduce((accumulator, currentValue) {});`


##### Function

function declaration: syntax e.g., `function add(a,b) {return a+b;}`
	we can call function before its declaration  & this not true with function expression
function expression: syntax e.g., 
	`const a = function add(a,b) {return a+b;}`
	`const b = function(a,b) {return a+b;}`
function argument: 
	implicit default value of parameter is `undefined`.
	setting explicit default value: `function add(a=0, b=0) {return a+b;}`
	all extra argument to function are ignored.
	rest operator: It is use to get variable number of arguments. syntax: `function(...args) {}`
getter/setter:
```javascript
const person = {
    firstName: "sachin",
    lastName: "walunjakar",
    get fullName() {return this.firstName + " " + this.lastName;},
    set fullName(value) {
        let name = value.split(" ");
        this.firstName = name[0];
        this.lastName = name[1];
    }
};
```
global/local scope:
	variable define with `let & const` has scope limited to block in which they are defined & if there is no block then variable has global scope.
	local variable take precedence over global variable.
	scope of variable define with `var` scope is not limit to block in which it is define but limited function in which it is defined. 
	 function scope: `var`
	 block scoped variable: `let, const`
	`this` keyword: It reference object that is executing current function
		for methods this references obj
		for normal function this references global object like window, global.
	   arrow function inherit `this` from calling function.
	     







	