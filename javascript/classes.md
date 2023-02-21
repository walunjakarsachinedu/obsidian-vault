### Class
classes are syntactic sugar over prototypical inheritance.   
hoisting is not possible for classes in javascript meaning creating instance before class declaration is not possible.   
    
creating class:  
using declaration: `class Student {}``  
using expression: `const Student = class{}`  
  
`[]` operator: we can set property name based on expression. like in e.g, `[expression](){}`   
   
define static member: `class Student { static count; }`  
  
implement private member:  
- using _ underscore: this method not restrict member from accessing.  
- using `Symbol`: set property name to symbol    
	- e.g., `_age = Symbol(); class Student{ [_age]() {} }`  
- using `WeakMap`:    
	 - e.g,  `_age = WeakMap(); class Student{ _age.set(this, 8); }`  
	 - access using `_age.get(this)` 
  
getter & setter: use `get & set` keyword in front of method create getters & setters.   
   
Inheritance:  
- use `extend` keyword to inherit class.
- use `super` keyword to call parent constructor.
  
>javascript engine walk up tree from child all the way to parent to access property. use version of property that it find first.