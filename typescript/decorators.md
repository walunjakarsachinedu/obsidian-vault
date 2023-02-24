### Decorators
It is just a function that javascript engine calls and pass class to it.   
It is use to add new property, methods and delete or modify existing property.     
It is called only once.     
      
creating decorators:
```typescript
function Component(constructor: Function) {
    constructor.prototype.newProperty = 'value';
}

@Component // add newProperty to Student class
class Student {}
```
    
     
parameterized decorators:       
It is decorator factory that take arguments return new decorator    

```typescript
type ComponentOptions = { selector: string }

function Component(options: ComponentOptions) {
    return function(constructor: Function) {
        constructor.prototype.selector = options.selector;
    }
}

interface Student { selector: String }

@Component({selector: "student"})
class Student {}

let student: Student = new Student();
console.log(student.selector);
```
     
**Decorator composition**: we can apply multiple decorator to class    
decorators are call in reverse order of order in which they are applied.     
```typescript
function Component(constructor: Function) { }
function Pipe(constructor: Function) { }

@Component @Pipe
class Student {}
```
      
Method Decorators:    
```typescript
function Log(target: any, methodName: string, descriptor: PropertyDescriptor) {
    const original = descriptor.value;
	// modifying behaviour of method
    descriptor.value = function (...args: any) {
        console.log("Before");
        original.call(this, ...args)
        console.log("After");
    }
}

class Person {
    @Log
    says(message) { console.log(`Person says: ${message}`); }
}

let p = new Person();
p.says("hello world");
```
       
accessor decorator: decorator for getters & setters.   
```typescript
function Capitalize(target: any, methodName: string, descriptor: PropertyDescriptor) {
    const original = descriptor.get;
    descriptor.get = function () {
        const result = original!.call(this);
        return (typeof result === 'string') ? result.toUpperCase() : result;
    }
}

class Person {
    constructor(public firstName: string, public lastName: string) {}
    @Capitalize
    get name() { return `${this.firstName} ${this.lastName}` }
}

let person = new Person("sachin", "walunjakar");
console.log(person.name);
```
      
Property Decorators:   
```typescript
function MinLength(length: number) {
    return function(target: any, propertyName: string) {
        let value: String;
        const descriptor: PropertyDescriptor = {
            get() { return value },
            set(newValue: string) { 
                if(newValue.length < length) 
                    throw Error(`${propertyName} should have at least ${length} length.`);
                value = newValue;
            }
        };
        Object.defineProperty(target, propertyName, descriptor);
    }
}


class Person {
    @MinLength(4)
    name: string;
    constructor(name: string) { this.name = name }
}

let person = new Person("a");
```
   