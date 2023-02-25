### Class
  
- creating class:
```typescript
class Person {
	id: number;
	firstName: string;
	secondName: string;
	constructor(id: number, firstName: string, lastName: string) {
		this.id = id;
		this.firstName = firstName;
		this.secondName = lastName;
	}
}
// or 
class Person {
	constructor(public readonly id: number, public firstName: string, public lastName: string) {}
}
```

- createing instance: `let person: Person = new Person("sachin", "walunjakar");`
- checking type of user defined class: `if(person instanceOf Person) {}`
	- `typeof` can be use for pre-mitive types.
- `readonly` keyword: use this keyword at time of property definition to make it readonly. It is like `final` keyword in dart but only restricted to be use in the class property.
- optional propertie: add "`?`" in fornt of property to make it optional
- access control keywords: `public, private, protected`
	- best practice: prefix underscore to private property
 - getter & setter: 
```typescript
class Account {
    private _balance = 0;
	get balance(): number { return this._balance; }
    set balance(amount: number) { if (amount > 0) this._balance = amount; }
}
```
- **index signature**:  
```typescript
class map { [index: string]: string; } 
```
- static members:  use `static` keyword in property or method to make them static member.
	- we can use `private` keyword to make them only access inside class
- inheritance: 
```typescript
class Person { constructor(public name: string) {} }
class Student extends Person {
	constructor(public studentId: number, name: string) { super(name); }
}
```
- `override` keyword: helps to make sure that method is overrided properly with correct signature. 
- abstract classes & interface:
```typescript
abstract class Shape { 
	constructor(public color: string) {}
	abstract render(): void; 
}
class Circle extends Shape {
  constructor(public radius: number, color: string) { super(color); }
  render(): void { throw new Error("Method not implemented."); } 
}

// pure abstract classes: it do not provide any logic or any algorithm, it just provide structure to object
interface Calendar {  
	name: string;
	addEvent(): void;
	removeEvent(): void;
}

class GoogleCalendar implements Calendar { // class implement interface
    constructor(public name: string) {}
    addEvent(): void { throw new Error("Method not implemented."); }
    removeEvent(): void { throw new Error("Method not implemented."); }
}
```


>To get the property type, passing property of class to class index then class will return type of property. e.g, `let name: Product['name']; // string variable`