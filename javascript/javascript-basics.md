### Getting Started

ECMAScript (ES) is specification that javascript follows.
Based on ECMAScript specification version of javascript is determine. e.g., (ES6) is newer version of javascript.

Every browser have javascript engine to javavscript.
Node is c++ program with embedded chrome "V8" javascript engine.


### Basics

Variable: 
	declaring variable: `let name;`  or `let name = 'sachin';`
	default value for any uninitialized variable is `undefined`. 
	 declaring multiple variable: `let name, age;`
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
  