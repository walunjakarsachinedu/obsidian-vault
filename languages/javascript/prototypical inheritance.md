### prototype 
Prototype is parent object in inheritance. A prototype is just a regular object.  
Access using property: `__prototype__` or using function: `Object.getProtoTypeOf(obj)`
Example:-  
	every object inherit => `Object.  
	every array inherit => `Array` => `Object.  
Object constructed by given constructor will have the same prototype.  
Constructor has `prototype` property which references object use as parent of object constructed from this constructor.
Prototype/Instance members:   
	single instance of prototype member is shared by all objects whereas separate instance member is created for each object.  
	 creating prototype member: `ConstructorFunction.prototype.property = value;.  
	 creating instance member: `ConstructorFunction() { this.property = value; }.  

getting description for property: `Object.getOwnPropertyDescriptor(obj, 'property_name').  
	configuration: we can delete property  
	enumerable: whether property is included during enumeration  
	writable: whether property is overwritable.   
	we can update this description using: `Object.defineProperty(obj, 'property', { writable: true, configuration: false, enumerable: true});.  


### prototypical inheritance:  
In prototypical inheritance, only prototype member are inherited not instance member.  
get object to be use as prototype: `Object.create(value).`    
inheritance: setting object prototype to point to prototype of parent prototype   
e.g., `Circle.prototype = Object.create(Square.prototype);` this assignment should be done before use prototype to create prototype member.  
best practice: Constructor should resetted after prototype is resetted.  
	e.g., `Circle.prototype.constructor = Circle;.  
calling super class: `ParentClass.call(this, arg1, arg2);`   
Function to inherit class:   
```javascript
function extend(Child, Parent) {
   Child.prototype = Object.create(Parent.prototype);
   Child.prototype.constructor = Child;
}
```
  
> Avoid creating inheritance hierarchies. Favor Composition over inheritance

mixin: Instead of defining inheritance to inherit features, we define different features as separate object & use this objects to compose new object  
function to add mixins in objects: `function mixin(target, ...sources) { Object.assign(target, ...sources); }.  

